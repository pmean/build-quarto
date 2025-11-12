---
title: Histogram options in SAS
source: "New"
author: Steve Simon
date: 2024-07-19
categories:
- "*Blog post"
- Year 2024
- SAS software
output: html_document
page_update: no
---

Several of my students wanted information on how to modify graphs in SAS. I'm glad they asked, because the worst thing you can do with any software is to take the graph that appears based on the default options. The default options in SAS are actually pretty good, but you still need to revise your graphs so you can paint a fair picture of what is going on with your data. Revise your graphs about as often as you rewrite your text.

I wrote a program to show a few of the more important options that you have for revising histograms in SAS.  I have separate pages that show [how to revise scatterplots in SAS][sim5] and [how to revise linegraphs in SAS][sim6].

<!---more--->

Here is the documentation header for the program I wrote along with some preliminaries to show where to find the data and where to store the output.

```{}
* histogram-options.sas
  author: Steve Simon
  date: created 2024-07-19
  purpose: show some options for a histogram
  license: public domain;

libname storage "/home/mail129/data";

ods word file=
    "/home/mail129/results/histogram-options.docx";
```

I will use a dataset that has information about body fat and measures of a person's circumference at various places on their body. Here are the first few rows of data. Refer to the [data dictionary][sim3] for more details.

[sim3]: https://github.com/pmean/datasets/blob/master/fat.yaml

```{}
proc print
    data=storage.fat(obs=5);
  title1 "First five lines of data";
run;
```

![](http://www.pmean.com/new-images/24/sas-histogram-options-01.png)

This is the code to produce a histogram with the default options. Following this code and graph, you will see various ways to change the display of the histogram. The code should be largely self-explanatory.

```{}
proc sgplot
    data=storage.fat;
  histogram ht;
  title1 "Histogram with default options ";
run;
```

![](http://www.pmean.com/new-images/24/sas-histogram-options-02.png)

```{}
proc sgplot
    data=storage.fat;
  histogram ht / scale=count;
  title1 "Histogram with counts";
run;
```

![](http://www.pmean.com/new-images/24/sas-histogram-options-03.png)

```{}
proc sgplot
    data=storage.fat;
  histogram ht / binstart=25 binwidth=10;
  title1 "Histogram with wide bins";
run;
```

![](http://www.pmean.com/new-images/24/sas-histogram-options-04.png)

```{}
proc sgplot
    data=storage.fat;
  histogram ht / binstart=25 binwidth=2;
  title1 "Histogram with narrow bins";
run;
```

![](http://www.pmean.com/new-images/24/sas-histogram-options-05.png)

```{}
proc sgplot
    data=storage.fat;
  histogram ht / nofill;
  title1 "Histogram without fill color";
run;
```

![](http://www.pmean.com/new-images/24/sas-histogram-options-06.png)

```{}
proc sgplot
    data=storage.fat;
  histogram ht / fillattrs=(color=CX00FF00);
  title1 "Histogram with green fill";
run;
```

![](http://www.pmean.com/new-images/24/sas-histogram-options-07.png)

You're done once you close the output file.

```{}
ods word close;
```

If you want to explore further, check out these resources.

-   Sanjay Matange. Getting Started with SGPLOT - Part 5 - Histograms. SAS blog, 2017-04-30. Available in [html format][sas1].
-   SAS Institute. SGPLOT Procedure. Histogram Statement. Available in [html format][sas2].
-   SAS Institute. Color-Naming Schemes. Available in [html format][sas3].


[sas1]: https://blogs.sas.com/content/graphicallyspeaking/2017/04/30/getting-started-with-sgplot-histograms/
[sas2]: https://documentation.sas.com/doc/en/pgmsascdc/9.4_3.5/grstatproc/n17xrpcduau1f8n1c1nhe477pv18.htm
[sas3]: https://documentation.sas.com/doc/en/pgmsascdc/9.4_3.5/grstatproc/p0edl20cvxxmm9n1i9ht3n21eict.htm

[sim5]: http://new.pmean.com/sas-scatterplot-options/
[sim6]: http://new.pmean.com/sas-linegraph-options/

An [earlier version][sim2] of this page was published on [new.pmean.com][sim1].

[sim1]: http://new.pmean.com
[sim2]: http://new.pmean.com/sas-histogram-options/

