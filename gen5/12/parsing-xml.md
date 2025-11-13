---
title: "Parsing information in an XML file"
author: Steve Simon
date: 2012-07-20
source: http://www.pmean.com/12/xml.html
categories:
- "*Blog post"
- Year 2012
- Being updated
output: html_document
page_update: no
---

Note: This page was written before I knew about the stringr package in R. It simplifies the code and makes it easier to understand. If I find the time, I would like to update this page using stringr functions.

I use a GPS app on my iPhone to track my runs, and I wanted to be able to take the data from that app and manipulate it directly. This app produces files in GPX format, which is a version of XML (extended markup languate). The XML format is pretty easy to view, but it doesn't import easily into a program like R. There are programs out there that can import XML data into R, but I found it easier just to manipulate the XML file using the read.table and grep commands.

There XML format offers a lot of flexibility, and this is a two-edged sword. You look for information between tags, and these tags can be found in a single line of text or can span multiple lines of text. So any effort to read XML files should allow for this flexibility. I'm going to cheat, and assume that the information I am looking for does not span multiple lines. It works for the GPX files that I use, but may not work for GPX files created by other systems.

The first thing you need to do is to get the data into R. The read.table command works but there is a trick. You want to have a vector whose first element is a string representing the first line of the GPX file, whose second element is a string representing the second line of the GPX file, etc. But read.table has a default option that causes problems.

If sep = "" (the default for read.table) the separator is ‘white space’, that is one or more spaces, tabs, newlines or carriage returns.

