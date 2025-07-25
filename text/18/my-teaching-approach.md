---
title: "My teaching approach"
author: "Steve Simon"
source: "http://blog.pmean.com/my-teaching-approach/"
date: "2018-04-02"
categories:
- "*Blog post"
- 2018
- Professional details
output: html_document
page_update: partial
---

I am applying for a variety of jobs and some of the universities that I
am applying to want to know my approach to teaching. It's an interesting
thing to write about, because most of my teaching experience is in a
non-traditional format. Here's what I wrote for one job I applied
for.

<!---More--->

I have taught in a wide range of non-traditional formats: short courses
at regional, national, and international conferences, and webinars for a
geographically diverse audience. Students in these classes have a choice
and will not tolerate a poorly taught class. I take it as validation of
my teaching quality that I have been re-invited over and over again to
give talks by the same organizations (American Society of Andrology, The
Analysis Factor, International Research Conference on Complementary
Medicine, Medical Library Association, Midwest Society of Pediatric
Research).

I don't have (and don't believe in) an overarching philosophy of
teaching. Good teaching comes from the little things, and I attribute my
teaching success to three little things: finding compelling examples,
using humor to make a point, and spending a large portion of my limited
teaching time on small group exercises. I also want to mention some of
the special challenges that I have faced with teaching in an online
(webinar) format.

## Compelling teaching examples

It takes a lot of time to find compelling teaching examples. They need
to be vivid and memorable. They need to reflect the practice of
statistics in the real world, but at the same time they need to avoid
obscure details that only specialists in an area can follow.

In a book chapter that I wrote for Big Data Analysis for Bioinformatics
and Biomedical Discoveries, I was faced with a challenge to find a
compelling data set to illustrate the R programming language in action.
Most data sets used in Bioinformatics, however, are narrowly focused and
require a fairly specialized knowledge to fully comprehend. I chose a
data set that had broader appeal and which was easily followed by anyone
with a reasonable medical background, Son et al. Database of mRNA gene
expression profiles of multiple human organs, Genome Res 2005.
15:443-450. This study took tissue samples from 19 different organs of
30 people (158 samples total) and fed them to a DNA microarray. This
provided expression levels of almost 19 thousand genes. This made the
data set large enough to qualify for a big data analysis. More
importantly, the comparison was concrete and easy to discuss. How does
gene expression differ in the heart versus the liver, or in the pancreas
versus the spleen? Also important to me was that the data used in Son et
al was freely available for download at the journal's website.

Another compelling data set is mortality on the Titanic, a large ocean
liner that in 1912 struck an iceberg and sunk. One of the first things
you might do with this data set is to calculate a two by two table of
gender versus survival. The Titanic sunk during an era where society
really did believe in the mantra "women and children first" though
perhaps more so among first and second class passengers. The
crosstabulation of gender and survival would look something like this.

"`{r titanic, echo=FALSE}
d <- list(c("Female", "Male"), c("No", "Yes"))
ti <- matrix(c(154, 709, 308, 142), 2, 2, dimnames=d)
print(ti)
"`

You can bring these numbers to life by pointing out that Kate Winslet
was in the upper right corner of the 308 women who survived and that
Leonardo DiCaprio, sadly, was in the lower left corner of the 709 men
who died. The data set has an interesting feature: the relative risk of
death is 2.5 times higher for males than females, but the odds ratio is
much higher, almost 10. It also allows you to study a rather complex
interaction of gender and passenger class. I've used the Titanic data
set in a tutorial article about measures of risk (Simon SD.
Understanding the odds ratio and relative risk. J Androl. 2001.
22(4):533-6), in a short course on logistic regression, and for some of
the homework assignments in the Introduction to R, Introduction to SAS,
and Introduction to SPSS classes. I take as validation of this approach
the fact that other groups (most notably Kaggle) have also adopted the
Titanic as an instructional data set.

Compelling examples are not limited to data sets. In my book,
Statistical Evidence in Medical Trials, I talk about blinding with
specific attention to blinding in surgical trials. Surgery is easily
understood: you cut someone open, take something out, and sew them back
up again. But it requires special challenges to ensure blinding, such as
the use of extra large bandages to cover up the size of the incision. I
make special reference to a study of Parkinson's Disease where fetal
cells were injected directly into the brain. The study had a control
group, and in order to maintain the blind, the control patients also had
their heads shaved, were put under an anesthetic, and the surgeons
actually drilled into their skulls. The only difference was that nothing
was injected after drilling if you were in the control group. Needless
to say, this was a highly controversial study with one ethical expert
writing a critical article with the title "I Need a Placebo Like I Need
a Hole in the Head." The gruesome thought of skull drilling makes this
example memorable.

