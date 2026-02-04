---
title: "What is Research Data?"
teaching: 40
exercises: 20
---

:::::::::::::::::::::::::::::::::::::: questions

- What is research data, and why is it important in academic and scientific research?
- What are the different types of research data?
- Where can research data come from?
- What are the key components of research data management (RDM)?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Data types
- Sources of data
- What is research data management (collection, storage, organisation, sharing etc)

::::::::::::::::::::::::::::::::::::::::::::::::

## Understanding data types

Alex is a researcher studying artworks in The Metropolitan Museum of Art. They have just received a dataset containing information about paintings, sculptures, textiles, drawings, and photographs from across the museum’s collection. Before Alex can analyse anything, they need to understand what kinds of data the dataset contains.

Even though the dataset looks like a simple spreadsheet, each column has an underlying data type, and knowing these types will help Alex (and you!) avoid errors, clean the dataset effectively, and choose the right kinds of visualisations or analyses.

### What is a data type?

A data type describes the kind of information a value represents. It tells the computer how to interpret the data:

- Is it text?
- A number?
- A date?
- A true/false flag?

When a dataset mixes formats (e.g., a date stored as text, or a number stored as a string), analysis becomes harder and mistakes are more likely. Alex will soon discover that the MET dataset contains a mix of clean values and some messy ones - for example, dates written as 1990, "ca. 1931", and "07/06/2019 00:00". Understanding data types helps Alex make sense of this variation.

### Why data types matter

Data types are important because they affect how the computer reads, stores, and analyses information. If a column is stored in the wrong format, it can lead to errors, misleading results, or limitations in what you can do with the data. For example:

- Accurate analysis: If dates are stored as text, Alex won’t be able to sort artworks chronologically or calculate how old an object is.
- Avoiding mistakes: Numbers stored as strings (e.g., "1980" instead of 1980) may be ignored in calculations or treated incorrectly.
- Cleaning data effectively: Understanding data types helps Alex spot inconsistencies, such as mixing "ca. 1931" with 1931, so they know what needs fixing.
- Choosing the right visualisation: Charts depend on data types. A timeline needs dates; a bar chart grouping by artist needs clean text labels; averages require numeric data.
- Improving data quality: Identifying incorrect or mixed data types early helps Alex avoid downstream issues, especially when merging datasets or building models.

In summary: knowing data types helps ensure the dataset is trustworthy, analysable, and ready for exploration

### Common data types, examples from the MET Museum dataset

Here are some common data types you'll encounter:

- **String**: Text or characters, like `"Claude Monet"` or `"Oil on canvas"`
- **Integer**: Whole numbers, like `1985`, `42`, or `0`
- **Float**: Decimal numbers, like `27.5` or `3.14`
- **Boolean**: True/False values, like `TRUE`, `FALSE`, `Yes`, `No`
- **Datetime**: Calendar dates or timestamps, like `"2020-01-01"` or `"12/11/2027"`

Now that Alex has identified the main data types, let's try classifying some values ourselves.

::::::::::::::::::::::::::::::::::::: challenge

Challenge: What data type is it?

Alex found the following values in the MET dataset. For each one, decide what data type it currently is (it may not be what you think it should be!).

```
"Claude Monet"
1872
"ca. 1931"
"07/06/2019 00:00"
2021-07-14
27.5
"Oil on canvas"
TRUE
```

Write down the data type you would assign to each value.

:::::::::::::::::::::::: solution

```
"Claude Monet"           is a string
1872                     is an integer
"ca. 1931"               is a string (messy date)
"07/06/2019 00:00"       is a string (looks like a date but stored as text)
2021-07-14               is a date
27.5                     is a float
"Oil on canvas"          is a string
TRUE                     is a boolean
```

:::::::::::::::::::::::::::::::::
:::::::::::::::::::::::::::::::::

Notice how several values look like dates or numbers but are stored as text - this is common in real datasets and affects how we analyse them.

### Identifying data types in your own dataset

So far, Alex has been looking at individual values. In practice, researchers usually work with whole datasets at once, often in spreadsheets, CSV files, or databases. Let’s think about how to identify data types when your data is laid out in columns.

Imagine Alex opens the MET Museum dataset in a spreadsheet. Each column represents a variable, and each row represents an artwork. The column headers might look something like this:

