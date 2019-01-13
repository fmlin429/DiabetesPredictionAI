# Predict Diabetes with Watson Machine Learning
Capstone Project: Predict Diabetes with Watson Machine Learning

## 1. Use Case and Business Requirements

Based on the historical diabetics Diagnostic data to create a prediction model which provides prediction for people who are likely to develop diabetes with 70% or greater accuracy. Deploy the model to Watson Machine Learning for the Model Evaluation 

## 2. Overall Pipeline Steps

The learning goals of this notebook are:

* Load a CSV file into the Object Storage Service linked to Watson Studio
* Pandas Datafame to clean and fix the dataset
* Apache® Spark machine learning model Pipe line with Random Forest Regression
* Train and evaluate the model
* Persist & Delopy a model in a Watson Machine Learning repository
* Call the Watson Machine Learning Web Services 

<img width="805" alt="mlpipeline" src="https://user-images.githubusercontent.com/18288611/51089850-6e24f000-1739-11e9-8597-2d0ace8773d9.png">

## 3. Architecture Decisions: Choose Dataset and IBM Services & Tools

* Dataset: https://www.kaggle.com/uciml/pima-indians-diabetes-database (Suggest to download the modified dataset fitting this project from Github) 
* Watson Studio for ETL & Model Development (Jupyter noteBook)
* Watson Machine Learning for Production Deployment (API available for application)

## 4. Extract, Transform and Load (ETL) through Pandas and Spark APIs

The Orginal Data looks like following: 

<img width="799" alt="diabetesrawdata" src="https://user-images.githubusercontent.com/18288611/51089896-e8557480-1739-11e9-978c-4035afb40fc3.png">

Following ETL tasks have been performed by Pandas:
* Check if there are empty rows
* Replace the cells with value 0 to the mean of the column (alternative way is to delete the related rows)
* Remove the columns which is highly correlated with other columns

Following ETL tasks have been included in Spark Pipeline:
* Replace the characters to digital as the label column
* Combining all feature columns together as a feature vector 

## 4. Models Applied

* Random Forest (Got the best results, included in the main program)
* Naive Bayes and LDA (included in a sparate program (got Lower accuracy results)

## 5. Publish and Deployed to Watson Machine Learning 


## 6. Call Watson Machine Learning API

* from Python Program in jupyter notebook 
* from Postman 