There is no more compelling example relating to research methodology
than the efforts to find a treatment for AIDS. Controversies surrounding
AIDS research has changed the way we approach research today. When I
lecture about surrogate outcomes, it is easy enough to come up with
examples where reliance on surrogate outcomes has led us astray. The
classic example is the CAST trial which showed that the use of
anti-arrythmic drugs in patients with heart rhythm problems actually led
to an increase in mortality versus placebo. It is harder to find
examples where reliance on surrogate outcomes has helped us. AIDS
trials, however, do clearly illustrate the value of surrogate outcomes.
In the first studies of anti-retroviral treatments for AIDS patients,
scientists originally advocated the use of "hard" endpoints like
mortality and opportunistic infections. But AIDS advocates pushed for
surrogate outcomes like changes in CD4 cell counts because hard
endpoints took too long and required waiting until you had accumulated a
sufficient number of bad events in the untreated group. It is clear that
reliance on surrogate outcomes reduced the number of deaths in the
clinical trial itself and allowed much earlier FDA approval of these
treatments.

## Using humor to make a point

My audiences are often apprehensive. Will this guy speak a lot of Greek
and formulas to me? A bit of humor very early in the talk will often
allay some of those fears. I try hard, however, to use humor as well to
make a point. Humor comes from an exaggeration of a basic idea to levels
of absurdity, which you can use profitably to emphasize your basic idea
later in your talk.

In a lecture on sample size justification for a short course on grant
writing, I started with a (fictional) story of a researcher who gets a
six year, ten million dollar NIH grant and writes up a report
summarizing the research saying "This is a new and innovative surgical
approach and we are 95% confident that the cure rate is somewhere
between 3% and 98%." This becomes a repeated touchstone for the rest of
the talk. The agency that you are seeking to get grant money from wants
some assurance that the results will be informative when you finish your
work, and not a confidence interval that goes from 3% to 98%.

The previous joke is an original of mine, but I'm not above stealing
other people's jokes. There is a classic about two statisticians
travelling on an airplane and one engine after another explodes. After
each explosion, the pilot announces that everything is okay, but the
flight is delayed further and further after each explosion. After the
third explosion, one statistician turns to the other and say "Boy I hope
that last engine doesn't explode" [dramatic pause] "or we'll be up
here forever!". I use this joke when I teach linear regression, because
it illustrates a dangerous extrapolation beyond the range of observed
data. Later, I introduce the intercept term and offer an interpretation
(the estimated average value of Y when X equals zero). Then I point out
that such an interpretation is a dangerous extrapolation when you have
no data near the value X=0. In fact,the estimated travel time of a jet
with X=0 engines is also an intercept term requiring the exact type of
dangerous extrapolation.

I also use humor to assess my audience as well. At the very start, I'll
tell a corny joke about degrees of freedom (a joke so bad that I won't
repeat it here). I look at who laughs and who doesn't. When most of my
audience laughs, I compliment them by telling them that if you
understood that joke, you won't have any problems with the rest of my
lecture. When most of my audience is quiet, I tell them that they are
going to learn a lot today (and I teach things a bit more slowly).

Humor can be overdone, and students are not listening to you for
entertainment. I try to keep my jokes short and get them out of the way
early. But a little bit of humor does seem to help a lot.

## Spending time on small group exercises

I hate to do small group exercises. I really hate them. When you are
giving a short course at a research conference, you have a limited time
frame, usually three to four hours. Small group exercises can easily eat
up a third to a half of that time. I'd much rather be talking because
there's so much to teach and so little time. Even so, I include small
group exercises in almost all my short courses. The feedback I have
gotten from students has been that the small group exercises are the
best part of the class.

Constructing a small group exercise is not easy. You have to find a
problem that students can tackle, so it can't be too hard, but it has to
be challenging enough to force them to use some of the things they have
just learned. It has to be something that everyone in the group feels
that they can contribute. And it has to be something that each small
group can summarize to the entire class in five minutes or less.

The reason that small group exercises work is that students have a
variety of different experiences and can learn from each other. The more
experienced students benefit because they have to understand the
concepts at a higher level in order to articulate these concepts to the
rest of the group. The less experienced students benefit because they
get a chance to hear about the same concepts a second time and from a
different perspective.

