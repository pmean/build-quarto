---
title: Importing value labels from Access into SPSS
author: Steve Simon
source: http://www.pmean.com/05/ValueLabels.html
date: 2005-05-24
categories:
- "*Blog post"
- 2005
- Being updated
- Data management
output: html_document
page_update: partial
---
**[StATS]: Importing value labels from Access into
SPSS (May 24, 2005)**.

Someone asked about importing data from Access into SPSS. The Access
file has value labels (e.g., 1=Male, 2=Female, 3=Missing) and wanted to
know if there was any<U+FFFD> way to get this information into SPSS.

You cannot easily import value labels into SPSS, as far as I know. One
workaround is to use a join in Access to link the table that has the
number codes to the table that has the labels. Then export that join
into SPSS. You will get a column of data with the number codes and a
second column of data with the value labels.

You can also browse
for pages similar to this one at [Category: Data
management](../category/DataManagement.html).

Earlier versions are [here][sim1] and [here][sim2].

[sim1]: http://www.pmean.com/05/ValueLabels.html
[sim2]: http://new.pmean.com/importing-value-labels/

