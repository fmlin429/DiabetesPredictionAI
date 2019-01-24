# Prototyping a Cognitive Application on Diabetes  Diagnosis on Watson AI PaaS Services
Capstone Project: Predict Diabetes with Watson Machine Learning

## 1. Learning Goals
* Experience all the essential steps by building the Cognitive Application based on Data Science (AI, Machine learning)
Build, Train, and analysis the Model in Watson Studio 
Deploy and expose the model in Watson Machine Learning
Build up the Cognitive Application based on the deployed Model

* Project Selection: 
Goal: The Data with well known features which could be used by a common understandable applications. Pima Indians Diabetes Database (Primary Project). https://www.kaggle.com/uciml/pima-indians-diabetes-database

## 2. Use Case and Business Requirements

* Build Model: Based on the historical diabetics Diagnostic data to create a Diabetes Prediction Model which provides prediction for people who are likely to develop diabetes with 70% or greater accuracy

* Deploy Model: Deploying the model to Watson Machine Learning for the Model Evaluation 

* Apply Model: Build a Cognitive Application based on the Diabetes Prediction Model deployed in Watson Machine Learning


## 3. Overall Pipeline & Architecture

The learning goals of this notebook are:

1. Build Model in Watson Studio
2. Deplopy Model in Watson Machine Learning
3. Apply Model through Chatbot build by Watson Assistant Application

<img width="913" alt="screen shot 2019-01-24 at 3 50 04 pm" src="https://user-images.githubusercontent.com/18288611/51712084-50863f00-1ff3-11e9-88b8-4190de940ca6.png">

## 4. User Experience Design

#### Slack bot takes values of the key features from the customer: 
* Pregnancies
* Glucose 
* BloodPressure 
* SkinThickness 
* Insulin 
* BMI 
* DiabetesPedigreeFunction 
* Age

#### Results are returned from Cognitive Application: 
* Non-Diabetes probability
* Diabetes probability

#### Following Chatbot reflects the user experience: 

![image](https://user-images.githubusercontent.com/18288611/51712316-f8037180-1ff3-11e9-8cfb-2e0622cd1d6a.png)


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














