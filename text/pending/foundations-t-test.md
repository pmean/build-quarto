---
title: The mathematical foundations of the two sample t-test
source: "New"
author: Steve Simon
date: 2025-10-22
categories: 
- "*Blog post"
- 2025
- Being updated
output: html_document
page_update: no
---

A student wanted to know a bit more about the mathematical foundations of the two sample t-test. Without getting too deep into the mathematics (meaning that I can't invoke anything involving Calculus), here is an overview of how the two sample t-test works.

<!---more--->

Let the symbol $E[]$ represent the expected value (or more colloquially, the mean). Let the symbol $V[]$ represent the variance (the square of the standard deviation).

If A and B are two random variables, then

$E[A+B]=E[A]+E[B]$

and

$V[A+B]=V[A]+V[B]$

but only if A and B are independent!

Finally, if k is a constant, then

$E[kX]=kE[X]$

and

$V[kX]=k^2V[X]$.

Now here is the general fraemwork for the two sample t-test. 

You collect two samples,

$X_{11}, X_{12}, ..., X_{1n_1}$

$X_{21}, X_{22}, ..., X_{2n_2}$

Note that $n_1$ and $n_2$ do not need to be equal. 

The t-test has three assumptions:

1. normality
2. homogeneity
3. independence

Mathematically, the last two assumptions mean that

$E[X_{1i}] = \mu_1$; $V[X_{1i}] = \sigma^2$

$E[X_{2i}] = \mu_2$; $V[X_{2i}] = \sigma^2$

Note that the two variances are equal (homogeneity), but the two means may or may not be equal.

Under these assumptions, you can show that 

$E[\bar{X}_1] =$

$\ \ E[\frac{1}{n_1}\Sigma X_{1i}] =$

$\ \ \frac{1}{n_1}E[\Sigma X_{1i}] =$

$\ \ \frac{1}{n_1}\Sigma E[X_{1i}] =$

$\ \ \frac{1}{n_1} n_1 \mu_1 = \mu_1$

By similar calculations, you can show that

$V[\bar{X}_1]=\frac{1}{n_1}\sigma^2$; $E[\bar{X}_2]=\mu_2$; $V[\bar{X}_2]=\frac{1}{n_2}\sigma^2$

Knowing this, it then follows that

$E[\bar{X}_1-\bar{X}_2] = \mu_1-\mu_2$; $V[\bar{X}_1-\bar{X}_2] = \sigma^2(\frac{1}{n_1}+\frac{1}{n_2})$

If you assume normality then

$\frac{(\bar{X}_1-\bar{X}_2)-(\mu1-\mu2)}{\sigma\sqrt{\frac{1}{n_1}+\frac{1}{n_2}}}$ is distributed as N(0, 1).

If the null hypothesis ($H_0\ \mu_1-\mu_2=0$) is true then 

$\frac{(\bar{X}_1-\bar{X}_2)}{\sigma\sqrt{\frac{1}{n_1}+\frac{1}{n_2}}}$ is distributed as N(0, 1).

We don't know what $\sigma$ is so we have to use a different ratio

$\frac{(\bar{X}_1-\bar{X}_2)}{S_p\sqrt{\frac{1}{n_1}+\frac{1}{n_2}}}$ 

where $S_p$ is the pooled standard deviation. 

This change means that the quantity in question is no longer a normal distribution. It has sampling error in both the numerator and denominator. It, instead, has a t distribution with $n_1+n_2-2$ degrees of freedom.

If you want to test the null hypothesis, you should accept the null hypothesis if 

$T = \frac{(\bar{X}_1-\bar{X}_2)}{S_p\sqrt{\frac{1}{n_1}+\frac{1}{n_2}}}$ 

is close to zero and reject the null hypothesis if T is large negative or T is large positive.

In mathematical terms, rejecting the null hypothesis is $T <  -c$ (large negative) or $T > c$ (large positive) where c is a constant that you choose to have good properties. In particular, you want the probabilitiy of a Type I error (rejecting the null hypothesis when the null hypothesis is true) to be small.

If you choose limits of $t(\alpha/2; n_1+n_2-2)$ and $t(1-\alpha/2; n_1+n_2-2)$ then

$P\big[T < t(\alpha/2; n_1+n_2-2)] +P\big[T > t(1-\alpha/2; n_1+n_2-2)\big] = \alpha$