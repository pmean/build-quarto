---
title: Steps to insure digital accessibility
source: "New"
author: Steve Simon
date: "2026-05-08"
categories: 
- "*Blog post"
- Year 2026
- Writing research papers
output: html_document
page_update: no
---

Digital accessibility is becoming an increasing requirement for the work that both I and my students do. If you create written documents or video presentations, you need to take steps to insure that anyone who views these documents or presentations is able to use them.

<!---more--->

The information on digital accessibility that you can find on the web is quite daunting. In an effort to try to understand this, I have tried in my own work to think about two things: 

-   how to make written documents accessible for people with vision issues,
-   how to make video presentations accessible for people with hearing issues.

There are other considerations, but it helps at first to focus on these two settings. If you want to dig deeper into the types of people you need to be thinking about when you produce content on the web, review the [stories of nine users with diverse disabilities][ref-wai-nodate1] at the web accessibility initiative.

[ref-wai-nodate1]: https://www.w3.org/WAI/people-use-web/user-stories/

## Considerations for written documents

Making your written documents accessible to people with vision issues is difficult because there is a large amount of variation in the limitations that people have. 

### For people with minor limitations to their vision

Vision problems does not necessarily mean full blindness. You should try to accomodate people who have some vision but with limitations. For these people, two things can help.

#### High contrast

The default on the web is black text on a white background. You may, however, wish to use different colors for the text and/or the background. There are several reasons to do this, but if you go down this road, think about contrasts. Certain combinations of text and background colors are difficult to read. Even if they seem okay to you, they may provide problems with people with limited vision. The key general issue is that some colors, such as red and blue are dark. Some colors, yellow especially, are bright. Don't combine bright text with a bright background or dark text with a dark background. There are a [variety of ways to check for good contrast][ref-wai-nodate2].

[ref-wai-nodate2]: https://www.w3.org/WAI/test-evaluate/easy-checks/color-contrast/

#### Large zoom friendly fonts

Make sure that you use font sizes of 12 points or larger. This is especially true for documents where adjusting the font size by the end user is not easy, such as PDF files.

For documents where adjusting the font size is easy, try looking at your document at zoom levels of 200% or larger. Look for

-   awkward line breaks, 
-   text that extends beyond the screen, or 
-   text that that creeps on top of or behind images.

### For people with major vision limitations

People with serious vision limitations may need to use screen readers. These take the digital text in a written document and converts it into speech. Try to produce documents that work effectively with screen readers.

#### Document headings

Documents that are more than a few paragraphs long should include headings. Headings are often indicated by the use of bold text, centering, or larger fonts. These are fine, but formatted elements like this are lost when read out loud by a screen reader. You should use heading levels in addition to formatted elements.

The highest level heading, often just called h1, is needed at least once. This could be the title of the entire document. Or you could use h1 several times to indicate major sections of your document.

Parts of your document could then be separated into subheadings (h2), subsubheadings (h3), and so forth. You might use h2 for individual chapters and h3 for sections within a chapter. Please make sure that you document headings follow a logical order. No jumping, for example from h1 to h3.

People relying on screen readers do not have an easy way to jump past certain sections or navigate quickly around a large document. The use of headings also provides an organizational structure to your writing, which benefits anyone reading your document.

#### No bare links

Screen readers will read individual letters of anything that does not look like a simple word or number. So try to avoid citing lengthy urls (http://whatever) directly. Hide the url instead behind a descriptive link.

#### Images

#### Tables

## Considerations for video presentations

### Captions

### Transcripts

## Considerations for video presentations