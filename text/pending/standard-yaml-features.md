---
title: Some options for the yaml header in Quarto
source: "New"
author: Steve Simon
date: 2026-02-02
categories: Blog post
tags:
- Quarto documents
- R programming
output: html_document
page_update: no
---

I have been using Quarto for a couple of years now and I really like it. I wanted to document a few options that I like for the yaml header in a Quarto.

<!---more--->

```{}
format: 
  html:
    embed-resources: true
editor_options:
  chunk_output_type: console
execute:
  echo: false
  error: true
```

## The basic structure for yaml files.

First let's establish some basic ground rules for yaml files. Even minor deviations from this structure can cause problems.

## Key-value pairs

The simplest lines of yaml header are 

`key: value`

and this can be extended to multiple values with

```{}
key:
- value1
- value2
- value3
```

or

```{}
key:
  value1
  value2
  value3
```

## Key level hierarchies

You can have two levels for your keys, such as

```{}
key1:
  key2: value
```

or three levels

```{}
key1:
  key2: 
    Key3: value
```

and so forth. Indentation is VERY important here, as are the colons.

## html format options

You can ask for an html document with a simple `format: html` but there is a way to specify changes or enhancements. To do this, you split the statement, putting `format:` on one line and placing an indented `html` followed by a semicolon on the next line. Your options then follow on a doubly indented line.

The html format option I use the most is `embed-resources: true`. By default, Quarto places some support files for your html output in a subfolder with the same name as your html page (without the .html extension, of course). I'm not sure why this is the default option, but it makes your life more complicated when you want to share your output with someone else. You have to send the html file AND the folder.

If you want a single file without an accompanying folder, specify `embed-resources: true`.  Note the use of lower case here. This is to make quarto more consistent with the programming standards of Python.

## Controlling where code chunk output goes

I normally create an entire html document using the `Render` button inside of RStudio, but sometimes I will run individual chunks, especially when I am testing new code.
 
You can control where the output goes when you run individual program chunks in Quarto. By default, your output is placed directly beneath the code chunk. If you want to output to appear in the console window instead, add the lines

```{}
editor_options:
  chunk_output_type: console
```

to your yaml header.

## Applying chunk options to the entire file

The `execute` key allows you to specify options that apply to every chunk. If you want to suppress the listing of code, specify

```{}
execute:
  echo: false
```

in your yaml header. Other common options that you can control are

-   `error: true` which produces output, even if you have an error in your code
-   `message: false` to suppress informational messages
-   `warning: false` to suppress warning messages

You can also control the size of all the graphs in your code using the `fig-width` and `fig.height` keys. Note that `fig.width` and `fig.height` could also be used. If you mix Python in with your R code, you might want to stick with the dash as a delimiter rather than the dot. Dots have special meaning in Python.

## Where to find more information abot yaml and Quarto

There is a nice (and very short) [YouTube video][ref-keys] by David Keys that talks about placing code chunk output in the console.

Look at [Chapter 15][ref-tdg-15] of the online book [Quarto: The Practical Guide][ref-tdg] written by Mine Cetinkaya-Rundel for a more complete explanation of various options you can include in your yaml header.

The definitive guide for anything about Quarto is the [Quarto site][ref-quarto] run by Posit. Go to the [html basics][ref-html] page for more information about what to put in the yaml header.

The [yaml website][ref-yaml] provides detailed documentation about the yaml specifications. This goes into far more detail than you need to write a yaml header for Quarto, but it helps you better understand the importance of various formating requirements.

[ref-html]: https://quarto.org/docs/output-formats/html-basics.html
[ref-keys]: https://youtu.be/MsR244A4iNk
[ref-quarto]: https://quarto.org/
[ref-tdg-yaml]: https://quarto-tdg.org/yaml
[ref-tdg]: https://quarto-tdg.org/
[ref-yaml]: https://yaml.org/


https://quarto.org/docs/output-formats/html-basics.html