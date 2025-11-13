---
title: A simple trick in R
author: Steve Simon
source: http://www.pmean.com/05/TrickR.html
date: 2005-10-11
categories:
- "*Blog post"
- Year 2005
- Being updated
- R software
output: html_document
page_update: partial
---

There may be times when you have a string in R that represents a
specific R command. How would you run this command. This was answered
recently on the Bioconductor mailing list. You use the eval() and
parse() functions. Here's an example:

`R.function <- "mas"  R.args <- "data.raw"  R.command <- paste(R.function,"(",R.args,")",sep="")  R.command[1] "mas(data.raw)"eval(parse(text=method))`

The parse() function turns the string into an unevaluated expression
and the eval() function evaluates this expression.

The do.call() function can also work.

`do.call(R.function,list(R.args))`

This sort of thing is useful if you need to loop through a sequence of
commands, a sequence of of arguments, or a sequence of models. I'll
try to show an example where you could not do this through a simpler
approach when I have time.

You can also browse
for pages similar to this one at [Category: R
software](../category/RSoftware.html).

Earlier versions are [here][sim1] and [here][sim2].

[sim1]: http://www.pmean.com/05/TrickR.html
[sim2]: http://new.pmean.com/string-to-command/
