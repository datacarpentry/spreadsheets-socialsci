---
title: "Formatting data tables in Spreadsheets"
teaching: 15
exercises: 15
questions:
- "What are some common challenges with formatting data in spreadsheets and how can we avoid them?"
objectives:
- "Recognise and resolve common spreadsheet formatting problems."
keypoints:
- "Never modify your raw data. Always make a copy before making any changes."
- "Keep track of all of the steps you take to clean your data."
- "Organize your data according to tidy data principles."
- "Avoid using multiple tables within one spreadsheet."
- "Avoid spreading data across multiple tabs (but do use a new tab to record data cleaning or manipulations)."
- "Record zeros as zeros."
- "Use an appropriate null value to record missing data."
- "Don't use formatting to convey information or to make your spreadsheet look pretty."
- "Place comments in a separate column."
- "Record units in column headers."
- "Include only one piece of information in a cell."
- "Avoid spaces, numbers and special characters in column headers."
- "Avoid special characters in your data."
---



## Data formatting Principles

It can be tempting to treat spreadsheet programs like lab notebooks, that is,
relying on context, notes in the margin,
spatial layout of data and fields to convey information. As humans, we
can (usually) interpret these things, but computers don't view information the same way, and
unless we explain to the computer what every single thing means (and
that can be hard!), it will not be able to see how our data fit
together. The goal of a spreadsheet is to balance being human readable (and editable) and machine-readable, so there are special organizing principles at play here.

Using the power of computers, we can manage and analyze data in much more
effective and faster ways, but to use that power, we have to set up
our data for the computer to be able to understand it (and computers are very
literal).

This is why it’s extremely important to set up well-formatted
tables from the outset - before you even start entering data from
your very first preliminary experiment. Data organization is the
foundation of your research project. It can make it easier or harder
to work with your data throughout your analysis, so it's worth
thinking about when you're doing your data entry or setting up your
experiment. You can set things up in different ways in spreadsheets,
but some of these choices can limit your ability to work with the data in other programs or
have the you-of-6-months-from-now or your collaborator work with the
data. We are going to introduce a set of principles called "Tidy Data" as guidelines.  

> ## Tip
> The best layouts/formats (as well as software and
> interfaces) for data entry and data analysis might be
> different. It is important to take this into account, and ideally
> automate the conversion from one to another.
{: .callout}

### Structuring data in spreadsheets


The cardinal rules of using spreadsheet programs for data:

1. Put all your variables in columns - the thing you're measuring,
   like 'weight' or 'temperature'.
2. Put each observation in its own row.
3. Don't combine multiple pieces of information in one
   cell. Sometimes it just seems like one thing, but think if that's
   the only way you'll want to be able to use or sort that data.
4. Leave the raw data raw - don't change it!
5. Export the cleaned data to a text-based format like CSV (comma-separated values) format. This
   ensures that anyone can use the data, and is required by
   most data repositories.

For instance, we're going to be working with data from a study of
agricultural practices among farmers in two countries in eastern
sub-Saharan Africa (Mozambique and Tanzania). Researchers conducted
interviews with farmers in these countries to collect data on
household statistics (e.g. number of household members,
number of meals eaten per day, availability of water),
farming practices (e.g. water usage), and assets (e.g. number of farm plots,
number of livestock). They also recorded the dates and locations of
each interview.

If they were to keep track of the data like this:

![multiple-info example](../fig/multiple-info.png)

the problem is that number of livestock and type of livestock are in
the same field. So, if they wanted to
look at the average number of livestock owned, or the average number of each type
of livestock,
it would be hard to do this using this data setup. If instead we put the count
of each type of livestock in it's own column, this would make analysis
much easier. The rule of thumb, when setting up a datasheet, is that each
variable (in this case, each type of livestock) should have its own column,
each observation should have its own row, and each cell should contain only a
single value. Thus, the example above should look like this:

![single-info example](../fig/single-info.png)

Notice that this now allows us to make statements about the number of each type of
animal that a farmer owns, while still allowing us to say things about the
total number of livestock. All we need to do is sum the values in each row to
find a total. We'll be learning how to do this computationally and reproducibly
later in this workshop.



> ## Handy References
>
> Two excellent references on spreadsheet organization are:
>
> * Karl W. Broman & Kara H. Woo, *Data Organization in Spreadsheets*, Vol. 72,
> Issue 1, 2018, The American Statistician.
> <https://www.tandfonline.com/doi/full/10.1080/00031305.2017.1375989>
>
> * Hadley Wickham, *Tidy Data*, Vol. 59, Issue 10, Sep 2014, Journal of
> Statistical Software. <http://www.jstatsoft.org/v59/i10>
{: .callout}



### Keeping track of your analyses

When you're working with spreadsheets, during data clean up or analyses, it's
very easy to end up with a spreadsheet that looks very different from the one
you started with. In order to be able to reproduce your analyses or figure out
what you did when Reviewer #3 asks for a different analysis, you should

- create a new file or tab with your cleaned or analyzed data. Don't modify
the original dataset, or you will never know where you started!
- keep track of the steps you took in your clean up or analysis. You should track
these steps as you would any step in an experiment. You can
do this in another text file, or a good option is to create a new tab in your spreadsheet
with your notes. This way the notes and data stay together.

