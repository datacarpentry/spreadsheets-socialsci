---
title: "Dates as data"
teaching: 10
exercises: 5
questions:
- "What are good approaches for handling dates in spreadsheets?"
objectives:
- "Recognise problematic or suspicious date formats."
- "Use formulas to separate dates into their component values (e.g. Month, Day, Year)."
keypoints:
- "Use extreme caution when working with date data."
- "Splitting dates into their component values can make them easier to handle."
---

Dates in spreadsheets are often stored in a single column. While this seems the
most natural way to record dates, it actually is not best
practice. A spreadsheet application will display the dates in a
seemingly correct way (to a human observer) but how it actually handles
and stores the dates may be problematic.

In particular, please remember that functions that are valid for a given
spreadsheet program (be it LibreOffice, Microsoft Excel, OpenOffice,
Gnumeric, etc.) are usually guaranteed to be compatible only within the same
family of products. If you will later need to export the data and need to
conserve the timestamps, you are better off handling them using one of the solutions discussed below.  

When you enter a date into a spreadsheet it looks like a date although the spreadsheet may 
display different text from what you input. For example if you enter '7/12/88' into your
Excel spreadsheet it may display as '07/12/1988' (depending on your version of Excel). These
are different ways of formatting the same date. 

Different countries write dates differently. If you are in the UK, for example, you will interpret
the date above as the 7th day of December, however a research from the US will interpret the same entry as the 12th day of July. This regional variation is handled automatically by your
spreadsheet program so that when you are typing in dates they appear as you would expect. If you 
try to type in a US format date into a UK version of Excel, it may or may not be treated as a 
date.

This regional variation is one good reason to treat dates, not as a single data point, but as 
three distinct pieces of data (month, day, and year). Separating dates into their component parts
will avoid this confusion, while also giving the added benefit of allowing you to compare, for
example data collected in January of multiple years with data collected in February of multiple years.

