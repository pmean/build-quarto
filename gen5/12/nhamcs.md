---
title: New post
source: "New"
author: Steve Simon
date: 2012-06-22
categories:
- "*Blog post"
- 2012
- Being updated
output: html_document
page_update: no
---

Here is a brief abstract.

I want to summarize some of the work that I have done with the National Hospital Ambulatory Care Survey (NHAMCS). This is a fascinating and very useful data set, but it has a lot of subtle issues that you need to be aware of.

<!---more--->

NHAMCS and it's twin sister NAMCS (National Ambulatory Care Survey) are national probability samples produced by the Centers for Disease Control and Prevention (CDC). A national probability sample means that sampling was done in a way to allow you to make valid extrapolations to the entire United States. This can only be done through very sophisticated sampling methods that involve both cluster sampling and stratified sampling. These occur at several different levels of the sample.

The complex sample, especially the clustering, greatly complicates the data analysis. But it's important to remember why CDC needed to use a complex sample. Think a bit about trying to get a simple random sample of 1,000 people in the United States. Such a sample would probably end up selecting individuals at least 500 separate communities if not more. You'd fly into a community, sample one or two people, and fly on to another community. Not only would this be physically exhausting, it would cost way too much money. Clustering allows you to sample a larger number of individuals at a single location, so that you're not flying to a new city every single day.

An important aspect of the complex sample is the need for sample weights. These weights are needed in every complex sample in order to get proper standard errors, but they become especially important in surveys where certain groups are oversampled. In some CDC surveys (not NHAMCS), the researchers deliberately ovesample in two minority groups, African-Americans and Hispanics, in order to assure a large enough sample size for analysis in these subgroups. If you are doing an analysis across all race/ethnicity groups, then failure to use sample weights will provide problems with the point estimates in additon to the standard errors.

Both NAMCS and NHAMCS are visit specific and not patient specific. This means that you can calculate the number of Emergency Room visits involving asthma attacks, but you cannot calculate the number of children who visit the Emergency Room because of an asthma attack.

NAMCS tracks visits to office-based physicians, while NHAMCS tracks visits to the Emergency Department and separately tracks visits to outpatient clinics. A nice brief summary of thes samples appears at
--> http://www.cdc.gov/nchs/ahcd/about_ahcd.htm

We were interested in the quality of care provided to children with asthma, bronchiolitis, and croup in the emergency room setting. We originally published information for a single year (2005) and then we examined trends over time starting with data from 1995 and continuing through 2009. We originally wanted to look all the way back to the beginning of the survey (1992) but there were some important variables not available in the earlier years.

You can download the raw data from NHAMCS. It is a fixed width text file. CDC also provides code for reading this data into SAS, SPSS, and Stata, though for earlier years there is only code for SAS and not the other two programs. This code is important becuase it provides variable names, variables labels, and value labels. There are substantial changes in the type of data collected from year to year, though the key variables remain largely the same.

The drug classifications in NHAMCS are quite complicated. The first complication is that a patient may receive multiple drugs during their stay in the ED. The second complication is that each drug may belong to several different classes of drugs. The third complication is that a drug may have several different ingredients.

Here are the variables for year 2003:

```{}
gen1 %5s "Generic name code for medication #1 "
prescr1 %1f "Prescription status code for medication #1 "
contsub1 %1f "Controlled substance code for medication #1 "
comstat1 %1f "Composition status code for medication #1 "
drug1cl1 %4s "Drug Class #1 for Medication #1 "
drug1cl2 %4s "Drug Class #2 for Medication #1 "
drug1cl3 %4s "Drug Class #3 for Medication #1 "
drg1ing1 %5s "Ingredient code #1 for medication #1 "
drg1ing2 %5s "Ingredient code #2 for medication #1 "
drg1ing3 %5s "Ingredient code #3 for medication #1 "
drg1ing4 %5s "Ingredient code #4 for medication #1 "
drg1ing5 %5s "Ingredient code #5 for medication #1 "
Notice that this list is just for the first of eight possible drugs, so there are 96 different variables to sort through.
```

Here are the variables for year 2006:

```{}
drugid1 %6s "Drug ID for med #1 "
prescr1 %1f "Prescription status code for med #1 "
contsub1 %1f "Controlled status code for med #1 "
comstat1 %1f "Composition status code for med #1 "
rx1cat1 %3s "Multum drug category #1 for medication #1 "
rx1cat2 %3s "Multum drug category #2 for medication #1 "
rx1cat3 %3s "Multum drug category #3 for medication #1 "
rx1cat4 %3s "Multum drug category #4 for medication #1 "
rx1v1c1 %3s "Level 1 of Multum drug category #1 for med #1"
rx1v1c2 %3s "Level 1 of Multum drug category #2 for med #1"
rx1v1c3 %3s "Level 1 of Multum drug category #3 for med #1"
rx1v1c4 %3s "Level 1 of Multum drug category #4 for med #1"
rx1v2c1 %3s "Level 2 of Multum drug category #1 for med #1"
rx1v2c2 %3s "Level 2 of Multum drug category #2 for med #1"
rx1v2c3 %3s "Level 2 of Multum drug category #3 for med #1"
rx1v2c4 %3s "Level 2 of Multum drug category #4 for med #1"
rx1v3c1 %3s "Level 3 of Multum drug category #1 for med #1"
rx1v3c2 %3s "Level 3 of Multum drug category #2 for med #1"
rx1v3c3 %3s "Level 3 of Multum drug category #3 for med #1"
rx1v3c4 %3s "Level 3 of Multum drug category #4 for med #1"
```

Notice that there are now 160 variables to sort through. But there's more. In a different part of the database are eight more variables.

```{}
gpmed1 %1f "Med #1 given in ED or Rx at discharge? "
gpmed2 %1f "Med #2 given in ED or Rx at discharge? "
gpmed3 %1f "Med #3 given in ED or Rx at discharge? "
gpmed4 %1f "Med #4 given in ED or Rx at discharge? "
gpmed5 %1f "Med #5 given in ED or Rx at discharge? "
gpmed6 %1f "Med #6 given in ED or Rx at discharge? "
gpmed7 %1f "Med #7 given in ED or Rx at discharge? "
gpmed8 %1f "Med #8 given in ED or Rx at discharge? "
These variables were not available in 2004 and earlier years.
```

But there's still one more complication. In 2005 earlier years, CDC used a different coding system for drugs than for yeaqrs 2006 and later.

-   http://www.cdc.gov/nchs/ahcd/trend_analysis.htm

So we had to create two files for each drug: one listing the codes needed for 2005 and earlier and the other listing the codes needed for 2006 and later. For antibiotics, the values are

```{}
346
347
348
353
```

in 2005 and earlier and

```{}
008
009
011
012
013
014
015
016
018
```

for 2006 and later.
 
An earlier version is [here][sim2].
 
[sim2]: http://new.pmean.com/nhamcs/
