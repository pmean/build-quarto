---
title: I abhor Lilliefor and other tests of normality
author: Steve Simon
date: 2005-06-07
categories:
- "*Blog post"
- 2005
- Statistical assumptions
output: html_document
page_update: partial
---

Someone asked me about a log transformation for their data. It seemed like a good idea, based on my general comments on the log transformation, but the test of significance for normality (Lilliefor's test) was still rejected even after the log transformation.

<!---More--->

In general, I dislike Lilliefor's test (and other tests of normality like the Shapiro-Wilks test). They have way too much power power for large sample sizes and will often end up detecting trivial departures from normality. Instead of a formal test, use a histogram, boxplot, normal probability plot, or whatever to get a qualitative indication of how close your data is to a normal distribution.

## Further reading

Steve Simon. Checking the assumption of normality. PMean blog 2002-09-11. Available in [html format][ref-simon-2002] 

NIST. Normal Probability Plot. Section 1.3.3.21 of the NIST/SEMATECH e-Handbook of Statistical Method, last updated in April 2012. Available in [html format][ref-nist-2012].

You can find an [earlier version][sim1] of this page on my [original website][sim2].

[ref-simon-2002]: http://new.pmean.com/checking-normality-assumption/
[ref-nist-2012]: https://www.itl.nist.gov/div898/handbook/eda/section3/normprpl.htm


[sim1]: http://www.pmean.com/05/TestsNormality.html
[sim2]: http://www.pmean.com/original_site.html
