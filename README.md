# ![](./images/GA-logo.png) Project 1: Optimising Hospital Resourcing based on Weather Conditions

## Overview

Weather has been long associated with a variety of human health impact, from frostbite due to extreme cold temperatures to dehydration and heat exhaustion due to prolonged exposure to high temperatures. Singapore's tropical climate is no stranger to heat-related health incidents, including heat cramps, heat stroke or even death.

Even as Singapore's climate can be described as always hot, there are certain parts of the year or day when temperatures can be more uncomfortable, potentially causing more health incidents. It is thus important for hospitals to plan and be prepared for higher case loads of health incidents during specific parts of the year or day.

---

## Problem Statement

The CEO of a local acute hospital wants to be better prepared in dealing with surges of health incidents due to fluctuations in Singapore's weather, especially since such health incidents are expected to rise as the climate gets hotter due to global warming. He has tasked us to identify periods of the year when the weather would cause higher numbers of hospital admissions, so that he can allocate medical and manpower resources more efficiently.

This project attempts to examine the trends and relationship of the various weather variables (e.g., temperature, humidity, rainfall etc.) with human health incidents (i.e., hospital admissions), and identify fluctuations which can be a good guide for the hospital in allocating resources.

---

## Datasets

### Weather Data

There are 7 weather datasets in the `data` folder for this project, obtained from [data.gov.sg](https://data.gov.sg/). These are:

* [`rainfall-monthly-number-of-rain-days.csv`](./data/rainfall-monthly-number-of-rain-days.csv): Monthly number of rain days from 1982 to 2022. A day is considered to have “rained” if the total rainfall for that day is 0.2mm or more.
* [`rainfall-monthly-total.csv`](./data/rainfall-monthly-total.csv): Monthly total rain recorded in mm(millimeters) from 1982 to 2022
* [`rainfall-monthly-highest-daily-total.csv`](./data/rainfall-monthly-highest-daily-total.csv): Maximum rainfall in a day recorded for each month from 1982 to 2022
* [`surface-air-temperature-monthly-mean.csv`](./data/surface-air-temperature-monthly-mean.csv): Monthly mean air temperature from 1982 to 2022
* [`surface-air-temperature-monthly-mean-daily-maximum.csv`](./data/surface-air-temperature-monthly-mean-daily-maximum.csv): Monthly mean of daily maximum air temperature from 1982 to 2022
* [`wet-bulb-temperature-hourly.csv`](./data/wet-bulb-temperature-hourly.csv): Hourly wet-bulb temperature from 1982 to 2022
* [`sunshine-duration-monthly-mean-daily-duration.csv`](./data/sunshine-duration-monthly-mean-daily-duration.csv): Monthly mean sunshine duration in hours from 1982 to 2022


### Human Health Data

There are 2 human health datasets in the `data` folder for this project, obtained from [SINGSTAT TABLEBUILDER](https://tablebuilder.singstat.gov.sg/). These are:

* [`Monthly Hospital Admissions Public Sector Outpatient Attendances And Day Surgeries.csv`](./data/Monthly&#32;Hospital&#32;Admissions&#32;Public&#32;Sector&#32;Outpatient&#32;Attendances&#32;And&#32;Day&#32;Surgeries.csv): Monthly number of various types of hospital admissions from 1982 to 2022.
* [`Monthly Deaths By Ethnic Group And Sex.csv`](./data/Monthly&#32;Deaths&#32;By&#32;Ethnic&#32;Group&#32;And&#32;Sex.csv): Monthly number of deaths from 1982 to 2022.

### Merged Data

The final merged weather and health dataset is in the `data` folder:

* [`Monthly Weather Health Dataset.csv`](./data/Monthly&#32;Weather&#32;Health&#32;Dataset.csv): Merged dataset for EDA.

---

## Technical Report

The technical report is split into 2 parts in the `code` folder for this project. These comprise -
- [`data_preprocessing.ipynb`](./code/data_preprocessing.ipynb): A Jupyter notebook that cleans and merges the weather and human health dataset by date.
- [`data_analysis.ipynb`](./code/data_analysis.ipynb): A Jupyter notebook that describes the data with visualizations & statistical analysis.

---

## Conclusions & Recommendations

1. Weather plays a part in the expected resourcing needed for the hospital in part due to the number of emergency cases (and by extension admissions and deaths which are highly correlated) associated with different weather conditions during different periods of the year. A combination of uncharacteristic weather conditions can also have an impact on the number of emergency cases.

2. To summarise the analysis, higher resourcing should be prepared under these circumstances:
    - Mean air temp and sunshine are higher than usual for any given month (i.e. in highest quartile). This is likely related to higher risk of heat-related injuries due to higher temperatures and sun exposure.
    - Max wet-bulb temp is lower than usual for any given month (i.e. in lowest quartile). This is likely due to strong negative correlation between air temp and wet-bulb temp, given that scientific literature suggests higher wet-bulb temp to be more associated with heat-related incidents due to increasing difficulty of the human body to cool down when both humidity and temperatures are high (i.e. higher wet-bulb temp).
    - In months of Feb, Mar and Jul, particularly when mean air temp is higher than usual.
   
   <br>

3. On a brighter note, lower resourcing can be prepared under these circumstances:
    - In the month of Jun, when sunshine hours is higher than usual and mean air temp is lower than usual.


