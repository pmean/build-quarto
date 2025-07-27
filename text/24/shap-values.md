---
title: "A gentle introduction to SHAP values in R"
source: "New"
author: Steve Simon
date: "2024-07-10"
categories:
- "*Recommendation"
- 2024
- Interpretable machine learning
output: html_document
page_update: no
---

![Figure 1. Excerpt from website](http://www.pmean.com/new-images/24/shap-values-01.png){width=80%}

::: notes

SHAP values provide you a way to interpret the impact of individual independent variables in a variety of "black box" machine learning models, such as Random Forest. It looks at how a prediction changes when a variable is not included in the model. This page shows how to fit SHAP values using R.

-   Pablo Casas. A gentle introduction to SHAP values in R. Data Science Heroes blog, 2019-03-18. Available in [html format][ref-casas-2019].

[ref-casas-2019]: https://blog.datascienceheroes.com/how-to-interpret-shap-values-in-r/

An [earlier version][sim2] of this page was published on [new.pmean.com][sim1].

[sim1]: http://new.pmean.com
[sim2]: http://new.pmean.com/shap-values/

:::
