---
title: "Exporting data"
teaching: 10
exercises: 10
questions:
- "How can we export data from spreadsheets in a way that is useful for downstream applications?"
objectives:
- "Store spreadsheet data in universal file formats."
- "Export data from a spreadsheet to a CSV file."
- "Add a column to a dataframe to indicate the filename."
keypoints:
- "Data stored in common spreadsheet formats will often not be read correctly into data anlysis software, introducing errors into your data."
- "Exporting data from spreadsheets to formats like CSV or TSV puts it in a format that can be used consistently by most programs."
---

## Spreadsheet storage formats

Excel and other spreadsheet applications store the data in their own proprietary formats. 
This is fine if you only intend to use the data in the same application that it was created in, but it
can make it difficult to open the spreadsheet files in other applications that you may want to use to 
process the data.

In future versions of Excel Microsoft may make changes to the format, so that existing files are not even readable by the latest versions of Excel.


The .xlsx format used by versions of Excel since 2007 is in fact a folder of compressed XML files. 
You can rename a .xlsx file as a .zip file and extract the individual files. 
Amongst other things there will be an XML file for each of the tabs in your spreadsheet.

You could load this XML file into a text editor and read the data in it. But XML is a very verbose data format, designed originally for 
transferring data between one computer application and another. You may be able to read it but it would not be in the nice tabular format
that you see when it is loaded into Excel.

If you tried to load the .xlsx file directly into a text editor, the result would be gibberish as the text editor 
would simply try to display the characters in the compressed data file.


> ## Exercise
> 
> 1. Copy an .xlsx file and rename it as a .zip file.
> 
>    Extract the folders/files form the .zip file.
> 
>    Find the XML file corresponding to one of the tabs in the spreadsheet and open it in any text editor.
> 
>    Can you find the spreadsheet data in it? How easy would it be to use in this format?
> 2. Try opening a .xlsx file directly into a Text editor. 
> 
>    Can you find the spreadsheet data in it? How easy would it be to use in this format?
{: .challenge}

## Saving spreadsheet data as a csv file

CSV  stands for Comma Seperated Values. As the name suggests data items are stored seperated by commas. 
If there is a header row, then this is stored in the same way.
This makes a .csv file not only human readable, but it is a format that can also be read by any other data or 
statistical analysis applications such as Stata or SPSS.
It is also very easy to read .csv files in programming languages like Python or R.

This makes CSV an almost univeral portable format. 

> ## Exercise
> 1. create an Excel spreadsheet with the following data in it 
> 
> ![link_to_simple_data](../fig/spreadsheet_simple_data_01.png)
> 
> 2. Save the spreadsheet as a .csv file using
>    File | Save as   and select .csv fromm  the drop down box for the filetype.
> 
> 3. Load the file back into Excel by double-clicking the filename. Does the data look the same as it was?
> 
> 4. Open the .csv file in a text editor. What does the data look like?
> 
> > ## Solution
> > 
> > 1. When the .csv file created from the .xlsx file in Excel is opened it looks just as it did when it was saved.
> > 2. When you open the file in a text editor you will see that the data from cell  cell B4 has been placed in quotes.
> >    Excel does this automatically as it detected that the data included a comma. 
> > 
> > Most applications will ignore commas in quoted strings when reading a .csv file, but it is not guaranteed. 
> > It is also not guaranteed that an application writing a csv file will put strings in quotes if there are commas.
> > 
> > If commas are causing problems an alternative to csv is tsv. 't' stands for Tab. Instead of commas seperating the values, the Tab character is used.
> > All applications that will save as a csv file will also allow you to save as a tsv file.
> > 
> > A tsv file has an additional advantage in that when you load it into a text editor, the editor interprets the Tab characters, so all of the columns will
> > line up with their column names.
> {: .solution}
{: .challenge}


