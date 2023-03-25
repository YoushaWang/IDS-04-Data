# IDS-04-Data

## Introduction
In this project, we are going to build a major Big Data system to perform a Data Engineering related task.    

My project is loan prediction. The database is loan amount and loan amount term with the infomation about the person.    

I use AWS S3 to store our data and use AWS Sagemaker to do machine learning model code part. A model is built to predict the loan based on the data we provided, and we also calculate the accuracy of our model compared with real data.    

## Data Analysis
In this loan prediction dataset, we have the infomation of applicants those who previously applied for the loan.   

The database is collected from Kaggle, and consists two CSV file, one is train data and another one is test data. We use read_csv function to load data.   

The Training data consists of 614 samples and 12 features[Loan_ID, Gender, Married, Dependents, Education, Self_Employed, ApplicanIncome, CoapplicantIncome, LoanAmount, Loan_Amount_Term, Credit_History and Property Area].    

## Code Overflow

1. import important module   
2. import data file. If we do it locally, local address is needed; if we import data through AWS S3, sagemaker module is needed.
```
from sagemaker import get_execution_role
role = get_execution_role()
bucket='pro4'
train_key = 'train.csv'
train = 's3://{}/{}'.format(bucket, train_key)
```
3. data anlysis   
4. data cleaning   
5. build model and do evaluation

## Data Result
```
The accuracy of the Logistic Regression is 0.837398:
The accuracy of the Linear Discriminant Analysis is 0.837398:
The accuracy of the K Nearest Neighbors is 0.739837:
The accuracy of the Decision Tree is 0.699187:
The accuracy of the Gaussian Naive Bayes is 0.829268:
The accuracy of the Random Forest is 0.796748:
The accuracy of the Support Vector is 0.813008:
```

## Steps
1. create a bucket on AWS S3    
<img width="500" alt="s3-setup" src="/img/s3-setup.jpg">
2. upload our data to AWS S3
<img width="500" alt="s3-upload" src="/img/s3-upload.jpg">
3. create a notebook instance in AWS Sagemaker
<img width="500" alt="sage-setup1" src="/img/sage-setup1.jpg">
4. create a IAM role for sagemaker AWS
<img width="500" alt="sage-setup2" src="/img/sage-setup2.jpg">
5. the notebook instance is created successful after wait
<img width="500" alt="sage-setup3" src="/img/sage-setup3.jpg">
6. click "open jupyter" and create "conda_python3" file and do code there
<img width="500" alt="sage-setup4" src="/img/sage-setup4.jpg">    

## Requirement
1. Use a major Big Data system to perform a Data Engineering related task

2. Example systems could be: (AWS Athena, AWS Spark/EMR, AWS Sagemaker, Databricks, Snowflake)

## Reference
1. https://www.kaggle.com/code/vtella/starter-loan-prediction-problem-36866eee-e/notebook#Introduction
2. https://www.kaggle.com/code/annmary25/loan-status-prediction/notebook#Building-Model-&-Evaluation