| Object ID | Title             | Artist       | Object Date | Medium         | Is Public Domain | Height (cm) |
| --------- | ----------------- | ------------ | ----------- | -------------- | ---------------- | ----------- |
| 436121    | Water Lilies      | Claude Monet | 1906        | Oil on canvas  | TRUE             | 200.5       |
| 459055    | Untitled          | Unknown      | ca. 1931    | Gelatin silver | FALSE            | 27          |
| 12345     | Portrait of a Man | Rembrandt    | 07/06/2019  | Oil on panel   | TRUE             | 98.0        |

Even without doing any analysis, Alex can already start identifying data types by asking a few simple questions about each column.

#### Step 1: Look at the values, not just the column name

Column names are helpful, but they don’t always tell the full story. For each column, Alex checks:

- Are the values mostly text, numbers, dates, or true/false?
- Do all the values follow the same format?
- Are there any “odd” entries that don’t match the rest?

For example:

- **Artist**: text (string)
- **Height (cm)**: numeric (float), even though some values look like whole numbers
- **Is Public Domain**: boolean
- **Object Date**: mixed: some look like numbers, some like text, some like dates

Watch out for the last one!

#### Step 2: Watch out for mixed data types in a single column

One of the most common problems in spreadsheets is **mixing data types in the same column**. Alex notices that _Object Date_ contains:

- `1906` (looks like an integer)
- `ca. 1931` (text)
- `07/06/2019` (date-like text)

Even though these all describe dates, the computer will usually treat the entire column as **text**, which makes it hard to sort, filter, or calculate with.

#### Step 3: Use spreadsheet tools to check data types

Spreadsheets don’t just display data, they also interpret it. Most spreadsheet software gives visual and functional clues that indicate how values are stored, which can help you identify the underlying data type of a column.

#### Step 4: Ask “what should this data type be?”

A useful habit is to separate:

- what the data type **currently is**
- from what the data type **should ideally be**

For example:

- _Height (cm)_: should be numeric
- _Is Public Domain_: should be boolean
- _Object Date_: should be a date (even if that requires cleaning later)

Writing this down helps Alex plan their data cleaning and analysis steps.

#### Key takeaway

When working with your own dataset in a spreadsheet:

- Data types usually apply at the **column level**
- Mixed formats are common and normal
- Identifying data types early helps prevent errors later
- You don’t need to fix everything right away, just notice and document it

::::::::::::::::::::::::::::::::::::: challenge

### Challenge: What data type is this column?

Alex opens a _different_ part of the MET dataset containing information about exhibitions and acquisitions.

| Column name      | Example values                                         |
| ---------------- | ------------------------------------------------------ |
| Accession Number | 1975.1, 2003.45a, 1988.12                              |
| Department       | European Paintings, Asian Art, Modern and Contemporary |
| Acquisition Year | 1998, 2005, Unknown                                    |
| Credit Line      | Gift of John Smith, Purchase, Bequest                  |
| On Display       | Yes, No                                                |
| Gallery Number   | 802, 305, NA                                           |
| Last Updated     | 2022-11-03, 03/07/2021, 15 Aug 2020                    |

For **each column**:

1. Decide what the data type **currently is** in the spreadsheet.
2. Decide what the data type **should ideally be** for analysis.

Think about:

- Mixed formats and missing values
- Columns that look numeric but include text
- Dates written in different ways

You do not need to clean the data — just identify the data types.

:::::::::::::::::::::::: solution

### One possible solution

| Column name      | Current data type    | Ideal data type |
| ---------------- | -------------------- | --------------- |
| Accession Number | String               | String          |
| Department       | String               | String          |
| Acquisition Year | String (mixed)       | Integer or date |
| Credit Line      | String               | String          |
| On Display       | String               | Boolean         |
| Gallery Number   | String (mixed)       | Integer         |
| Last Updated     | String (mixed dates) | Date            |

**Notes:**

- _Accession Number_ looks numeric but contains letters and punctuation, so it must be text.
- _Acquisition Year_ mixes numbers with `"Unknown"`, forcing the column to be stored as text.
- _On Display_ represents a yes/no value but is stored as strings.
- _Gallery Number_ includes numeric values and missing data (`NA`), which often results in text storage.
- _Last Updated_ represents dates, but inconsistent formats prevent it from being treated as a date automatically.

:::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::

## Where research data comes from

Research data can originate from many different sources. Understanding where data comes from helps researchers assess its reliability, limitations, and appropriate uses.

### What is a data source?

A data source is the origin of the data - where it was collected, generated, or obtained. This could be a person, an instrument, a database, a sensor, or a computational process.

