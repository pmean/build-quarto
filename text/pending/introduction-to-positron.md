---
title: Introduction to Positron
source: "New"
author: Steve Simon
date: 2025-09-24
categories: 
- "*Blog post"
- Being updated
output: html_document
page_update: no
---

I attended a webinar about Positron, a new integrated development environment (IDE). It is developed by Posit, the same company that brought us R Studio. Here is some resources about Positron, mostly resources that were mentioned in the webinar or resources that I googled while watching.

<!---more--->

The actual webinar will be available soon as a YouTube video, but I do not have the link yet. Instead, look at these resources.

-   Julia Silge. A first look at Positron. A next generation IDE for data science. Available as a [YouTube video][ref-silge-2025].
    -   Perhaps the best place to start is a 20 minute talk by Julia Silge. This talk is oriented to those of us who have worked mostly with R and RStudio. You might also want take a peek at [Julia Silge's blog][ref-silge-nodate] which covers all sorts of interesting things.

-   David Kane. Positron Tutorials, 2025. Available in [html format][ref-kane-2025].
    -   David Kane created an R package that you can install from CRAN. It has tutorials that discuss using Positron with R code, Quarto, the command line interface, git, and Quarto websites.

-   Differences between the repository and Visual Studio Code. Available in [html format][ref-microsoft-nodate].
    -   Visual Studio Code is an IDE developed by Microsoft. It is a well-established product with an enthusiastic user base. It is also a mature product, having been in regular use since 2015. For various technical reasons, Microsoft cannot place Visual Studio Code under an open source license. They have, however, generously placed quite a bit of their work in Code-OSS, an open source project that anyone can use to develop their own IDEs, free from any proprietary restrictions. Positron is based on Code-OSS.

-   Open VSX Registry. Available in [html format][ref-openvsx-nodate].
    -   Visual Studio Code is easily extensible and many users have developed and distributed extensions. Because of similar licensing issues, extensions without proprietary restrictions are distributed on an alternative site, Open VSX. Many of the extensions distributed as part of Positron as well as optional extensions that you might want to add to Positron are available here.

-   Joe Cheng, Sara Altman. Databot. Posit blog, 2025-08-28. Available in [html format][ref-cheng-2025].
    -   Positron sports two artificial intelligence (AI) features. Databot is an assistant for exploratory data analysis. It can reveal the underlying structure of a complex dataset, identify potential quality problems with a dataset, and propose avenues of exploration for that dataset. The authors of the blog post warn that these features should not be considered a substitute for review by a human expert, but rather as an assistant to someone who is already familiar with data management and data analysis issues.

-   Stephen Turner. Positron Assistant. Paired Ends blog, 202507-16. Available in [html format][ref-turner-2025].
    -   The second AI feature of Positron is Positron Assistant. it uses two systems, Github Copilot and Anthropic Claude to help you generate code. Other systems that can help you generate code will be added soon.

-   Publishing from VS Code or Positron. Posit Connect documentation, 2025. Available in [html format][ref-posit-connect-2025].
    -   Posit Connect is a platform where you can publish output from R, Python, and other packages. You can make this output publicly available or restrict it to specific people. R Studio has had the capability to post output on Posit Connection for quite a while. That capability is now available if you are using the Positron IDE or the Visual Studio Code IDE.

-   Download Positron. Positron documentation 2025. Available in [html format][ref-posit-positron-2025].
    -   If you find this all interesting, you can download Positron from the Posit website. It is no longer in beta mode, but some of the newer features are still in flux.
    
[ref-cheng-2025]: https://posit.co/blog/introducing-databot/    
[ref-kane-2025]: https://ppbds.github.io/positron.tutorials/
[ref-microsoft-nodate]: https://github.com/microsoft/vscode/wiki/Differences-between-the-repository-and-Visual-Studio-Code
[ref-openvsx-nodate]: https://open-vsx.org/
[ref-posit-connenct-2025]: https://docs.posit.co/connect/user/publishing-positron-vscode/
[ref-posit-positron-2025]: https://positron.posit.co/download.html
[ref-silge-2025]: https://www.youtube.com/watch?v=aKSrptGegeo
[ref-silge-nodate]: https://juliasilge.com/
[ref-turner-2025]: https://blog.stephenturner.us/p/positron-assistant-copilot-chat-agent