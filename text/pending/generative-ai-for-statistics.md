---
title: "Uses of Generative AI in Statistics"
source: "New"
author: Steve Simon
date: 2025-02-07
categories: Blog post
tags:
- Generative AI
output: html_document
page_update: no
---

I have not been thrilled with all of the hype and hoopla about generative artifical intelligence (generative AI) that is in the press and everywhere. My thoughts about this are similar to those of Corey Mohler in [this particular comic strip][mohler-no-date]. Nevertheless, there are some useful applications of this technology and I need to learn how to use them. Here's a brief summary of what I (as a total beginner in this area) know.

<!---more--->

## What is Generative AI?

Generative AI is a form of Artificial Intelligence (AI) using machine learning models that are trained on massive amounts of text or image data. They allow the end user to create original text or image files that meet certain requirements. The files are original in the sense that they are a synthesis of a large number of existing files without being quite like any single one of those files.

Use of AI to create text and images has been around for quite a long time. The distinguishing feature of the recently developed Generative AI models is how realistic the results are. It is very difficult for you and I to distinguish the difference between text or image files created by other humans and text or image files created by Generative AI. It is difficult for computers as well. AI models have been developed to detect what files were created by Generative AI, but these AI models have not fared so well. It seems that computers have outsmarted themselves. This raises some difficult questions if you develop work through Generative AI and pass it off as your own work.

## Large Language Models, Deep Learning, and Neural Networks

You will often see these models described as Large Language Models with the acronym LLM. I like the term generative AI instead of LLM because of the applications to images, music, video, and other non-language output. But much of the output of generative AI models is language, so LLM is not such a bad choice.

Most of the generative AI models rely on a ariticial neural net (ANN) models or deep learning model. Although NN models were inspired by how the human brain works (hence the adjective neural), but the NN nets really are quite different from the gray stuff we have inside our skulls. See PYMNTS (2023) for a nice explanation of LLMs, ANNs, and may other generative AI acronyms.

PYMNTS. There Are a Lot of Generative AI Acronyms — Here’s What They All Mean. Blog post, 2023-10-17. Available in [html format][ref-pymnts-2023]

[ref-pymnts-2023]: https://www.pymnts.com/artificial-intelligence-2/2023/a-primer-on-generative-ais-alphabet-soup-of-acronyms/

## How do Generative AI models work for images

There are at least two approaches for generating images: diffusion and generative adversarial networks (University of Toronto, nodate).

With diffusion, you train a deep neural network to convert a group of images into static, or random featureless images. Then if you reverse the deep neural network and feed it other random featureless images, it will produce (if all works well) images that are similar to the group of images that was used to trained the deep neural network.

A generative adversarial network develops two deep neural nets, a generator and a discriminator. The generator develops images that it hopes are similar to real images. Then the real images and the generator images are fed into the discriminator, which tries to identify which images are real and which are not. Information that the discriminator uses to determine realness then helps the generator develop images that are harder to discern from real images. The discriminator then tries to develop a system that is better and still able to identify which images are real. This goes back and forth, but the generator eventually wins and is able to produce images that look so real that the discriminator can't tell the difference. 

Generating realistic looking images is not enough. You need to select images that are responsive to a text prompt. This requires developing an encoder. An encoder converts a text string into a numeric vector in such a way that a similar text strings produce vector that are close to one another. Where the text strings differ on a common factor, the vectors (hopefully) will reflect this in a consistent way. So the difference in vectors between "man" and "woman" will match the difference in vectors between "king" and "queen". The difference in vectors between "man" and "king" will match the difference in vectors between "woman" and "queen" but in a different way. Encoding attempts to assign meaning to words. The encodings are then matched with images so that a text prompt using the word "king" will produce image features associated with maleness and royalty.

A simple statistical exercise comparing words associated with "geek" or "nerd" (Settles 2013) produced a simple graph that could be thought of as a two dimensional encoding. The encodings used in Generative AI require hundreds if not thousands of dimensions.

