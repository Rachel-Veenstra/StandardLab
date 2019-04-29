# StandardLab Coding Documentation
### Purpose, Inputs, Outputs, Authors, & Updates
<br>

## **_Ureides and Nitrates:_**
> #### **Correct Order for Code-Flow**
> - 1) make_sheets
> - 2) lab_checks *(optional)*
> - 3) data_screening
> - 4) ure_nit_concentration

<br>
<br>

### 1) **_'make__sheets' Code_**

> #### Purpose: 
>> ##### Importing files, extracting data, and creating a set of datasheets for lab use.

<br>

>#### Inputs: 
>> ##### .csv file (NAMED IN FORMAT SPECIFIED) with Sample ID information in "Student_Lists" folder
>>>- Naming format: (Initials_Location_StudyAbbreviation)
>>>- Example: RV_MAN_CTS.csv

>> ##### User input (when prompted) of how many samples will be run per set

<br>

>#### Output:
>> ##### Set of datasheets in Lab_Sheets folder that are:
>>- Comprised of four columns

>>>1) Data type : Contains class information given as B (blank), C (curve), O (original sample), or D (duplicated sample)

>>>2) Sample_Wt(g) : Contains blank cells for lab to fill (unit = grams)

>>>3) Sample_ID : Contains identification information for blanks, curve values, and *DUPLICATED* Sample ID values from .csv file provided

>>>4) Absorbance : Contains blank cells for lab to fill

>>- Separated based on identified set size
>>- Duplicated for ureide and nitrate analysis
>>> - Standard curve (C) values unique to analysis type
>>- Uniquely named based on name of original .csv file, set number, analysis type

<br>

>#### Author: Rachel Veenstra
>#### Date Created: 03-29-2019
>#### Date Updated: 04-26-2019

<br>
<br>
<br>

### 2) **_'lab__checks' Code_**

> #### Purpose: 
>> ##### Simple scan for informational evaluation of set quality - as requested by lab technicians. **For more detailed information on selected quality screening parameters, click [here](https://github.com/Rachel-Veenstra/StandardLab/blob/master/Additional_Documentation/Screening_Params.md).**

<br>

>#### Inputs: 


>> ##### User input (when prompted): name of ONE lab sheet to be scanned.
>>>- Example: *A_1_URE_RV_MAN_CTS_04_26_19*
>>>- DO NOT include .csv when passing file name.
>>>- Code with automatically navigate to correct folder based on file name.

<br>

>#### Output:
>> ##### Printed analysis of blanks, curve, corrected curve, and individual sample variance.
>>>- Example: A_1_URE_MS_GH_LI_06_25_18

>>> ```This sheet has the following properties:```<br>
```- Acceptable blank readings.```<br>
```- A calibration curve r-squared value of 0.8999.```<br>
```- A CORRECTED curve r-squared value of 0.9527.```<br>
```- Greater than 10% variance in 1 sample(s).```


<br>

>#### Author: Rachel Veenstra
>#### Date Created: 04-17-2019
>#### Date Updated: 04-26-2019

<br>
<br>
<br>

### 3) **_'data__screening' Code_**

>#### Purpose: 
>> ##### Importing files, extracting data, and screening completed datasheets for quality parameters. **For more detailed information on selected quality screening parameters, click [here](https://github.com/Rachel-Veenstra/StandardLab/blob/master/Additional_Documentation/Screening_Params.md).**

>> ##### Runs through sheets on a folder-by-folder basis to keep each topic/study subset separate.

<br>

>#### Inputs: 
>> ##### Completed lab .csv files (NAMED IN FORMAT SPECIFIED) in topic folder in "Lab_Sheets" folder
>>- Naming format: (Repetition_Set_AnalysisType_Initials_Location_Experiment_Date).csv
>>> - Example: A_1_NIT_RV_PYN_MO_04_18_19.csv

>> ##### Created folder named "Completed" in topic folder with completed lab sheets. 

<br>

>#### Output:
>> ##### Files moved to "Completed" folder within topic folder after running.
>> ##### Files with curves of unacceptable blank values renamed as "x_BAD_BLANKS....".csv.
>> ##### Files with curves of unacceptable r-squared renamed as "x_BAD_CURVE....".csv.
>> ##### Samples in sheets with bad curves, and any samples with unacceptable variance between original and duplicates are identified and used to create datasheets for necessary repetitions.
>> ##### Set of new datasheets saved in topic folder of "Lab_Sheets" folder that are:
>>- Comprised of four columns

>>>1) Data type : Contains class information given as B (blank), C (curve), O (original sample), or D (duplicated sample)

>>>2) Sample_Wt(g) : Contains blank cells for lab to fill (unit = grams)

>>>3) Sample_ID : Contains identification information for blanks, curve values, and *DUPLICATED* Sample ID values from list to be re-run

>>>4) Absorbance : Contains blank cells for lab to fill

>>- Separated based on identified set size
>>> - Standard curve (C) values unique to analysis type
>>- Uniquely named based on name of original .csv file, repetition, set number, analysis type
>>> - Example: B_1_URE_RV_MAN_CTS_00_00_00.csv
>>> - B (second repetition), 1 (first set), URE (ureides analysis), RV_MAN_CTS (student and study), 00_00_00 (date template)

<br>

>#### Author: Rachel Veenstra
>#### Date Created: 04-05-2019
>#### Date Updated: 04-26-2019
<br>
<br>

### 4) **_'ure__nit__concentration' Code_**

>#### Purpose: 
>> ##### Importing and extracting data from completed, screened datasheets. **For more detailed information on selected quality screening parameters, click [here](https://github.com/Rachel-Veenstra/StandardLab/blob/master/Additional_Documentation/Screening_Params.md).**

>> ##### Runs through sheets on a folder-by-folder basis to keep each topic/study subset separate.

<br>

>#### Inputs: 
>> ##### Completed lab .csv files (NAMED IN FORMAT SPECIFIED) in topic folder in "Lab_Sheets" folder
>>- Naming format: (Repetition_Set_AnalysisType_Initials_Location_Experiment_Date).csv
>>> - Example: A_1_NIT_RV_PYN_MO_04_18_19.csv

>> ##### Original list of sample id's from "Student_Lists/Completed" folder.

<br>

>#### Output:
>> ##### Set of two results sheets for each experiment/location (one for ureides and one for nitrates) saved in new folder (named based on experiment) in "Results" directory that are:
>>- Comprised of two types of columns:

>>>1) Sample_ID : Contains identification information for blanks, curve values, and *DUPLICATED* Sample ID values from list to be re-run

>>>2) Concentration : Calculated ureide or nitrate concentration (extrapolated from curve absorbances and corrected by blank values)

>>- Concentration columns are named based on the sheet from which data in that column was taken to allow for easy checks of "off-data" in the results sheet.

>>- All acceptable readings for each sample are shown, including those with greater than 10% variance (because blanks and curve of set passed screening process). These type of samples are flagged with an "x_" on the final sheet.

>>> - Example: "x_97.0345" would have a variance of greater than 10% between original and duplicate samples. 

>>> - To find the original data for this sample/reading, one would go to the sheet indicated at the top of the column this value was found in.

<br>

>#### Author: Rachel Veenstra
>#### Date Created: 04-11-2019
>#### Date Updated: 04-26-2019