The way to avoid this is to choose a separator that does not appear in the file at all. I chose the tilde character ("~") and crossed my fingers hoping that a stray tilde would not cause problems with reading the file. I also had to tell R that the file had no header. Also, the read.table command has an annoying problem in that it tends to convert some character fields into factors. I usually avoid this implicit conversion and make this conversion explicitly (or, more often than not, don't convert to factors). You can add the argument, as.is=TRUE, to avoid implicit conversions. It's probably not needed here, but I include it out of habit. So the official command for reading in the GPX file is

```{}
gpx <- read.table("Track 115.gpx",header=FALSE,as.is=TRUE,sep="~")
```

The result, gpx, is a data frame with one column, V1. Here are the first twenty elements of gpx$V1

```{}
[1] "<?xml version=1.0 encoding=UTF-8?>"
[2] "<gpx xmlns=http://www.topografix.com/GPX/1/1 version=1.1 xmlns:xsi=http://www.w3.org/2001/XMLSchema-instance xsi:schemaLocation=http://www.topografix.com/GPX/1/1 http://www.topografix.com/GPX/1/1/gpx.xsd creator=MotionXGPSFull 18.0 Build 4229R>"
[3] "<trk>"
[4] "<name><![CDATA[Track 110]]></name>"
[5] "<desc><![CDATA[Jul 11, 2012 4:27 pm]]></desc>"
[6] "<trkseg>"
[7] "<trkpt lat=38.8582672 lon=-94.6330210>"
[8] "<ele>292.685</ele>"
[9] "<time>2012-07-11T21:27:05Z</time>"
[10] "</trkpt>"
[11] "<trkpt lat=38.8582672 lon=-94.6330210>"
[12] "<ele>292.635</ele>"
[13] "<time>2012-07-11T21:27:06Z</time>"
[14] "</trkpt>"
[15] "<trkpt lat=38.8582734 lon=-94.6328050>"
[16] "<ele>292.635</ele>"
[17] "<time>2012-07-11T21:27:18Z</time>"
[18] "</trkpt>"
[19] "<trkpt lat=38.8583545 lon=-94.6327209>"
[20] "<ele>292.650</ele>"
```

This file looks fairly easy to parse. You need the lat and lon values inside the <trkpt> tag, the elevation values between the <ele> and </ele> tags and the time values between the <time> and </time> tags. You can ignore the <name> and <desc> tags near the beginning of the file, and there are some other tags near the end of the file that you can ignore as well.

To disentangle this gpx file, you need to create string vectors with only the information relevant to latitude and longitude, only the elevation, and only the time. R has several base functions that replicate the UNIX utilty, grep. These grep-like functions allow you to find, and in some cases replace, information in a vector of strings. You can do some very powerful find and replace activities, but for the really sophisticated activities, you need a solid understanding of regular expressions.

Yiou can manipulate the gpx file, though, without too much effort. The grep function will tell you the elements of the vector that contain your search string

```{}
> grep("<trkpt",gpx$V1)
[1] 7 11 15 19 23 27 31 35 39 43 47 51 55 59 63
[16] 67 71 75 79 83 87 91 95 99 103 107 111 115 119 123
[31] 127 131 135 139 143 147 151 155 159 163 167 171 175 179 183
```

or alternately, the grepl function will create a logical vector that is true for those elements that have your search string and false for those that do not.

```{}
> grepl("<trkpt",gpx$V1)
[1] FALSE FALSE FALSE FALSE FALSE FALSE TRUE FALSE FALSE FALSE TRUE FALSE
[13] FALSE FALSE TRUE FALSE FALSE FALSE TRUE FALSE FALSE FALSE TRUE FALSE
[25] FALSE FALSE TRUE FALSE FALSE FALSE TRUE FALSE FALSE FALSE TRUE FALSE
```

You can even get a subvector using grep with the argument, value=TRUE.

```{}
> grep("<trkpt",gpx$V1,value=TRUE)
[1] "<trkpt lat=38.8581430 lon=-94.6329712>"
[2] "<trkpt lat=38.8582454 lon=-94.6328131>"
[3] "<trkpt lat=38.8582783 lon=-94.6327897>"
```

To pull out the numeric values (e.g., the latitude measurement), you need to use the substr function. If you count carefully, the = sign just to the left of the latitude value is in column 11 and the blank just to the right of the latitude value is in column 22. so you should extract columns 12 through 21.

```{}
> substr(grep("<trkpt",gpx$V1,value=TRUE),12,21)
[1] "38.8581430" "38.8582454" "38.8582783" "38.8583503" "38.8584147"
[6] "38.8584147" "38.8584464" "38.8585000" "38.8585650" "38.8586030"
[11] "38.8586020" "38.8586409" "38.8586689" "38.8586456" "38.8586369"
```

This assumes too much though. What if latitude values are in the single digits (near the equator, for example)? That's unlikely to happen with my runs, but what if the system that produces the gpx file carries 6 or 8 decimal places instead of 7? So it would be safer to determine the location of the equal sign to the left of the latitude value and the blank to the right of the latitude value. You need a different variant of the grep function in R, called regexpr.

regexpr returns an integer vector of the same length as text giving the starting position of the first match or -1 if there is none, with attribute "match.length", an integer vector giving the length of the matched text (or -1 for no match).

This

```{}
>regexpr(" lon=",gpx$V1)
[1] -1 -1 -1 -1 -1 -1 22 -1 -1 -1 22 -1 -1 -1 22 -1 -1 -1 22 -1 -1 -1 22 -1
[25] -1 -1 22 -1 -1 -1 22 -1 -1 -1 22 -1 -1 -1 22 -1 -1 -1 22 -1 -1 -1 22 -1
[49] -1 -1 22 -1 -1 -1 22 -1 -1 -1 22 -1 -1 -1 22 -1 -1 -1 22 -1 -1 -1 22 -1
...
[1633] -1 -1 -1 -1 -1 -1 -1 -1 -1 -1
attr(,"match.length")
[1] -1 -1 -1 -1 -1 -1 5 -1 -1 -1 5 -1 -1 -1 5 -1 -1 -1 5 -1 -1 -1 5 -1
[25] -1 -1 5 -1 -1 -1 5 -1 -1 -1 5 -1 -1 -1 5 -1 -1 -1 5 -1 -1 -1 5 -1
[49] -1 -1 5 -1 -1 -1 5 -1 -1 -1 5 -1 -1 -1 5 -1 -1 -1 5 -1 -1 -1 5 -1
...
[1633] -1 -1 -1 -1 -1 -1 -1 -1 -1 -1
attr(,"useBytes")
[1] TRUE
```

This shows that, at least for this data set, thee string " lon=", if it is found, always starts in column 22, and always has length of 5. Certain regular expressions have variable length, so this match.length attribute can be important at times. The useBytes attribute is helpful when you are working with certain languages, such as Chinese, where the individual "letters" require two bytes rather than one.

Earlier versions are [here][sim1] and [here][sim2].
 
[sim1]: http://www.pmean.com/12/xml.html
[sim2]: http://new.pmean.com/parsing-xml/