Burr Settles. On “Geek” Versus “Nerd”. Slackpropogation blog, 2013-06-03. Available in [html format][settles-2013]. 

[settles-2013]: https://slackprop.wordpress.com/2013/06/03/on-geek-versus-nerd/

## How do Generative AI models work for text

Some of the concepts behind these text models have been around for a long time. Autocorrect looks at a word that is not in your dictionary and finds a word that is reasonably close. Autocomplete will look at string of letters that you type and try to predict the word that you might use. 

Generative AI models for text, also known as large language models, take this concept further by predicting words and phrases that fit well with the previous words and phrases. They rely on some of the same approaches described above for images.

## Generative AI models for programming

These models can also generate music and videos. More importantly from the perspective of Statistics, Generative AI models can produce computer programs. This was an unexpected benefit of these models. They were trained on vast amounts of information found on the Internet, and that included vast amounts of computer code. 

So when people asked programming questions, these Generative AI models could spit out some pretty good code.

Now there are Generative AI models that specialize in programming. They can produce programs based on text prompts that actually work well enough that some teachers are using them in their Statistics classes. I have not had much experience yet with this, but it appears to be a promising area.

## What are some of the concerns with this new technology?

First, I have to say that there are some serious ethical and legal problems with at least some of these Generative AI programs. I can't say it is true of all of them, but at least some of them represent a massive theft of intellectual property.

## Copyright concerns

Generative AI uses a neural network to produce a sequence of words in response to a user's prompt. This neural network (and just about any neural network) needs a large amount of data for training. This data comes from scraping the Internet. 

Fine. But much of the material on the Internet is copyrighted. Worse yet, the Internet includes many resources that themselves are thefts of intellectual property.

## A brief detour

I have to tell a silly story here. My website is in the public domain. I have to exclude direct quotes from other websites. Also, some of the images that I use from other websites are excluded. Now I don't mind if someone scrapes my Internet site and makes use of it. It may literally be an example of GIGO (Garbage In Garbage Out). 

I do try to respect other copyrights for example. This includes giving credit when required for open source images. Some of what I do probably falls under the fair use provisions of copyright law. Maybe it fits under the umbrella of non-profit education. I am hardly an expert here, but if anyone wrote to me and raised an issue about copyright, I would fix the problem immediately.

Back a few years, though, I used an open source attribution license. Go ahead and use my stuff, I said, as long as you give me credit. Most people did. I have a bad joke on my website titled "How many IRB members does it take to screw in a light bulb" that has been republished with attribution on several other web sites [here is one][grobman-no-date]. But one site, an IRB newsletter, took my joke and published it as if it was their own writing. Of all the people who should be respecting intellectual property, it should be a group dedicated to ethical conduct. But no!

Now I don't care. I find it more amusing than anything. But it illustrates a point. Just because you put your content up on the Internet does not mean that everyone else has the right to use that content without restriction.

3. Katie Hope Grobman. Psychology Humor about Ethics Boards. Copernican Revolution blog. Available in [html format][grobman-no-date].

[grobman-no-date]: https://copernicanrevolution.org/humor/irb-ethics-boards

## Creative Commons licenses

When you publish your work on the Internet, you have the option of using a Creative Commons open source license. This is a popular choice on the Internet. There are several license options. You can require that anyone using your content has to [cite the original source][cc-by-4.0]. You can require that they only use your content for [non-commercial purposes][cc-by-nc-4.0]. You can require that they use your content [only in an unmodified form][cc-by-nd-4.0] (no derivative works). 

Any one of these licenses could be seen as forbidding the use of your content in training a neural net. Well maybe not. 

## More restrictive copyrights

It's worse than this, though. There is lots of material on the Internet that is published with much more restrictive copyright provisions. Include phrases like "any use of this material without the express written consent of ... is prohibited." 

## Theft of already stolen materials

