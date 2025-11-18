Readme file for The SAFI Teaching Database
Generated on 2019-09-19 for teaching purposes.

Recommended citation for the dataset: Woodhouse, Philip; Veldwisch, Gert Jan; Brockington, Daniel; Komakech,
Hans C.; Manjichi, Angela; Venot, Jean-Philippe (2018): SAFI Survey Results. doi:10.6084/m9.figshare.6262019.v1

## PROJECT INFORMATION

1. Title of dataset: The SAFI (Studying African Farmer-led Irrigation) Teaching Database

2. Author information:

  Principal Investigator
  Name: Philip Woodhouse
  Address: University of Manchester
  Email: [phil.woodhouse@manchester.ac.uk](mailto:phil.woodhouse@manchester.ac.uk)

  Co-Investigators:
  Name: Gert Jan Veldwisch
  Name: Daniel Brockington
  Name: Hans C Komakech
  Name: Angela Manjichi
  Name: Jean-Philippe Vernot

3. Data of data collection: November 2016 - June 2017

4. Funder Name: DFID-ESRC Growth Research Programme (DEGRP) grant ES/L01239/1

5. Publications:
  Farmer-led irrigation development and investment strategies for food security, growth and employment in
  Africa. Policy Brief. [www.safi-research.org/resources](https://www.safi-research.org/resources)

***

DATA ACCESS INFORMATION

***

1. Licences / restrictions placed on access to the dataset: CC0
  2: Access through figshare: doi:10.6084/m9.figshare.6262019.v1

***

METHODS OF DATA COLLECTION

***

1. Describe the methods for data collection and / or provide links to papers describing data collection methods:
  This is survey data relating to households and agriculture in Tanzania and Mozambique. The survey data was collected
  through interviews conducted between November 2016 and June 2017. This is a teaching version of the dataset,
  not the full version.

2. Instrument information:
  The survey was split into several sections:
  A - General questions about when and where the survey was conducted;
  B - Information about the household and how long they have been living in the area;
  C - Details about the accommodation and other buildings on the farm;
  D - Details about different plots of land they grow crops on;
  E - Details about how they irrigate the land and availability of water;
  F - Financial details including assets owned and sources of income;
  G - Details of financial hardships;
  X - Information collected directly from the smartphone (GPS) or automatically included in the form (InstanceID).

3. Data procesessing:
  The survey data was collected through interviews using forms downloaded to Android Smartphones. The survey forms were
  created using the ODK (Open Data Kit) software via an Excel spreadsheet. The collected data were then sent back to the server.
  The server can be used to download the collected data in both JSON and CSV formats.

4. Analysis methods:
  Descriptive and summary statistics were calculated using SPSS.

***

SUMMARY OF DATA FILES

***

1. List of data files:
  Filename: SAFI\_clean.csv
  Short description: CSV file containing the combined teaching data on one worksheet.

  Filename: SAFI\_messy.xlsx
  Short description: Excel file containing data for Tanzania and Mozambique recorded on separate worksheets
  and requiring data cleaning prior to anlysis.

  Filename: SAFI\_dates.xlsx
  Short description: Excel file containing date data for understanding how to format dates in spreadsheets.

2. Relationships between files:
  No official linkages between files.

***

DATA-SPECIFIC INFORMATION FOR SAFI\_clean.csv

***

1. Number of variables: 14

2. Number of cases: 131

3. Missing data codes: NULL

4. Variable list
  Variable name: key\_ID
  Variable description: Added to provide a unique ID for each observation 	(the InstanceID field does this as well)
  Variable coding/values: Numeric values
  Range of values: 1-202

  Variable name: village
  Variable description: Village name
  Variable coding / values: Text
  Range of values: God, Chirodzo, Ruaca

  Variable name: interview\_date
  Variable description: Date of interview
  Variable coding: Date YYYY-MM-DDTime
  Range of values: 2016-11-16 - 2017-06-04

  Variable name: no\_membrs
  Variable description: How many members live in the household?
  Variable coding: Numeric value (continuous)
  Range of values: 2 - 19

  Variable name: years\_liv
  Variable description: How many years have you lived in this, or a neighbouring village?
  Variable coding: Numeric value (years, continuous)
  Range of values: 1-96

  Variable name: respondent\_wall\_type
  Variable description: What type of walls are in the house?
  Variable coding: Text (categories)
  Range of values: burntbricks, muddaub, sunbricks, cement

  Variable name: rooms
  Variable description: How many rooms in the house are used for sleeping?
  Variable coding: Numeric value (continuous)
  Range of values: 1-8

  Variable name: memb\_assoc
  Variable description: Is the participant a member of an irrigation association?
  Variable coding: Yes / No / NULL

  Variable name: affect\_conflicts
  Variable description: Has the person been affected by conflicts with other irrigators in the area?
  Variable coding: Text (category)
  Range of values: once, more\_once, frequently, never, NULL

  Variable name: liv\_count
  Variable description: Livestock count
  Variable coding: Numeric value (continuous)
  Range of values: 1-5

  Variable name: items\_owned
  Variable description: Which of the following items are owned by the household (list provided)
  Variable coding: Text (string separated by semicolon)

  Variable name: no\_meals
  Variable description: How many meals do people in your household normally eat in a day?
  Variable coding: Numeric value (continuous)
  Range of values: 2-3

  Variable name: months\_lack\_food
  Variable description: Indicate which months, in the last 12 months where you have faced a situation when you did not have enough food to feed the household?
  Variable coding: Text (string separate by semicolon)
  Range of values: Month given in abbreviation or none

  Variable name: InstanceID
  Variable description: Unique identifier for the form data submission
  Variable coding: unique ID alpha-numeric string

***

DATA-SPECIFIC INFORMATION FOR SAFI\_messy.xlsx

***

1. Number of variables: 14 across two worksheets (Tanzania and Mozambique)

2. Variable list
  Variable name: key\_ID
  Variable description: Added to provide a unique ID for each observation (the InstanceID field does this as well)
  Variable coding/values: Numeric values
  Range of values: 1-202

  Variable name: roof\_type
  Variable description:  Type of roof on accommodation
  Variable coding / values: Text (categories)
  Range of values: grass, mabatisloping

  Variable name: wall\_type
  Variable description: Type of wall in accommodation
  Variable coding:  Text (categories)
  Range of values:  muddaub, burntbricks

  Variable name: floor\_type
  Variable description: Type of floor in accommodation
  Variable coding: Text (categories)
  Range of values: earth, cement

  Variable name: live\_stock\_owned\_and\_numbers
  Variable description: Type of livestock owned and total number owned
  Variable coding: Alpha numeric
  Range of values: 1-4, poultry, oxen, cows, goats

  Variable name: plots
  Variable description: Number of plots cultivated in the last 12 months
  Variable coding: Numeric (categories)
  Range of values: 1-4 and -999

  Variable name: water use
  Variable description: Do you bring water to your fields, stop water leaving your fields or drain water out of any of your fields?
  Variable coding: text (categories)
  Range of values: no, yes, Y, N, 1, 1, no (only in summer)

  Variable name: rooms
  Variable description: Number of rooms in the house used for seleeping
  Variable coding: Numeric
  Range of values: 1 - 4

  Variable name: oxen
  Variable description: Do you own oxen?
  Variable coding: Numeric binary
  Range of values: 0, 1

  Variable name: poultry
  Variable description: Do you own poultry
  Variable coding: Text
  Range of values: 1,2 Yes

  Variable name: goats
  Variable description:  Do you own goats?
  Variable coding: Text
  Range of values: 1, 0, No

  Variable name: cows
  Variable description: Do you own cows?
  Variable coding: Text
  Range of values: 1,0, Yes

  Variable name: total
  Variable description:Total number of livestock owned
  Variable coding: Numeric (continuous)
  Range of values: 1-4

  Variable name: look after cows
  Variable description: Does the participant look after cows?
  Variable coding: Yes / No

***

DATA-SPECIFIC INFORMATION FOR SAFI\_dates.xlsx

***

1. Number of variables: 14 across two worksheets (DD\_MM\_YEAR and MM\_DD\_YEAR)

2. Variable list
  Variable name: Interview dates
  Variable description: Date that interview took place
  Variable coding/values: Date
  Range of values: DD-MM-YYYY or MM\_DD\_YYYY depending on spreadsheet

  Variable name: years\_farm
  Variable description: Number of years the household have been farming in this area
  Variable coding / values:
  Range of values:

  Variable name: parents\_live
  Variable description: Did your parents live in this village or neighbouring village?
  Variable coding:  Yes / No
  Range of values:  Yes / No

  Variable name: no\_membrs
  Variable description: How many members live in your household?
  Variable coding: Numeric value
  Range of values: 2 - 19

  Variable name: roof\_type
  Variable description: Type of roof on the accommodataion
  Variable coding: Text (categories)
  Range of values: grass, mabatisloping

  Variable name: respondent\_wall\_type
  Variable description: Type of wall in the accommodation
  Variable coding: Text (categories)
  Range of values: burntbricks, muddaub, sunbricks, cement

  Variable name: floor\_type
  Variable description: Type of floor in the accommodation
  Variable coding: Text (categories)
  Range of values: earth, cement
