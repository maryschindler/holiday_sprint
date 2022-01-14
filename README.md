## General Assembly Holiday Sprint 2022 - Exploring Lego Data
An EDA of Lego datasets from Kaggle.com, with modeling done on the features 'is_spare' and 'color_trans'

Data source: https://www.kaggle.com/rtatman/lego-database


**Table of Contents**

- Background
- Problem Statement
- Data Cleaning and Exploratory Data Analysis (EDA)
- Modeling
- Observations and Conclusions
- Future Considerations


## Background
I just recently completed General Assembly's Data Science Immersive Bootcamp (done remotely). As part of post-course support, General Assembly asked that I participate in a 'Holiday Sprint' - formulating and completing a project (self-chosen) in four weeks. While students were encouraged to work in up to groups of three (including with students from the Software Engineering and User Experience cohorts), I had only just completed my course and wanted to 'test' the skills I had acquired in a solo-setting. 


## Problem Statement
As outlined above, General Assembly asked past participants to take part in a project of their choosing. Based on the time of year - the Holidays - I decided to explore data related to the classic toy Legos. Several datasets about different Lego features, sets, colors, models, etc. were available on Kaggle.com and served as the basis for my project: [Source: Kaggle](https://www.kaggle.com/rtatman/lego-database). The data was current as of July 2017 and does not reflect any Lego sets made after that time.  

![image info](../data/downloads_schema.png)

I had several goals related to the project, including: 
1) Examine the existing data, noting any trends through EDA
2) Concatenate the existing datasets into one 'main' dataset that had a entry for each Lego piece belonging to a Lego set. 
3) Examine the new main dataset, noting any trends through EDA
4) Build a model for one of the binary features in the main dataset. 


## Data Cleaning and EDA
The for this project was originally in the form of 8 separate .csv files, each containing various information about Legos. I did not clean the individial datasets. EDA, however, was done on each dataframe. A few take aways from that EDA:

- Approximately 79% of Lego colors are opaque while the other 21% of Colors are either transparent or translucent
- Approx. 99% of all Lego sets are on their first version
- Approx. 95% of all Lego pieces are necessary to their sets, the other 5% are spare pieces
- The top five most frequent categories by number of parts are:
    - Minifigs
    - Minifig Accessories
    - Non-Lego
    - Duplo, Quatro, and Primo
    - Tiles Printed
- No Lego sets were manufactured in 1951 or 1952
- The themes: 'Supplement', 'Fire', 'Airport', 'Harbor', and 'Traffic' are the five most popular (frequent) set themes

Once the separate dataframes were joined additional EDA, as well as light data cleaning, was completed. For Data Cleaning, there were the same 182 entries in 'part_name', 'part_cat_id', and 'part_cat_name' that were null, these were dropped from the dataframe. Additionally the columns 'part_cat_name', 'color_name', 'color_rgb', 'invt_set_num', and 'set_theme_name' duplicated data from other columns and were also dropped from the dataframe. Any columns that were dtype float were converted to 'int'. Lastly, I featured engineered a column 'percent_of_set' which rounded the piece 'quantity' column divided by the 'total_set_parts' column. After this process was complete I generated a myriad of data visualizations to represent the cleaned data. 


## Modeling
Due to the size of the data set as well as limitations set by my computing power I chose to build a predictive model for binary classification on two features: 'is_spare', which tells the user whether or not a lego piece in a set is a spare, and 'color_trans', which tells the user whether or not the color of the lego piece is non-opaque (transculent or transparent)

To that end, I used three different models:

- LogisticRegression
- KNeighborsClassifier
- SupportVectorClassifier

Regarding the 'is_spare' outcome:
- LogReg returned training/testing scores of: 0.9484/ 0.9483
    - The features 'color_trans	(coef. 1.4346), quantity (coef. -1.1832), and 'set_age'	(coef. -0.0551) had the greatest impact on the model
    
- KNeighborsClassifier was tuned with the hyperparameters n and p, with the scores for training/testing data as follows:
    - k = 1, p = 1', 0.984, 0.9284
    - k = 1, p = 2', 0.984, 0.9293
    - k = 3, p = 1', 0.9665, 0.9406
    - k = 3, p = 2', 0.9663, 0.9408
    - k = 5, p = 1', 0.9608, 0.9458
    - k = 5, p = 2', 0.9605, 0.9459
    - k = 7, p = 1', 0.9583, 0.9485
    - k = 7, p = 2', 0.9578, 0.9481
    - k = 9, p = 1', 0.9564, 0.9499
    - k = 9, p = 2', 0.9561, 0.9497

- RandomForestClassifier (rfc) was the most overfit with training/testing scores of: 0.9851, 0.9489. Overall, however, rfc produced an accuracy score of 95% when determining whether a Lego piece is spare to a set or not. 


## Observations & Conclusions
Regrettably the data used in the project was only current through July 2017; the Lego Group has manufactured many new sets since that time that were not included here. Some of the obversations made below (like the set with the most number of unique pieces, the lego piece appearing most frequently among all sets, etc.) may no longer be accurate:

- The piece category 'plates' was the majority category by approx. 25,000 pieces
- Black legos are the most frequently appearing in Lego sets, followed by:
    - White
    - Light Bluish Gray
    - Red
    - Dark Bluish Gray
- Of all Lego pieces, 93.74% are opaque, while the other 6.26% are translucent or transparent
- The Lego set with the most pieces by volume was the 'Mosaic Dino', with 1,440 pieces: #https://www.bricklink.com/v2/catalog/catalogitem.page?S=k34432-1#T=I


## Future Considerations

1. Rebrickable (website from where the Kaggle data was originally gathered) has its own API as well as offers a download of the entire Lego catalog. Unfortunately, I had realized this about half-way through the project, however, should I re-visit the project in the future I would want to use to most recent (re: accurate) data.

2. Test additional models? Build a Neural Network to see if we could model for a multi-class classification, like set age. REWORDS THESE WORDS.