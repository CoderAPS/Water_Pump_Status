# Flatiron Data Science Course - Project 3
#### Created by Nick Hall and Ahmad Samiee
#### Cohort DS-NATL-080822


## Project Overview 
For this project we will solving a classification problem. We will use models appropriate for classification to make prediction for given unseen data.  The dateset is split into two, one for training the models and the other for testing/verifying the performance of our models. Also, we took the approach of trying a couple of different models starting out with simple model with low performance and working toward better models with better performance.


## Business Problem 
We have been tasked by our stakeholder, Tanzanian Ministry of Water, to setup a model that can predict water pumps needing repair or operationally non-functional. Because of our business objective, we have decided to use recall for our model metric. Recall in this situation means what percentage of water pumps that are broken or need repair can our model predict correctly.

## Master Data Set
The dataset was obtained from from [DrivenData](https://www.drivendata.org) and the records were collected by Taarifa and Tanzanian Ministry of Water.  After the data was read into pandas dataframe it was split into two where 70% of data is used for training the models and 30% is used to verify prediction performance of the various models.

## Data Cleaning,Feature Engineering and Processing
The original target consisted of three categories: 'functional', 'non-functional' and 'functional needs repair'. This was feature engineered into two categories by creating a new column. If the the pump was 'functional' a value of 0 was assigned to this new column and if the pump was 'non-fuctional' or 'functional needs repair' a value of 1 was assigned to this new column.<br>
Missing or NAN values for categorical features was filled with most frequent value and for numerical features the average for the column was used to fill in or replace. Most this was accomplished with sklearn Imputer. The the categorical features were then processed with sklearn's OneHotEncoder and the numerical features were processed with StandardScaler. The data was then split into train and test.


## Model Development
For model development we ultilized sklearn Pipeline and GridSearchCV to efficiently test out our models. We evaluated the data with the following models: 
* DummyClassifier as base model
* Logistic Regression
* DecisionTreeClassifier 
* KNeighborsClassifier
* VotingClassifier with DecisionTreeClassifier and KNeighborsClassifier
* RandomForestClassifier

## Conclusion
This project is a binary classification problem where prediction models are trained to predict the status of water pumps, especially those water pumps needing repair or operationally non-functional. Because of our business objective, we have decided to use recall for our model primary metric and accuracy for overall performance. Recall in this situation means what percentage of water pumps that are broken or need repair can our model predict correctly. Our base model is DummyClassifier which gave a recall 0 and accuracy of 0.54.  Logistic Regression provides better predictions with a recall of 0.65 and accuracy of 0.76.  The next four models which are DecisionTree, KNeighbors, VotingClassifier (with DecisonTree and KNeighbors and Random Forest give similar result with a recall between 0.76 - 0.77 and accuracy between 0.78 - 0.83. RandomForest gives a slightly better performance with a recall of 0.77 and accuracy of 0.83 and therefore it is our best model.  
