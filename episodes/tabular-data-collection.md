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


::::::::::::::::::::::::::::::::::::: challenge 

## Challenge 1: Can you find any inconsistencies or problems with data entered into a spreadsheet?

A dataset called ####.csv is in the zip file. Please open the file in spreadhseet software (e.g. Google Spredsheets or Excel). Using a coloured fill identify any inconsistencies or problem data in the spreadsheet that you think might cause problems for anyone analysing the data.

:::::::::::::::::::::::: hint 

Inconsistencies might include where measurements are in different units, there are differing formats for dates, differing cases, or where something is indicated ina  variety of different ways but all mean the same thing

::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

## Prevent inconsistencies during data collection

As we've seen so far, our dataset contains a number of inconsistencies that will 
complicate analysis. In an ideal world, we would have avoided introducing these 
errors while collecting the data. It's always simpler to avoid inconsistencies 
in the first place, rather than trying to fix them later!

How could we have adjusted our data collection to avoid this? Let's take the 
`lastconserv` column as an example, which represents the date when the object 
was last conserved. Here we see a large number of different date / time formats, 
including:

- 28/01/2025 = day / month / year
- 07/21/2023 = month / day / year
- 26.03.23 = day . month. year
- 07/06/2019 00:00 = day / month / year hour:minute

To avoid this, we could have enforced a specific date/time format during 
collection. For example, if we were using a form, we could have limited 
responses in this field to only accept dates as year-month-day, with no time 
entry allowed. 

There are also some incorrect dates in this column e.g. `30/2/2024` (30th 
February 2024). February only has 28 days, or 29 during a leap year, so this 
date is impossible. We could have avoided this by providing some kind of date 
validation in the form - e.g. using a calendar input that only contains real dates.

### Some general guidelines

- Avoid free text fields during data collection. This increases the risk of 
spelling mistakes, additional spaces etc., that will complicate the final analysis.

- If a column should only contain particular values, then enforce this! For 
example, you could use a drop-down menu with set options to choose from.

- Add validation to avoid 'impossible' values. For example, are values only 
valid within a certain range? Are negative values valid?

- Where multiple formats are possible (e.g. with dates / times), enforce a 
specific format.


::::::::::::::::::::::::::::::::::::: challenge 

## Challenge: Methods to prevent inconsistencies during data collection

In a small group, consider how you could prevent the other inconsistencies you 
identified in the dataset. What checks or rules could you introduce during data 
collection?

:::::::::::::::  solution

## Solution

There are many different solutions to these inconsistencies, but here are some 
examples:

- `istimelinework` could have used a drop down menu that enforced only two 
choices of `True` or `False`. 
- a check could have been added to enforce that `accessionyear` (the year the 
object entered the collection) is always after `objectdate` (the year the object 
was created).
- `artistnationality` could have used a drop-down menu containing set 
nationality options. This would have avoided inconsistencies like `France` 
vs `French`.


:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::



::::::::::::::::::::::::::::::::::::: keypoints 

- keypoint 1
- keypoint 2

::::::::::::::::::::::::::::::::::::::::::::::::
