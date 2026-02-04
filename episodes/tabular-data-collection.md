---
title: "Tabular Data Collection"
teaching: 30
exercises: 30
---

:::::::::::::::::::::::::::::::::::::: questions

- What types of variables are commonly found in tabular data?
- What kinds of data inconsistencies can affect the quality of a dataset?
- What are some common causes of inconsistent or messy data?
- What practices can help ensure clean, consistent data during collection and entry?
- Why is it important to provide clear instructions or rules when collecting data?
- What is a data dictionary, and why is it useful?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

After following this episode, learners will be able to:

- List variable types and formats
- Identify inconsistencies in data that can cause problems during analysis
- Describe methods that can be used during data collection and data entry that can prevent inconsistencies
- Write guidance for how to collect and enter data
- Create a data dictionary describing a dataset

::::::::::::::::::::::::::::::::::::::::::::::::

## Variables, data types and formats

Alex has received a dataset from the MET museum and needs to understand the types of variables before exploring or analysing it further.

::::::::::::::::::::::::::::::::::::: prereq

## Follow along: Open up the dataset

You should have downloaded a dataset called Met_Objects_Dataset_sample.txt as part of the [setup instructions](../learners/setup.md#data-sets). Please open this file in whatever spreadsheet software you are using (e.g. LibreOffice, Excel). The file is tab delimited (i.e. within each row a gap is used to separate values into their columns) so you may need to use whatever Text to Columns tool your spreadsheet software provides to convert it into columnar data. The first row contains the column headers.

::::::::::::::::::::::::::::::::::::::::::::::::

### What is a data point?

A data point is a single piece of information collected for one variable about one item.

In the MET museum dataset Alex is using, each row is an object (like a painting or sculpture), and each cell is a data point.

Alex’s dataset looks like a spreadsheet, but underneath, each column contains a specific **data type**, which we covered in section 1. Knowing these helps to avoid errors and choose the right tools for analysis.

### What is a variable?

A variable is a characteristic or attribute that can take on different values. In tabular data, variables are usually represented as columns, where each row contains an observation or entry.

However, the concept of a variable is independent of format, it’s not defined by being a column, but by being a consistent type of information collected across observations.

For example, in Alex's MET dataset, variables might include objectid, artistname, or dateacquired.

### Types of variables

#### Numeric variables

Variables that represent measurable quantities. These can be integers or floats. Numeric variables can be _Discrete_, which means they take on specific, separate values (often counts), or _Continuous_, which can take on any value within a range (often measurements).

**Examples**:

- `objectid` → `12345` _(integer, discrete — a unique ID number)_
- `heightcm` → `23.5` _(float, continuous — a measurement in centimeters)_
- `objectdate` → `1890` _(integer, discrete — a specific year)_

#### String variables

Free-form or descriptive text.

**Examples**:

- `artistdisplayname` → `"Claude Monet"` _(string)_
- `title` → `"Woman with a Parasol"` _(string)_

#### Categorical variables

Variables that represent groups or categories. These could be strings, integers, or floats - anything used to label a category!  
Categorical variables can be _Nominal_, which means there is no inherent order (e.g., `artistnationality`), or _Ordinal_, which means the categories follow a logical order (e.g., `popularity`).

**Examples**:

- `gender` → `"Female"`, `"Male"` _(string, nominal)_
- `medium` → `"Marble"`, `"Bronze"`, `"Oil on canvas"` _(string, nominal)_
- `istimelinework` → `"Yes"` / `"No"` _(string, nominal — or Boolean: `TRUE` / `FALSE`)_
- `artistdecade` → `1950`, `1960`, `1980` _(integer, ordinal — ordered decades)_

#### Date/time variables

Variables that represent dates or times.

**Examples**:

- `lastconserv` → `"2001-05-12"` _(datetime or string)_
- `objectdate` → `1990` _(integer)_, `"ca. 1890"` _(string)_

::::::::::::::::::::::callout

Note on overlapping types:

Some variables can belong to more than one category depending on their use and format. For example:

`objectdate = 1890` might be treated as a numeric variable (discrete integer) if used for sorting or calculations.

The same `objectdate` could also be considered a date/time variable if formatted as `"1890-01-01"` and used in time-based analyses.

`artistdecade = 1950` could be a categorical variable (ordinal) if grouped into decade-based categories for comparison.

It’s okay for a single value to have more than one interpretation - what matters is how it's used in context.

::::::::::::::::::::

::::::::::::::::::::::caution

⚠️ Some columns might look like numbers but contain inconsistent formats (e.g., "ca. 1890"). These need cleaning before they can be analysed as dates.

::::::::::::::::::::

#### Summary

Understanding the difference between conceptual types (how the data is used or interpreted) and technical types (how the data is stored or formatted) is key for working effectively with tabular data. For example, a column might be technically an integer but conceptually a category (like decades or survey scores).

| Conceptual Type    | Technical Type | Description                  | Example                            |
| ------------------ | -------------- | ---------------------------- | ---------------------------------- |
| Nominal            | String         | Categories, no order         | `artistnationality = Australian`   |
| Ordinal            | String         | Categories with order        | `popularity = high`                |
| Discrete Numeric   | Integer        | Countable numbers            | `objectid = 123456`                |
| Continuous Numeric | Integer, Float | Measurable, decimals allowed | `height = 27.5`                    |
| Boolean            | Boolean        | Yes/No, True/False           | `ishighlight = TRUE`               |
| Date/Time          | Datetime       | Dates or times               | `lastconserv = 12/11/2027`         |
| Textual            | String         | Free text                    | `artistdisplayname = Claude Monet` |
| Identifier         | Integer/String | Unique reference             | `objectnumber = 1982.456`          |

::::::::::::::::::::::::::::::::::::: callout

**Tip for learners (like Alex):**

Understanding both the _conceptual meaning_ and the _technical format_ of your data helps you clean it correctly, document it clearly, and analyse it without errors.

::::::::::::::::::::::::::::::::::::::::::::::::

## Identify inconsistencies in data

Before we can clean or analyse data, it's important to check for inconsistencies, values that don't follow a standard or expected format. These might include:

- Different spellings or formats for the same category
- Mixed use of upper/lower case
- Inconsistent date formats
- Unexpected blank or missing values
- Invalid or impossible values (e.g. negative heights, future birth dates)

These inconsistencies can lead to errors or misleading results if not corrected.

### Example: Inconsistencies in the `artistgender` column

Here’s an example of how the same concept ("artistgender") can be recorded in many different ways:

| objectid | artistgender |
| -------- | ------------ |
| 1001     | Female       |
| 1002     | female       |
| 1003     | F            |
| 1004     | Male         |
| 1005     | MALE         |
| 1006     | M            |
| 1007     | Unknown      |
| 1008     |              |

We can see:

- `"Female"`, `"female"`, and `"F"` all refer to the same category
- `"Male"`, `"MALE"`, and `"M"` are also equivalent
- `"Unknown"` and the blank entry might indicate missing or uncertain data

These differences need to be standardised before analysis — for example, converting all values to lowercase and replacing shorthand terms with full words.

::::::::::::::::::::::::::::::::::::: challenge

## Challenge 1: Can you find any inconsistencies or problems with data entered into a spreadsheet?

Let's have a deep dive into the Met_Objects_Dataset_sample.txt dataset. Using a coloured fill identify any inconsistencies or problem data in the spreadsheet that you think might cause problems for anyone analysing the data.

:::::::::::::::::::::::: hint

Inconsistencies might include where measurements are in different units, there are differing formats for dates, differing cases, or where something is indicated in a variety of different ways but all mean the same thing

::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

---

Next, we’ll look at how to avoid these kinds of issues from happening in the first place.

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
- 26.03.23 = day.month.year
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

## Write data collection guidelines

As we saw in the last section, there are many additional checks / rules we
could have added during data collection to make our dataset more consistent and 
easier to analyse. It's good practice to document these rules before data 
collection takes place so that it's clear to yourself, along with any 
collaborators and future users of your dataset, exactly how values were 
collected. This will also be invaluable when it's time to write the methods 
section of any papers or reports that use this data.

Make sure you include information about how to handle missing values. How will
these be represented in your table? It is also useful to explicitly state why a 
value may be missing (if possible). For example, in our dataset some objects are 
made by manufacturing companies like `United Merchants & Manufacturers` rather 
than an individual artist - in this case `artistgender` will be missing, as it 
doesn't apply in this scenario.

::::::::::::::::::::::::::::::::::::: challenge 

## Write data collection guidelines

Choose a variable from the dataset (e.g. `lastconserv`) and write some 
bullet-point guidelines for its collection. For example:

- Which values are valid for this variable?

- Which format should be used?

- Are any checks required against other variables in the table?

- If a value is missing, how should it be represented? E.g. NA, None, not applicable

::::::::::::::::::::::::::::::::::::::::::::::::

## Data Dictionaries

### What is a Data Dictionary?

A **data dictionary** is a table that describes the variables in your dataset. It provides key information such as:

- **Variable name** (column header)
- **Description** (what the variable represents)
- **Data type** (e.g., string, integer, boolean, datetime)
- **Possible values or format** (especially for categorical variables)
- **Units** (if relevant)

Data dictionaries help others (and future you!) understand and use your data consistently and correctly.

#### Example: Wildlife Observations Dataset

Here’s a sample data dictionary for a fictional dataset tracking wildlife sightings in a nature reserve:

| Variable Name      | Description                              | Data Type | Possible Values / Format       | Units |
| ------------------ | ---------------------------------------- | --------- | ------------------------------ | ----- |
| `sighting_id`      | Unique ID for each observation           | Integer   | 1, 2, 3, …                     | N/A   |
| `species_name`     | Name of the animal species observed      | String    | e.g., "Red Fox", "Barn Owl"    | N/A   |
| `count`            | Number of individuals seen               | Integer   | 0, 1, 2, …                     | Count |
| `observation_date` | Date the observation was recorded        | Datetime  | YYYY-MM-DD                     | N/A   |
| `location`         | Area of the park where sighting occurred | String    | "North Woods", "Wetland Trail" | N/A   |
| `is_endangered`    | Whether the species is endangered        | Boolean   | TRUE, FALSE                    | N/A   |

::::::::::::::::::::::::::::::::::::: challenge

## Challenge: Write a Data Dictionary for Alex

Alex is trying to make sense of the MET museum dataset. Help Alex out by creating a mini data dictionary!

1. Open the file `Met_Objects_Dataset_sample.txt`
2. Choose **three variables (columns)** from the dataset
3. For each one, write down:
   - The **variable name**
   - A **short description**
   - The **data type** (e.g., string, integer, date)
   - Any **possible values** or **units**, if relevant

Work in pairs or small groups and compare your answers.

::::::::::::::::::::::::::::::::::::: 

::::::::::::::::::::::::::::::::::::: keypoints 

- keypoint 1
- keypoint 2

::::::::::::::::::::::::::::::::::::::::::::::::
