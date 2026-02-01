---
title: Getting IRB approval for your research
author: Steve Simon
source: http://www.pmean.com/02/irb.html
date: 2002-10-09
categories:
- "*Blog post"
- Year 2002
- Incomplete page
- Ethics in research
output: html_document
page_update: no
---

Dear Professor Mean: 

*I am submitting a proposal to our Institutional Review Board (IRB). Is there anything you can do to help me get IRB approval?* 

Loyal Reader

Dear Reader:

<!---more--->

Why not bring a freshly baked batch of chocolate chip cookies to the IRB meeting? I'd be glad to sample the batch first to make sure it tastes okay.

![](http://www.pmean.com/new-images/02/irb3.gif "Image of two cookies")

## Disclaimer

In a perfect world, everyone would listen when Professor Mean talks and they would decide things exactly the way he would. Alas, it's not a perfect world. Your IRB almost certainly uses criteria that differ from the guidance I give below.

So don't try the PMSS defense: You should approve this protocol because Professor Mean Said So. Sadly, it does not work.

By the way, if you serve on an IRB, I'd love some feedback from you on how your IRB assesses scientific validity.

## Short answer

The IRB does look at a variety of issues, but the one with particular relevance to statistics is whether the study has scientific validity. It is unethical to expose research subjects to any risks, discomforts, or inconveniences if the study has dubious validity. The Declaration of Helsinki states

*Medical research involving human subjects should only be conducted if the importance of the objective outweighs the inherent risks and burdens to the subject.* www.wma.net/e/policy/17-c_e.html 

Justification for scientific validity also appears in the Nuremberg Code.

*The experiment should be such as to yield fruitful results for the good of society, unprocurable by other methods or means of study, and not random and unnecessary in nature.* ohsr.od.nih.gov/nuremberg.php3

Good statistical design can touch on several aspects of scientific validity:

-   Is your sample chosen appropriately?
-   Is your sample size large enough?
-   Are you measuring things well?
-   Do you have a good plan for analysis of the data?

Make sure that you provide enough documentation in your proposal to convince the IRB that the answer is YES! to all these questions.

## Is your sample chosen appropriately?

Who you choose to participate in your research study will say a lot about how easily you can generalize your results to the real world. No sample is perfect, and even just the process of asking for informed consent can hurt generalizability.

If you randomly select subjects and/or randomly assign them to treatment and control, that's good. But more important is the pool of subjects that you are drawing your sample from. Ideally, your pool of subjects should include the full spectrum of the rainbow. In practice, logistical constraints make this ideal impossible.

Watch out when you select subjects only when your research coordinator is on the clock, or only from a tertiary care center. These are examples, where you may not have much success in extrapolating your findings to a more general group of patients. You can't generalize to all fruit when your sample is restricted to apples.

![](http://www.pmean.com/new-images/02/irb4.gif "Image of a variety of different fruits")

Sometimes there are hidden restrictions on your sample. Some studies may implicitly exclude patients if they:

-   speak English poorly,
-   move around a lot, or
-   lack a primary care physician.

The logistics of your research and limitations on your time and trouble may also place restrictions on your sample by excluding patients who arrive on weekends and evenings.

Sometimes these restrictions are trivial and sometimes not. It's best to acknowledge these implicit restrictions and be honest about the extent to which they hurt your ability to generalize.

Also, you need to be very careful about selecting your control group. The control group needs to be identical to the treatment group, except for the therapy or exposure being studied. If the control group differs on other factors, especially factors that affect prognosis, then you have problems. You need to control for these other factors, through randomization, matching, or covariate adjustment.

## Is your sample size large enough?

The size of your sample plays a vital role in scientific validity. You can't ignore this issue. Every single research study, no matter what the type, should have an explicit justification of the sample size. Virtually every research area has identified and documented problems with inappropriate sample sizes. Failure to consider sample size represents one of the biggest problems with research today.

With a small sample size, you may not have enough precision to make any useful statements about your research data. This is a waste of research dollars, but it is also unethical. An inadequate sample size needlessly puts subjects at risk without any benefit  to society.

The opposite problem can also occur. Some research studies include too many research subjects, but this problem is rarer. Including too many research subjects is also a waste of research money and it is also unethical. You are exposing more patients to the risks, discomforts, and inconveniences of the research study than you need to make precise statements about your data.

![](http://www.pmean.com/new-images/02/irba.gif "Image of two normal curves separated by 0.2 standard deviations, a small effect size. Boxplots at the bottom of the picture show the same two distributions.")

The justification of your sample size could take the form of a power calculation, if you have a formal research hypothesis. If your study will produce some simple descriptive statistics, then you should show that the confidence limits about these statistics will be reasonably narrow. Even if your study has a non-quantitative objective, you should still justify your sample size, possibly using a non-quantitative criteria.

There are many complex formulas for determining sample size; here is some general advice.

First you need to think about the size of the difference you are trying to detect and compare that to the standard deviation of your outcome measurement. If you are trying to detect differences that are small relative to your standard deviation, then you need a very large sample size. Detecting a difference that is about one fifth of a standard deviation, for example, might require a sample size in the hundreds.

If you are trying to detect a difference that is very large relative to your standard deviation, then you can get by with a smaller sample size. Detecting a difference that is about the same size as a standard deviation would only require a few dozen subjects.

Be careful! You might be tempted to say that you are only looking for differences that are large relative to the standard deviation, but you may end up painting yourself into a corner. If you suspect that your control group is a full standard deviation or more away from the treatment group, then this difference is one that would be so large as to be visibly different.

![](http://www.pmean.com/new-images/02/irbb.gif "Image of two normal curves separated by 0.8 standard deviations, a large effect size. Boxplots at the bottom of the picture show the same two distributions.")

For example, Jacob Cohen points out that 13 year old girls and 18 year old girls differ in average height by about 0.8 standard deviations. He also mentions that the Ph.D. holders and college freshman differ in average IQ by about the same amount. Do you really believe that your study will show such a large difference?

Second, when you are counting events, discrete events like deaths, it is the number of these events, not the total number of subjects studied, that determines the precision of your results. When the events are very rare, this means that you have to sample a large number of patients in order to accumulate enough events.

As a very rough guide, you should strive for at least 25 to 50 events per group. If your event occurs only 1% of the time, that means that you might need as many as 5,000 patients per group. If an event occurs one fourth of the time, you might be able to get by with one or two hundred patients per group.

```{}
Event  Recommended
Rate   sample size

 25%       100 to    200
  5%       500 to  1,000
  1%     2,500 to  5,000
  0.2%  12,500 to 25,000
```

Finally, if the sample size you need is unattainable--you don't have the budget, perhaps, or the study would take too long--then consider redesigning your experiment. Find a way to reduce the variability of your outcome measure. A cross-over design, for example, will usually have much less variability because each patient serves as his/her own control. Sometimes intermediate measurements (often called surrogate measurements) will improve your sensitivity enough so you can attain a reasonable amount of precision with a limited sample size.

Sometimes research will have a qualitative rather than quantitative goal. We might be interested, for example, in the issues that children with sickle cell disease face, or teenagers reasons for starting to smoke cigarettes. For qualitative studies, there is no mathematical formula that you can apply to justify your sample size.

The sample size needs to be large enough to ensure a rich and complete set of responses. Look for a sample size large enough to ensure that both ends of the spectrum (and the middle) are represented. If the population you are studying is very homogenous, then as few as a dozen patients may be enough. You may also wish to depart from random sampling and use a purposive sample instead. You can also justify a small sample size if you use purposive sampling. A purposive sample deliberately looks for patients with certain characteristics and can ensure that you have included all relevant viewpoints and perspectives in your study.

Another way to assess the sample size is by saturation. Saturation occurs when the same themes get repeated over and over and no new ideas are generated.

## Are you measuring things well?

There are a lot of scientific issues that I can't answer here. Is arterial distensibility is a good marker of heart disease? What is the best way to determine gestational age? Should you measure blood pressure in the left arm or the right arm?

I can, however, ask some questions that will help you determine whether your measures are clinically relevant.

![](http://www.pmean.com/new-images/02/irb5.gif "Image of a heart and an electrocardiogram")

## Is your measure valid and reliable?

Every discipline has slightly different definitions and standards for validity and reliability. As ageneral rule, the issues of validity and reliability become most important when you are measuring something abstract, like stress, or something subjective, like quality of life.

The easiest way to ensure validity and reliability is to use measures that have already been established in the peer reviewed literature. You can also hedge your bets by including several measures of the same outcome.

If you have concerns about validity and reliability, you might reserve a fraction of your sample (from 5% to 20% is a good starting point) for more thorough analysis. These patients might receive additional tests to verify that your simple outcome measure actually works well. Or you might have these patients evaluated by two different people and measure the level of agreement.

Be cautious about sources of information that are known to be imperfect. For example, in a study of 295 deaths from child maltreatment, only half were identified as such on the death certificates. The gender of the child, whether the perpetrator was a parent, and whether the child died in a rural or urban county, had a differential impact on ascertainment.

## Do you define all your terms objectively?

Research must be repeatable, so you need to use terms that are defined well enough so that another expert could reproduce your work and come up with roughly comparable findings.

You need to provide operational definitions for any events that are subject to differing interpretations. For example, the Scottish Intercollegiate Guidelines Network defines life threatening asthma as:

"*Features of life threatening asthma include agitation, altered level of consciousness, fatigue, exhaustion, cyanosis, and bradycardia. Air entry is often greatly reduced, which may lead to a 'silent chest'. The peak flow, if recordable, is usually less than 33% of best or predicted.*"  www.sign.ac.uk/guidelines/fulltext/38/section2.html

Up to 1992, the National Center for Health Statistics defined current and former smokers by asking the following two questions:

-   "Have you ever smoked 100 cigarettes in your lifetime?"
-   "Do you smoke now?" www.cdc.gov/nchs/datawh/nchsdefs/currentsmoker.htm

The Social Security Administration defines blindness as:

"*when your vision cannot be corrected to better than 20/200 in your better eye, or if your visual field is 20 degrees or less, even with corrective lens. Many people who meet the legal definition of blindness still have some sight and may be able to read large print and get around without a cane or guide dog.*" www.rcep7.org/socialsecurity/faq/blind/default.html

## Is your outcome important to your patients?

Patients are usually interested in one of three things: morbidity (will I develop diabetes?), mortality (will I die?), or quality of life (will I be able to lift and carry a bag of groceries?). Ideally, you should try to measure one or more of these things directly. If you can't measure them directly, then does your indirect measurement (sometimes called a surrogate measurement) have a strong link with morbidity, mortality, or quality of life?

Also, are you focusing on a short term outcome because of your convenience, when your patients are most interested in long term outcomes? It is easy to get someone to quit smoking for a week, but it is much harder to get them to persist through a full year.

## Do you have a good plan for analysis of the data?

It is important to have a plan. If you don't tell the IRB what you expect to do with your data, they won't be able to decide if the goal of your research is worth the risks, discomforts, and inconveniences of the patients in the study.

This does not have to be very detailed. If all you want to do is a descriptive study where you estimate a few means and proportions, then that's all you need to say. A lot of very valuable research does nothing more than this. Here's an example:

*In this research study, we will study children with severe hearing loss  in order to estimate the proportion who lose a hearing aid, and the average expense associated with these losses.*

![](http://www.pmean.com/new-images/02/irb7.gif "Image of a man signing a contract"]

It's a myth that all research requires a hypothesis specified prior to the collection of the data.  Most (but not all) qualitative research lacks a formal hypothesis. A descriptive study like the one described above does not have a research hypothesis. Some other examples of research without a formal hypothesis include:

-   pilot testing of a questionnaire,
-   studies assessing validity or reliability, and
-   exploratory or hypothesis generating research.

You can sometimes artificially contrive a hypothesis in these situations, but it is usually better to explicitly state that you don't have a research hypothesis. Instead identify the alternative goal you are trying to achieve or the question you are trying to answer. For example;

*There is no research hypothesis for this pilot study. Our goal instead is to identify ambiguous language, missing categories, and other problems with the patient satisfaction questionnaire.*

If you are testing a hypothesis, you need to specify that hypothesis as well as how you will test that hypothesis. This may appear difficult to you, but if you don't muck this up too badly, the IRB will probably give you a pass. You need to show enough detail so you don't appear totally incompetent.

If your data analysis plan is bad, it can still be fixed after the data are collected. In contrast, if you have a lousy control group or your sample size is grossly inadequate, you need to do something before you start collecting data.

So don't worry about the details too much. If you specify a Mann-Whitney test and you really needed to use a Kruskal-Wallis test instead, the IRB will probably still approve your study contingent on fixing that detail. Still, there are some statistical details that you need to worry about.

-   If your data are paired or matched, you must use a statistical approach that acknowledges this.
-   If some of your outcome variables are categorical and some of them are continuous, you have to use a different statistical model for each of these data types.
-   If you plan to remove outliers or possibly stop your study early, you need to be explicit about the rules and conditions for these actions.

Specify what your alpha level is (usually 5%) and whether your hypothesis is one-sided or two-sided. A one-sided test looks at changes in a single direction. Changes in the opposite direction are considered either impossible or irrelevant. One-sided tests are often used when changes in the opposite direction would have the same implications as a null finding. For example, we might find that a new drug is equivalent to a placebo, or that it performs worse than a placebo. We would refuse to adopt the drug in either situation. So comparisons to a placebo are usually one-sided.

Contrast this with testing a standard drug to a new drug. If the new drug performs worse, we would never use it, but if it is equivalent, then we would use part of the time based on other factors like cost, convenience, and patient preference. Comparisons of two active drugs are usually two-sided. This might change, however, if the side effect profile of one drug is so harsh that you would only prescribe it when it is superior.

## Further reading

Assert: A standard for the review and monitoring of randomized clinical trials. Howard Mann. (Accessed on October 14, 2002). http://www.assert-statement.org/ Excerpt: "The ASSERT statement is the articulation of A Standard for the Scientific and Ethical Review of Trials. It proposes a structured approach whereby research ethics committees review proposals for, and monitor the conduct of, randomized controlled clinical trials. In order to ensure the ethical conduct of research involving human subjects, the ASSERT checklist comprises items that need to be addressed by investigators applying for approval to conduct a clinical trial. These items are chosen to enable fulfillment of certain universally applicable requirements for the ethical conduct of research: social and scientific value; scientific validity; fair subject selection; favorable risk-benefit ratio; and respect for potential and enrolled subjects."

Content and quality of 2000 controlled trials in schizophrenia over 50 years. Thornley B and Adams C. British Medical Journal 1998:317(7167);1181-1184. [Abstract] [Full text] [PDF]

Underascertainment of Child Maltreatment Fatalities by Death Certificates, 1990-1998. Crume TL, DiGuiseppi C, Byers T, Sirotnak AP and Garrett CJ. Pediatrics 2002:110(2);e18. [Abstract] [PDF]

## Very bad joke: How many IRB members does it take to screw in a light bulb?

![](http://www.pmean.com/00/Images/irb8.gif "Image of a lightbulb")

As documented in 45 CFR 46.107(a), this review board must consist of five (5) or more members, and at least one of these members must possess a background in Electrical Engineering. In addition, at least one of the members must come from a home without any electricity. Any member of the IRB who owns stock in an electrical utility or who regularly pays bills to an electrical utility should recuse themselves from participation in the review of this research.

If the bulb should burn too brightly, burn too dimly, or flicker, then an adverse event report should be sent to the IRB (21 CFR 312.32). If the light bulb is dropped, then a serious adverse event report should be sent to the FDA by telephone or by facsimile transmission no later than seven (7) calendar days after the sponsor's initial receipt of the information.

If this is a multi-center light bulb trial, then a data and safety monitoring board (DSMB) may be needed (NIH Policy for Data and Safety Monitoring, June 10, 1998, http://grants.nih.gov/grants/guide/notice-files/not98-084.html, accessed on October 9, 2002). The DSMB should review any adverse event reports and interim results. If the clinical equipoise of the light bulb is lost, then the DSMB should terminate the study and provide all previously recruited light bulbs with the best available light bulb socket.

In order to maintain scientific integrity, the use of a placebo socket may be necessary. The placebo socket should have the same taste, appearance, and smell of a regular socket and the fact that this socket has no electricity should be hidden from the light bulb and from the person screwing in the light bulb. According to the 2000 revision of the Declaration of Helsinki, paragraph 29, the use of placebo sockets is acceptable where no proven prophylactic, diagnostic, or therapeutic socket exists.

A systematic review of all previous research into light bulbs must be presented so that the IRB can determine, per 45 CFR 46.11(a)(2), that the risks to the light bulb are reasonable in relation to anticipated benefits. The IRB should also ensure that the selection of light bulbs is equitable (45 CFR 46.11(a)(3)). If the light bulb has less than 18 watts of power, then additional requirements (45 CFR 46.401 through 409) apply.

The IRB must ensure that an informed consent document be prepared in language that the light bulb understands (45 CFR 46.116). This document should explain the expected duration of the light bulb's participation in the research, any reasonably foreseeable risks, and the extent to which the confidentiality of the light bulb will be maintained. This document should also emphasize that participation is voluntary and the light bulb can withdraw itself from the socket at any time without any penalty or loss of benefits.

The clipart on this page was courtesy of the clipsahoy web site: http://www.clipsahoy.com/index2.html.

<!---More--->

Earlier versions are [here][sim1] and [here][sim2].

[sim1]: http://www.pmean.com/02/irb.html
[sim2]: http://new.pmean.com/getting-irb-approval/
