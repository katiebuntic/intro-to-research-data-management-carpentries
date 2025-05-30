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

### What is a variable?

A variable is a characteristic or attribute that can take on different values. In tabular data, variables are usually represented as columns, where each row contains an observation or entry.

However, the concept of a variable is independent of format, it’s not defined by being a column, but by being a consistent type of information collected across observations.

For example, in Alex's MET dataset, variables might include objectid, artistname, or dateacquired.

### Types of variables

#### Numeric variables

Variables that represent measurable quantities.

**Examples**:

- objectid → `12345` _(Integer)_
- heightcm → `23.5` _(Float)_
- objectdate → `1890` _(Integer)_

#### Text variables

Free-form or descriptive text.

**Examples**:

- artistdisplayname → `"Claude Monet"` _(String)_
- title → `"Woman with a Parasol"` _(String)_

#### Categorical variables

Variables that represent groups or categories.

**Examples**:

- gender → `"Female"`, `"Male"` _(String)_
- medium → `"Marble"`, `"Bronze"`, `"Oil on canvas"` _(String)_
- istimelinework → `"Yes"` / `"No"` _(String)_ _(or TRUE/FALSE — can be Boolean!)_

#### Date/time variables

Variables that represent dates or times.

**Examples**:

- lastconserv → `"2001-05-12"`
- objectdate → `1990`, `"ca. 1890"`

> ⚠️ Some columns might look like numbers but contain inconsistent formats (e.g., "ca. 1890"). These need cleaning before they can be analysed as dates.

### Types of data

#### Summary table

| Conceptual Type    | Technical Type | Description                  | Example                            |
| ------------------ | -------------- | ---------------------------- | ---------------------------------- |
| Nominal            | String         | Categories, no order         | `artistnationality = Australian`   |
| Ordinal            | String/Integer | Categories with order        | `artistgender = Female`            |
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

::::::::::::::::::::::::::::::::::::: challenge

## Challenge 1: Can you find any inconsistencies or problems with data entered into a spreadsheet?

A dataset called ####.csv is in the zip file. Please open the file in spreadhseet software (e.g. Google Spredsheets or Excel). Using a coloured fill identify any inconsistencies or problem data in the spreadsheet that you think might cause problems for anyone analysing the data.

:::::::::::::::::::::::: hint

Inconsistencies might include where measurements are in different units, there are differing formats for dates, differing cases, or where something is indicated ina variety of different ways but all mean the same thing

::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::
