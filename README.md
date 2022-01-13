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
NEED TO TYPE

We have been contracted by a rideshare company to look into the impacts of the Spring and Fall Daylight Savings Time changes on traffic accidents. To accomplish this we will be using Sobhan Moosavi’s US Accidents dataset that has gathered ~ 1.5 million US traffic accidents from February 2016 to December of 2020. The goal of this project will be to develop a model that can predict the severity (on a 1-4 scale) of a given traffic accident, and then deploy that model for use in real-time.


## Background
I just recently completed General Assembly's Data Science Immersive Bootcamp (done remotely). As part of post-course support, General Assembly asked that I participate in a 'Holiday Sprint' - formulating and completing a project (self-chosen) in four weeks. While students were encouraged to work in up to groups of three (including with students from the Software Engineering and User Experience cohorts), I had only just completed my course and wanted to 'test' the skills I had acquired in a solo-setting. 



## Data Cleaning and EDA
NEED TO TYPE

The original dataset contained 1,516,064 accident entries from 2016 to 2020, ranking the traffic impact of each accident on a scale of 1 to 4. Due to computing power the dataset was paired down to for different datasets, each representing the geographical area surrounding: Chicago, Boston, Atlanta, and Denver.

A function called 'mrclean' was responsbility for cleaning the each cities' data. Once the data was cleaned and various features extracted from 'datetime' types (year, month, week, etc.), a feature 'IS_DST' was generated based on weather or not the accident took place the week following the change to DST.


## Modeling
Due to the size of the data set as well as limitations set by my computing power I chose to build a predictive model for binary classification on two features: 'is_spare', which tells the user whether or not a lego piece in a set is a spare, and 'color_trans', which tells the user whether or not the color of the lego piece is non-opaque (transculent or transparent)

To that end, I used three different models:
- LogisticRegression
- KNeighborsClassifier
- SupportVectorClassifier

## Observations & Conclusions
Regrettably the data used in the project was only current through July 2017; the Lego Group has manufactured many new sets since that time that were not included here. Some of the obversations made below (like the set with the most number of unique pieces, the lego piece appearing most frequently among all sets, etc.) may no longer be accurate:
- wordswordswords
- wordswordswords
- wordswordswords

WORDS ABOUT THE MODELING
WORDS ABOUT THE MODELING
WORDS ABOUT THE MODELING
WORDS ABOUT THE MODELING

## Future Considerations

1. Rebrickable (website from where the Kaggle data was originally gathered) has its own API as well as offers a download of the entire Lego catalog. Unfortunately, I had realized this about half-way through the project, however, should I re-visit the project in the future I would want to use to most recent (re: accurate) data.
2. Test additional models? Build a Neural Network to see if we could model for a multi-class classification, like set age. REWORDS THESE WORDS.