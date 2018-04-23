---
title: "Quality control"
teaching: 10
exercises: 5
questions:
- "How can we carry out basic quality control and quality assurance in spreadsheets? "
- "What spreadsheet aids are available to assist me when inputting data?"
objectives:
- "Use data validation on input"
- "Use the Excel Data Entry form"
keypoints:
- "In general you can type any kind of data into any cell in a spreadsheet"
- "Excel does provide tools which allow you to restrict the type of data and ranges of values you can enter"
- "Using Excel tables can make data entry simpler, by automatically inserting new rows complete with data validation rules when needed"
---

## Validating data on input

By default you can type any kind of nonsense into any cell of a spreadsheet.

When we are populating data tables however there is the expectation that values in a given column will 
be of a specific type at least.

It is quite possible that the nature of the data table will allow us to further limit the acceptable values for the cells in a column.

For example a column recording age certainly should be numeric, greater than 0 and unlikely to be greater than 120.

Excel allows the user to specify a variety of data validations to be applied to a cell content. If the validation fails then an error is raised and the cell is not populated.

Although validation is not applied retrospectively, if a cell to which validation has subsequently been applied contains a value which would fail the validation, then a green triangle is placed in the top left corner of the cell as a warning but the value in the cell is not removed.

Details of the different types of validation possible and how to set them up are available at this [link](https://support.office.com/en-us/article/Apply-data-validation-to-cells-29FECBCC-D1B9-42C1-9D76-EFF3CE5F7249)

We will look at a couple of simple examples.

1. Restrict data to a numeric range
2. Restrict data to entries from a list



### Restrict data to a numeric range

1. select the cell or cells for which you wish to apply the restriction
2. In the Data Tools section of the Data tab select Validation tools.

![Data_validation_01](../fig/spreadsheets_Data_validation_01.png)

3. From the Allow drop down box select 'Whole number'. 
4. The window content will change. The value in the data box will say 'between' and Min and Max boxes
will be provided for you to specify a range 

![Data_validation_02](../fig/spreadsheets_Data_validation_02.png)

5. Fill in the min and max values as you like and click OK
6. In you selected cell try putting in a value within your chosen range and then outside the range.
   In the first instance the value will be accepted and in the second an error message will be produced.
   
![Data_validation_03](../fig/spreadsheets_Data_validation_03.png)



### Restrict data to entries from a list


1. select the cell or cells for which you wish to apply the restriction
2. In the Data Tools section of the Data tab select Validation tools.
3. From the Allow drop-down box select 'List'. 
4. The window will change to include a Source box.
![Data_validation_04](../fig/spreadsheets_Data_validation_04.png) 
5. In the source box you can type a comma separated list of values that you want to accept. Then click OK.
6. The cell which has had the data validation applied to it will now have a drop-down arrow against it (when the cell is selected). When you click the arrow you will be able to select a value from your list. If you simply type a value which is not on the list you will get an error message.
  
Typing a list of values for simple choices like True and False or Red, Amber, Green might be convenient, if the list is longer it makes sense to create the list as a small table (in a separate tab of the workbook), give the table a name and then reference the table name as the source in the Source box.

Using a table in this way makes the process more flexible. If you add or remove contents from the table, then these are immediately reflected in any *New* cell entries based on this source. You can also have different cells refer to the same source.


## Creating tables for data entry

Using the data validation functionality of Excel is a very powerful way of reducing erroneous data being entered into your data table.

You may have spotted a slight flaw in the plan though.

> ## Discussion  
> 
> What makes the processes described above somewhat impractical?
> 
> > ## Solution
> > 
> > The validation needs to be applied to each cell or cells in advance. Instead of selecting individual cells, you can select a complete column. Even if the first row contains a column name, as the validation is not applied retrospectively, this will not cause a problem.
> {: .solution}
{: .discussion}

A better way to apply data validation on data entry is to create a proper data table in Excel.

To do this;

1. In the top row of an empty worksheet (because you only want one table per worksheet) type in the column names for your data, in the order in which you expect to enter them.
2. On the next row select the cell in the column for which you wish to apply data validation
3. Set up the appropriate validation for this cell and repeat for any cells in the second row whose columns  you wish to apply data validation to.
4. Select a cell in the top row and from the Insert menu bar select Table from the Tables section.
![Data_validation_05](../fig/spreadsheets_Data_validation_05.png) 
5. Check the box 'My table has header' and extend the size of the table from one row to two by changing the last 1 to a 2. Then click OK.
6. A table will be created with your column headings and a single blank row beneath them. 
7. You can enter data into this blank row. Any cell which has data validation set up for it will be restricted in accordance with the data validation you set up.
8. When you have entered data into the last column of the table and hit the Tab key, a new row of the table will be created and the cursor will be placed in the first column of it. 
9. In this new row and all subsequent rows added to the table, the data validation for all of the columns originally set up with data validation will be repeated.



## The Excel Data Entry form

In older versions of Excel there was a data entry form which allowed you to input single records (rows of data) by completing a pop-up form. Although this is still available it does not appear on the default menu and toolbars. The basic functionality of inserting rows is essentially superseded by the use of defined tables and entering data directly into them as we have done in steps 7 and 8 above. The above method has the advantage of stopping data entry as soon as you try to place invalid data in a cell covered by a data validation rule.

In the old Data entry form the data validation rules were only checked when a compiled record was being inserted. 





