---
title: Optimization using the MM algorithm
author: Steve Simon
source: http://www.pmean.com/05/MMalgorithm.html
date: 2005-02-14
categories:
- "*Blog post"
- Year 2005
- Being updated
- Statistical computing
output: html_document
page_update: partial
---
A comment on EDSTAT-L reminded me about this important issue. Many
problems in Statistics involve finding an optimal point of a rather
complex and messy function. In some situations, the optimal point is the
largest value for this function and in other situation, the optimal
point is the smallest value. The simplest and best known example of this
is regression. This approach tries to estimate a line (or sometimes a
more complex curve) that is "close" to most of the data. The approach,
least squares, tries to minimize the sum of squared deviations between
the line and the data. Even simple problems such as estimating a median
can be recast in terms of minimizing distance.

Optimization using a computer is a rather difficult and complex process
because an approach that works well for one set of problems may perform
poorly for another set. A nice tutorial on the state of the art for
optimization is:

- **A Tutorial on MM Algorithms.** Hunter DR, Lange K. The American
Statistician 2004: 54(1); 30-37.

Earlier versions are [here][sim1] and [here][sim2].


[sim1]: http://www.pmean.com/05/MMalgorithm.html
[sim2]: http://new.pmean.com/mm-optimization/
