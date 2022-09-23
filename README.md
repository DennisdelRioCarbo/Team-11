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

## Questions hoped to be answered with the data

- Can we predict if someone  is at risk of getting  heart disease given personal key indicators within 10 years?

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
The machine learning algorithm that works best for the dataset we are planning to use for this project would be supervised machine learning, and we have a target variable present in the dataset. It is ideal as we would like our dataset to predict whether the patients would be at risk of having coronary heart disease in the next 10 years. We will map out a decision tree diagram to help us decide on the variables we will be using in order to successfully predict the outcomes.  
