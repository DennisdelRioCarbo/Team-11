# Team-11

## Presentation Link
https://docs.google.com/presentation/d/18XLgKJ3PVczhViG3uts_fAbnepvY002qdzyHd9rh7xY/edit?usp=sharing

# **Framingham 10 year risk of future (CHD) coronary heart disease.**

## Reason topic selected
According to the CDC *heart disease* is the leading cause of death in the United States and the number one killer in Canada, it is also the most costly disease in Canada, putting the greatest burden on our national health care system.

A number of factors, individually or in combination, can lead to heart disease, namely: high blood pressure, high blood cholesterol, and smoking are key risk factors for heart disease. About half of people in the United States (47%) have at least one of these three risk factors. Several other medical conditions and lifestyle choices can also put people at a higher risk for heart disease, including: diabetes, overweight and obesity, unhealthy diet, diets rich in saturated fat, physical inactivity, excessive alcohol use, stress and a family history of heart disease

Men are generally more likely to develop heart disease. An increasing number of women are experiencing heart disease but they are under-diagnosed. For both sexes, the risk of heart disease increases with age.

### Framingham heart study dataset

The **Framingham Risk Score** is a sex-specific algorithm used to estimate the 10-year cardiovascular risk of an individual. The **"Framingham"** heart disease dataset includes over 4,240 records, 16 columns and 15 attributes. The goal of the dataset is to predict whether the patient has 10-year risk of future (CHD) coronary heart disease.
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
Data cleaning is an essential step as it will dictate the flow of the entire project. It will allow for any step taken afterwards to be done efficiently. For our dataset, *Pandas* will be used to clean the data, to drop any unnecessary columns/rows. *Matplotlib* and *seaborn* for graphs and visualizations.

## Data exploration
The data was imported from the database and displayed as a DataFrame using Pandas. The dataset contained 3,658 rows and 16 columns. We explored the column names which are the ones mentioned previously and the data types which are either *float64* or *int64*. One of the column names was changed from “male” to “sex” when the data file was imported into the database as we thought it better represented the feature. We looked for null and duplicate values which we didn't find any. We then proceeded to explore graphically how the data in the different columns is distributed, and performed basic statistic exploration with pandas. We also explored correlations and relationships  between the different features graphically. 
Refer to `framingham_eda.ipynb` file for code and graphs. 

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


## Machine Learning
- Refer to `framingham_ml.ipynb` file for code.

### Preliminary data preprocessing
For the data preprocessing the data was imported from the database in *AWS* and connected to *postgresql* using *sqlalchemy*. The data was checked for duplicate and null values. The null values were dropped and there were no duplicate entries. The column 'male' was changed to 'sex' for clarity. This part of the preprocessing was done when the data was imported to the database.

Given the difference in values  and that some features are continuous and some are categorical the data was standardized using *scikitlearn StandardScaler*.

