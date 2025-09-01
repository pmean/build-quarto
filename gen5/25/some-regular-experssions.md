---
title: Examples of some simple regular expressions
source: "New"
author: Steve Simon
date: 2025-08-31
categories: 
- "*Blog post"
- Data management
output: html_document
page_update: no
---

I wanted to use some regular expressions to do a word count for every files on my website. First, I had to remove anything that was not a word. The simplest way is to replace the regular expression `[^A-za-z]` with a blank, change multiple blanks to a single blank, and then split the file by the blank character.

Not quite, but close. I had to run a series of regular expressions to get an accurate word count. Here are some of the details, which I am sharing because it represents a helpful introduction on how to use regular expressions for a practical purpose.

<!---more--->

A regular expression is a string with special characters that allow you to hunt for individual pieces within a longer string. They are very useful when the individual pieces are not quite identical, but still follow a common pattern. The stringr library in R is one of many libraries that will use regular expressions to find these individual pieces. You can manipulate these pieces, change them to something else, or remove them entirely.

## Paste individual strings into a single very long string.

Let's assume that I already have the contents of a particular web page in a vector called file_text. For my application, I first needed to paste together multiple lines of a page into a single string.

```{}
	file_text |>
	  paste0(collapse=" ") |>
```

## Remove yaml header

Then I had to remove the yaml header which stars with a sequence of three dashes and ends with a sequence of three dashes. The `.*` says anything between the first set of three dashes and before the second set of three dashes. The `?` tells the computer to not use a "greedy" match but instead find the smallest section bounded by three dashes on either side.

```{}
    str_replace("---.*?---", " ") |>           # yaml fence
```

## Remove text inside square brackets

I also wanted to remove any thing between the square brackets, `[` and `]`. This, almost always, represented a special markdown code and not a word. The `.*` again says anything between the left square bracket and the right square bracket. The `?` again tells the computer to grab only the shortest string. One more complication. The square brackets (and several other symbols) carry special meaning in a regular expression. If you want to actually hunt for a square bracket, you have to precede it with an escape character. The escape character for regular expressions is a backslash, `\`. But the escape character for R is also a backslash. So if you are using regular expression inside of R, you have to make a double escape, `\\`.

```{}
    str_replace_all("\\[.*?\\]", " ") |>       # square bracketed text
```

## Remove websites

I also wanted to remove any web sites. All my websites start with `http://` and I needed to remove anything that follows, up to, but not including the first blank character. The code `\\S` (remember the double escape that you need when using regular expressions inside of R) says anything EXCEPT a white space character (blank, tab, or newline). The asterisk, `*`, tells your computer to find zero or more instances of a non-blank character. The plus sign, `+`, is similar, except that the plus sign tell your computer to find one or more instances. This is a subtle, but important difference. The regular expression `http://\\S*` will identify `http://` followed by a blank as a match but `http://\\S+` would not.

```{}
    str_replace_all("http://\\S*", " ") |>     # web links
```

## Remove numbers and symbols

The following code gets rid of any numbers or symbols. The `A-Z` matches any uppercase letter and the `a-z` matches any lowercase letter. The caret, `^`, tells your computer to invert things and to match anything that is NOT a letter. I had to add a dash, `-`, because I did not want a word like `non-standard` to be replaced with `non standard` as that would count any hyphenated word as two words.

```{}
    str_replace_all("[^A-Za-z-]", " ") |>      # non-letters
```

## Remove quote marks

No longer did I need to remove symbols and numbers with a series of regular expressions. I want, however, to show one special case that I used in my earlier code. It is tricky to use regular expressions to hunt for the double quote, `"` and the single quote, `'`. Notice below that I have to surround the double quote mark with a pair of single quotes. Using `"""` leads to unbalanced quote marks, almost always a recipe for disaster. Likewise a single quote always has to be surrounded by a pair of double quotes.

```{}
    str_replace_all('"', " ") |>             # double quotes
    str_replace_all("'", " ") |>             # single quotes
```

Sometimes you have a string with both single and double quotes, like the sentence `The word "don't" is a contraction.` The answer to this is the escape character, which has to be doubled when you are using regular expressions inside of R.

## Wrapping up

Wrapping up, you have to convert any multiple blanks to single blanks, split the string into individual pieces and then count the pieces. The `str_split` function produces a list, so you need to use the `unlist` function to turn it into a vector.

```{}
    str_replace_all("\\s+", " ") |>            # multiple whitespace
    str_split(" ") |>
    unlist()
```

There are a few minor details that I haven't talked about. I also need to mention that there are libraries in R that will do word counts for you. I needed to create my own function because of the special cases (the yaml header and web URLs). In any case, I hope this application of regular expressions to do a word count has been interesting.