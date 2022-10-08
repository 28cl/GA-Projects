# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 2 - Ames Housing Data and Kaggle Challenge

------

## Background

Ames is the a city in the state of Iowa, USA. It is best known as the home of Iowa State University, with leading agriculture, design, engineering, and veterinary medicine colleges. It is the nineth largest city, with a population of about 67,000 people. Dubbed a college town, the students of Iowa State University makes up about half of its population. This also means that property rental is a huge market in this city.

Iowa is located in the midwest region and suffers hot, humid summers and freezing winters. On the average, there are about 200 sunny days in Iowa.

Iowa State University is ranked #75 amongst public colleages, making it an attractive university to attend if you live in the region ([*source*](https://www.forbes.com/colleges/iowa-state-university/?sh=5892079a14dc)). It is also home to a research laboratory for the U.S. Department of Energy and NASA’s Iowa Space Grant Consortium.

On top of that, as inflation is expected to rise at rates not seen before in the past 40 years, moving to "cheaper" states and/or cities to live in seems like an attractive option. Compared to other college towns like Austin, Texas, prices for renting an apartment is generally 50 to 60% cheaper ([*source*](https://www.cnbc.com/2022/07/13/these-are-americas-10-cheapest-states-to-live-in.html)).


## Problem Statement

- We are a team of real estate consultants providing advice to property developers and/or clients for asset appreciation.

- Aims: Identify features with a strong positive correlation to the sale price of a home and generate business insights to maximize the ROI.

- We will focus on some neighbourhood(s) as well as the features that can fetch the highest sale price.

- The three neighbourhood(s) that I am working on are: NAmes, College Creek and Old Town.

- The features that I am interested to look at are: Bedrooms, Full Bathrooms, Basement as well as Kitchen.


## Assumptions

The assumptions made for this modelling are:

- As developers, there is no fixed land space per house decided upon yet.

- Multicolinearity between features are assumed to be absent when predicting which features will drive sale price.

- Cost of building the features was not taken into account.

## Datasets

We will use the dataset containing housing data from Ames, Iowa, United States. The dataset provides information used in assessing values for residential properties sold from 2006 to 2010, compiled by the Ames Assessor’s Office.

The dataset contains 2051 observations and 81 features. It is further divided into training and test sets for the purpose of model training.

### Training Data

- [`train.csv`](./datasets/train.csv): 2051 observations and 81 features, including 80 predictors of sale price and 1 response feature containing the corresponding sale price of properties

### Test Data

- [`test.csv`](./datasets/test.csv): 878 observations and 80 features, with the sale price feature removed

## Modelling Process

The follow steps were taken:

1. Data Cleaning
2. Exploratory Data Analysis of categorical and numerical features
3. Feature engineering, Encoding and Get Dummies
4. Modelling
5. Applying Model on business problem


## Summary of Analysis

### Regression Models for all features

Five different models were tested on training data:

1. Linear Regression
2. Ridge Regression
3. Lasso Rergression
4. Elastic Net Regression
5. GridSearchCV

Prediction was first done with all the features available but the RMSE generalisation was no where near 5% difference. As such, features were chosen based on their correlation as well as p-values to the Sale Price. Features that had high correlation and good p-value scores but had multi-colinearity issues were also dropped. 

The 3 models with the best generalisation is as follows:

|Rank	|Model	| Train MSE.    |Test MSE	   | Generalisation |
|-----	|----	|-------		   |----------- | -----          |
|1st	|Ridge	|1,071,613,309  |1,031,319,693|  -3.76%   |
|2nd	|Lasso	|1,053,664,116  |1,012,762,457|  -3.88%  |
|3rd 	|Linear|1,053,661,325	|1,012,770,260|  -3.88%  |

The most important features that affect the sale price positively are: above average overall quality, ground living area, garage area, fireplace (2 or less) and size of the basement.

The most important features that affect the sale price negatively are: house age, below average overall quality.

### Business Analysis

NAmes, CollgCr and OldTown were filtered out into separate datasets and the ridge regression model that was developed in the first part of the modelling was applied to 3 separately. These three neighbourhoods were picked as they have the most data available in terms of rows.

The findings of the analysis are as follows:

- Obviously, a larger living area will result in a higher sale price.
- Ground Living area increase in sale price is very similar to 1st floor SF as the general area increases when the 1st floor SF increases.
- For quality, You can tell that from Above Average (Overall Qual_6) and above, the Sale Price tends to increase except for College Creek. It seems that the houses located at College Creek need to be at least Very Good (Overall Qual_8) in quality for the sale prices to increase.
- The larger the garage area, the higher the sale price.
- House Age does not seem to affect the sale prices for houses located at Old Town as much as the houses in the other areas.
- In terms of full and half bathrooms, the price increase does not seem to be very different. Perhaps to save space and cost, to consider building half bathrooms instead (difference is without shower facilities).
- For Basement Exposure, which refers to walkout or garden level walls, having no exposure will result in a significant drop in prices (Bsmt_Exposure_4).

## Conclusion and Recommendations

- There will always an issue of multicolinearity between the features.
- Difference in sale price could be driven by other external factors like inflation, location (distance away from amenities etc), season, mortage interest and political climate which were not taken into account. 
- The data collected does not have a good representation of all the neighborhoods in Ames. Some neighbourhoods have more rows compared to others.


We can consider using models other than Linear/Lasso/Ridge Regression on the same dataset and see if we are able to yield better generalisation.