![image](https://user-images.githubusercontent.com/104289098/192667826-c79b16f6-43b7-4f90-9159-418c3de08137.png)

![image](https://user-images.githubusercontent.com/104289098/192667860-4c180af6-cc1b-4e11-bd4c-3d27b76429a2.png)

### Preliminary feature engineering and feature selection
The dataset contains two similar features, one of them is if the participant smokes *currentSmoker* and number of cigarettes per day *cigsPerDay* that the person smokes. *currenSmoker* is categorical (0=non-smoker or 1=smoker) and *cigsPerDay* is continuous (float64). If *currentSmoker* is 0, then *cigsPerDay* would be 0. These two features showed high correlation in the exploratory data analysis  so *currentSmoker* was dropped in favour of *cigsPerDay*.
- Our target  is *TenYearCHD* which is the result of the Framingham risk score that determines whether a person is at risk of developing coronary heart disease in 10 years. The values of the target are categorical as int64 (0=is not at risk of developing  CHD in ten years/1=at risk of developing CHD in ten years).
- The rest of the features are: *sex, age, education, cigsPerDay, BPMeds, prevalentStroke, prevalentHyp, diabetes, totChol, sysBP, diaBP, BMI, heartRate* and *glucose*.

![image](https://user-images.githubusercontent.com/104289098/192667920-794bb7bd-c80a-417e-8d6a-baa11260ddbe.png)

- Given that the dataset is imbalanced we resampled the data using *RandomOverSampler* from the *imblearn* library.

![image](https://user-images.githubusercontent.com/104289098/192668888-0989a737-0c4a-4e3d-9da3-0c72fc12ecf5.png)

### How data was split into training and testing sets
The data was split into training and testing sets using the *scikitlearn* module *test_train_split*. Given the imbalance in the dataset in the target class (*TenYearCHD*) the data was stratified (*stratify=y*) during the split.

![image](https://user-images.githubusercontent.com/104289098/192670375-6409bf48-3dad-4c74-b983-a464bc215167.png)


### Model choice
The first Machine Learning  model we chose is *Logistic Regression* as we are trying to predict a discrete binary outcome. Logistic regression is easier to implement, interpret, and very efficient to train. It can have good accuracy for many simple data sets and it performs well when the dataset is linearly separable. Although we believe *Logistic regression* might work in this case, *logistic regression* inherently runs on a linear model and there are other models available which could also prove useful.

![image](https://user-images.githubusercontent.com/104289098/192915334-4e4201a8-8f3a-4eec-9a1e-3922d447b4e1.png)

### Changes in model
We compared the initial *Logistic Regression* where we resampled using *Random Oversampling* with three more models: *Logistic regression* with *SMOTEENN*, *Balanced Random Forest Classifier* and a *Neural Network*.
After running th *Balanced Random Forest Classifier* for the first time and checking the importances, we decided to drop the additional features as their importance value did not even reach 0.01: *prevalentStroke, BPMeds and diabetes*. 

![ml_importances](https://user-images.githubusercontent.com/104289098/193963789-c5209b1e-e928-4f51-875e-dce907210934.png)

We also dropped a row containing an extreme outlier for the *totChol* feature to try to minimize disruption in the model.

### Additional Model Training
we retrained the original model (*Logistic Regression with Random Oversampling*) and also trained the other models using the feature engineering mentioned above.

### Current accuracy score
- So far the *accuracy score* has not been high with any of the models with 76% being the highest on the *Neural Network*. For the problem we are trying to solve we believe it is important to have a high recall for the *TenYearCHD class 1* (people who are at risk of developing coronary heart disease) as it is important to detect all the individuals who might be at risk even if some of those predictions turn out to be wrong. So far the models have had very low precision for the * class 1 target* which brings down the *f1* score. 
- The highest recall score for the *class 1* so far has been 84% using *Logistic Regression* using *SMOTEENN* for resampling.

## Dashboard 
For our dashboard and presentation we'll use *Tableau* and *Google slides*.
### Tableau Dashboard Link
https://public.tableau.com/app/profile/ankit.naik2727/viz/CapstoneProject_16643228593060/CHDbyAgeGroupandBMI

The dashboard creation process flow diagram will be as below.
![Tableau dashboard Process Diagram](https://user-images.githubusercontent.com/103617509/193188180-19bcf4f4-ccea-4216-b64e-cadad41364f2.png)

### Data transformation steps
•	Change column name “Male” to “Gender” -- 0 – Male, 1 – Female

•	Create a column with age groups (5 years) -- Eg. 31-35, 36-40….

•	Change values of Column Current Smoker --  0 – Non-Smoker, 1 – Smoker

•	Create a column with group of cigperday -- (either 5 or 10)  Eg. 0-5, 6-10 or 0-10, 11-20

•	Change values of Column Diabetes -- 0 – No Diabetes, 1 – Diabetes

•	Create a column with cholesterol level groups -- <200 – Desirable, 200 - 239 – Borderline high, >240 High

•	Create a column with systolic blood pressure level groups -- <120 – Normal, 120-129 – Elevated, 130-139 Hypertension Stage 1, 140-179 Hypertension Stage 2, >180 Hypertensive Crisis

•	Create a column with diastolic level groups -- <80 – Normal, 80 – Elevated, 81-89 Hypertension Stage 1, 90-119 Hypertension Stage 2, >120 Hypertensive Crisis

•	Create a column with BMI level groups -- <18.5 – Underweight, 18.5-24.9 – Healthy weight, 25-29.9 Overweight, 30-39.9 Obesity, >40 Class 3 Obesity

## Illustrative Visuals for Dashboards and Story
•	Compare 10 years CHD data in different gender

•	Use the above scenario to compare between age groups

•	Define the effects of habits on different health issues

•	Compare the effect of smoking habit, diabetes, cholesterol, blood pressure and BMI on 10 years CHD
  

## Data and Database

The database was created on *AWS* and then linked to *postgresSQL*, which is the database we intend to use. Wel'll use *sqlalchemy* to connect and make queries to the database.
<br>

- Raw dataset:&nbsp; [framingham.csv](finalFiles/framingham.csv)
- Clean dataset:&nbsp; [fragmingham.csv](finalFiles/fragmingham.csv)
- Tables structure:&nbsp; [ERD](finalFiles/Images/ERD.png)
- Database Link on AWS:&nbsp; [postgreSQL Database](dataanalyticsdb.cxnhjzyey4ka.us-east-2.rds.amazonaws.com) 
- Data Link on AWS:&nbsp; [csv file](https://classprojectdata.s3.amazonaws.com/framingham.csv)
- RDS Link for Spark:&nbsp;  <br/> jdbc:postgresql://dataanalyticsdb.cxnhjzyey4ka.us-east-2.rds.amazonaws.com:5432/coursefinalproject
- Database connection for Python: <br/> conn = sa.create_engine('postgresql://root:postgres@dataanalyticsdb.cxnhjzyey4ka.us-east-2.rds.amazonaws.com:5432/coursefinalproject')

![ERD](https://user-images.githubusercontent.com/104289098/193169397-cf9f2dcc-a0b3-43d9-b8c3-314ca9f2b017.png)


### - on AWS
- __Create AWS RDS__
- __Connect database to postgreSQL__
- __Create temp tables__ <br/>
  to avoid errors while importing data, we should make temp tables with only varchar data type for each field
  ![tempTable.png](finalFiles/Images/tempTable.png)
  <br/>
  
- __Create final tables with appropriate data types__

  
  ![mainTable.png](finalFiles/Images/mainTable.png)
  <br/>
  
- __Import CSV files__

  
  ![importCSV2.png](finalFiles/Images/importCSV2.png)
  <br/>
  
- __Check data imported properly__

  
  ![checkPostgresData.png](finalFiles/Images/checkPostgresData.png)
  <br/>
  
- __Clean and normalize data and copy into final table__

  
  ![normalizeData1.png](finalFiles/Images/normalizeData1.png)
  <br/>
  
  ![normalizeData2.png](finalFiles/Images/normalizeData2.png)
  <br/>
  
- __Join two tables and copy into a postgres view__

  
  ![joinTables.png](finalFiles/Images/joinTables.png)
<br/>


### in Python

- __Read data in Jupyter Notebook and make a DataFrame__

  
  ![fromAWS.png](finalFiles/Images/fromAWS.png)
  <br/>
  
- __Remove records with null value in the fields__
  
  ![removeNulls.png](finalFiles/Images/removeNulls.png)
  
  <br/>
  
- __Copy cleaned data into fragmingham table on AWS database__

  
  ![toAWS.png](finalFiles/Images/toAWS.png)
  <br/>
  
- __Check the data in table__

  <br/>
  
  ![checkDataTable.png](finalFiles/Images/checkDataTable.png)
  <br/>

