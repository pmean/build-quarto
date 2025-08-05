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