::::::::::::::::::::::::::::::::::::: challenge

### Quick check

Which of the following could be considered a data source?

- A spreadsheet downloaded from a website
- A survey respondent
- A microscope
- A computer model

**Answer:** All of them.

::::::::::::::::::::::::::::::::::::::::::::::::

### Primary data

Primary data is data collected directly by the researcher for a specific research question. This might include surveys, interviews, experiments, field observations, or measurements. Primary data offers high relevance but often requires more time and resources to collect.

::::::::::::::::::::::::::::::::::::: callout

### Reflect

Have you ever collected primary data?

- What made it valuable?
- What made it challenging?

::::::::::::::::::::::::::::::::::::::::::::::::

### Secondary data

Secondary data is data that was originally collected by someone else for a different purpose and reused in a new study. Examples include government statistics, museum collections, published datasets, or previously published research data. Secondary data saves time but may not perfectly match the research question.

### Generated or synthetic data

Generated or synthetic data is created through computational processes such as simulations, models, or algorithms. This includes data produced by climate models, agent-based simulations, or machine learning systems. Synthetic data is useful for testing hypotheses or protecting privacy, but depends heavily on the assumptions of the model.

### Sensor and observational data

Sensor and observational data is collected automatically or systematically through observation, often over time. Examples include environmental sensors, satellite imagery, traffic counters, or wildlife cameras. This data can be large and continuous, requiring careful storage and management.

### Data from instruments, tools, and experiments

This type of data is produced by scientific instruments, laboratory equipment, or specialised tools. Examples include microscope images, sequencing data, spectrometer readings, or experimental measurements. Instrument data often requires calibration, metadata, and specialised software to interpret.

::::::::::::::::::::::::::::::::::::: callout

### Metadata moment

Why might metadata (for example, calibration settings or units) be especially important for this kind of data?

::::::::::::::::::::::::::::::::::::::::::::::::

### Examples of data sources in different disciplines

Different fields rely on different data sources. For example, historians may use archival documents, social scientists may use surveys or census data, natural scientists may collect experimental measurements, and digital humanities researchers may work with digitised texts or images.

### Considering data quality and limitations

Every data source has limitations. Researchers should consider how the data was collected, potential biases, missing values, accuracy, and whether the data is appropriate for their research question. Understanding these limitations is essential for responsible analysis and interpretation.

::::::::::::::::::::::::::::::::::::: challenge

### Classify it

You download a CSV file of air pollution measurements collected by a government agency.

Is this:

- Primary data
- Secondary data

:::::::::::::::::::::::: solution

**Secondary data** because you didn’t collect it yourself.

::::::::::::::::::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge

### Challenge: What kind of data source is this?

Below are several research scenarios. For each one, decide **what type of data source** is being described.

You may find that more than one category could apply — choose the **best fit**.

1. A researcher records temperature and humidity every 10 minutes using a weather station on a university rooftop.

2. A PhD student analyses digitised letters from a national archive that were scanned and published online by another institution.

3. A social scientist designs and distributes a questionnaire to study students’ experiences of remote learning.

4. A computer scientist creates a simulated dataset to test how an algorithm behaves under different conditions.

5. A biologist collects gene expression data using a sequencing machine in a laboratory experiment.

:::::::::::::::::::::::: solution

### One possible solution

1. **Sensor and observational data**  
   (Data collected automatically and repeatedly over time.)

2. **Secondary data**  
   (Data reused from an existing collection created by others.)

3. **Primary data**  
   (Data collected directly by the researcher for a specific study.)

4. **Generated or synthetic data**  
   (Data created through simulation or computational processes.)

5. **Data from instruments, tools, and experiments**  
   (Data produced by specialised scientific equipment.)

:::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::

## Introduction to research data management

### What is Research Data Management (RDM)?

### Why RDM matters

### The research data lifecycle

### RDM in practice: Alex and the MET Dataset

:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: instructor

Inline instructor notes can help inform instructors of timing challenges
associated with the lessons. They appear in the "Instructor View"

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

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

::::::::::::::::::::::::::::::::::::: keypoints

- Use `.md` files for episodes when you want static content
- Use `.Rmd` files for episodes when you need to generate output
- Run `sandpaper::check_lesson()` to identify any issues with your lesson
- Run `sandpaper::build_lesson()` to preview your lesson locally

::::::::::::::::::::::::::::::::::::::::::::::::
