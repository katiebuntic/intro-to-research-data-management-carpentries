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

### Common data types

Here are some common data types you'll encounter:

- **String**: Text or characters, like `"Claude Monet"` or `"Oil on canvas"`
- **Integer**: Whole numbers, like `1985`, `42`, or `0`
- **Float**: Decimal numbers, like `27.5` or `3.14`
- **Boolean**: True/False values, like `TRUE`, `FALSE`, `Yes`, `No`
- **Datetime**: Calendar dates or timestamps, like `"2020-01-01"` or `"12/11/2027"`

### Examples from the MET Museum dataset

### Identifying data types in your own dataset

## Where research data comes from 

### What is a data source?

### Primary data

### Secondary data

### Generated or synthetic data 

### Sensor and observational data

### Data from instruments, tools, and experiments

### Examples of data sources in different disciplines 

### Considering data quality and limitations 

## Introduction to research data management

### What is Research Data Management (RDM)?

### Why RDM matters

### The research data lifecycle 

### RDM in practice: Alex and the MET Dataset


:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: instructor

Inline instructor notes can help inform instructors of timing challenges
associated with the lessons. They appear in the "Instructor View"

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge 

## Challenge 1: Can you do it?

What is the output of this command?

```r
paste("This", "new", "lesson", "looks", "good")
```

:::::::::::::::::::::::: solution 

## Output
 
```output
[1] "This new lesson looks good"
```

:::::::::::::::::::::::::::::::::


## Challenge 2: how do you nest solutions within challenge blocks?

:::::::::::::::::::::::: solution 

You can add a line with at least three colons and a `solution` tag.

:::::::::::::::::::::::::::::::::
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


::::::::::::::::::::::::::::::::::::: keypoints 

- Use `.md` files for episodes when you want static content
- Use `.Rmd` files for episodes when you need to generate output
- Run `sandpaper::check_lesson()` to identify any issues with your lesson
- Run `sandpaper::build_lesson()` to preview your lesson locally

::::::::::::::::::::::::::::::::::::::::::::::::
