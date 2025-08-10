---
title: Data privacy resources
source: "New"
author: Steve Simon
date: 20xx-xx-xx
categories: Blog post
tags:
- Being updated
output: html_document
page_update: no
---

I attended an introductory talk at the Joint Statistical Meetings on data privacy. It's a very complicated area and I can not do it justice. There was a detailed explanation of differential privacy, for example, which quantifies the trade-off between the utility of a modification to a dataset and the ability of that modification to preserve individaul privacy. I did not some of the key regulatory issues associated with data privacy. 

<!---more--->

HIPAA, short for the Health Insurance Portability and Accountability Act, is something that I was already familiar with, but it is worth sharing a [link][ref-nih-nodate] here anyway.

[ref-nih-nodate]: https://www.hhs.gov/hipaa/index.html

FERPA, 

Title 13, https://www.census.gov/about/policies/privacy/data_stewardship/title_13_-_protection_of_confidential_information.html

Title 26, https://www.justice.gov/archives/jm/criminal-resource-manual-506-disclosure-under-26-usc-6103i1

GDPR, https://gdpr-info.eu/

https://clairemckaybowen.com/

https://epic.org/wp-content/uploads/privacy/reidentification/Sweeney_Article.pdf

api_key <- ""

url <- "https://api.openai.com/v1/chat/completions"

headers <- add_headers(
  Authorization = paste("Bearer", api_key),
  `Content-Type` = "application/json"
)

body <- list(
  model = "gpt-3.5-turbo",
  messages = list(
    list(role = "user", content = "On a scale of 1 to 10, classify the sentiment of the phrase 'R is not at all complicated'")
  ),
  temperature = 0.7
)

response <- POST(url, headers, body = body, encode = "json")
content <- content(response, as = "parsed")

# Display the ChatGPT reply
cat(content$choices[[1]]$message$content)


https://www.cs.utexas.edu/~shmat/shmat_oak08netflix.pdf

https://lmaowisc.github.io/

https://www.danieldsjoberg.com/ggsurvfit-rmed-webinar-2024/


NSQIP: https://www.facs.org/quality-programs/data-and-registries/acs-nsqip/

Ittenbach: https://ascpt.onlinelibrary.wiley.com/doi/full/10.1111/cts.13545

Graphviz: https://graphviz.org/

dot extension: https://www.stata.com/manuals/h2omldotextension.pdf

Individual Conditional Expectation: https://christophm.github.io/interpretable-ml-book/ice.html

Janzing: https://arxiv.org/abs/1910.13413

Ribiero: https://arxiv.org/pdf/1602.04938

Lundberg: https://arxiv.org/abs/1705.07874

Biecek: https://arxiv.org/html/2402.13914v2

GBM: https://pmc.ncbi.nlm.nih.gov/articles/PMC3885826/

Breiman: https://projecteuclid.org/journals/statistical-science/volume-16/issue-3/Statistical-Modeling--The-Two-Cultures-with-comments-and-a/10.1214/ss/1009213726.full

IBM HR data: https://inseaddataanalytics.github.io/INSEADAnalytics/groupprojects/January2018FBL/IBM_Attrition_VSS.html

h2o: https://h2o.ai/resources/download/

BLS firing: https://www.racket.news/p/lies-damn-lies-and-statistics?r=lcwq0&utm_campaign=post&utm_medium=email&triedRedirect=true

America's Essential Data: https://essentialdata.us/

Houston Wastewater Epidemiology: https://www.hou-wastewater-epi.org/

s7: https://www.tidyverse.org/blog/2024/11/s7-0-2-0/

ggtrace: https://yjunechoe.github.io/ggtrace/

easy-geom-recipes: https://github.com/EvaMaeRey/easy-geom-recipes

ggplot2 extensions: https://exts.ggplot2.tidyverse.org/gallery/

ggplot2-extenders: https://ggplot2-extenders.github.io/ggplot-extension-club/

virtual control animals: https://pubmed.ncbi.nlm.nih.gov/38043132/

eTRANSAFE: https://etransafe.eu/virtual-control-groups-one-step-forward-into-the-future-of-animal-testing-in-toxicology/

vict3r: https://www.vict3r.eu/

https://pubmed.ncbi.nlm.nih.gov/38043132/


Bayesian clinical trial design incorporating historical data. Joseph Ibrahim.

Duan 2006.

Han 2025 ordered NPP

Barbeta 2019

Shen 2024

Adapted normalized power prior

mu is 1, v is IG

Elastic prior: Jiang 2021, https://pubmed.ncbi.nlm.nih.gov/34437714/

## Mixture prior

Also self-adapting mixture prior

Yang 2023 SAM Biometric

Zhao 2025 PS-SAM JBS 

## Bayesian Additive Regression Trees, Tianjian Zhou

https://www.linkedin.com/in/tianjianzhou/

## Chen

Xie 2025 Simpsons Paradox, https://jds-online.org/journal/JDS/article/1414/file/pdf

https://jds-online.org/journal/JDS/article/1400/info

## ggplot2 extenders

https://ggplot2-extenders.github.io/ggplot-extension-club/

https://exts.ggplot2.tidyverse.org/gallery/

https://github.com/EvaMaeRey/easy-geom-recipes

https://bsky.app/profile/brodriguesco.bsky.social/post/3lrzj6r2yws2b

https://yjunechoe.github.io/ggtrace/

https://www.tidyverse.org/blog/2024/11/s7-0-2-0/

## Houston

https://www.hou-wastewater-epi.org/

https://essentialdata.us/

## BLS firing

https://www.linkedin.com/posts/ron-wasserstein_federalstatistics-countonstatistics-datainfrastructure-activity-7357455511585189888-8DCk/?utm_source=share&utm_medium=member_ios&rcm=ACoAAACSchgBtwofZMnsx319FgrLi29y6KpmwW4

https://www.racket.news/p/lies-damn-lies-and-statistics?r=lcwq0&utm_campaign=post&utm_medium=email&triedRedirect=true

## Stata

https://h2o.ai/resources/download/

https://inseaddataanalytics.github.io/INSEADAnalytics/groupprojects/January2018FBL/IBM_Attrition_VSS.html

https://projecteuclid.org/journals/statistical-science/volume-16/issue-3/Statistical-Modeling--The-Two-Cultures-with-comments-and-a/10.1214/ss/1009213726.full

https://pmc.ncbi.nlm.nih.gov/articles/PMC3885826/

https://docs.h2o.ai/h2o/latest-stable/h2o-docs/welcome.html

## LLMs

https://arxiv.org/html/2402.13914v2

http://arxiv.org/pdf/1602.04938

https://arxiv.org/abs/1910.13413

https://arxiv.org/abs/1705.07874

https://christophm.github.io/interpretable-ml-book/pdp.html

https://christophm.github.io/interpretable-ml-book/ice.html

https://www.stata.com/manuals/h2omldotextension.pdf

https://graphviz.org/

## CDM/CDS

https://ascpt.onlinelibrary.wiley.com/doi/full/10.1111/cts.13545

## Historical controls

https://www.linkedin.com/in/tianjianzhou/


