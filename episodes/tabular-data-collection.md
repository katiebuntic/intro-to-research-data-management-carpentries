---
title: "Tabular Data Collection"
teaching: 30
exercises: 30
---

:::::::::::::::::::::::::::::::::::::: questions 

- Have a look at a really dirty data set
- Is there a standard set of responses?
- Is it freetext?
- How do you control what data is being collected?
- Asking the right questions
- Data dictionaries

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

After following this episode, learners will be able to:

- List variable types and formats
- Identify inconsistencies in data that can cause problems during analysis
- Describe methods that can be used during data collection and data entry that can prevent inconsistencies
- Write guidance for how to collect and enter data
- Create a data dictionary describing a dataset

::::::::::::::::::::::::::::::::::::::::::::::::


:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: instructor

Inline instructor notes can help inform instructors of timing challenges
associated with the lessons. They appear in the "Instructor View"

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge 

## Challenge 1: Can you find any inconsistencies or problems with data entered into a spreadsheet?

A dataset called Met_Objects_Dataset_sample.txt is in the zip file. Please open the file in whatever spreadsheet software you are using (e.g. OpenLibre, Excel). The file is tab delimited (i.e. within each row a gap is used to separate values into their columns) so you may need to use whatever Text to Columns tool your spreadsheet software provides to convert it into columnar data. The first row contains the column headers. Using a coloured fill identify any inconsistencies or problem data in the spreadsheet that you think might cause problems for anyone analysing the data.

:::::::::::::::::::::::: hint 

Inconsistencies might include where measurements are in different units, there are differing formats for dates, differing cases, or where something is indicated ina  variety of different ways but all mean the same thing

::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

## Figures

You can use standard markdown for static figures with the following syntax:

`![optional caption that appears below the figure](figure url){alt='alt text for
accessibility purposes'}`

![You belong in The Carpentries!](https://raw.githubusercontent.com/carpentries/logo/master/Badge_Carpentries.svg){alt='Blue Carpentries hex person logo with no text.'}

::::::::::::::::::::::::::::::::::::: callout

Callout sections can highlight information.

They are sometimes used to emphasise particularly important points
but are also used in some lessons to present "asides": 
content that is not central to the narrative of the lesson,
e.g. by providing the answer to a commonly-asked question.

::::::::::::::::::::::::::::::::::::::::::::::::


## Math

One of our episodes contains $\LaTeX$ equations when describing how to create
dynamic reports with {knitr}, so we now use mathjax to describe this:

`$\alpha = \dfrac{1}{(1 - \beta)^2}$` becomes: $\alpha = \dfrac{1}{(1 - \beta)^2}$

Cool, right?

::::::::::::::::::::::::::::::::::::: keypoints 

- Use `.md` files for episodes when you want static content
- Use `.Rmd` files for episodes when you need to generate output
- Run `sandpaper::check_lesson()` to identify any issues with your lesson
- Run `sandpaper::build_lesson()` to preview your lesson locally

::::::::::::::::::::::::::::::::::::::::::::::::
