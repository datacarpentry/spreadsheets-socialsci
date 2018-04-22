---
title: "Creating data tables in a spreadsheet"
teaching: 15
exercises: 0
questions:
- "How should I design and format my spreadsheet?"
objectives:
- "Employ best practices when creating spreadsheet data"
keypoints:
- "If you inherit data in a spreadsheet, you may have to re-structure the data to make it usable and/or consistent "
- "Careful design of your own spreadsheets will make then easily usable and portable to other systems"
---


## Spreadsheets outline

In this lesson, we’re going to talk about:

- Using best practice to create your own data tables in spreadsheets
- Reformatting existing spreadsheets (using Excel)
- Recognising and reformatting dates in spreadsheets
- Basic quality control; using data validation and Data entry forms (in Excel)
- Exporting data from spreadsheets

### Spreadsheet programs

Many spreadsheet programs are available. We will use Microsoft Excel in our examples.
Although it is not open source software it is very widely available and used.

Free spreadsheet programs such as LibreOffice and OpenOffice are available.
The functionality of these may differ from Excel, but in general they can be used to perform similar tasks.


## Problems with Spreadsheets

Although spreadsheets are good as a data entry tool, they are in practice used for a variety of tasks.
Often they are used for presentation of data or summaries of the data or graphs and charts derived from the data.

Because they are being aimed at presentation, the data may be laid out in ways which are 'easy on the eye'.

This type of report layout formatting, complete with white space, merged cells, colour and grids may aid
readability, but they do not aid processing of the data or the portability of the data.

Similarly, including data summaries, complex functions and graphs, using the provided drag and drop features of
the spreadsheet can cause issues when documenting the work or trying to demonstrate data quality and consistency.

The real problem with data in spreadsheets is that you may have simply inherited the spreadsheet and could
not exercise any control in its construction or entry of the data within it.

In the next episode we will look at how you may be able to deal with some of these problems by re-formatting the data.

In later sections we will look at how you can use the functionality of Excel to make data entry easier and more error free.

To finish this section we want to outline some best practices for the creation of data tables within a spreadsheet.



## Creating a spreadsheet to hold data

When we usually think of 'data', our mind often thinks of information
    contained in tables.
Within this table, we think of columns representing variables
    and the rows representing observations.
Spreadsheets are very good at recording data in this way.

![simple_spreadsheet](../fig/spreadsheet_simple_data_01.png)

Once we have data organized this way, it is easy to get drawn into adding
    additional information and/or styling to our data.
This is often due to us wanting to make the data simpler to understand and
    the amount of functionality modern spreadsheet software provide.
In a sense, the more additional information we add to the table or data,
    the more our data begin to look like a set of notes.
Typical additions we make to data include:

* The use of colour codes to indicate values
* Adding multiple tables in a single sheet
* Inconsistently defined values for variables, or inconsitent variable naming conventions
* Introduction of white space and the merging of cells - to make it look more readable

You can set things up in different ways in spreadsheets -
    often incorporating many of these points from above.
However, some of these choices can limit your ability to
    work with the data in other programs or
    have the you-of-6-months-from-now or your collaborator work with the data.
We advocate keeping spreadsheet contents to be a simple table design,
    with the rows and columns following the guidelines for Tidy data as indicated by Hadley Wickham in his paper ['Tidy Data'](https://www.jstatsoft.org/article/view/v059i10).


## The simple guidelines

1. One table per spreadsheet (or one per spreadsheet tab) at most
2. Start in cell A1
3. First row is for column names
4. No spaces in column names
5. Only a single variable in each column
6. Use a consistent format for the column values. i.e. don't mix date formats, consistency when representing boolean values
7. One observation per row.
8. Static data columns first, then measured or recorded data columns then calculated columns
9. Keep formulas simple


## More detailed guidelines

The guidelines above should result in simple, easy to understand data tables. For simple data entry
there should be no difficulty is applying them.

Despite this spreadsheets are not ideal for analysis purposes, due to the lack of an audit trail of what has been done
in the drag and drop, point and click environment, creating derived columns using simple formulae may be acceptable
and convenient.

For more more complex spreadsheets you can employ further best practices to make them not only more readable but also
more maintainable. This document [Twenty principles for good spreadsheet practice](http://www.icaew.com/~/media/corporate/files/technical/information%20technology/excel%20community/166%20twenty%20principles%20for%20good%20spreadsheet%20practice.ashx)
from the ICAEW has some useful further advice.

Always remember, the more complex the spreadsheet, the more likely that it will contain errors.
Googling 'Spreadsheet Errors' or more specifically 'Reinhart and Rogoff' will allow you to investigate how bad things can get.
