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

:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: instructor

Inline instructor notes can help inform instructors of timing challenges
associated with the lessons. They appear in the "Instructor View"

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

## Variables and data types and formats

Alex has received a dataset from the MET museum and needs to understand the types of variables before exploring or analysing it further.

### What is a data point?

A data point is a single piece of information collected for one variable about one item.

In the MET museum dataset Alex is using, each row is an object (like a painting or sculpture), and each cell is a data point.

Alex’s dataset looks like a spreadsheet, but underneath, each column contains a specific **data type**. Knowing these helps avoid errors and choose the right tools for analysis.

#### Basic data types

Before we look at different types of variables, here are some common data types you'll encounter:

- **String**: Text or characters, like `"Claude Monet"` or `"Oil on canvas"`
- **Integer**: Whole numbers, like `1985`, `42`, or `0`
- **Float**: Decimal numbers, like `27.5` or `3.14`
- **Boolean**: True/False values, like `TRUE`, `FALSE`, `Yes`, `No`
- **Datetime**: Calendar dates or timestamps, like `"2020-01-01"` or `"12/11/2027"`

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

- artistdisplayname → `"Claude Monet"` _(string)_
- title → `"Woman with a Parasol"` _(string)_

#### Categorical variables

Variables that represent groups or categories. These could be strings, integers, or floats — anything used to label a category!  
Categorical variables can be _Nominal_, which means there is no inherent order (e.g., `artistnationality`), or _Ordinal_, which means the categories follow a logical order (e.g., `popularity`).

**Examples**:

- `gender` → `"Female"`, `"Male"` _(string, nominal)_
- `medium` → `"Marble"`, `"Bronze"`, `"Oil on canvas"` _(string, nominal)_
- `istimelinework` → `"Yes"` / `"No"` _(string, nominal — or Boolean: `TRUE` / `FALSE`)_
- `artistdecade` → `1950`, `1960`, `1980` _(integer, ordinal — ordered decades)_

#### Date/time variables

Variables that represent dates or times.

**Examples**:

- lastconserv → `"2001-05-12"` _(datetime or string)_
- objectdate → `1990` _(integer)_, `"ca. 1890"` _(string)_

> ⚠️ Some columns might look like numbers but contain inconsistent formats (e.g., "ca. 1890"). These need cleaning before they can be analysed as dates.

#### Summary

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

Before we can clean or analyze data, it's important to check for inconsistencies — values that don't follow a standard or expected format. These might include:

- Different spellings or formats for the same category
- Mixed use of upper/lower case
- Inconsistent date formats
- Unexpected blank or missing values
- Invalid or impossible values (e.g. negative heights, future birth dates)

These inconsistencies can lead to errors or misleading results if not corrected.

### Example: Inconsistencies in the `gender` column

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

---

Next, we’ll look at how to avoid these kinds of issues from happening in the first place.

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

::::::::::::::::::::::::::::::::::::: challenge

## Challenge 1: Can you find any inconsistencies or problems with data entered into a spreadsheet?

A dataset called ####.csv is in the zip file. Please open the file in spreadhseet software (e.g. Google Spredsheets or Excel). Using a coloured fill identify any inconsistencies or problem data in the spreadsheet that you think might cause problems for anyone analysing the data.

:::::::::::::::::::::::: hint

Inconsistencies might include where measurements are in different units, there are differing formats for dates, differing cases, or where something is indicated ina variety of different ways but all mean the same thing

::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::