In the short course on grant writing, we gave each group a different
research paper (actually, just the abstract from the paper) and asked
them to suggest a new study with a different research design that builds
on the paper's findings and that an agency might want to fund. Showing
just the abstract is a big no-no in Evidence Based Medicine, but we
apologized and explained that if we handed them a full paper they would
run out of time before they even finished the research paper. Each group
then appointed a spokesperson to summarize the original paper (just the
PICO: Patient group, Intervention, Comparison group, and Outcome
measure) and then propose their new research design. Once the
spokesperson was done, we asked if anyone else in the small group wanted
to add anything and opened it up for comments and questions by the other
students. Getting our students to visualize a new research study was one
of the big successes of our short course.

In a short course on setting up an independent statistical consulting
practice, I was actually able to get two small group exercises squeezed
into a four hour format. The first exercise was pairing up students and
asking them to share with their partner where they hoped to be five
years from now. This served as an ice breaker and got students to think
about what a career as a consultant might mean for them. The second
small group exercise took some fictional accounts (loosely based on
reality) of bad client interactions. The groups had to decide on the
best course of action, and this quite honestly might involve just
walking away from the project completely, an option that is always
available to an independent consultant. The short time frame did not
allow each group to summarize their findings to the rest of the class,
but the students still found the small group exercises to be valuable.

In a short course, Statistics for Medical Librarians, that I have taught
in an online format and at multiple regional and national meetings of
the Medical Library Association, I used small group exercises to dissect
statistics found in actual peer-reviewed publications. I teach concepts
like confidence intervals, provide a non-technical interpretation, and
then ask students to do the same in small groups. I show them actual
papers (actually abstracts again to save time) that show how a
confidence interval might look "in the wild." Then each group has to
summarize the abstract using a PICO format and then interpret the
highlighted confidence interval in that abstract. All of the abstracts
that I choose are from Open Source journals so the librarians can track
down the full articles after the class ends, if they are so inclined.

## Online teaching

I wanted to mention a bit about the special challenges associated with
online teaching, because I see a transition to online teaching almost
everywhere I look. I have done webinars, a form of online training, for
several several organizations. I've learned a lot from these webinars,
though they are not the same as teaching a semester long class in an
online format.

One lesson I have learned is that you have to work much much harder at
establishing a rapport with your students. In every webinar I have
taught, I do not have the option of requiring the students to make
themselves visible on a webcam, and only in a few did I have the option
of having students ask questions orally rather than through a chat box.
This makes the webinars less fun, quite frankly, than a short course
taught to a live audience. But I have embraced the webinar format
because it allows the participation of a large number of students who
are otherwise geographically isolated.

To make up for not seeing and often not hearing the students, I try to
make myself seen--using my own webcam when possible. I also take extra
time to more directly encourage student participation. It starts with a
joke. I introduce the joke with an exhortation. It is difficult, I point
out, to say something funny and then hear total silence on the other
end, so I after I tell this joke, I want you to type something in the
chat box. A "haha" if you liked the joke or a "groan" if you hated it.
Then I read the chorus of responses after the joke. It reinforces the
connection between me and my audience and it lowers the barrier for
students to use the chat box later for more serious comments.

When you ask for questions during a webinar, you need to wait long
enough for people to type their questions. And you need to follow up
your answer with another exhortation "Did that make sense" because you
don't get the feedback from the knowing nods or the glazed eye
confusion.

A webinar format demands a good Powerpoint presentation. I do not always
use Powerpoint for live talks and short courses and subscribe to the
admonition of many that "Powerpoint is Evil." For a webinar, however, if
you don't give students a Powerpoint slide to look at, it makes it that
much harder to keep a student's attention.

I've taught two traditional courses (Introduction to R and Introduction
to SPSS) in an online format. These are in an asynchronous format.
Students listen to mp4 files where you lecture and show Powerpoint
slides and live screen shots of R and SPSS as those programs grind
through their computations. The one issue I've noticed with the
asynchronous format is that if one student asks a question, the other
students would not normally get to benefit from hearing that question
and hearing my response. They also lose out on the opportunity to add
something to my answer if they can. So it is very important to share
questions and answers that otherwise would only come to you privately
via email.

Neither Introduction to R nor Introduction to SPSS lends itself well to
small group exercises, but I do recognize by watching others at my
current job that small group exercises take a much different form in an
online format. In particular, they require much more written
communication than oral communication, and the effort, especially for an
asynchronous format, is spread out over a longer time frame. This can
actually be an advantage because you need to explain yourself more
clearly in a written format and the slower pace encourages more thought
as well.

No doubt that I will encounter other issues as I teach more classes in
an online format. I learned a lot about online teaching at various talks
at the Joint Statistical Meetings, and plan to keep my eyes and ears
open for other people's experiences.


