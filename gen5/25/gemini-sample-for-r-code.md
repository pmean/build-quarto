---
title: "Gemini query for R code"
source: "New"
author: Steve Simon
date: 2025-02-21
categories: Blog post
tags:
- Generative AI
output: html_document
page_update: no
---

I sent the query "write an R program to read the file titanic.csv" to Gemini. Here is the response I got. I added a small code fragment at the beginning and end to display this as code inside of this page. Notice how Gemini added a few bonus commands that make sense for this request.

<!---more--->

```{}
# Read the titanic.csv file into a data frame called 'titanic_data'
titanic_data <- read.csv("titanic.csv")

# Display the first few rows of the data frame to verify that the file was read correctly
head(titanic_data)

# You can also use other functions to explore the data:

# Display the structure of the data frame (variable names, data types, etc.)
str(titanic_data)

# Get a summary of the data (min, max, mean, median, etc. for numeric variables)
summary(titanic_data)

# Get the number of rows and columns in the data frame
dim(titanic_data)

# List the column names
names(titanic_data)
```
