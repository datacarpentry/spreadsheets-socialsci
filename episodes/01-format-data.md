---
title: "Formatting problems"
teaching: 15
exercises: 20
questions:
- "What are some common challenges with formatting data in spreadsheets and how can we avoid them?"
objectives:
- "Recognise and resolve common spreadsheet formatting problems."
- "Describe the importance of metadata."
- "Identify metadata that should be included with a dataset."
keypoints:
- "Avoid using multiple tables within one spreadsheet."
- "Avoid spreading data across multiple tabs (but do use a new tab to record data cleaning or manipulations)."
- "Record zeros as zeros."
- "Use an appropriate null value to record missing data."
- "Don't use formatting to convey information or to make your spreadsheet look pretty."
- "Place comments in a separate column."
- "Record units in column headers."
- "Include only one piece of information in a cell."
- "Avoid spaces, numbers, and special characters in column headers."
- "Avoid special characters in your data."
- "Record metadata in a separate plain text file."
---
## Data formatting problems

The most common mistake made is treating treating spreadsheet programs like lab notebooks, that is, 
relying on context, notes in the margin,
spatial layout of data and fields to convey information. As humans, we
can (usually) interpret these things, but computers don't view information the same way, and
unless we explain to the computer what every single thing means (and
that can be hard!), it will not be able to see how our data fit
together.

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
data.

> ## Tip
> The best layouts/formats (as well as software and
> interfaces) for data entry and data analysis might be
> different. It is important to take this into account, and ideally
> automate the conversion from one to another.
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

> ## Introduce the Data
> If not already discussed, introduce the dataset that will be used in this
> lesson, and in the other Social Sciences lessons, the [Studying African Farmer-led Irrigation (SAFI) Dataset](http://www.datacarpentry.org/socialsci-workshop/data). 
>
> The data used in these lessons are taken from interviews of farmers in two countries in eastern sub-Saharan Africa (Mozambique and Tanzania). These
> interviews were conducted between November 2016 and June 2017 and probed 
> household features (e.g. construction materials used, number of household members), agricultrual practices (e.g. water usage), and assets (e.g. number
> and types of livestock). 
> 
> This is a real dataset, however, it has been simplified for this workshop.
> If you're interested in exploring the full dataset further, but you can 
> download it [from Figshare](FIXME add link) and work with it using exactly the same tools we’ll learn about today.  
{: .callout}


> ## Exercise
> 
> We're going to take a messy version of the SAFI data and describe how we would clean it up.
>
> 1. Download the data by clicking [here]().
> 2. Open up the data in a spreadsheet program. 
> 3. You can see that there are two tabs. Two field assistants conducted the surveys, one
in 2013 and one in 2014, and they both kept track of the data in their own way. Now
you're the person in charge of this project and you want to be able to 
start analyzing the data.   
> 4. With the person next to you, identify what is wrong with this spreadsheet. Also discuss the steps you would need to take to clean up the 2013 and 2014 tabs, and to put them all together in one spreadsheet. 
>
> **Important** Do not forget our first piece of advice, the
> create a new file (or tab) for the cleaned data, never
> modify your original (raw) data.
> 
> After you go through this exercise, we'll discuss as a group what was wrong
> with this data and how you would fix it. 
> 
> > ## Solution
> > - Take about 10 minutes to work on this exercise.
> > - All the mistakes in [02-common-mistakes](../02-common-mistakes) are present in the messy dataset. If
> > exercise is done during a workshop, ask people what they saw as wrong with
> > the data data. As they bring up different points, you can refer to [02-common-mistakes](../02-common-mistakes)
> > or expand a bit on the point they brought up.
> > - If you get a response where they've fixed the date, you can pause and go to the [03-dates-as-data](../03-dates-as-data) lesson. Or you can say you'll come back to dates at the end. 
> {: .solution}
{: .challenge}

An excellent reference, in particular with regard to R scripting is

> Hadley Wickham, *Tidy Data*, Vol. 59, Issue 10, Sep 2014, Journal of
> Statistical Software. [http://www.jstatsoft.org/v59/i10](http://www.jstatsoft.org/v59/i10).


