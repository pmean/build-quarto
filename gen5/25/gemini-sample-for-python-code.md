---
title: "Gemini query for Python code"
source: "New"
author: Steve Simon
date: 2025-02-21
categories: Blog post
tags:
- Generative AI
output: html_document
page_update: no
---

I sent the query "write a python program to read the file titanic.csv" to Gemini. Here is the response I got. I added a small code fragment at the beginning and end to display this as code inside of this page. Notice how Gemini added a few bonus commands that make sense for this request.

<!---more--->

```{}
import pandas as pd

# Read the titanic.csv file into a pandas DataFrame called 'titanic_data'
titanic_data = pd.read_csv("titanic.csv")

# Display the first few rows of the DataFrame to verify that the file was read correctly
print(titanic_data.head())

# You can also use other methods to explore the data:

# Display the structure of the DataFrame (variable names, data types, etc.)
print(titanic_data.info())

# Get a summary of the data (min, max, mean, median, etc. for numeric variables)
print(titanic_data.describe())

# Get the number of rows and columns in the DataFrame
print(titanic_data.shape)

# List the column names
print(titanic_data.columns)
```
