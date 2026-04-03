---
title: "Gemini query for SAS code"
source: "New"
author: Steve Simon
date: 2025-02-21
categories: Blog post
tags:
- Generative AI
output: html_document
page_update: no
---

I sent the query "write a SAS program to read the file titanic.csv" to Gemini. Here is the response I got. I added a small code fragment at the beginning and end to display this as code inside of this page. Notice how Gemini added a few bonus commands that make sense for this request.

<!---more--->

```{}
/* Read the titanic.csv file into a SAS dataset called 'titanic_data' */
PROC IMPORT DATAFILE="titanic.csv"
    DBMS=CSV
    OUT=titanic_data
    USEOBS=ALL; /* Reads all observations */
RUN;

/* Display the first few rows of the data to verify that the file was read correctly */
PROC PRINT DATASET=titanic_data(OBS=10); /* Display the first 10 observations */
RUN;

/* You can also use other procedures to explore the data: */

/* Display the structure of the dataset (variable names, data types, etc.) */
PROC CONTENTS DATASET=titanic_data;
RUN;

/* Get a summary of the data (min, max, mean, median, etc. for numeric variables) */
PROC MEANS DATASET=titanic_data;
RUN;

/* Get the number of rows and columns in the data set */
PROC SQL;
    SELECT COUNT(*) AS num_rows, COUNT(*) AS num_cols
    FROM DICTIONARY.COLUMNS
    WHERE LIBNAME = "WORK" AND MEMNAME = "TITANIC_DATA";
QUIT;

/* List the column names */
PROC CONTENTS DATASET=titanic_data;
RUN;
```