Put these principles in to practice today during the exercises.





> ## LibreOffice Users
> The default for LibreOffice is to treat tabs, commas, and semicolons as delimiters.
> This behavior can cause problems with both the data for this lesson and other data
> you might want to use. This can be fixed when opening LibreOffice by deselecting
> the "semicolons" and "tabs" checkboxes.
{: .callout}

> ## Exercise
>
> We're going to take a messy version of the SAFI data and describe how we would clean it up.
>
> 1. Download the [messy data](https://ndownloader.figshare.com/files/11502824).
> 2. Open up the data in a spreadsheet program.
> 3. Notice that there are two tabs. Two researchers conducted the interviews,
>    one in Mozambique and the other in Tanzania. They both structured their
>    data tables in a different way. Now, you're the person in charge of this
>    project and you want to be able to start analyzing the data.
> 4. With the person next to you, identify what is wrong with this spreadsheet.
>    Discuss the steps you would need to take to clean up the two tabs, and to
>    put them all together in one spreadsheet.
>
> **Important** Do not forget our first piece of advice, to create a new file
> (or tab) for the cleaned data, never modify your original (raw) data.
>
> After you go through this exercise, we'll discuss as a group what was wrong
> with this data and how you would fix it.
>
> > ## Solution
> >
> > - Take about 10 minutes to work on this exercise.
> > - All the mistakes listed below are
> > present in the messy dataset. If this
> > exercise is done during a workshop, ask people what they saw as wrong with
> > the data. As learners point out errors, expand a bit on the point they brought up using the remainder of the episode.
> {: .solution}
{: .challenge}



## Common Spreadsheet Errors

This lesson is meant to be used as a reference for discussion as learners identify issues with the messy dataset discussed in the
previous lesson. Instructors: don't go through this lesson except to refer to responses to the exercise in the previous lesson.

There are a few potential errors to be on the lookout for in your own data as well as data from collaborators or the Internet. If you are aware of the errors and the possible negative effect on downstream data analysis and result interpretation, it might motivate yourself and your project members to try and avoid them. Making small changes to the way you format your data in spreadsheets, can have a great impact on efficiency and reliability when it comes to data cleaning and analysis.

- [Using multiple tables](#tables)
- [Using multiple tabs](#tabs)
- [Not filling in zeros](#zeros)
- [Using problematic null values](#null)
- [Using formatting to convey information](#formatting)
- [Using formatting to make the data sheet look pretty](#formatting_pretty)
- [Placing comments or units in cells](#units)
- [Entering more than one piece of information in a cell](#info)
- [Using problematic field names](#field_name)
- [Using special characters in data](#special)

## <a name="tables"></a> Using multiple tables

A common strategy is creating multiple data tables within
one spreadsheet. This confuses the computer, so don't do this!
When you create multiple tables within one
spreadsheet, you’re drawing false associations between things for the computer,
which sees each row as an observation. You’re also potentially using the same
field name in multiple places, which will make it harder to clean your data up
into a usable form. The example below depicts the problem:

![multiple tables](../fig/multiple-tables-example.png)

In the example above, the computer will see (for example) row 24 and assume that all columns A-J
refer to the same sample. This row actually represents two distinct samples
(information about livestock for informant 1 and information about plots for informant 2). Other rows are similarly problematic.

## <a name="tabs"></a> Using multiple tabs

But what about workbook tabs? That seems like an easy way to organize data, right? Well, yes and no. When you create extra tabs, you fail
to allow the computer to see connections in the data that are there (you have to introduce spreadsheet application-specific functions or
scripting to ensure this connection). Say, for instance, you make a separate tab for each day you take a measurement.

This isn't good practice for two reasons:
1) you are more likely to accidentally add inconsistencies to your data if each time you take a measurement, you start recording data in a new tab, and
2) even if you manage to prevent all inconsistencies from creeping in, you will add an extra step for yourself before you analyze the
data because you will have to combine these data into a single datatable. You will have to explicitly tell the computer how to combine
tabs - and if the tabs are inconsistently formatted, you might even have to do it manually.

The next time you’re entering data, and you go to create another tab or table,
ask yourself if you could avoid adding this tab by adding another column to your original spreadsheet.

Your data sheet might get very long over the course of the experiment. This makes it harder to enter data if you can’t see your headers
at the top of the spreadsheet. But don't repeat your header row. These can easily get mixed into the data,
leading to problems down the road.

Instead you can freeze the column headers so that they remain visible even when you have a spreadsheet with many rows.

[Documentation on how to freeze column headers](https://support.office.com/en-ca/article/Freeze-column-headings-for-easy-scrolling-57ccce0c-cf85-4725-9579-c5d13106ca6a)

## <a name="zeros"></a> Not filling in zeros

It might be that when you're measuring something, it's
usually a zero, say the number of cows that an informant has, in a
region where most farmers have goats and no cows. Why bother
writing in the number zero in that column, when it's mostly zeros?

![filling in zeros](../fig/zeros-example.png)

However, there's a difference between a zero and a blank cell in a spreadsheet. To the computer, a zero is actually data. You measured
or counted it. A blank cell means that it wasn't measured and the computer will interpret it as an unknown value (otherwise known as a
null value).

The spreadsheets or statistical programs will likely mis-interpret blank cells that you intend to be zeros. By not entering the value of
your observation, you are telling your computer to represent that data as unknown or missing (null). This can cause problems with
subsequent calculations or analyses. For example, the average of a set of numbers which includes a single null value is always null
(because the computer can't guess the value of the missing observations). Because of this, it's very important to record zeros as zeros and truly missing data as nulls.

## <a name="null"></a> Using problematic null values
**Example**: using -999 or other numerical values (or zero) to represent missing data.

**Solution**: One common practice is to record unknown or missing data as -999, 999, or 0. Many statistical programs will not recognize
that these are intended to represent missing (null) values. How these values are interpreted will depend on the software you use to
analyze your data. It is essential to use a clearly defined and consistent null indicator.
Blanks (most applications) and NA (for R) are good choices. White et al, 2013, explain good choices for indicating null values for different software applications in their article:
[Nine simple ways to make it easier to (re)use your data.](http://library.queensu.ca/ojs/index.php/IEE/article/view/4608/4898) Ideas in Ecology and Evolution.

![White et al.](../fig/white_table_1.jpg)


## <a name="formatting"></a> Using formatting to convey information

**Example**: highlighting cells, rows or columns that should be excluded from an analysis, leaving blank rows to indicate separations in data.

![formatting](../fig/bad-formatting.png)

**Solution**: create a new field to encode which data should be excluded.

![good formatting](../fig/better-formatting.png)


## <a name="formatting_pretty"></a> Using formatting to make the data sheet look pretty

**Example**: merging cells.

**Solution**: If you’re not careful, formatting a worksheet to be more aesthetically pleasing can compromise your computer’s ability to
see associations in the data. Merged cells will make your data unreadable by statistics software. Consider restructuring your data in
such a way that you will not need to merge cells to organize your data.


## <a name="units"></a> Placing comments or units in cells

**Example**: Some of your informants only irrigate their plots at certain times of the year. You've added this information as notes directly into the cell with the data.

**Solution**: Most analysis software can't see Excel or LibreOffice comments, and would be confused by comments placed within your data
cells. As described above for formatting, create another field if you need to add notes to cells. Similarly, don’t include units in
cells: ideally, all the measurements you place in one column should be in the same unit, but if for some reason they aren’t, create
another field and specify the units the cell is in.

![comments in cells](../fig/comments-in-cells.png)

## <a name="info"></a> Entering more than one piece of information in a cell

**Example**: Your informant has multiple livestock of different types. You record this information as "3, (oxen , cows)" to indicate that there are three total livestock, which is a mixture of oxen and cows.

**Solution**: Don't include more than one piece of information in a cell. This will limit the ways in which you can analyze your data.
If you need both these types of information (the total number of animals and the types), design your data sheet to include this information. For example, include a separate column for each type of livestock.

## <a name="field_name"></a> Using problematic field names
Choose descriptive field names, but be careful not to include spaces, numbers, or special characters of any kind. Spaces can be
misinterpreted by parsers that use whitespace as delimiters and some programs don’t like field names that are text strings that start
with numbers.  

Underscores (`_`) are a good alternative to spaces. Consider writing names in camel case (like this: ExampleFileName) to improve
readability. Remember that abbreviations that make sense at the moment may not be so obvious in 6 months, but don't overdo it with names
that are excessively long. Including the units in the field names avoids confusion and enables others to readily interpret your variable names.

**Examples**  

<table align = "left" style = "width =50%; border: 1px solid black;">
<tr>
	<td> <b>Good Name</b></td> <br />
	<td> <b>Good Alternative </b> </td><br />
	<td> <b>Avoid </b></td><br />
</tr>
<tr>
	<td> wall_type </td>
	<td> WallType </td>
	<td> wall type </td>
</tr>
<tr>
	<td> longitude </td>
	<td> GpsLongitude </td>
	<td> gps:Longitude </td>
</tr>
<tr>
	<td> gender </td>
	<td> gender </td>
	<td> M/F </td>
</tr>
<tr>
	<td> Informant_01 </td>
	<td> first_informant</td>
	<td> 1st Inf</td>
</tr>
</table>

## <a name="special"></a> Using special characters in data

**Example**: You treat your spreadsheet program as a word processor when writing notes, for example copying data directly from Word or
other applications.

**Solution**: This is a common strategy. For example, when writing longer text in a cell, people often include line breaks, em-dashes,
etc in their spreadsheet.  Also, when copying data in from applications such as Word, formatting and fancy non-standard characters (such
as left- and right-aligned quotation marks) are included.  When exporting this data into a coding/statistical environment or into a
relational database, dangerous things may occur, such as lines being cut in half and encoding errors being thrown.

General best practice is to avoid adding characters such as newlines, tabs, and vertical tabs.  In other words, treat a text cell as if
it were a simple web form that can only contain text and spaces.


{% include links.md %}
