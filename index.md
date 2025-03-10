---
layout: default
---
# RE 397 Lab Section A

[![.github/workflows/ci.yaml](https://github.com/pages-themes/architect/actions/workflows/ci.yaml/badge.svg)](https://github.com/pages-themes/architect/actions/workflows/ci.yaml) [![Gem Version](https://badge.fury.io/rb/jekyll-theme-architect.svg)](https://badge.fury.io/rb/jekyll-theme-architect)

![Thumbnail of Architect](https://www.thebalancemoney.com/thmb/FPww6Q4c7FzgNtwa0DA_lLEO160=/750x0/filters:no_upscale():max_bytes(150000):strip_icc():format(webp)/real-estate-what-it-is-and-how-it-works-3305882-1f1ca22206274467862367e2dc59f25b.png)

## Introduction

About myself.

[Welcome to connect me on Linkedin](https://www.linkedin.com/in/zhongmin-luo-9b5400221/)


## Announcement
1. Grading policy
2. According to Canvas schedule this Lab session takes up 110 minutes, but it usually finishes up within 90 minutes.
3. I will set up a regular office hour on Friday between 2:00pm - 3:00 pm via [Zoom](https://washington.zoom.us/j/95676546990) to answer lab questions.
4. Lab will be recorded and you will find recording link on this webpage later!!

## Discussion: Why Data Modeling? 
![attachsytem](attachsystem.png)

## Lab 1
*January 14, 2025*
### Organize dataset
1. Assignment folder
### Download dataset
1. Net migration share
> Go to [Census annual net migration data and population estimates](https://www.census.gov/data/tables/time-series/demo/popest/2020s-total-metro-and-micro-statistical-areas.html)
Find **cbsa-est2023-alldata**
2. Population change rate
> same step as net migration share
3. Share of recent constructed residential
> select the table **Table B25127** then the year of 2023, then under “Geographies” -> “Metropolitan/Micropolitan Statistical Area” -> all metropolitan statistical areas in the US and PR

### A Few Reminders 
1. **When you are downloading dataset from the Census website, you should click `ZIP` because using the zip option, the data format will come the way we need for this project. You do not need to remove the MOE or Transpose before downloading, although doing so will not have any issue for the final results.**
2. “OCC_Tittle” in the section of "Employment" is just a column name in the dataset. You do not need to worry about that for Lab1. This is for Thursday or next week’s lab.
3. we use `2020 5-year estimate` which is inconsistent with `2023 1-year estimate` because of COVID, the survey response was extremely low and `margin of error` was too high in many places to generate reliable/meaningful estimates, that is why Census only published `5-year estimates` for 2020.

## Lab 2
*January 21, 2025*
### Questions for Practice 4 (30mins)
### Assignment 1 continue
1. Share of recent constructed residential units
* First, you should find these three variables **`Estimate!!Total:`	`Estimate!!Total:!!Owner occupied:!!Built 2020 or later:`	`Estimate!!Total:!!Renter occupied:!!Built 2020 or later:`** from `B25127` you downloaded from ACS website.
![see](B25127.png)
* Second, Create 5-digit MSA ID based on GEOID from the Census ACS downloads. Use Excel formula “=right([CELL], 5)” to extract the last 5 digit of each GEOID. You will need to use this as the common field to join other datasets. After converting, a best practice is to copy and paste value in the same column, and convert text to number
* calculate Share of recent constructed residential unites using the formula:
> (“Owner occupied:!!Built 2020 or later:” + “Renter occupied:!!Built 2020 or later:”) / “Total:”
Your calculation should be like ![this](sharecal.png)

2. Price Rent Ratio
* remember you should have two different dataset downloaded from ACS website. ![Look](pricetorent.png)
* copy and paste `Estimate!!Median value (dollars)`	`Estimate!!Median gross rent` data **separately** on your sheet
* For each data table, create numeric `GEOID` as we do in the second step in Share of recent residential unit above.
* create another next to your Median Value column called Median Gross Rent.
* Use VLOOKUP function to join the Median Gross Rent data to Median Value data. Below is the detail of VLOOKUP function in excel. You can also look at this [video](https://www.youtube.com/watch?v=xIynD1gFOLo).
* Finally calcuate Price rent ratio using the formula:
>“Median value (dollars)” / (“Median gross rent” * 12)
** Be care of bracketing median gross rent multiplied by 12**
Your result should look like ![this](pricerent.png)

**VLOOKUP=(lookup_value, table_array, col_index_num, [range_lookup])**
1. lookup_value
The value you want to search for in the first column of the table_array.
2. table_array
The range of cells (e.g., *A1:D10*) containing the data. The first column of this range is where lookup_value will be searched.
3. col_index_num
The column number (starting from 1 for the first column of table_array) from which the value will be returned.
5. [range_lookup] (Optional)
A logical value that specifies whether you want an exact match or an approximate match:
TRUE (or omitted): Finds the closest match that is less than or equal to the lookup_value. The first column must be sorted in ascending order.
FALSE: Finds an exact match. If no exact match is found, the function returns #N/A.


### Lab 3
*1.28.2025*
1. Poll Everywhere: Learn feedback from students.
2. Professor Wang's lab recording is available [here](https://washington.zoom.us/rec/share/hVrUHCj2BcmUEB78oV0v_OZ9Lo7S_YPp3aPZkzYJvQCEBaAwbNxPjfMDBRb7ZGjX.J75yRutD1-2UMLwb)
## Continue on the rest of four measures!
1. Rent change rate
* Copy and paste dataset of 2020 and 2023 Table 25064
* Create GEOID for both dataset
* Calculate inflation rate for `B25064_001E`
* VLOOKUP data. Join 2020 inflation-adjusted dataset to 2023 dataset as we did last week.
* Calculate rent change by
> (2023 median rent – 2020 inflation-adjusted median rent) / 2020 inflation-adjusted median rent

2. Employment change rate
* Filter “OCC_TITLE” (column J) = All Occupations in 2020 and 2023 employment dataset
* Copy and paste data
* VLOOKUP one dataset to the other
* Calculate based on formula:
> (2023 employment count – 2020 employment count) / 2020 employment count

3. Your turn!
4. Change in percentage of renters
* Find `Estimate!!Total:`and `Estimate!!Total:!!Renter occupied!`in 2020 and 2023 TableB25003.
* Copy, paste and create GEOID as usual.
* Calculate percentage of rent change in 2023 and 2020 respectively
> Estimate!!Total:!!Renter occupied_23/Estimate!!Total
* VLOOKUP join percentage of rent change in one year to the other year.
* calculate change based on formula:
> pct_rent_23 -pct_rent_20

### You are almost done!! YEAHHHHHH!

### Lab5
*2.4.2025*
## Resume unfinished Practice7
## Discussions
1. Assignment1
2. Z score and probability
## Assignment2 starts

### Lab 6
*2.11.2025*
## VLOOKUP Function Problem
1. try to use absolute reference like this
    `=VLOOKUP(A2, track!$A:$C, 3, 0)`
2. autofill manually together
## Remove incomplete data
1. Know function `if count`
2. Create a new column and use `=IF(COUNT(E2,F2,Q2,S2,AE2,AG2)=6,0,1)` to check whether variables below have complete information or not.
- "Number of Units", "Star Rating", "Avg Unit SF", "Avg Asking/Unit", "Year Built", "Number of Stories"
2. Under `Check` column, filter **0**.
3. You are supposed to have around 4305 observations after filtering.
## Remove duplicate 
1. Copy and paste these 4305 observations to a new sheet
2. Select `property address` column and use `Conditional Formatting` to hightlight duplicate data.
3. Filter by color pink.
4. Select `Ascending` if necessary.
5. Now you should have around 196 duplicate data and you need to remove them.
6. Select both `property address` and `property name` column and use `Remove Duplicate`
7. Clear filter by color
8. Now you are supposed to have around 42xx observations. (Any number of observations around this number is fine).
## Assess completeness
1. Copy and paste these **"Number of Units", "Avg Unit SF", "Avg Asking/Unit", "Year Built", "Number of Stories"** of 42xx observations, to a new sheet called "assess completeness" (or whatever you want to call).
2. Go back to the step of "Remove incomplete data" and filter **1**
3. After you filter **1**, you will have around 2130 observations.
4. Copy and paste **"Number of Units", "Avg Unit SF", "Avg Asking/Unit", "Year Built", "Number of Stories"** of 2130 observations, to the same sheet.
> You can do this step with two methods. One just copy and paste it to "assess completeness" and then do the t-test. Second, you besides independent and dependend variables, copy and paste "Property Address" and "Property Name" as well. Then remove duplicate data as what we do in the step of "Remove duplicate".
5. Open your Data Anlysis tool and select `t-Test: Two-Sample Assuming Equal Variances` and select the column of variable you want to compare, like ![below](ttest1.png). (Here I am comparing `Year Built` variable and you should do the rest of other variables)
## Correlation
1. Create a new sheet, copy and paste 42xx observations with complete and also non-duplicate data to it.
2. You should have following variables:
- "Number of Units", "Star Rating", "Avg Unit SF", "Avg Asking/Unit", "Year Built", "Number of Stories"
4. Open your Data analysis tool and select `correlation` and inser things like ![below](corre.png).
## Simple Regression
1. Select "Star Rating" column and go to Insert tab and select `Pivote Table`.
2. PivotTable Fields window will pop up.
3. Drag "Star Rating" and `Rows` and `Values`. When Draging Star Rating to Values, right click "Sum of Star Rating" and change the ![filed setting](field.png). You want to count the number of star rating not summarize all of them. ![1](coun.png]
4. Get rid of Star Rating **1** because it violates the assumption that you should have enough observations for each category. ![uncheck](uncheck1.png).
5. Open Data analysis and select regression. This time `Star Rating` will be independent variable and Avg `Asking/Unit` is dependent variable.
6. Create k-1 dummies. So insert 3 new columns by "Star Rating" column.
7. Use `if function`, like `IF(B2=3, 1,0`), which means if cell B2 equals to 3, the new cell will be 1, otherwise it goes to 0. ![dummy](dummy.png). Here our reference category is **star rating 2**.
8. Run the regression again but this time your should change your input x range, like ![below](dum2.png)
9. Now to answer the question, consider what those coefficients of three Star rates stand for? You need to calculate difference between Star 3 to Star 2, Star 4 to Star 3, and Star 5 to Star4. ![diff](diff.png).
## Multivariate
1. copy and paste same date in simple regression step but remove Star Rating column that Star Rating serves as numeric variable.
2. Run regression again and remember select residule. ![mul](multi.png). 
