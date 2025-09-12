---
title: "Curve fitting - xkcd"
source: "New"
author: Steve Simon
date: "2025-04-13"
categories: Recommendation
tags:
- Linear regression
output: html_document
page_update: no
---

## xkcd comic

-   Title "CURVE-FITTING METHODS AND THE MESSAGE THEY SEND"
-   Drawn by Scott Munro
-   Open-source license
-   [Link to comic][ref-xkcd] at xkcd.com
-   [More details][ref-explain] at explain-xkcd.com

[ref-xkcd]: https://xkcd.com/2048/
[ref-explain]: https://www.explainxkcd.com/wiki/index.php/2048:_Curve-Fitting

::: notes

This is an introduction that I wrote for a webinar. Let me share it here. I started with a cartoon from the xkcd site of Scott Munro. Scott Munro produces comics that poke fun at various scientific and mathematical concepts. There are a handful that directly address statistics, including this one. The actual panels in the comic are small, so I split them up onto separate slides.

:::

## xkcd comic, caption

![](http://pmean.com/new-images/25/xkcd-00.png "Caption of xkcd comic")

::: notes

I am taking a bit of liberty with the original cartoon by showing individual panels separately. I hope that Scott Munro doesn't mind. 

Here is the overall caption.

:::

## xkcd comic, panel 01

![](http://pmean.com/new-images/25/xkcd-01.png "Panel 01 of xkcd comic")

::: notes

The first panel shows a scatter of data points with a linear regression fit. The caption reads, "Hey, I did a regression."

:::

## xkcd comic, panel 02

![](http://pmean.com/new-images/25/xkcd-02.png "Panel 02 of xkcd comic")

::: notes

This shows a scatter of data points with a quadratic regression fit. The caption reads, "I wanted a curved line, so I made one with Math."

:::

## xkcd comic, panel 03

![](http://pmean.com/new-images/25/xkcd-03.png "Panel 03 of xkcd comic")

::: notes

This shows a scatter of data points with a logarithmic regression fit. The caption reads, "Look, it's tapering off!"

:::

## xkcd comic, panel 04

![](http://pmean.com/new-images/25/xkcd-04.png "Panel 04 of xkcd comic")

::: notes

This shows a scatter of data points with an exponential regression fit. The caption reads, "Look, it's growing uncontrollably."

:::

## xkcd comic, panel 05

![](http://pmean.com/new-images/25/xkcd-05.png "Panel 05 of xkcd comic")

::: notes

This shows a scatter of data points with a loess smoothing curve. The caption reads, "I'm sophisticated, not like those bumbling polynomial people."

:::

## xkcd comic, panel 06

![](http://pmean.com/new-images/25/xkcd-06.png "Panel 06 of xkcd comic")

::: notes

This shows a scatter of data points with a flat linear regression fit (slope=0). The caption reads, "I'm making a scatter plot but I don't want to."

:::

## xkcd comic, panel 07

![](http://pmean.com/new-images/25/xkcd-07.png "Panel 07 of xkcd comic")

::: notes

This shows a scatter of data points with a logistic curve regression fit. The caption reads, "I need to connect these two lines, but my first idea didn't have enough Math."

:::

## xkcd comic, panel 08

![](http://pmean.com/new-images/25/xkcd-08.png "Panel 08 of xkcd comic")

::: notes

This shows a scatter of data points with no particular regression line, but a very wide (nd probably appropriate) confidence band. This captures the idea that there is uncertainty not only in the deviation of the points from the regression curve, but true uncertainty about the shape of that regression curve. The caption reads, "Listen, science is hard. But I'm a serious person doing my best."

There is an active field of research under the topic uncertainty quantification that tries to take into account all the sources of uncertainty including uncertainty about which model is the correct model.

:::

## xkcd comic, panel 09

![](http://pmean.com/new-images/25/xkcd-09.png "Panel 09 of xkcd comic")

::: notes

This shows a scatter of data points with a piecewise linear regression fit. The caption reads, "I have a theory and this is the only data I could find."

:::

## xkcd comic, panel 10

![](http://pmean.com/new-images/25/xkcd-10.png "Panel 10 of xkcd comic")

::: notes

Here the proposed regression model gets a bit silly. This shows a scatter of data points with a smooth curve connecting every data point. The caption reads, "I clikced 'smooth lines' in Excel."

:::

## xkcd comic, panel 11

![](http://pmean.com/new-images/25/xkcd-11.png "Panel 11 of xkcd comic")

::: notes

This shows a scatter of data points with a smoother that looks like it uses medians somehow. The caption reads, "I had an idea for how to clean up the data. What do you think?"

:::

## xkcd comic, panel 12

![](http://pmean.com/new-images/25/xkcd-12.png "Panel 12 of xkcd comic")

::: notes

This shows a scatter of data points with what looks like a B-spline. The caption reads, "As you can see, this model smoothly fits the - Wait, No, No, Don't extend it. AAAAAA!!"

:::

