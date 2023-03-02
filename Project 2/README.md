<img src="http://imgur.com/1ZcRyrc.png" style="float: left; margin: 20px; height: 55px">

# Project 2: Singapore HDB Resale Price Predictions
### Overview

This project entails a Kaggle challenge, using Singapore public housing data to create a regression model that predicts the price of Housing Development Board (HDB) flats in Singapore. The goal of this challenge is to predict the sales price for HDBs using features present in the dataset. The root mean squared error (RMSE) is used to evaluate the models.

---

### Problem Statement

Can we improve the accuracy of HDB Resale Price predictions for prospective buyers by utilising historical Singapore public housing data, to better estimate the market value of the HDB flat they intend to purchase?

---

### Datasets

There are 2 datasets from the [DSI-SG-Project-2 Regression Challenge](https://www.kaggle.com/competitions/dsi-sg-project-2-regression-challenge-hdb-price/overview). These are:

- `train.csv`: Contains all of the training data for the model. The target variable (SalePrice) is removed from the dataset
- `test.csv`: Contains test data for the model

---

### Data Dictionary

There are more than 70 features in the Singapore public housing dataset outlined as follows:

| Feature | Description |
| ---- | ---- |
| resale_price | the property's sale price in Singapore dollars. This is the target variable that you're trying to predict for this challenge. |
| Tranc_YearMonth | year and month of the resale transaction, e.g. 2015-02 |
| town | HDB township where the flat is located, e.g. BUKIT MERAH |
| flat_type | type of the resale flat unit, e.g. 3 ROOM |
| block | block number of the resale flat, e.g. 454 |
| street_name | street name where the resale flat resides, e.g. TAMPINES ST 42 |
| storey_range | floor level (range) of the resale flat unit, e.g. 07 TO 09 |
| floor_area_sqm | floor area of the resale flat unit in square metres |
| flat_model | HDB model of the resale flat, e.g. Multi Generation |
| lease_commence_date | commencement year of the flat unit's 99-year lease |
| Tranc_Year | year of resale transaction |
| Tranc_Month | month of resale transaction |
| mid_storey | median value of storey_range |
| lower | lower value of storey_range |
| upper | upper value of storey_range |
| mid | middle value of storey_range |
| full_flat_type | combination of flat_type and flat_model |
| address | combination of block and street_name |
| floor_area_sqft | floor area of the resale flat unit in square feet |
| hdb_age | number of years from lease_commence_date to present year |
| max_floor_lvl | highest floor of the resale flat |
| year_completed | year which construction was completed for resale flat |
| residential | boolean value if resale flat has residential units in the same block |
| commercial | boolean value if resale flat has commercial units in the same block |
| market_hawker | boolean value if resale flat has a market or hawker centre in the same block |
| multistorey_carpark | boolean value if resale flat has a multistorey carpark in the same block |
| precinct_pavilion | boolean value if resale flat has a pavilion in the same block |
| total_dwelling_units | total number of residential dwelling units in the resale flat |
| 1room_sold | number of 1-room residential units in the resale flat |
| 2room_sold | number of 2-room residential units in the resale flat |
| 3room_sold | number of 3-room residential units in the resale flat |
| 4room_sold | number of 4-room residential units in the resale flat |
| 5room_sold | number of 5-room residential units in the resale flat |
| exec_sold | number of executive type residential units in the resale flat block |
| multigen_sold | number of multi-generational type residential units in the resale flat block |
| studio_apartment_sold | number of studio apartment type residential units in the resale flat block |
| 1room_rental | number of 1-room rental residential units in the resale flat block |
| 2room_rental | number of 2-room rental residential units in the resale flat block |
| 3room_rental | number of 3-room rental residential units in the resale flat block |
| other_room_rental | number of "other" type rental residential units in the resale flat block |
| postal | postal code of the resale flat block |
| Latitude | Latitude based on postal code |
| Longitude | Longitude based on postal code |
| planning_area | Government planning area that the flat is located |
| Mall_Nearest_Distance | distance (in metres) to the nearest mall |
| Mall_Within_500m | number of malls within 500 metres |
| Mall_Within_1km | number of malls within 1 kilometre |
| Mall_Within_2km | number of malls within 2 kilometres |
| Hawker_Nearest_Distance | distance (in metres) to the nearest hawker centre |
| Hawker_Within_500m | number of hawker centres within 500 metres |
| Hawker_Within_1km | number of hawker centres within 1 kilometre |
| Hawker_Within_2km | number of hawker centres within 2 kilometres |
| hawker_food_stalls | number of hawker food stalls in the nearest hawker centre |
| hawker_market_stalls | number of hawker and market stalls in the nearest hawker centre |
| mrt_nearest_distance | distance (in metres) to the nearest MRT station |
| mrt_name | name of the nearest MRT station |
| bus_interchange | boolean value if the nearest MRT station is also a bus interchange |
| mrt_interchange | boolean value if the nearest MRT station is a train interchange station |
| mrt_latitude | latitude (in decimal degrees) of the the nearest MRT station |
| mrt_longitude | longitude (in decimal degrees) of the nearest MRT station |
| bus_stop_nearest_distance | distance (in metres) to the nearest bus stop |
| bus_stop_name | name of the nearest bus stop |
| bus_stop_latitude | latitude (in decimal degrees) of the the nearest bus stop |
| bus_stop_longitude | longitude (in decimal degrees) of the nearest bus stop |
| pri_sch_nearest_distance | distance (in metres) to the nearest primary school |
| pri_sch_name | name of the nearest primary school |
| vacancy | number of vacancies in the nearest primary school |
| pri_sch_affiliation | boolean value if the nearest primary school has a secondary school affiliation |
| pri_sch_latitude | latitude (in decimal degrees) of the the nearest primary school |
| pri_sch_longitude | longitude (in decimal degrees) of the nearest primary school |
| sec_sch_nearest_dist | distance (in metres) to the nearest secondary school |
| sec_sch_name | name of the nearest secondary school |
| cutoff_point | PSLE cutoff point of the nearest secondary school |
| affiliation | boolean value if the nearest secondary school has an primary school affiliation |
| sec_sch_latitude | latitude (in decimal degrees) of the the nearest secondary school |
| sec_sch_longitude | longitude (in decimal degrees) of the nearest secondary school |

---

### Technical Report

The technical report comprises four main components for this project. This includes:
- Part 1 - Data Cleaning, EDA, Feature Engineering: The cleaning of data, analysis on various features and transformation of selected features for the models
- Part 2 - Model Tuning and Evaluation: The construction, evaluation and selection of models
- Part 3 - Key Findings and Recommendations: A summary of the main results and insights gained from the data analysis, and recommendations for consideration
- Part 4 - Kaggle Submission: Exportation of the production model for submission into Kaggle

---

### Conclusion and Recommendations


In summary, key factors determining resale price which prospective buyers should bear in mind include:

- **Location**: Marine Parade, Tanglin or Changi can fetch a much higher resale price than other areas, while those in Woodlands and Sembawang are expected to see the lowest prices.

- **Full Flat Type**: Resale prices generally increases with larger number of rooms, in addition flat types such as masionette/terrace fetch higher resale price.

- **Flat Size**: For every 100 sqft increase, resale price increases by $29.6k

- **Flat Storey**: For every 10 floors increase, resale price increases by $41.6k

- **HDB Age**: For every 10 years increase in age of the flat, resale price decreases by about $46k.

Other considerations:

- **Present Value for Resale Price**: This study assumes that Resale Prices provided are in present value. If otherwise, for future studies, we could explore factoring a compound average annual rate of inflation of 1.2%.

- **Other Inangible Aspects to Consider**: Availability/ Proximity to green spaces and community spaces, promoting social activities and family bonding, etc.
