# make_sheets Code
## Creating Datasets

#### Purpose: 
> ##### Importing files, extracting data, and creating a set of datasheets for lab use.

<br>

#### Inputs: 
> ##### .csv file (NAMED IN FORMAT SPECIFIED) with Sample ID information in "Student_Lists" folder
- Naming format: (Initials)_(StudyAbbreviation).csv
- Example: RV_PYN.csv

> ##### User input (when prompted) of how many samples will be run per set

<br>

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

<br>

#### Author: Rachel Veenstra
#### Date Created: 03-29-2019

<br>
<br>
<br>

# data_screening Code
## Quality Screening

#### Purpose: 
> ##### Importing files, extracting data, and screening completed datasheets for quality parameters.
> ##### Runs through sheets on a folder-by-folder basis to keep each topic/study subset separate.

<br>

#### Inputs: 
> ##### Completed lab .csv files (NAMED IN FORMAT SPECIFIED) in topic folder in "Lab_Sheets" folder
- Naming format: (Repetition)_(Set#)_(AnalysisType)_(Initials)_(StudyAbbreviation)_(topic/studysubset)_(date).csv
- Example: A_1_NIT_RV_PYN_MO_04_18_19.csv

> ##### Created folder named "Completed" in topic folder with completed lab sheets. 

<br>

#### Output:
> ##### Files moved to "Completed" folder within topic folder after running.
> ##### Files with curves of unacceptable r-squared renamed as "x_BAD_CURVE....".csv.
> ##### Samples in sheets with bad curves, and any samples with unacceptable variance between original and duplicates used to create datasheets for re-running.
> ##### Set of datasheets saved in topic folder of "Lab_Sheets" folder that are:
- Comprised of four columns

>>1) Data type : Contains class information given as B (blank), C (curve), O (original sample), or D (duplicated sample)

>>2) Sample_Wt(g) : Contains blank cells for lab to fill (unit = grams)

>>3) Sample_ID : Contains identification information for blanks, curve values, and *DUPLICATED* Sample ID values from list to be re-run

>>4) Absorbance : Contains blank cells for lab to fill

>- Separated based on identified set size
>> - Standard curve (C) values unique to analysis type
- Uniquely named based on name of original .csv file, repetition, set number, analysis type

<br>

#### Author: Rachel Veenstra
#### Date Created: 04-05-2019