# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3: Web APIs & NLP


## Problem Statement
Using Pushshift's API, to collect posts from two subreddits. Thereafter, to use NLP to train a classifier to correctly predict which subreddit a given post came from.


## Datasets
The datasets that we will be using are scraped from subreddits r/iphone and r/GooglePixel. About 10,000 rows of data was scraped from both subreddits and saved into 2 separate .csv files.

- [`iphone.csv`](./datasets/iphone.csv): 9,971 rows of data with 81 features scraped from r/iphone subreddit

- [`pixel.csv`](./datasets/pixel.csv): 9,990 rows of data with 82 features scraped from r/GooglePixel subreddit

- [`combined.csv`](./datasets/combined.csv): 11,004 rows of data with 11 features. Data from [`iphone.csv`](./datasets/iphone.csv) and [`pixel.csv`](./datasets/pixel.csv) are combined in this .csv file after data cleaning


## Modelling Process
The follow steps were taken:

1. Web Scraping using Pushshift API
2. Data Cleaning
3. Preprocessing
2. Exploratory Data Analysis
3. Hyperparameter Tuning
4. Modelling
5. Findings

## Summary of Analysis
Six different types of classifiers were used in this project. They are:

1. Multinomial Naive Bayes with Count Vectorizer
2. Multinomial Naive Bayes and TF-IDF Vectorizer
3. Support Vector Machines and CountVectorizer
4. Support Vector Machines with TF-IDF Vectorizer
5. Random Forest and CountVectorizer
6. Random Forest and TF-IDF Vectorizer


|Estimator|Vectorizer|Train Accuracy|Test Accuracy|Generalization|Sensitivity|Specificity|
|---------|----------|--------------|-------------|--------------|-----------|-----------|
|Multinomial Naive Bayes|Count|94.53%|92.7%|1.83%|0.94|0.91|
|Multinomial Naive Bayes|Tfidf|95.47%|91.1%|4.37%|0.92|0.9|
|Support Vector Machine|Count|98.36%|93.52|4.84%|0.93|0.94|
|Support Vector Machine|Tfidf|100%|94.37%|5.63%|0.94|0.95|
|Random Forest|Count|96.18%|94.31%|1.87%|0.93|0.96|
|Random Forest|Tfidf|97.07%|94.06%|3.01%|0.93|0.95|


## Conclusion and Summary

### Findings

- All of the models are overfitted
- Multinomial Naive Bayes with Count Vectorizer produced the best generalisation score, which is expected as NB model is usually high variance, low bias, and tend not to overfit data
- Support Vector Machine with Tfidf Vectorizer produced the highest accuracy but did not perform very well in terms of generalisation. Able to explore GridSearchCV with diffferent C values and probably introduce gamma (to manipulate the curve)
- Even though highest accuracy is the most important metric in this project, Random Forest with Count Vectorizer provides a relatively high accuracy (second) and good generalisation (second)
- Hence, I am inclined to choose Random Forest with Count Vectorizer as the preferred model

### Misclassified Rows

Taking a look at the misclassified rows, the findings are as follows:

- both iphone/apple and pixel/google in their content
- have very little text in their content
- have generic text that is applicable to both subreddits

### Improvements

We can try to improve on the overfitting seen in all the models and improve on the generalisation further by: 

- Increase amount of dataset used
- Try using different stop words
- Explore using Bagging Classifier
- Continue to use Random Forest but explore GridSearchCV more parameters in terms of n_estimator and max depth
