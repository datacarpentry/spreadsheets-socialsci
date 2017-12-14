---
title: "Re-formatting a spreadsheet report"
teaching: 10
exercises: 15
questions:
- "How can I re-format a spreadsheet report to remove header lines?"
objectives:
- "Use formulas to restructure a spreadsheet layout"
keypoints:
- "Heading lines may contain information relevant to the rows below it and needs to added to each of them"
- "There may be multiple heading lines with different information in each"
---


## Re-formatting a 'Report' spreadsheet

In this episode we are going to look a simple spreadsheet which has been designed as if it was to be a printed
report rather than a single data table.

We will highlight the problems with the layout and then provide instructions on how it might be changed to be 
more usable for analysis.

The spreadsheet can be downloaded from [here](../data/report_data_o.xlsx)

The problems that we can see are as follows:

* White space to the top and to the left of the data.
* There are two header line types with different data items in each
* One of the header line has two seperate data items

What we would want is a spreadsheet which looks more like [this](../data/report_data_c.xlsx)


In this final version, we have removed all of the white space and the information in the header lines 
has been converted into columns of the data table. We had to add our own header row at the top.



## Exercise 

This is a walkthrough exercise with the instructor.

Convert the report spreadsheet into a clean data table.

### Solution

1. Take a copy of the spreadsheet we wish to change to perform the subsequent tasks on. - Never edit the original data.
2. We need to take the Year value from the first header and associate it with each of the data rows. We will put this information in column 'B'
   Select the cell B4 and insert the formula `=IF($F4="Year",$G4,$B3)`. Drag this formula down to the bottom of the data. For each cell the value of 2015 should be repeated.
3. We are now going to apply similar formulas to extract the 2nd header information items into columns.
   Select the cell C4 and insert the formula `=IF($D4="Month",$E4,$C3)`.  Drag this formula down to the bottom of the data. For each cell the value of Jan or Feb should be repeated.
   With the exception of the first 3 which will be 0. 
   Select the cell A4 and insert the formula  `=IF($H4="Region",$I4,$A3)`. Drag this formula down to the bottom of the data. For each cell the value of North or South should be repeated.
   With the exception of the first 3 which will be 0. 
4. Select any cell with data in it and then from the Insert menu bar select insert Table. Excel should suggest a range which covers all of the data. If it doesn't change the values of the range accordingly and click OK.
   The created table will have column names of 'Column1', 'Column2' etc.
5. We now need to convert all of our formulas into values. To do this select any cell in the table and type `Ctrl+A` to select the whole table. 
   Right mouse click and select copy. Right mouse click again and select Paste values.
6. We now have all of the data that we need in the form of a table, we just need to remove all of the white space by deleting all of the rows which do not contain Day or Reading values and then insert our own Header row
   containing the column headings.
7. Select the filter arrow on 'Column4' and on the text filter select  only 'Day', 'Month' and (blanks). These represent the values in this column that we need
   to delete. After these rows have been filtered, select them all and delete them, then remove the filter on Column4.
8. Select any cell in the table and from the `Table | Design` toolbar select `convert to range`.
9. Delete any blank rows at the top and empty columns on the right and then rename the remaining columns to more meaningful names like; Region, Year, Month, Day and Reading.



These instructions apply spefically to this particular spreadsheet and its layout. 
For other spreadsheets the instructions would have to be adapted. 

The formulas would have to be changed, but the general format would be the same. You are usually moving data from a heading row into a set of columns. But you have to allow for the possibility that there may be multiple heading rows with different data for a different set of rows.

When you filter to find all of the rows to delete, you may need to use a different column or 
even filter twice using two different columns.


