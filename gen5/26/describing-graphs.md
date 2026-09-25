---
title: Using generative AI to describe a graph
source: "New"
author: Steve Simon
date: "2026-09-23"
categories: 
- "*Blog post"
- Year 2026
- Generative AI
output: html_document
page_update: no
---

Writing web pages are fun, but there is one important detail that is tedious. If you publish a web page, you should provide a description of any image included in that webpage for the benefit of any readers with visual impairments. I try to do this, but my descriptions are much too brief and I forget to include any description for many of my images. Worse still, there are hundreds of images from the years before I became sensitized to the need for these descriptions. I decided to experiment with the use of Gemini, an artificial intelligence system made freely available by Google. Gemini did a pretty darned good job.

<!---more--->

This is a graph I was using in a class. It has a lot of interesting context, so I thought it would be an interesting test case to see how well a generative AI model could describe the graph to a visually impaired viewer.

![](http://pmean.com/new-images/26/describing-plots-01.png "Graph that needs a description")

I went to the [Gemini website][ref-gemini-nodate], and uploaded the image shown above and added the following text.

"This plot shows votes by county in Florida for the 2000 presidential election. Provide an interpretation of this plot for someone with visual impairments"

This is how Gemini responded. 

![](http://pmean.com/new-images/26/dscribing-graphs-02.png "Nicely formatted response from Gemini")

It was very nicely formatted, but not suitable for the alt text that you need to include with images on your web page. So I sent an additional bit of text

"recast this description as a single paragraph"

and here is what I got back

"This scatter plot displays county-level vote totals in Florida from the 2000 U.S. presidential election, comparing votes cast for George W. Bush on the horizontal axis (in thousands, ranging from 0 to 300) against votes cast for Pat Buchanan on the vertical axis (ranging from 0 to over 3,000). Most of the hollow circles representing Florida's counties form a dense, positive linear cluster along the bottom of the graph, showing that as Bush's vote count increased (mostly under 50,000 votes), Buchanan's vote count predictably increased as well (remaining mostly below 500 votes). However, the plot features one extreme outlier near the top center located at roughly 152,000 votes for Bush and over 3,400 votes for Buchanan—representing Palm Beach County, where the count was disproportionately high compared to the rest of the state—alongside a far-right outlier at approximately 288,000 votes for Bush and 550 votes for Buchanan.""

## Markdown version of the nicely formatted response

I wanted to reproduce, as closely as possible, the formatting used in the first response using markdown codes. So I sent Gemini a third prompt.

"Take the text from your first response and use markdown formatting codes to preserve as much of the appearance of your response."

Here is what Gemini produced.

This scatter plot displays county-level vote totals in Florida from the 2000 U.S. presidential election, comparing votes cast for George W. Bush against votes cast for Pat Buchanan[cite: 1]. 

### Visual Structure & Layout
* **Horizontal Axis (X-axis):** **Votes for Bush (thousands)**, ranging from 0 to 300 (i.e., 0 to 300,000 votes)[cite: 1].
* **Vertical Axis (Y-axis):** **Votes for Buchanan**, ranging from 0 to over 3,000 votes[cite: 1].
* **Data Points:** Each hollow circle represents one of Florida's 67 counties[cite: 1].

### Key Patterns & Trends
* **General Linear Trend:** For almost all counties, there is a clear positive correlation between Bush's vote count and Buchanan's vote count[cite: 1]. Most data points form a tight, linear cluster along the bottom of the graph, starting near (0, 0) and extending toward roughly 180,000 votes for Bush and 1,000 votes for Buchanan[cite: 1].
* **General Cluster:** Most small-to-midsize counties are clustered densely below 50,000 votes for Bush and under 500 votes for Buchanan[cite: 1].

### Notable Outliers
* **Extreme Outlier (Palm Beach County):** There is one striking anomaly near the top center of the plot located at roughly **152,000 votes for Bush** and over **3,400 votes for Buchanan**[cite: 1]. This point sits far isolated vertically above the general trendline, where other counties with similar Bush totals received fewer than 1,000 votes for Buchanan[cite: 1]. (Historically, this discrepancy in Palm Beach County was widely attributed to the infamous "butterfly ballot" design.)
* **High-Volume Outlier:** A single point appears at the far right around **288,000 votes for Bush** and roughly **550 votes for Buchanan**, reflecting a very high Bush vote total but a typical Buchanan vote count[cite: 1].

## So how did Gemini do?

This is a free version of Gemini, so you might get even better results with a paid version. I do not know how other generative AI models like ChatGPT or Claude would do, either. Still, I'd have to say this is a very good summary. 

-   Gemini provided a good descrition of two axes, including the fact that the X-axis represented thousands of votes. Gemini also listed the ranges for the X and Y axes.
-   Gemini describe the cluster of points showing a strong positive association.
-   Gemini noted the two outliers. It pulled in information from other sources that identified the largest outlier as the votes in Palm Beach County. It referenced the controversial butterfly ballot used in that county. That detail was lost when I asked for a single paragraph summary, but that's okay.

## Two cautionary statements

You should never upload private or sensitive information to Gemini or other generative AI models. If you need to work with this type of data often, pay for a license that allows you to keep all your sensitive information locally.

Second, the very good summary here is helped by the fact that much is already out there on the Internet about the Florida vote in the 2000 election. Your datasets and graphs probably do not have much, if any, coverage on the Internet. So don't expect as much for most day-to-day applications as you saw with the Florida 2000 election example.

[ref-gemini-nodate]: https://gemini.google.com/app