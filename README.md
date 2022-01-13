## General Assembly Holiday Sprint 2022 - Exploring Lego Data
An EDA of Lego datasets from Kaggle.com, with modeling done on the features 'is_spare' and 'color_trans'

Data source: https://www.kaggle.com/rtatman/lego-database

**Table of Contents**

- Assignment Requirements
- Problem Statement
- Background
- Data Cleaning and EDA
- Modeling
- Observations and Conclusions
- Future Considerations

## Problem Statement
We have been contracted by a rideshare company to look into the impacts of the Spring and Fall Daylight Savings Time changes on traffic accidents. To accomplish this we will be using Sobhan Moosavi’s US Accidents dataset that has gathered ~ 1.5 million US traffic accidents from February 2016 to December of 2020. The goal of this project will be to develop a model that can predict the severity (on a 1-4 scale) of a given traffic accident, and then deploy that model for use in real-time.

## Background
Daylight Savings Time (DST) is an annual time change that occurs in the Spring and Fall in nearly seventy (70) countries across the globe. In the United States the time change to DST begins annually at 2:00 AM on the second Sunday in March. DST ends at 2:00 AM on the first Sunday in November. Numerous studies have been done attempting to correlate the change to DST and negative health and behavioral impacts.

## Data Cleaning and EDA
The original dataset contained 1,516,064 accident entries from 2016 to 2020, ranking the traffic impact of each accident on a scale of 1 to 4. Due to computing power the dataset was paired down to for different datasets, each representing the geographical area surrounding: Chicago, Boston, Atlanta, and Denver.

A function called 'mrclean' was responsbility for cleaning the each cities' data. Once the data was cleaned and various features extracted from 'datetime' types (year, month, week, etc.), a feature 'IS_DST' was generated based on weather or not the accident took place the week following the change to DST.

## Modeling
We wanted to look at the feature importance of the is_DST feature to determine how impactful Daylight Savings could be when predicting accident severity. We focused in on the Chicago data for modeling purposes since it was the largest data set among the cities we observed.

We tried a few different model types to see which produced the best results:

- Decision Tree
- Random Forest
- BAG
- XGBoost

## Observations & Conclusions
While we found that the end of DST in the Fall has no statistically relevant effect on average severity of traffic impact, the start of DST in the Spring has a large effect on the average severity of traffic impact in all cities we observed

Because the impact is so significant at the start of DST Sigmoids Data Science can confidently recommend that Rideshare Company ® begin lobbying to abolish DST altogether.

## Future Considerations
1. NLP on the dropped feature “description” to see if a determination could be made on accident locations. For example, a service road can be beneath a highway and accidents could happen in both locations but it’s more likely for an accident to occur at higher speeds on the highway.
2. Further ANOVA to include the frequency of accidents and impact of Day/Night on accident severity during the week of DST.
3. Additional modeling on cities other than Chicago to see if the models’ performance holds across geographic locations.
4. Contact the creator of the dataset and ask what the quality of “accident severity” measures (how long the duration of each severity is).
5. Integrate GeoPandas into the Streamlit app in order to have ‘drag-and-drop’ functionality with the map.