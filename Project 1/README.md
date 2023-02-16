<img src="http://imgur.com/1ZcRyrc.png" style="float: left; margin: 20px; height: 55px">

# Project 1: Optimising Resources at the Museum to Cater for Changes in Visitor Attendance Due to Weather Conditions

### Overview

Weather can be a key concern for visitors when choosing a place of interest to visit, when preparing their trip and during their stay. Singapore's tropical climate with abundant rainfall, high and uniform temperatures and high humidity all year round, could influence museum-going behaviours. It is thus valuable to examine how Singapore's weather conditions influence attendance at the museums so that the museums can better cater resources (e.g. schedule more docents on days with expected high footfall to provide more guided tours,...).  

---

### Problem Statement

The CEO of a local museum consortium would like to understand periods of the year when the weather conditions would be associated with higher attendance, to facilitate resource allocation.

As seen from various research, attendance is expected to be affected by weather conditions. The CEO has tasked us to identify how attendance at the museum is associated with weather conditions and identify relevant periods to step up resources.

This project attempts to examine the trends and relationships of various weather variables (e.g. temperature, humidity, rainfall,..) with attendance to a few indoor and outdoor attractions, in particular the museums. The aim is to identify observations guiding the museums in allocating resources and refining its programmes, and to understand the effect on complementary leisure activities.

---

### Datasets

#### Weather Data

