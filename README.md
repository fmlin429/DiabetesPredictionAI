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

## 3. Extract, Transform and Load (ETL) through Pandas and Spark APIs

The Orginal Data looks like following: 