Even more of a problem is that there are many publishers on the Internet that are themselves great thieves of intellectual property. Can you re-use material that has already been stolen once? I hope not. See the Appel (2023), Levy (2024), and Metz (2024) references for overviews of some of the issues.

Gil Appel, Juliana Neelbauer and David A. Schweidel. Generative AI Has an Intellectual Property Problem. Harvard Business Review, 2023-04-07. Available in [html format][appel-2023].

Annelise Levy. Nvidia Illegally Scraped YouTube Videos for AI, Suit Says. Bloomberg Law, 2024-08-15. Available in [html format][levy-2024]

Cade Metz, Cecilia Kang, Sheera Frenkel, Stuart A. Thompson, Nico Grant. How Tech Giants Cut Corners to Harvest Data for A.I. The New York Times, 2024-04-06. Available in [html format][metz-2024].

[appel-2023]: https://hbr.org/2023/04/generative-ai-has-an-intellectual-property-problem
[levy-2024]: https://news.bloomberglaw.com/ip-law/nvidia-illegally-scrapped-youtube-videos-to-train-ai-suit-says
[metz-2024]: https://www.nytimes.com/2024/04/06/technology/tech-giants-harvest-data-artificial-intelligence.html

## Fair use and copyright law

Companies that are using open source and copyrighted material to train their models argue that their work falls under the fair use provisions of copyright law. The key word here is transformative. Here is a quote from [copyright.gov][ref-copyright-nodate].

[ref-copyright-nodate]: https://www.copyright.gov/fair-use/index.html

*"Transformative uses are those that add something new, with a further purpose or different character, and do not substitute for the original use of the work."*

Is a neural net transformative? I doubt it, but the issue is certainly open to debate. There is also a call to modify intellectual property laws to allow generative AI uses of copyrighted materials (Crouch 2025).

Dennis Crouch. Jack Dorsey and Elon Musk Call for Abolition of "All IP Law". Patentlyo blog, 2025-04-14. Available in [html format][crouch-2025]

[crouch-2025]: https://patentlyo.com/patent/2025/04/jack-dorsey-abolition.html

## Are you feeding the beast?

A common use of generative AI is to upload a lengthy document and ask for a brief summary. Look carefully at the license for your generative AI model because some models will take anything that is submitted by users and add it to the content it already has and build the newest model from it. You may not care what these models do with your data, but maybe you should. In particular, if you work with confidential information, such as medical records, you should insist on a closed loop AI model. In a closed loop model, anything that you feed into a generative AI model is kept locally and does not leave for Internet parts unknown.

## Style and manner

There's a second issue about intellectual theft beyond the theft of those developing the Generative AI models. You can use Generative AI to create original content, but in a style or manner that is so similar to the original writer or artist that it infringes on their intellectual property. 

This is a gray area in copyright law, and many experts say that this is not a violation of copyright, but I still think this should be a concern.

## Plagiarism concerns

Finally, you might find yourself accused of plagiarism if the content you get from a Generative AI program was crafted too closely to a single source. I am unaware of any examples where this has happened, but I would encourage anyone using content from a Generative AI program to run their results by a plagiarism detector before publishing it.

Peer-reviewed journals have concerns about the use of Generative AI both in the publications that they have submitted and in the peer reviews themselves.

## Hallucinations

You can conceive of these generative AI models as producing a sequence of words where each word in the sequence seems to be a likely choice given the previous words. This can lead to responses where one sentence ends up contradicting the previous sentence, where the sequence wanders off from the original request, or where the sequence states a fact that sounds bold and confident, but which is just plain wrong.

United States Artificial Intelligence Institute. Understanding AI Hallucinations: Exploring Causes and Preventive Solutions, 2024-10-12. Available in [html format][ref-usaii-2024].

[ref-usaii-2024]: https://www.usaii.org/ai-insights/understanding-ai-hallucinations-exploring-causes-and-preventive-solutions

## Reinforcing prejudices and stereotypes

## Resource usage

-   Power
-   GPUs

