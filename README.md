# A Cognitive Solution on Diabetes  Diagnosis on Watson AI PaaS (Watson Studio, Watson ML, Watson Assistant)
Capstone Project: Predict Diabetes with Watson Machine Learning

Youtube Video to Stakeholders: 
https://youtu.be/M4aMxwCC5KM

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


## 5. Architecture Decisions: Choose Dataset and IBM Services & Tools

* Dataset: https://www.kaggle.com/uciml/pima-indians-diabetes-database (Suggest to download the modified dataset fitting this project from Github) 
* Watson Studio for ETL & Model Development (Jupyter noteBook)
* Watson Machine Learning for Production Deployment (API available for application)
* Watson Assistant and IBM clould for Cogintive Application Development

## 6. ETL and EDA

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

## 7. Build Models (Supervised Learning) 

### 7.1 Build Models (Supervised Learning) 

* Accuracy (Naive Bayes Model) = 0.7292
* Accuracy (Logistic Regression Model): 0.7500
* Accuracy (Decision Tree Model): 0.6823
* Accuracy (Linear Discriminant Analysis-LDA): 0.7448
* Accuracy (Support Vector Machine - rbf Model): 0.6406
* Accuracy (Support Vector Machine - linear Model): 0.7344
* Accuracy (Random Forest): 0.7708

* MAE (Naive Bayes Model): 0.4692
* MAE (Logistic Regression Model): 0.4458
* MAE (Decision Tree Model): 0.4707
* MAE (Linear Discriminant Analysis-LDA): 0.4502
* MAE (Support Vector Machine - rbf Model): 0.3594
* MAE (Support Vector Machine - linear Model): 0.4561
* MAE (Random Forest): 0.4487

#### * Random Forest (Returned the best results, included in the main program)

### 7.2. Build Models (Non-Supervised Learning) 

A simple Feedforward Neural Network was built based on the features given. 

## 8. Publish and Deploy Model to Watson Machine Learning 

Please follow the steps in the code. 

Check the deployment information from Watson ML Console. Need to update follow features to test & verify
* Mode_ID
* Deployment_ID
* url 

## 9. Apply Model through Calling the Scoring API
* Calling through jupyter notebook 
* Calling through Postman
* Calling through the Node-Red Application with Watson Assistant (Node-Red Code is included) 

![image](https://user-images.githubusercontent.com/18288611/51792536-0aa6b380-2178-11e9-96a1-4c9144bc821b.png)

