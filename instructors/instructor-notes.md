---
title: Instructor Notes
---

## Instructor notes

## Lesson motivation and learning objectives

The purpose of this lesson is not to teach how to do data analysis in spreadsheets,
but to teach good data organization and how to do some data cleaning and
quality control in a spreadsheet program.

## Lesson design


#### [Formatting data](../episodes/01-format-data.md)

- Introduce the dataset that will be used in this lesson, and in the other Social Sciences lessons, the [Studying African Farmer-led Irrigation (SAFI) Dataset](https://www.datacarpentry.org/socialsci-workshop/data).
- Go through the point about keeping track of your steps and keeping raw data raw
- Go through the cardinal rule of spreadsheets about columns, rows and cells
- Hand them a messy data file and have them pair up and work together to clean up the data.
  *Give them 15 minutes to do this.*
- Learners who are using LibreOffice for the workshop will have problems with the dataset
  as the default for LibreOffice is to treat tabs, commas, and semicolons as delimiters. This
  can be fixed when opening LibreOffice by deselecting the "semicolons" and "tabs" checkboxes.
- Ask for what people did to clean the data. As they bring up different points you can
  refer to them in the [Common formatting problems](../episodes/02-common-mistakes.md) file, or expand a bit on the point they brought up.
  All these mistakes are present in the messy
  dataset.
- If you get a response where they've fixed the date, you can pause and go to the
  [dates](../episodes/03-dates-as-data.md) lesson. Or you can say you'll come back to dates at the end.
  There's an exercise in that file about how to change the
  date into three columns using Excel's built in MONTH, DAY, YEAR functions. Have them
  run through that exercise.

#### [Common formatting problems](../episodes/02-common-mistakes.md)

- **Don't go through this chapter** except to refer to as responses to the exercise in
  the previous chapter.

#### [Dates as data](../episodes/03-dates-as-data.md)

- Do the exercise and make the point about dates either in response to a learner bringing
  up date as an issue during the responses, or at the end of the response time.
- If learners are using a non-English language version of Excel, the `=MONTH()`, `=DAY()`, and other date
  functions won't work for them. They will need to type in their language's equivalent of that word in the formula.
- The spreadsheet for this episode has two tabs. The first tab is data stored as `DD-MM-YYYY`,
  the second is `MM-DD-YYYY`. If learners use the wrong tab for their location, they will get a `#VALUE` error.
- When using Libre Office, it is helpful to first save the file in ods format. Then be sure to convert
  the date column to type date by right clicking on the cell, choose "Format Cells..." then choose Date and
  take a type of date that uses `DD/MM/YYYY`, such as English (Botswana). Once you click ok, you will find that
  the date has been pre-pended by an apostrophe. For example 21/11/2016 becomes '21/11/2016. Edit the cell to
  remove the apostrophe. You will then find that the day(), month() and year() functions work.

#### [Quality assurance](../episodes/04-quality-assurance.md)

The challenge with this lesson is that the instructor's version of the spreadsheet software is going to look different than about half the room's. It makes
it challenging to show where you can find menu options and navigate through.

Instead discuss the concepts of quality control, and how things like sorting can help you find outliers in your data.

#### [Exporting data](../episodes/05-exporting-data.md)

- Have the students export their cleaned data as CSV. Reiterate again the need for
  data in this format for the other tools we'll be using.

#### Concluding points

- Now your data is organized so that a computer can read and understand it. This
  let's you use the full power of the computer for your analyses as we'll see in the
  rest of the workshop.
- While your data is now neatly organized, it still might have errors or missing data
  or other problems. It's like you put all your data in the right drawers, but the
  drawers might still be messy. The next lesson is going to teach you OpenRefine which
  is great for data cleaning and for some of the quality control that we touched on
  in this lesson. It also has the advantage that it automatically keeps track of the
  steps you take.

## Technical tips and tricks

Provide information on setting up your environment for learners to view your
live coding (increasing text size, changing text color, etc), as well as
general recommendations for working with coding tools to best suit the
learning environment.

## Common problems

#### Excel looks and acts different on different operating systems

The main challenge with this lesson is that Excel looks very different and how you
do things is even different between Mac and PC, and between different versions of
Excel. So, the presenter's environment will only be the same as some of the learners.

We need better notes and screenshots of how things work on both Mac and PC. But we
likely won't be able to cover all the different versions of Excel.

If you have a helper who has experience with the other OS than you, it would be good
to prep them to help with this lesson and tell how people to do things in the other OS.

#### Apple Numbers

Apple Numbers does not have data validation, which is needed for part of this lesson. A note
is included in the setup instructions pointing Numbers users to either Microsoft Excel
or LibreOffice.

#### People are not interactive or responsive on the Exercise

This lesson depends on people working on the exercise and responding with things
that are fixed. If your audience is reluctant to participate, start out with
some things on your own, or ask a helper for their answers. This generally gets
even a reluctant audience started.

## Common questions raised by participants

### How do you extract date components from the interview\_date field in SAFI\_clean.csv?

The interview\_date field in SAFI\_clean.csv when saved to SAFI\_clean.xlsx is difficult to
manage because there isn't a way to format the column as a date field, even using the
custom field formats. The easiest solution to this question is to show the student how to
extract the date information from the field. Make a new column and format it as a date.
In the first cell of the new column type =LEFT(C2,10) and then apply this to the column.
This function extracts the first 10 characters from the left side of the interview\_date
field and inserts them into a new column.

### How would you automatically transform the items\_owned field into a usable format?

If you are not following the course immediately with the OpenRefine lesson it is important
to make it clear that in the current format SAFI\_clean.csv is not ready for analysis.
The items\_owned column ideally needs to be split into separate yes / no / null columns.
Example: set up a new column 'bicycle' and format it as a number. You then need to extract
information from the items\_owned column about whether the word 'bicycle' is in the column.
One way of doing this is to use an IF statement: =IF(ISNUMBER(SEARCH("bicycle",K2))1,0).
The IF statement can include a wild character e.g. "bicy\*".


