---
title: "Data masking in R"
source: "New"
author: Steve Simon
date: "2024-10-05"
categories: 
- "*Recommendation"
- 2024
- R programming
output: html_document
page_update: no
---

![](http://www.pmean.com/new-images/24/data-masking-in-r-01.png "Excerpt from recommended website"){width=80%}

::: notes

One major innovation of tidyverse is the use of non-standard evaluation. It allows you to avoid a lot of repetition of dataframe names in R code. I wrote a [page about non-standard evaluation][ref-simon-2023] about a year ago, and referenced some key website that explain things. It was not a very good explanation, and the references that I included, although a bit better, were still difficult.

I ran across this page, which tries to clarify things. It uses a simpler term, data masking, instead of non-standard evaluation and it explains how distinguishing between programming variables (env-variables) and statistical variables (data-variables) is difficult inside of R functions and loops.

The topic is still not easy to follow, but this page seems to be better than my descriptions and earlier resources about this topic.

-   Lionel Henry, Hadley Wickham. Argument type: data-masking. Available in [html format][ref-henry-nodate].

[ref-henry-nodate]: https://rlang.r-lib.org/reference/args_data_masking.html
[ref-simon-2023]: http://new.pmean.com/non-standard-evaluation/

An [earlier version][sim2] of this page was published on [new.pmean.com][sim1].

[sim1]: http://new.pmean.com
[sim2]: http://new.pmean.com/data-masking-in-r/

:::
