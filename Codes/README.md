# make_sheets Code
## Creating Datasets

#### Purpose: 
> ##### Importing files, extracting data, and creating a set of datasheets for lab use.

#### Inputs: 
> ##### .csv file (NAMED IN FORMAT SPECIFIED) with Sample ID information in "Student_Lists" folder
- Naming format: (Initials)_(StudyAbbreviation).csv
- Example: RV_PYN.csv

> ##### User input (when prompted) of how many samples will be run per set

#### Output:
> ##### Set of datasheets in Lab_Sheets folder that are:
- Comprised of four columns

>>1) Data type : Contains class information given as B (blank), C (curve), O (original sample), or D (duplicated sample)

>>2) Sample_Wt(g) : Contains blank cells for lab to fill (unit = grams)

>>3) Sample_ID : Contains identification information for blanks, curve values, and *DUPLICATED* Sample ID values from .csv file provided

>>4) Absorbance : Contains blank cells for lab to fill

>- Separated based on identified set size
>- Duplicated for ureide and nitrate analysis
>> - Standard curve (C) values unique to analysis type
- Uniquely named based on name of original .csv file, set number, analysis type

#### Author: Rachel Veenstra
#### Date Created: 03-29-2019
