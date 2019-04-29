# StandardLab Data Screening Parameters


## **"data_screening" code:**

To ensure data quality, standardize processes for repeatability, and establish criteria for the purpose of bias removal in spec data analysis, the following benchmarks have been set for screening the quality of ureide and nitrate datasheets:

### Blanks
- A "good" blank will have a value > -0.10 and < 0.10.
- Of the four blanks in a set, at least two need to be "good" so an average can be determined.
- If there is one "bad" blank, it can be removed and the average taken of the other three "good" blanks.
- If there are two "bad" blanks, they can be removed and the average taken of the remaining two "good" blanks.
- If there are NOT two "good" blanks, the set needs to be re-run because it has no good "base values" for final concentration calculations.

_(See flow chart below for illustrations)_


### Curves
- A "good" curve will have an r<sup>2</sup> value > 0.95.
- Of the 12 initial curve points, 10 of them must produce a "good" curve.
- If the r<sup>2</sup> value of all 12 points is not "good": 
>- Decision matrix calculates all possible r<sup>2</sup> values removing one of the curve points.
>- If the highest possible r<sup>2</sup> value of 11 points is not "good":
>>- Decision matrix calculates all possible r<sup>2</sup> values removing two of the curve points.
>>- If the highest possible r<sup>2</sup> value of 10 points is not "good", set needs to be re-run because the curve data is not reliable for final concentration calculations.

### Samples
- A "good" sample will have a difference of < 10% between original and duplicate readings.
- **Variance = ( ( Absorbance**<sub>*MAX*</sub> **- Absorbance**<sub>*MIN*</sub>**) / Absorbance**<sub>*MAX*</sub> **) x 100%**
- A sample with > 10% difference will be re-run.
- _However_, the initial "bad" sample reading is calculated for concentration and included in the final datasheet for student viewing, but flagged as such ("x_"). There are several reasons for this:
>- The samples were run on a good curve with good blanks.
>- "The 10% Rule" may not be the best parameter for determining which samples need to be run again. (*Example: Variance between very low readings*)


### ***"data__screening"* Code Flow Chart**

![alt text](https://github.com/Rachel-Veenstra/StandardLab/blob/master/Additional_Documentation/data_screening_work_flow.png "data-screening Code Flow Chart")

Author: Rachel Veenstra

Created: April 2019
