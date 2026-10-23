---
title: Metadata
teaching: 15
exercises: 15
---

::::::::::::::::::::::::::::::::::::::: objectives

- Describe the importance of metadata
- Identify metadata that should be included with a dataset

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- What is metadata?
- How does metadata help future me and others to understand my data?

::::::::::::::::::::::::::::::::::::::::::::::::::

> This text on metadata was adapted from the online course [MANTRA - Research Data Management Training](https://mantra.ed.ac.uk/) by Research Data Service and the Institute for Academic Development, University of Edinburgh. MANTRA is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).)

## Importance

Recording data about your data ("metadata") is essential.
You may be on intimate terms with your dataset while you are collecting and analyzing it, but the chances that you will still remember the exact wording of the question you asked about your informants' water use (the data recorded in the column `water use`), for example, are slim.

As well, there are many reasons other people may want to examine or use your data - to understand your findings, to verify your findings, to review your submitted publication, to replicate your results, to design a similar study, or even to archive your data for access and re-use by others.

While digital data by definition are machine-readable, understanding their meaning is a job for human beings.
The importance of documenting your data during the collection and analysis phase of your research cannot be overestimated, especially if your research is going to be part of the scholarly record.

## Storing

Metadata should not be contained in the data file itself.
Unlike a table in a paper or a supplemental file, metadata (in the form of legends) should not be included in a data file since this information is not data, and including it can disrupt how computer programs interpret your data file.

Rather, metadata should be stored as a separate file in the same directory as your data file, preferably in plain text format with a name that clearly associates it with your data file.
However, out in the wild, you can find metadata in multiple file formats, from human but not machine-readable (such as PDF), to both human and machine-readable (XML or JSON).
Because metadata files are free text format, they also allow you to encode comments, units, information about how null values are encoded, etc. that are important to document but can disrupt the formatting of your data file.

Some of this information may be familiar to learners who conduct analyses on survey data that come with *codebooks*.
Codebooks will often describe the way a variable has been constructed, what prompt was associated with
it in a survey or interview, and what the meaning of various values are.
For example, the [General Social Survey](https://gss.norc.org) maintains their entire codebook online.
Looking at an entry for a particular variable, such as [the variable `SEX`](https://gssdataexplorer.norc.org/variables/81/vshow), provides valuable information about what survey waves the variable covers, and the meaning of particular values.

Additionally, file or database level metadata describes how files that make up the dataset relate to each other, what format they are in, and whether they supersede or are superseded by previous files.
A folder-level readme.txt file is the classic way of accounting for all the files and folders in a project.

## Standards

Metadata are most useful when they follow a standard.
For example, the [Data Documentation Initiative (DDI)](https://www.ddialliance.org) provides a standardized way to document metadata at various points in the research cycle.

This standard is applicable across disciplines, as it applies to a range of methods (from surveys to observational research) commonly used in the social, behavioral, economic, and health sciences.


Research librarians may have specific expertise in this area, and can be helpful resources for thinking about ways to purposefully document metadata as part of your research.

::::::::::::::::::::::::::::::::::::: instructor
For the next exercise, learners will open a CSV file. 
Instructions on how to load the file correctly (ensuring the delimiter is  interpreted properly regardless of the learner's computer settings) are provided in the [Quality Assurance episode](04-quality-assurance.md#restricting-data-to-a-numeric-range).

:::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::  challenge

## Exercise

Download a [clean version of this dataset](https://ndownloader.figshare.com/files/11492171) and open the file with your spreadsheet program.
This data has many more variables that were not included in the messy spreadsheet and is formatted according to tidy data principles.

Discuss this data with a partner and make a list of some of the types of metadata that should be recorded about this dataset.
It may be helpful to start by asking yourself, "What is not immediately obvious to me about this
data? 
What questions would I need to know the answers to in order to analyze and interpret this data?"

:::::::::::::::  solution

## Solution

Some types of metadata that should be recorded and made available with the data are:

- the exact wording of questions used in the interviews (if interviews were structured) or general prompts used (if interviews were semi-structured)
- a description of the type of data allowed in each column (e.g., the allowed range for numerical data with a restricted range, a list of allowed options   for categorical variables, whether data in a numerical column should be continuous or discrete)
- definitions of any categorical variables (e.g., definitions of "burntbricks" and "sunbricks")
- definitions of what was counted as a "room", a "plot", etc. (e.g., was there a minimum size)
- learners may come up with additional questions to add to this list

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::


:::::::::::::::::::::::::::::::::::::::: keypoints

- Metadata is "data about data" that keeps your dataset understandable, verifiable, and reusable over time.
- Keep metadata in a separate plain text file.
- Use metadata to record details you can't keep with the data (exact survey questions, variable definitions, units, allowed value ranges, etc).
- Use folder-level documentation to clarify how different files in a dataset relate to one another.
- Follow established standards to make your metadata consistent and easy for others to navigate.

::::::::::::::::::::::::::::::::::::::::::::::::::