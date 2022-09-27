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

## Expected Outcome/Questions hoped to be answered by the data. 

- Can we predict if an individual will develop Coronary Heart Disease (CHD) within ten years given certain risk factors?
- What is the correlation between different risk factors associated with heart disease?
- How are the different risk factors correlated with sex (male/female)?
- Which factors have more weight in predicting CHD?
- Prediction of an individual developing heart disease within next 10 years based on the personal health and lifestyle information.
- The prediction will help the medical professionals identifying the preventative measures to reduce the risk and educating patients on the risk if adequate care is not employed.

## Communication Protocol
- Slack Channel for Team 11
- Email
- Zoom meeting during virtual class time and office hours.
- Git hub

# Technologies Used
## Data Cleaning and Analysis
Data cleaning is an essential step as it will dictate the flow of the entire project. It will allow for any step taken afterwards to be done efficiently. For our dataset, Pandas will be used to clean the data, to drop any unnecessary columns/rows.
## Database Storage
The database was created on AWS and then linked to postgresSQL, which is the database we intend to use. 
## Machine Learning
The purpose of our capstone project is to determine whether the patients would be at risk of having Coronary Heart Disease (CHD) in the next 10 years based on the current lifestyle and health information. The outcome of the project is labeled as whether the person will or will not have a risk of having CHD. Moreover, we have a dataset that we can use to train the model to analyze data and identify the patterns and based on the patterns, make prediction on new data. As a result, we will be using the Supervised Machine Learning category. 

Based on the learning, Supervised Machine Learning can be further divided into Regression and Classification models. Since outcome of this work is discrete we will be utilizing the classification model and due to the fact that we are predicting the binary outcome, we will be utilizing the Logistic Regression.  

For achieving the expected outcome, we will be utilizing the Scikit-learn machine leaning library for python. We will be utilizing multiple modules from Scikit-learn library which will be finalized during the course of this project. 

## Dashboard 

## Data exploration.
The data was imported from the database and displayed as a DataFrame using Pandas.The dataset contained 3,658 rows and 16 columns. We explored the column names which are the ones mentioned previously and the data types which are either *float64* or *int64*. One of the column names was changed from “male” to “sex” when the data file was imported into the database as we thought it better represented the feature. We looked for null and duplicate values which we didn't find any. We then proceeded to explore graphycally how the data in the different columns is distributed, and performed basic statistic exploration with pandas .describe() method. We also  explored correlations and relationships  between the different features graphycally. 
Refer to **framingham_eda.ipynb file** for code and graphs. 
  
## Data analysis
After exploring and performing an initial analysis of the data, some of the findings are the following: 
- **Age** The age of the individuals in the dataset ranges between 32 and 70 years old. With only one participant being 32 and one participant being 70 years old. Most participants are between 40 and 59 years old. The mean age is 49.5 years old.
- **Sex** The dataset seems to be equally distributed among men and women. Out of the 3,658 participants there is a slight majority of women with 2,035 (55.6%) participants and 1,623 (44.4%) of men participants.
- **Distribution** Most continuous variables seem to show a normal distribution.  Total cholesterol (totChol), systolic blood pressure (sysBP), body mass index (BMI), heart rate (hearRate) and glucose (glucose) seem to present outliers.
 - **Correlation** The variables that show high correlation are systolic blood pressure (sysBP) and prevalent hypertension (prevalentHyp) which would be expected; the same goes for glucose and diabetes. The ten year coronary heart disease prediction does not show a high correlation with any of the variables.
 - **Ten Year Coronary Heart Prediction (TenYearCHD)** Of the 3,658 participants 557 (15.2%) are predicted to develop coronary heart disease within ten years. Out of the 557 positively predicted, 250 of those are women and 307 are men.