> ## Separating dates into components
>
> Download and open the [dates.xlsx]((../data/dates.xlsx?raw=true) file. This file
> contains a subset of the data from the SAFI interviews, including the dates on which the 
> interviews were conducted. 
> 
> Choose the tab of the spreadsheet that corresponds to the way you format dates in your
> location (either day first `DD_MM_YEAR`, or month first `MM_DD_YEAR`). 
> 
> Extract the components of the date to new columns. For this we 
> can use the built in Excel functions:
>
> `=MONTH()`    
> `=DAY()`  
> `=YEAR()`
>
> Apply each of these formulas to its entire column. 
> Make sure the new column is formatted as a number and not as a date.
>
> We now have each component of our date isolated in it's own column. This will allow us 
> to group our data with respect to month, year, or day of month for our analyses and will
> also prevent problems when passing data between different versions of spreadsheet 
> software (as for example when sharing data with collaborators in different countries).
>
> > ## Solution
> > ![dates exercise 1](../fig/solution_exercise_1_dates.png)
> > 
> > Note that this solution shows the dates in `MM_DD_YEAR` format. 
> {: .solution}
{: .challenge}


> ## Default year
> 
> Using the same spreadsheet you used for the previous exercise, add another data point
> in the `interview_date` column by typing either `11/17` (if your location uses `MM/DD` formatting)
> or `17/11` (if your location uses `DD/MM` formatting). The `Day`, `Month`, and `Year` columns
> should populate for this new data point. What year is shown in the `Year` column?
> 
> > ## Solution
> > If no year is specified, the spreadsheet program will assume you mean the current year
> > and will insert that value. This may be incorrect if you are working with historical data so
> > be very cautious when working with data that does not have a year specified within its date
> > variable.
> {: .solution}
{: .challenge}

## Historical data

Excel is unable to parse dates from before 1899-12-31, and will thus leave these untouched.  If you’re mixing historic data
from before and after this date, Excel will translate only the post-1900 dates into its internal format, thus resulting in mixed data.
If you’re working with historic data, be extremely careful with your dates!

Excel also entertains a second date system, the 1904 date system, as the default in Excel for Macintosh. This system will assign a
different serial number than the [1900 date system](https://support.microsoft.com/kb/180162). Because of this,
[dates must be checked for accuracy when exporting data from Excel](http://datapub.cdlib.org/2014/04/10/abandon-all-hope-ye-who-enter-dates-in-excel/) (look for dates that are ~4 years off). 

## Data formats in spreadsheets

Spreadsheet programs have numerous “useful features” which allow them to handle dates in a variety of ways.

![Many formats, many ambiguities](../fig/excel_dates_1.jpg)

But these "features" often allow ambiguity to creep into your data. Ideally, data should be as unambiguous as possible. 

### Dates stored as integers

The first thing you need to know is that Excel stores dates as numbers - see the last column in the above figure. Essentially, it counts the days from a default of December 31, 1899, and thus stores July 2, 2014 as  the serial number 41822.

(But wait. That’s the default on my version of Excel. We’ll get into how this can introduce problems down the line later in this lesson. )

This serial number thing can actually be useful in some circumstances. By using
the above functions we can easily add days, months or years to a given date.
Say you had a sampling plan where you needed to sample every thirty seven days.
In another cell, you could type:
    
    =B2+37
    
And it would return

    8-Aug

because it understands the date as a number `41822`, and `41822 + 37 = 41859`
which Excel interprets as August 8, 2014. It retains the format (for the most
part) of the cell that is being operated upon, (unless you did some sort of
formatting to the cell before, and then all bets are off). Month and year
rollovers are internally tracked and applied.

**Note**
Adding years and months and days is slightly trickier because we need to make
sure that we are adding the amount to the correct entity.

- First we extract the single entities (day, month or year)
- We can then add values to to that
- Finally the complete date string is reconstructed using the `DATE()` function.

As for dates, times are handled in a similar way; seconds can be directly
added but to add hour and minutes we need to make sure that we are adding
the quantities to the correct entities.

Which brings us to the many different ways Excel provides in how it displays dates. If you refer to the figure above, you’ll see that
there are many ways that ambiguity creeps into your data depending on the format you chose when you enter your data, and if you’re not
fully aware of which format you’re using, you can end up actually entering your data in a way that Excel will badly misinterpret. 

> ## Exercise  
> What happens to the dates in the "dates" tab of our workbook if we save this sheet in Excel (in `csv` format) and then open the file in a plain text editor (like TextEdit or Notepad)? What happens to the dates if we then open the `csv` file in Excel?
> > ## Solution
> > - Click to the "dates" tab of the workbook and double-click on any of the values in the `Date collected` column. Notice that the dates display with the year 2015.   
> > - Select `File -> Save As` in Excel and in the drop down menu for file format select `CSV UTF-8 (Comma delimited) (.csv)`. Click `Save`.  
> > - You will see a pop-up that says "This workbook cannot be saved in the selected file format because it contains multiple sheets." Choose `Save Active Sheet`.   
> > - Navigate to the file in your finder application. Right click and select `Open With`. Choose a plain text editor application and view the file. Notice that the dates display as month/day without any year information.   
> > - Now right click on the file again and open with Excel. Notice that the dates display with the current year, not 2015.   
> > As you can see, exporting data from Excel and then importing it back into Excel fundamentally changed the data!  
> {: .solution}
{: .challenge}

**Note**  
You will notice that when exporting into a text-based format (such as CSV), Excel will export its internal date integer instead of a useful value (that is, the dates will be represented as integer numbers). This can potentially lead to problems if you use other software to manipulate the file.

### Advantages of Alternative Date Formatting

### <a name="day"></a> Storing dates as YEAR, MONTH, DAY

Storing dates in YEAR, MONTH, DAY format helps remove this ambiguity. Let's look at this issue a bit closer.

For instance this is a spreadsheet representing insect counts that were taken every few days over the summer, and things went something like this:

![So, so ambiguous, it's even confusing Excel](../fig/6_excel_dates_2.jpg)

If Excel was to be believed, this person had been collecting bugs **in the future**. Now, we have no doubt this person is highly capable,
but I believe time travel was beyond even their grasp.

Entering dates in one cell is helpful but due to the fact that the spreadsheet programs may interpret and save the data in different ways
(doing that somewhat behind the scenes), there is a better practice.  

In dealing with dates in spreadsheets, separate date data into separate fields (day, month, year), which will eliminate any chance of
ambiguity. 

### <a name="doy"></a> Storing dates as YEAR, DAY-OF-YEAR

There is also another option. You can also store dates as year and day of year (DOY). Why? Because depending on your
question, this might be what's useful to you, and there is practically no possibility for ambiguity creeping in.

Statistical models often incorporate year as a factor, or a categorical variable, rather than a numeric variable, to account for 
year-to-year variation, and DOY can be used to measure the passage of time within a year. 

So, can you convert all your dates into DOY format? Well, in Excel, here’s a useful guide:

![Kill that ambiguity before it bites you!](../fig/7_excel_dates_3.jpg)

### <a name="str"></a> Storing dates as a single string

Another alternative could be to convert the date string
into a single string using the `YYYYMMDDhhmmss` format.
For example the date `March 24, 2015 17:25:35` would
become `20150324172535`, where:


YYYY:   the full year, i.e. 2015  
MM:     the month, i.e. 03  
DD:     the day of month, i.e. 24  
hh:     hour of day, i.e. 17  
mm:     minutes, i.e. 25  
ss:     seconds, i.e. 35  

Such strings will be correctly sorted in ascendng or descending order, and by
knowing the format they can then be correctly processed by the receiving
software.
