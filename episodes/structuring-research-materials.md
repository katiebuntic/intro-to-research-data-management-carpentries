---
title: "Structuring Research Materials"
teaching: 50
exercises: 10
---

:::::::::::::::::::::::::::::::::::::: questions 

- How can you structure data using a standard folder system for better organisation?
- What are the benefits of using a consistent file naming convention in research data management?
- Why is version control important, and how can it be incorporated into file naming practices?
- In what ways can version control tools like Git and GitHub be useful for managing data?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Organise their research data into a standard folder structure
- Name files with a consistent naming convention
- Understand why version control is important, and how to incorporate this into your naming conventions
- Explain why version control software such as Git/GitHub can be useful for certain types of data.

::::::::::::::::::::::::::::::::::::::::::::::::

## Folder systems

Alex has recently started a PhD on a project that has been running for a few years. He has been given access to the project's folders and has been asked by his supervisor to look through some files left by a researcher who recently left.

:::::::::::::::::::::::::::: challenge
### Organising files into a folder structure Part I

In groups, look through the folder of data that you have been given and discuss the following questions:

- What problems can you identify with how files are organised?
- How many different datasets can you identify?
- Which files are 'raw' vs 'processed' data?
- How would you improve the organisation of the files?


:::::::::::::::::::::::: hint

When thinking about how you could improve the organisation of the files, consider whether it might be easier to split them between different folders and whether any might need renaming

::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::

Alex goes to his supervisor and explains the problems he has found. His supervisor asks him to improve the organisation of the files as he is concerned that no-one will be able to find anything. 

:::::::::::::::::::::::::::: challenge
### Organising files into a folder structure Part II

Individually, look at the folder of files again and within it create a set of folders to organise each file into. You may want to create subfolders inside some of these folders too. Organise the files into your folders.

:::::::::::::::::::::::: hint

- Alex sees that during the project the researcher gave a presentation at a conference and that alongside the slides there are lots of documents relating to his attendance. Think about the different ways files related to the conference might be stored and consider which might be better for a team needing to share files, versus how an individual might be happy to store them.
- There are also various files related to a data analysis: can you see the different stages of that analysis process? How might you organise them?

::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::

Poor organisation can make it difficult to find files or to even see that a specific file exists.  This can become a massive problem where multiple people are working together or on projects that run over a number of years. Out-of-date versions of files may end up being used and shared, and important documents effectively lost. Relying on search tools to find documents assumes that you know that the document exists, and that you know how it was named; if you weren't the person who created it how would you know about it? If you think back to documents you created a few years ago, would you still be able to say what they were all called, what the latest versions were called, and what they all related to?

Taking a few moments to think about the structures you use to store files can save a lot of stress, and time, both for you and anyone you work with. If you work across multiple projects it can be worth coming up with a consistent approach, so that you and anyone you work with always knows where in the folder structure to find the same types of files. Structure folders heirarchically too: start broad and drill-down into specific areas.

It can be worth thinking of an old fashioned set of filing cabinets:
- each filing cabinet is a project
- each drawer is a an aspect of the project e.g. drawer 1 for data collection; drawer 2 for analysis; drawer 3 for papers and presentations
- within each drawer are folders containing files about specific subsections of that aspect e.g. in drawer 2 there are separate folders for code, raw data, cleaned data, graphs/ figures, and reports
- within each folder in each drawer there may be further sub-sections....

However, do be sensible about the level and number of folders you use: if you have lots of folders that only contain one file, you may have too many, making it more difficult and time-consuming to navigate. If you have very few folders then there may be too many files in a folder, making it difficult to find the relevant one.

Give each folder a name that is meaningful and concisely describes the contents of the folder, such as "raw_data", "conference_presentations", "expenses".

Whatever structures you choose, it is worth periodically reviewing it to make sure it is still fulfilling its purpose. Perhaps a section of the project folders can be archived? Perhaps there are now enough files of a particular type to necessitate a new folder?

In summary:

- Use folders! Don't just save files onto your desktop and expect to be able to find everything in future.
- Structure hierarchically. Start broad and drill-down into specific areas or projects
- Use a sensible number of folders. Too few or too many may both make it difficult or time-consuming to find files.
- Use sensible names. Consider project names and the types of files in each folder, such as "raw_data", "conference_presentations" or "expenses"
- Develop a consistent approach across projects
- Review folder content periodically, and consider moving folders and files that are no longer needed into an ‘archive’ folder

## File naming

Alex takes another look at the folder system he has created. The files are easier to search through but he notices that there are lots of inconsistencies in how they are named.

:::::::::::::::::::::::::::: discussion
### Naming Files Part I

Open the _______ folder and look at the names of the files. Can you identify any problems with the way the files are named? What kinds of issues might they cause for those working on the project?

::::::::::::::::::::::::::::