The risk of developing CHD within ten years is higher in people over 50 years old of both ages.
- **Smoking (currentSmoker/cigsPerDay)** Of all 3,658 participants almost half of them (1,789 or 48.9%) are smokers against 1,869 (51.1%) of non smokers.
There is a higher prevalence of smokers amongst men. Most smokers smoke around 20 cigarettes a day (1 pack).
- **Body Mass Index (BMI)** The body mass index seem to show a normal distribution with some of the outliers of higher values belonging to women.
Participants of both sexes who are predicted (1) to develop CHD within ten years present higher body mass index values.
- **Systolic Blood Pressure (sysBP)** Not all participants who are predicted (1) to develop CHD present high systolic blood pressures and neither do all participants who smoke present higher blood pressure.
- **Total Cholesterol (totChol)** Participants who are at risk of developing CHD do not seem to present higher levels of cholesterol than those who do not.
- **Glucose** Not all participants who are at risk of developing CHD (class 1) within ten years show having higher levels of glucose.
- **Diabetes** Only 99 (2.7%) participants reported having diabetes.
- **Hypertension (prevalentHyp)** 1,148 (31.2%) of participants responded to having prevalent hypertension. Women a more prone to present hypertension specially after age 50 whereas it seems to be more equally distributed amongst men of all ages.
There is more prevalent hypertension amongst participants at risk of developing CHD (class 1) .
- **Blood Pressure Medication (BPMeds)** Only 111 (3%) of participants reported taking blood pressure medication.
- **Stroke (prevalentStroke)** Only 21 (0.6%) of participants responded to having had a stroke.

## Work Flow
## 1. Data and Database
<br>

- Data in csv format:&nbsp; [framingham.csv](finalFiles/framingham.csv)
- Tables structure:&nbsp; [ERD](finalFiles/Images/ERD.png)
- Database Link on AWS:&nbsp; [postgreSQL Database](dataanalyticsdb.cxnhjzyey4ka.us-east-2.rds.amazonaws.com) 
- Data Link on AWS:&nbsp; [csv file](https://classprojectdata.s3.amazonaws.com/framingham.csv)
- RDS Link for Spark:&nbsp;  <br/> jdbc:postgresql://dataanalyticsdb.cxnhjzyey4ka.us-east-2.rds.amazonaws.com:5432/coursefinalproject
- Database connection for Python: <br/> conn = sa.create_engine('postgresql://root:postgres@dataanalyticsdb.cxnhjzyey4ka.us-east-2.rds.amazonaws.com:5432/coursefinalproject')

### - on AWS
- __Create AWS RDS__
- __Connect database to postgreSQL__
- __Create temp tables__ <br/>
  to avoid errors while importing data, we should make temp tables with only varchar data type for each field
  <br/>
  ![step3.png](finalFiles/Images/step3.png)
  <br/>
  
- __Create final tables with appropriate data types__

  
  ![step4.png](finalFiles/Images/step4.png)
  <br/>
  
- __Import CSV files__

  
  ![step4_2.png](finalFiles/Images/step4_2.png)
  <br/>
  
- __Check data imported properly__

  
  ![step5.png](finalFiles/Images/step5.png)
  <br/>
  
- __Clean and normalize data and copy into final table__

  
  ![step6_1.png](finalFiles/Images/step6_1.png)
  <br/>
  
  ![step6_2.png](finalFiles/Images/step6_2.png)
  <br/>
  
- __Join two tables and copy into a postgres view__

  
  ![step8.png](finalFiles/Images/step8.png)
  <br/>
  
### - in Python

- __Read data in Jupyter Notebook and make a DataFrame__

  
  ![step9.png](finalFiles/Images/step9.png)
  <br/>
  
- __Remove records with null value in the fields__
  
  ![step10_1.png](finalFiles/Images/step10_1.png)
  
  <br/>
  
- __Copy cleaned data into framingham table on AWS database__

  
  ![step11.png](finalFiles/Images/step12.png)
  <br/>
  
- __Check the data in table__

  <br/>
  
  ![step12.png](finalFiles/Images/step12.png)
  <br/>
