# Team-11

# **Framingham 10 year risk of future (CHD) coronary heart disease.**

## Reason topic selected
According to the CDC *heart disease* is the leading cause of death in the United States and the number one killer in Canada, it is also the most costly disease in Canada, putting the greatest burden on our national health care system.

A number of factors, individually or in combination, can lead to heart disease, namely: high blood pressure, high blood cholesterol, and smoking are key risk factors for heart disease. About half of people in the United States (47%) have at least one of these three risk factors. Several other medical conditions and lifestyle choices can also put people at a higher risk for heart disease, including: diabetes, overweight and obesity, unhealthy diet, diets rich in saturated fat, physical inactivity, excessive alcohol use, stress and a family history of heart disease

Men are generally more likely to develop heart disease. An increasing number of women are experiencing heart disease but they are under-diagnosed. For both sexes, the risk of heart disease increases with age.

### Framingham heart study dataset

The **Framingham Risk Score** is a sex-specific algorithm used to estimate the 10-year cardiovascular risk of an individual. The **"Framingham"** heart disease dataset inlcudes over 4,240 records, 16 columns and 15 attributes. The goal of the dataset is to predict whether the patient has 10-year risk of future (CHD) coronary heart disease.
The features included in this dataset are:

- *Sex* (0=female, 1=male)
- *age* (int)
- *education* (float)
- *currentSmoker* (0=non-smoker, 1=smoker)
- *cigsPerDay* (Number of cigarettes smoked per day)
- *BPMeds* (0=no meds, 1=takes BP meds)
- *prevalentStroke* (0=no stroke, 1=stroke)
- *prevalentHyp* (0=no hypertension, 1=hypertension)
- *diabetes* (0=no diabetes, 1=has diabetes)
- *totChol* (float. Total cholesterol)
- *sysBP* (float. Systolic blood pressure)
- *diaBP* (float. Diastolic blood pressure)
- *BMI* (float. Body Mass Index)
- *heartrate* (float. Heart Rate Per Minute)
- *glucose* (float. glucose level)
- *TenYearCHD* (0=no 10-year risk of CHD, 1=10-year risk of CHD)

The dataset can be found here:
https://www.kaggle.com/datasets/aasheesh200/framingham-heart-study-dataset?resource=download

## Expected Outcome

- Prediction of an individual developing heart disease within next 10 years based on the personal health and lifestyle information.
- The prediction will help the medical professionals identifying the preventative measures to reduce the risk and educating patients on the risk if adequate care is not employed.

## Communication Protocol
- Slack Channel for Team 11
- Email
- Zoom meeting during virtual class time and office hours.

# Technologies Used
## Data Cleaning and Analysis
Data cleaning is an essential step as it will dictate the flow of the entire project. It will allow for any step taken afterwards to be done efficiently. For our dataset, Pandas will be used to clean the data, to drop any unnecessary columns/rows.
## Database Storage
The database was created on AWS and then linked to postgresSQL, which is the database we intend to use. The data was tested using Spark on Google Colab. In the branch called “laleh”, there are links to where the data has been stored and points on the work process. There are also screenshots of the data being read using various dependencies and of the data being cleaned. The data cleaning included changing a column from “male” to “sex”, to make the data in that column clearer, also ensuring that there is no duplicates and dropping any null values. 
## Machine Learning

The purpose of our capstone project is to determine whether the patients would be at risk of having Coronary Heart Disease (CHD) in the next 10 years based on the current lifestyle and health information. The outcome of the project is labeled as whether the person will or will not have a risk of having CHD. Moreover, we have a dataset that we can use to train the model to analyze data and identify the patterns and based on the patterns, make prediction on new data. As a result, we will be using the Supervised Machine Learning category. 

Based on the learning, Supervised Machine Learning can be further divided into Regression and Classification models. Since outcome of this work is discrete we will be utilizing the classification model and due to the fact that we are predicting the binary outcome, we will be utilizing the Logistic Regression.  

For achieving the expected outcome, we will be utilizing the Scikit-learn machine leaning library for python. We will be utilizing multiple modules from Scikit-learn library which will be finalized during the course of this project. 


## Work Flow
## 1. Data and Database
<br>

- Data in .csv format:&nbsp; [framingham.csv](framingham.csv)
- Tables structure:&nbsp; [ERD](Images/ERD.png)
- Database Link on AWS:&nbsp; [postgreSQL Database](dataanalyticsdb.cxnhjzyey4ka.us-east-2.rds.amazonaws.com) 
- Data Link on AWS:&nbsp; [csv file](https://classprojectdata.s3.amazonaws.com/framingham.csv)
- RDS Link for Spark:&nbsp;  <br/> jdbc:postgresql://dataanalyticsdb.cxnhjzyey4ka.us-east-2.rds.amazonaws.com:5432/coursefinalproject
- Database connection for Python: <br/> conn = sa.create_engine('postgresql://root:postgres@dataanalyticsdb.cxnhjzyey4ka.us-east-2.rds.amazonaws.com:5432/coursefinalproject')

### - In AWS
- __Create AWS RDS__
- __Connect database to postgreSQL__
- __Create temp tables__ <br/>
  to avoid errors while importing data, we should make temp tables with only varchar data type for each field
  <br/>
  ![step3.png](Images/step3.png)
  <br/>
  
- __Create final tables with appropriate data types__

  
  ![step4.png](Images/step4.png)
  <br/>
  
- __Import CSV files__

  
  ![step4_2.png](Images/step4_2.png)
  <br/>
  
- __Check data imported properly__

  
  ![step5.png](Images/step5.png)
  <br/>
  
- __Clean and normalize data and copy into final table__

  
  ![step6_1.png](Images/step6_1.png)
  <br/>
  
  ![step6_2.png](Images/step6_2.png)
  <br/>
  
- __Join two tables and copy into a postgres view__

  
  ![step8.png](Images/step8.png)
  <br/>
  
### - in Python

- __Read data in Jupyter Notebook and make a DataFrame__

  
  ![step9.png](Images/step9.png)
  <br/>
  
- __Remove records with null value in the fields__
  
  ![step10_1.png](Images/step10_1.png)
  
  <br/>
  
- __Copy cleaned data into framingham table on AWS database__

  
  ![step11.png](Images/step12.png)
  <br/>
  
- __Check the data in table__

  <br/>
  
  ![step12.png](Images/step12.png)
  <br/>