Poor file naming practices can make it difficult and time-consuming to find files, and lead to people working on the wrong files, or even overwriting important files, thus losing important data. Just as with folder structure, taking some time early in a project to develop a naming convention can save time and effort in the long run, both for your future self, and for any colleagues you work with. Below are some key considerations when creating file names:

### What information to include

Carefully consider what information someone would need about the file to know it is the one they want. Do they need to know when it was created? Do they need to know what type of data it contains, for example, raw data, clean data? Does the file relate to a specific ID number? Some of those items of information might be good candidates to form part of the file name.

### Whether you need to be able to order the files by a characteristic

For example, will you need to be able to easily select the file that was created most recently? Or quickly find a file by a sample ID? If so, you will want that element of the name to be at the beginning of the file name. Sometimes you might have to prioritise one of those requirements: for example, maybe you need to find the most recent file relating to a specific sample, in which case you might name the files using the format:

sampleID_date

### Special Characters and Spaces

Avoid using special characters (such as ?#!"£$%^&*{}@/|\<> ) as operating systems and apps may handle these very differently, sometimes being completely unable to open a file with them in their name, or not recognising them at all. Some special characters have a meaning in particular programming languages, and may be interpreted as instructions to the computer rather than as part of the file name. 

Similarly, spaces in file names can cause problems:

:::::::::::::::::::::::::::: challenge
### Naming Files Part II

Look at the file name below:

STAR final results.xls

How do you think this might be interpreted by a computer?
How might you rewrite the name to avoid that?


:::::::::::::::::::::::::::: solution

If you have spaces in a file name, the computer may interpret a space as showing that the end of the file name has been reached, and therefore not treat the rest of the name as part of the file name. Alternatively, it may interepret it as several file names listed one after the other e.g. STAR final results.xls is either:

1 file named STAR followed by the command 'final'...

3 files named:

- STAR
- final
- results.xls

A better way to write this file name would be STAR_final_results.xls or STAR-final-results.xls

::::::::::::::::::::::::::::

::::::::::::::::::::::::::::

Recommendation: Use only numbers and letters (without accents) and use hyphens and underscores instead of spaces, to separate the different parts of the file name.

### Dates

:::::::::::::::::::::::::::: challenge
### Naming Files Part III

Look at the file names below:

A) 01022026_sputum_culture_results.csv

B) 03_09_2025_sputum_culture_results.csv

C) 05Jun25_sputum_culture_results.csv

D) 120126_sputum_culture_results.csv

E) 12252026_sputum_culture_results.csv

What order were those files created in? Are you sure?

:::::::::::::: hint

If the files came from laboratories in both the UK and in the USA, would that raise any concerns about how to read the dates on the files?

::::::::::::::

::::::::::::::::::::::::::::

Dates are a frequent cause of issues for researchers. Researchers from different countries may read date numbers differently: "05062026" may be one person's 5th of June (e.g. in the UK), while for another it's 6th of May (e.g. in the USA). Ensuring that everyone looking at the date reads it correctly can be the difference between the correct file being selected, and the wrong one. 

:::::::::::::::::::::::::::::: challenge
### Naming Files Part IV

Look at those file names again:

A) 01022026_sputum_culture_results.csv

B) 03_09_2025_sputum_culture_results.csv

C) 05Jun25_sputum_culture_results.csv

D) 120126_sputum_culture_results.csv

E) 12252026_sputum_culture_results.csv

Note that they were given in the order they would appear in a folder, i.e. in numerical and alphabetical order.

Can you think of a better way to write the dates, so that the files appear in date order? 

::::::::::::::::::::::::::::::

A good format for dates is YYYYMMDD (the ISO 8601 standard), or YYYY-MM-DD. This format ensures that everything can be easily ordered by year, then month, and then day. Seeing the year at the start of the date also indicates to those looking at the files that the date is probably being handled in this way.

## Version control

Alex has now organised the folders and renamed many of the files. Things look much better, but as he works through the project, he notices something worrying.

For several documents, there are multiple slightly different versions of the same file, and it’s not always clear:

- Which one is the most recent

- What changed between versions

- Who made those changes, or why

Some files include 'final' in the name... sometimes more than once.

::::::::::::::: challenge

Versions Everywhere

Look at the files in the _______ folder.

- How many different versions of the same document can you find?

- How can you tell which one is the “latest”?

- Are you confident you’d pick the right file to work on?

- What might go wrong if different people used different versions?

::::::::::::::: hint

You don’t need to open the files to answer these questions.  
Focus on the *file names* themselves:

- Look for words like `final`, `draft`, `v1`, `v2`, or dates
- Notice whether the versioning scheme is consistent across files
- Ask yourself what assumptions you’re making when deciding which file is “latest”

Would someone new to the project make the same assumptions?

:::::::::::::::
:::::::::::::::

Version control is about tracking change over time, so that you can:

- See what changed

- Return to earlier versions if needed

- Understand how a file reached its current state

File naming conventions can help, but they are often not enough on their own.

## Version control tools


