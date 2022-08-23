# Data Science Portfolio

Author: Hartarto WInata 

This repository contains the files for the Portfolio task for COMP2200/6200 in S1 2022. 

# Introduction

The aim of this portfolio is to research the MovieLens data collected by GroupLens Research Project at the University of Minnesota. 
This is done as the required task for Macquarie University course code COMP2200/6200 in S1 2022.

# Technologies & Requirements

The analysis mainly use Python 3 language with Jupyter Notebook as the media to execute the codes.
The Python packages used are:
- Pandas
- Numpy
- Seaborn
- Matplotlib
- Scikit-Learn

# Setup

To run this project:

```
1. Create a copy of this repository in the local machine.
2. Install Anaconda Package 3 from https://www.anaconda.com/products/distribution.
3. Run Anaconda Navigator.
4. Run Jupyter Notebook from Anaconda Navigator.
5. Open the directory of local machine working files cloned from repository before.
```

# Analysis Conducted

## Portfolio 1

This document will show the basic in preparing data for data science purpose, such as grouping, dealing with null/zero values, and basic visualisation for more informative explanation for the data and results.

1. Removing missing data.
2. Create a descriptive statistic summary.
   - Find number of unique user.
   - Descriptive statistics for all records.
   - Descriptive statistics for grouped records.
3. Create plot/graph and analyse the output.
   - Graph used for analyse are bar chart, histogram, and boxplot.
   - The analysis are written below as the summary of all graph observation.
4. Removing outliers.
   - The outliers condition has been set beforehand.

## Portfolio 2

In this documents, ww will try to run simple linear regression analysis to predict the dependant variable, which is rating, using the variables available in the csv. We also do some preparatory work and evaluation to find out if our model were capable to predict with decent score. Visualisation will be provided to compare different linear regression models with different explanatory variables and train data used.

1. Convert categorical features into numerical values using `Ordinal_Encoder`.
2. Explore the correlation between features.
   - The correlation strength is decided based on the magnitude.
   - The correlation relationship can be observed whether it is positive (parallel) or negative (inverse).
3. Split data into train and test data. Train data is used to train the model, which will be used to predict the test data.
   - Case 1: Train data contain 10% of the data.
   - Case 2: Train data contain 90% of the data.
4. Train linear regression model prediction.
   - (model-a) using the training/testing data in case 1 with two most correlated input features
   - (model-b) using the training/testing data in case 1 with two least correlated input features
   - (model-c) using the training/testing data in case 2 with two most correlated input features
   - (model-d) using the training/testing data in case 2 with two least correlated input features
5. Evaluating each model. THe evaluation metric used are:
   - `Mean_Squared_Error` (MSE)
   - `sqrt(Mean_Squared_Error)`(Root_MSE) 
   - `R<sup>2</sup>`
6. Visualize and interpret the result.
   - Bar graph is used to provide a better visualization for evaluation metric comparison.
   - It is found out that correlation does affect the evaluation metric result.

## Portfolio 3

This portfolio will run the logistic regression analysis, as the dependant variable will be a categorical variable. Logisitic regression is a machine learning technique used to predict binary/discrete output, using the explanatory variables included. The data preparation is almost the same as previous Portfolio 2, however, the evaluation score will be different, using `accuracy_score` and `Confusion_Matrix`. We will also try another advanced supervised machine learning techniques other than logisitic regression to find out how the evaluation will be different. 

1. Convert categorical features into numerical values using `Ordinal_Encoder`.
2. Split data into train and test data with 20% proportion for test data and the reminder for train data.
3. Train logisitic regression using data splitted before.
4. Visualize the logistic regression evaluation result.
   - `accuracy_score`
   - `confusion_matrix`
   - `plot_confusion_matrix`
5. Train logistic regression, but using RFE to select the best features to be included in the logistic regression model.
   - rank the best explanatory variables to be used for machine learning model.
   - compare the `accuracy_score` for each model using different number of explanatory variables.
   - visualize the logistic regression using RFE.
7. Train using K-Nearest Neighbourhood (KNN) model.
   1. Determine the best K to be used in the model using loop, then visualise the score for better understanding.
   2. Utilize `GridSearch_CV` for the same purpose of no. 7.1 and compare the results.
   3. Run KNN using the best K generated from no. 7.2.
   4. Visualize the output using the same tools in no. 4.
8. Compare the results
   - It is found out that KNN provided better model compared with simple logistic regression.
   - Better accuracy score and confusion matrix output.

## Portfolio 4

In this portfolio, the author would like to examine the effect of reported Covid-19 cases towards price of commodity during 2020, denoted with the price of rice, since rice is a staple food for most of the country. However, due to time constraint, the author believed that this analysis can be improved in the future. As the data is searched by the author himself, several preparatory steps, such as cleaning and managing outliers, need to be conducted before running the machine learning model. The data consists of two datasets, which are available in [here](https://github.com/COMP2200-S1-2022/data-science-portfolio-Winata898/tree/main/files). For the sources, `wfpvam_foodprices_2020.csv` are available from [Global Food Prices](https://data.humdata.org/dataset/wfp-food-prices), while `covid19_14des2020.csv` can be donwloaded from [European Centre for Disease Prevention and Control](https://www.ecdc.europa.eu/en/publications-data/download-todays-data-geographic-distribution-covid-19-cases-worldwide). 

1. Drop the data that is not irrelevant with the analysis purpose/question.
   - Data which are not in 2020.
   - Data which are not the price of 'Rice'.
2. Merge both datasets using `months` and `country_name` variable. Set the merge type as inner merge.
3. Clear any null/missing data.
   - Missing number of Covid-19 cases will be replaced with 0, assuming there is no report of Covid-19 cases.
   - Uncompleted data (December 2020) is removed.
4. Removing outlers from merged dataframe.
   - Plot using boxplot, 
   - Remove outliers from `price` detected from boxplot.
   - Replace outliers in `AverageMonthlyCovid19CasesPer1000000` with median value.
5. Plot the initial data
   - Line chart
   - Histogram
   - Boxplot
   - Scatter plot
6. Splitting Training and Testing data
   - Scalling the variables that will be splitted.
   - Split with the proportion of 20% test data and 80% training data.
7. Train the model using two machine learning model.
   - Simple Linear Regression Analysis
   - K-Fold Cross Validation
8. Visualize the Score for each model
   - Bar chart is used.
   - Due to the skewed data, the score seems to be biased

Overall, the author hope that the Portfolio 4 may serve as a foundation for more complex analysis related to the effect of Covid-19 towards price of commodities.