There are 7 weather-related datasets included in the [`data`](./data/) folder for this project, obtained from [data.gov.sg](https://data.gov.sg/).

These are:
* [`rainfall-monthly-highest-daily-total.csv`](../data/rainfall-monthly-highest-daily-total.csv): The maximum amount of rainfall within a day for each month from 1982 to 2022. 
* [`rainfall-monthly-number-of-rain-days.csv`](./data/rainfall-monthly-number-of-rain-days.csv): Monthly number of rain days from 1982 to 2022. A day is considered to have “rained” if the total rainfall for that day is 0.2mm or more.
* [`rainfall-monthly-total.csv`](./data/rainfall-monthly-total.csv): Monthly total rain recorded in mm(millimeters) from 1982 to 2022
* [`sunshine-duration-monthly-mean-daily-duration.csv`](https://data.gov.sg/dataset/sunshine-duration-monthly-mean-daily-duration): Monthly mean sunshine duration in hours from 1982 to 2022
* [`surface-air-temperature-monthly-mean.csv`](https://data.gov.sg/dataset/surface-air-temperature-mean-daily-minimum): Monthly mean air temperature from 1982 to 2022
* [`relative-humidity-monthly-mean.csv`](https://data.gov.sg/dataset/relative-humidity-monthly-mean): Monthly mean relative humidity from 1982 to 2022
* [`wet-bulb-temperature-hourly.csv`](https://data.gov.sg/dataset/wet-bulb-temperature-hourly): Hourly wet-bulb temperature from 1982 to 2022

#### Attendance Data

There is 1 attendance-related dataset included in the [`data`](./data/) folder for this project, obtained from [SINGSTAT TABLEBUILDER](https://tablebuilder.singstat.gov.sg/). It is as follows:
* [`data/monthly_visitorship.csv`](https://tablebuilder.singstat.gov.sg/table/TS/M891071): Number of visitors to selected places of interest from 1990 to 2022

#### Merged Data
The final merged weather and health dataset is in the `data` folder:
* [`Monthly Weather Attendance Dataset.csv`](./data/Monthly Weather Attendance Dataset.csv'): Merged dataset for EDA.

---

### Data Dictionary

There are 24 features in the monthly weather attendance dataset outlined as follows:

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**yrmth**|*string*|monthly weather attendance|The year and month of each data point (in YYYY-MM format).| 
|**maximum_rainfall_in_a_day**|*float*|monthly weather attendance|The maximum amount of rainfall within a day for the specific yrmth (units mm).|
|**no_of_rainy_days**|*float*|monthly weather attendance|The number of rainy days in the specific yrmth. A day is considered rainy if more than 0.2mm of rain fell.| 
|**total_rainfall**|*float*|monthly weather attendance|The total rainfall in the specific yrmth (units mm).| 
|**mean_sunshine_hrs**|*float*|monthly weather attendance|The mean hours of sunshine per day in the specific yrmth (units h).| 
|**mean_temp**|*float*|monthly weather attendance|The mean of the daily mean air temperature in the specific yrmth (units degree Celsius).| 
|**mean_rh**|*float*|monthly weather attendance|The mean of the daily relative humidity in the specific yrmth (units percentage).| 
|**wbt_mean**|*float*|monthly weather attendance|The mean of the daily mean wet-bulb temperature in the specific yrmth (units degree Celsius).| 
|**wbt_max**|*float*|monthly weather attendance|The mean of the daily maximum wet-bulb temperature in the specific yrmth (units degree Celsius).| 
|**asian_civilisations_museum**|*float*|monthly weather attendance|The total number of visitors (in thousands) to the asian civilisations museum in the specific yrmth.| 
|**national_museum_of_singapore**|*float*|monthly weather attendance|The total number of visitors (in thousands) to the national museum of singapore in the specific yrmth.| 
|**singapore_art_museum**|*float*|monthly weather attendance|The total number of visitors (in thousands) to the singapore art museum in the specific yrmth.| 
|**peranakan_museum**|*float*|monthly weather attendance|The total number of visitors (in thousands) to the peranakan museum in the specific yrmth.| 
|**science_centre_singapore**|*float*|monthly weather attendance|The total number of visitors (in thousands) to the science centre singapore in the specific yrmth.| 
|**jurong_birdpark**|*float*|monthly weather attendance|The total number of visitors (in thousands) to the jurong birdpark in the specific yrmth.| 
|**night_safari**|*float*|monthly weather attendance|The total number of visitors (in thousands) to the night safari in the specific yrmth.|
|**river_wonders**|*float*|monthly weather attendance|The total number of visitors (in thousands) to the river wonders in the specific yrmth.|
|**zoo**|*float*|monthly weather attendance|The total number of visitors (in thousands) to the zoo in the specific yrmth.|
|**chinese/japanese_garden**|*float*|monthly weather attendance|The total number of visitors (in thousands) to the chinese/japanese_garden in the specific yrmth.|
|**sun_yat_sen_nanyang_memorial_hall**|*float*|monthly weather attendance|The total number of visitors (in thousands) to the sun yat sen nanyang memorial hall in the specific yrmth.|
|**indian_heritage_centre**|*float*|monthly weather attendance|The total number of visitors (in thousands) to the indian heritage centre in the specific yrmth.|
|**malay_heritage_centre**|*float*|monthly weather attendance|The total number of visitors (in thousands) to the malay heritage centre in the specific yrmth.|
|**year**|*int*|monthly weather attendance|The year of the specific yrmth.| 
|**month**|*int*|monthly weather attendance|The month of the specific yrmth.| 

---

### Technical Report

The technical report comprises two main components for this project. This includes:
a. Data Preparation & Cleaning: The cleaning and merging of the weather-related and attendance dataset by date.
b. Data Analysis: Observations and analysis of the merged dataframe with visualisations and statistical analysis.

---

### Conclusions & Recommendations

To a certain extent, weather plays a part in the expected resourcing needed at the museums to cater to the higher footfall, in part due to the higher number of museum visitors associated with different weather conditions during different periods of the year. It is observed that a combination of weather conditions can also have an impact on the number of museum visitors.

In summary, more resourcing could be prepared under these circumstances:

1. Moderate air temperature (P50) and lower than usual wet-bulb temp (lowest quartile).
2. Lower mean air temp (P50 & below) and lower humidity (P50 and below)
3. Lower max wet-bulb temp and lower relative humidity
4. In the months of Jun, Jul and in particular Aug, especially when wet-bulb temp and relative humidity are low. With the knowledge that a segment of visitors are encouraged to visit during these periods, the museums may consider purchasing online ads particularly during these periods featuring on weather applications.

For complementary markets/outdoor leisure, the patterns of weather conditions vis-a-vis attendance was less clear. This could be because of several factors, for example, the availability of both indoor and outdoor spaces at large outdoor places of interest, etc.

Other considerations/ limitations of this study that we could examine further include:

1. Examining the accessibility: A mitigating factor to ease of accessing leisure activities under various weather conditions.
2. Examining intraday dynamics: Time specific effects of weather in a day (e.g.persistent rain) and individual responses.
3. Examining effects of ticketing/ programmes: Time-limited exhitbions, pre-paid bookings, etc.



