# Alcohol-Consumption-Predictions
Using Alcohol Research Group NAS Datasets from 1990-2010, predict the frequency of alcohol consumption of individuals based on demographic, geographic and behavioral information. 


Used Clustering and Random Forest in an attempt to impute the missing labels on the new behavioral features, but both model predictions had very low correlation to the test data.


# Alcohol Consumption

# Why Alcohol?
While in the miltary 10 years ago I was exposed to(and participated in) a lot of heavy drinking. It seemed a normal activity at the time, but I noticed some surprised reactions from people when discussing alcohol consumption in a military environment and it made me question, "Is this actually normal, or is my perception of what is considered heavy drinking skewed?"
Never having this opportunity to look at data about drinking trends, I was unable to answer that question. My goal for this project is to look at drinking trends and discover not what people consider heavy drinking, but how much people actually participate in drinking.

# Data Source
The data for this project comes from five different datasets provided by the Alcohol Research Group, spanning from 1990 through 2010. The datasets were created from phone questionnaires, so the data is self-reported. Each dataset contains 4000-7000 rows, detailing an individuals responses to alcohol related questions. The final dataset contains nearly 28,000 records. Each dataset contains 600-700 columns corresponding to each question on the questionnaire.
The datasets are not open source. Permissions must be granted from the Study Director to access the data.

[Link to ARG National Alcohol Survey Datasets](http://arg.org/nas-datasets/ "NAS Datasets")

# Data Wrangling 
Cleaning and organizing the data was a daunting task. Each dataset had nearly the same data, but formatted in slightly different ways. Most of the values did not represent the exact same thing. For example, the state codes in each dataset were not the same, so a dictionary for each individual dataset had to be created to match the values to their respective state names. Great attention to detail was required to ensure my final dataframe had consistent and accurate data. Many of the bevioral questions promtped for a numeric answer from 1-4 to represent relative importance of the question. These features had roughly 10% of their values as either null, or the participant failed to respond so an arbitrary number was inserted. These points were imputed from the probability of the existing values since the null data points seemed to be evenly spread with no apparent trend. The value could not be inputed with a standard mean or mode due to the fact that the existing data was parabolic, and the mean or mode would skew the data in one direction or the other

## Understanding the Data Values
Much of my analysis involved comparing the frequency of drinking among different demographics. The values are initially somewhat counter-intuitive, but easy to understand with a reference table. The questionnaire answers to drinking frequency consist of a numeric value between 1 and 11(1 corresponds to extremely heavy drinking, 11 corresponds to never had a drink). These values are used in questions about wine consumption, beer consumption, liquor consumption, and average alcohol consumption regardless of alcohol type. A complete table is provided below for reference.

Drinking Frequency Chart:

| Value | Description |
| --- | --- |
| 1 | Drink 3 or more times a day |
| 2 | Drink 2 times a day |
| 3 | Drink once a day |
| 4 | Drink nearly every day |
| 5 | Drink 3 or 4 times a week |
| 6 | Drink 1 or 2 times a week |
| 7 | Drink 2 or 3 times a month |
| 8 | Drink about 1 time a month |
| 9 | Drink less than 1 time a month |
| 10 | Drink less than 1 time a year |
| 11 | Never had a drink |

# Goal
The goal of this project is to build a model to predict a label for a 3-class engineered feature. The three classes will correspond to drinking frequency: 0 - Never drink; 1 - drinks occasionally(at most once a month); 2 - Drinks frequently(at least once a week). 



# EDA
After selection of features, each one was split into three groups corresponding to the target value to  visualize a difference in their distributions. The feature regarding the participants education, and also the his/her religion's opinions of alcohol seemed the most promising of the behavioral fetures.

INSERT PLOTS HERE