## Major AI companies

## OpenAI

Open AI was co-founded by by Sam Altman and Elon Musk in 2015. Sam Altman was briefly fired in November 2023 and then quickly reinstated. The primary product line for Open AI is ChatGPT, with the first version being released in December 2022.

## xAI

xAI was founded by Elon Musk, a co-founder of OpenAI. Musk split off from OpenAI in 2018 and had several very public spats with that company before and after starting up his new company. The primary product line of xAI is Grok with the first major release in November 2023.

## Anthropic

Anthropic is another company that sprang from the roots of OpenAI. It was founded in 2021 by former members of OpenAI, led by Daniela Amodei and Dario Amodei. Their primary product line is Claude, originally released in March 2023.

## Google

Google was originally founded as an Internet search engine in in 1998 by Larry Page and Sergey Brin. It has since branched out into many different areas. The company was restructured as Alphabet in 2015. The primary product line is Gemini, originally released in February 2023.

## I make a few feeble attempts to use generative AI

## A statistical query for Gemini

I sent the query "how do i select an appropriate sample size for a research study" to Gemini.

It gave a lengthy, but well organized response (link available soon). As I understand it, there is some variation in responses by this system if you word things slightly differently and maybe even if you use the exact same prompt.

## The bad

The recommendations left out any discussion of either effect sizes or the minimum clinically important difference. I'm not a big fan of effect sizes, by the way, but they are commonly cited in discussion of sample size justification. To no mention that and to not mention the MCID either is positively criminal. There is a brief mention of "the acceptable margin of error" tucked in under the third bullet, "Determine the Desired Level of Precision".

## The vague

The recommendations also did not discuss Type I or Type II error rates. Instead there was a brief mention of confidence levels, which are effectively equivalent to Type I error rates. The article does mention statistical power but does not define it. Here is the maddeningly vague and unhelpful response: "Statistical power: If you plan to conduct statistical tests, you need to ensure your sample size is large enough to achieve adequate statistical power."

## The good

The recommendations opened with very nice sections on defining your research objectives and identifying your target population. Notice the use of the word "your" which is a nice personal touch.

The recommendations also included advice that I and others might overlook at times. They warned about resource constraints, which can often place a firm ceiling on your sample size. It also suggested that you factor in the response rate in your sample size calculations.

And how could I not smile at their last major recommendation: "Consult with a Statistician". You don't always need a statistician, of course, but they recommend it if "you are unsure about any aspect of sample size determination".

The recommendations provided about a half dozen resources that they appear to have used in developing these recommendations. These are not the best resources, in my opinion, but they are still good.

## Comparison to Wikipedia page

It might be instructive to compare this response to the [advice given by Wikipedia][ref12] on sample size determination. The Wikipedia page does not appear to have any major omissions. It suffers, perhaps, with an excessively technical exposition and a focus on several narrow scenarios with limited applicability.

Wikipedia contributors. Sample size determination. Wikipedia, The Free Encyclopedia. 2025-02-07, Available in [html format][ref-wikipedia-2025].

[ref-wikipedia-2025]: https://en.wikipedia.org/wiki/Sample_size_determination

## My grade: B-

It is pretty amazing that Gemini was able to put something like this together at all. The writing was coherent, well-organized, and spoke directly to the reader. They completely missed an important issue and provided brief and vague comments on two other important issues.

Perhaps the response could be better if I had written a better question. Perhaps I should have followed up with additional questions. There is not enough time for me to explore this in much greater detail, though.

I think the response is slightly above average. I do prefer the Wikipedia page, but it is also not without faults. My own pages on sample size calculations are quite uneven, so maybe I shouldn't be so critical.

## Testing Gemini's capabilities to produce images

I tried a few times to produce images using Gemini that I might use in teaching. 

Here is the result using the prompt "draw an image of a right skewed histogram". This showed a reasonable histogram, but the title, the axis values and the axis labels are non-sensical. I suspect I could make this into a decent image with a few more specifics in my prompts. I'm not sure why Gemini decided to clip out the edges of the text in this plot.

