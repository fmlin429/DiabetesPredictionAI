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

After cleanse the data
<img width="820" alt="afterpandas" src="https://user-images.githubusercontent.com/18288611/51090125-db865000-173c-11e9-8829-80dabaa337a0.png">

Following ETL tasks have been included in Spark Pipeline:
* Replace the characters to digital as the label column
* Combining all feature columns together as a feature vector 

## 4. Models Applied

Random Forest (Got the best results, included in the main program)

* Accuracy for Training dataset = 0.856877
* Test Error for Training dataset = 0.143123

* Accuracy  for Validation dataset = 0.744589
* Test Error for Validation dataset = 0.255411

Naive Bayes and LDA (included in a sparate program with got Lower accuracy results)

## 5. Publish and Deployed to Watson Machine Learning 

Please follow the steps in the code. 

Check the deployment information from Watson ML Console. Need to update follow features to test & verify
* Mode_ID
* Deployment_ID
* url 

## 6. Call Watson Machine Learning API

Please follow the steps in the code. 

* from Python Program in jupyter notebook 
* from Postman 














