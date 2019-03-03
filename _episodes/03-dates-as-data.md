---
title: "Dates as data"
teaching: 10
exercises: 10
questions:
- "What are good approaches for handling dates in spreadsheets?"
objectives:
- "Recognise problematic or suspicious date formats."
- "Use formulas to separate dates into their component values (e.g. Month, Day, Year)."
keypoints:
- "Use extreme caution when working with date data."
- "Splitting dates into their component values can make them easier to handle."
---

## Date formats in spreadsheets

Dates in spreadsheets are often stored in a single column. While this seems the
most natural way to record dates, it actually is not best
practice. A spreadsheet application will display the dates in a
seemingly correct way (to a human observer) but how it actually handles
and stores the dates may be problematic.

In particular, please remember that functions that are valid for a given
spreadsheet program (be it LibreOffice, Microsoft Excel,
Gnumeric, etc.) are usually guaranteed to be compatible only within the same
family of products. If you will later need to export the data and need to
conserve the timestamps, you are better off handling them using one of the solutions discussed below.  

Spreadsheet programs have numerous “useful features” which allow them to handle dates in a variety of ways.

![Many formats, many ambiguities](../fig/excel_dates_1.jpg)

But these "features" often allow ambiguity to creep into your data. Ideally, data should be as unambiguous as possible.

## Dates stored as integers

The first thing you need to know is that Excel stores dates as numbers - see the last column in the above figure. Essentially, it counts the days from a default of December 31, 1899, and thus stores July 2, 2014 as  the serial number 41822.

> ## Excel's date systems
> Excel also entertains a second date system, the 1904 date system, as the default in Excel for Macintosh. This system will assign a
> different serial number than the [1900 date system](https://support.microsoft.com/en-us/help/214330/differences-between-the-1900-and-the-1904-date-system-in-excel). Because of this,
> [dates must be checked for accuracy when exporting data from Excel](http://datapub.cdlib.org/2014/04/10/abandon-all-hope-ye-who-enter-dates-in-excel/) (look for dates that are ~4 years off).
{: .callout}

This serial number thing can actually be useful in some circumstances. By using
the above functions we can easily add days, months or years to a given date.
Say you had a research plan where you needed to conduct interviews with a
set of informants every ninety days for a year.
In another cell, you could type:

=B2+90

And it would return

30-Sep

because it understands the date as a number `41822`, and `41822 + 90 = 41912`
which Excel interprets as the 30th day of September, 2014. It retains the format (for the most
part) of the cell that is being operated upon, (unless you did some sort of
formatting to the cell before, and then all bets are off). Month and year
rollovers are internally tracked and applied.

## Regional date formatting

When you enter a date into a spreadsheet it looks like a date although the spreadsheet may
display different text from what you input. For example if you enter '7/12/88' into your
Excel spreadsheet it may display as '07/12/1988' (depending on your version of Excel). These
are different ways of formatting the same date.

Different countries write dates differently. If you are in the UK, for example, you will interpret
the date above as the 7th day of December, however a researcher from the US will interpret the same entry as the 12th day of July. This regional variation is handled automatically by your
spreadsheet program so that when you are typing in dates they appear as you would expect. If you
try to type in a US format date into a UK version of Excel, it may or may not be treated as a
date.

This regional variation is one good reason to treat dates, not as a single data point, but as
three distinct pieces of data (month, day, and year). Separating dates into their component parts
will avoid this confusion, while also giving the added benefit of allowing you to compare, for
example data collected in January of multiple years with data collected in February of multiple years.

> ## Separating dates into components
>
> Download and open the [dates.xlsx](https://ndownloader.figshare.com/files/11502827) file. This file
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
from before and after this date, Excel will translate only the post-1900 dates into its internal format, thus resulting in mixed data. If you’re working with historic data, be extremely careful with your dates!

{% include links.md %}