![](http://www.pmean.com/new-images/25/generative-ai-01.png "Image produced by Gemini")

## A comparable search on Google Images

Well, yes, this is not bad, but how does it compare to a basic search on Google Images. I sent it a query "a right skewed histogram" and it found all sorts of good examples, even when I restricted the search to images licensed under Creative Commons licenses.

![](http://www.pmean.com/new-images/25/generative-ai-01a.png "Results from a Google Image search")

## Gemini tries and fails to draw boxplots

I also tried "draw a pair of boxplots where both show outliers". This did not produce anything close to what I wanted.

![](http://www.pmean.com/new-images/25/generative-ai-02.png "Image produced by Gemini")

## Gemini tries and fails to draw a QQ-plot

Finally, I tried "draw a qq-plot that shows evidence of normality". Again, this was not antwhere close to what I wanted. My guess is that there are many many histograms out there that helped to train Gemini, but more specialized plots like boxplots and qq-plots are not as abundant. That seems hard to fathom, but these generative AI models require massive amounts of data to do their work well. The lesson here, if I can draw one from a limited number of prompts to a single generative AI model. These models can do okay if they have a massive number of images, is that it does well at tasks that are profligate throughout their training data, but stumbles when you ask for something that is less common.

![](http://www.pmean.com/new-images/25/generative-ai-03.png "Image produced by Gemini")

## Gemini produces a nice image of a female statistician

I am not much for images that are tossed into a PowerPoint presentation to liven it up, but others more intelligent than I am do encourage the use of images instead of just text. So I tried a prompt "show a statistician hard at work" and when it produced a male image, I thought to try to be more inclusive with the prompt "show a female statistician hard at work". The result is actually not too bad. I do not know exactly what she is holding (a stylus, maybe?) but the desk and computer seem to fit the commonly held conceptions of how we do our work.

![](http://www.pmean.com/new-images/25/generative-ai-04.png "Image produced by Gemini")

## Testing Gemini's capabilities to write programs

"write an R program to read the file titanic.csv"

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

"write a SAS program to read the file titanic.csv"

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

"write a python program to read the file titanic.csv"

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

## References

2. Kunming Cheng, Zaijie Sun, Xiaojun Liu, Haiyang Wu and Cheng Li. Generative artificial intelligence is infiltrating peer review process. Crit Care 28, 149 (2024). doi: [10.1186/s13054-024-04933-z][cheng-2024]

6. McKinsey & Company. What is generative AI. 2024-04-02. Available in [html format][mckinsey-2024]

7. Corey Mohler. AI and the Meaning of Life. Existential Comics. No date. Available in [html format][mohler-no-date].

8. Riddhi Setty. AI Imitating Artist ‘Style' Drives Call to Rethink Copyright Law. Bloomberg Law, 2023-05-31. Available in [html format][setty-2023].

9. University of Toronto Libraries. How Generative AI models work - Artificial Intelligence for Image Research. Available in [html format][toronto-nodate].

[cc-by-4.0]: https://creativecommons.org/licenses/by/4.0/
[cc-by-nc-4.0]: https://creativecommons.org/licenses/by-nc/4.0/
[cc-by-nd-4.0]: https://creativecommons.org/licenses/by-nd/4.0/
[ref11]: https://library.umkc.edu/apply-ai-scholarly-works/

[cheng-2024]: https://doi.org/10.1186/s13054-024-04933-z
[mckinsey-2024]: https://www.mckinsey.com/featured-insights/mckinsey-explainers/what-is-generative-ai
[mohler-no-date]: https://existentialcomics.com/comic/557
[setty-2023]: https://news.bloomberglaw.com/ip-law/ai-imitating-artist-style-drives-call-to-rethink-copyright-law
[toronto-nodate]: https://guides.library.utoronto.ca/c.php?g=735513&p=5297039
