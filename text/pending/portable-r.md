---
title: "A portable version of R and RStudio for a USB stick"
source: "New"
author: Steve Simon
date: 2025-08-22
categories: 
- "*Blog post"
- 2025
- R software
output: html_document
page_update: no
---

There are times when you might want to install R and RStudio on a USB stick. This is a bit more complicated than installing R on your local hard drive. The advantage with a memory stick is that you can attach it to any computer and it should work, even if that computer does not have R/RStudio. Here are the details.

<!---more--->

Install R first. There is an [FAQ][ref-cran-nodate] about this on CRAN. You need to insure that R has read/write access to a temporary directory and another directory to serve as home. You may need to set up a shortcut to R.

Apparently, an RStudio installation can be done without much fuss at all, according to this [Josh Paulson support page][ref-paulson-2025] on the Posit website. 

[ref-cran-nodate]: https://cran.r-project.org/bin/windows/base/rw-FAQ.html#Can-I-run-R-from-a-CD-or-USB-drive_003f
[ref-paulson-2025]: https://support.posit.co/hc/en-us/articles/200534467-Creating-a-Portable-Version-of-RStudio-for-a-USB-Drive
