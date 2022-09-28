# Team-11

## EDA and Machined Learning 
This branch contains cleaning and  EDA of the *framingham.csv* dataset in jupyter notebook with connections to the postgresql database and a file using supervised machine learning  with *Logistic Regression*.

- Description of preliminary data preprocessing. For the data preprocessing the data was imported from the database in AWS and connected to postgresql using sqlalchemy. The data was checked for duplicated and null values. The null valued were dropped and there were no duplicate entries. The column 'male' was changed to 'sex' for clarity. 
Given the difference in values between the features and some features being continuous and some categorical the data was standardized using *scikitlearn StandardScaler*.

![image](https://user-images.githubusercontent.com/104289098/192667826-c79b16f6-43b7-4f90-9159-418c3de08137.png)

![image](https://user-images.githubusercontent.com/104289098/192667860-4c180af6-cc1b-4e11-bd4c-3d27b76429a2.png)

- Description of preliminary feature engineering and preliminary feature selection, including decision making process.
The dataset contains to similar features, one of them is if the participant smokes *currentSmoker* and number of cigarettes per day *cigsPerDay* that the person smokes. *currenSmoker* is categorical (0=non-smoker or 1=smoker) and *cigsPerDay* is continuous (float64). If *currentSmoker* is 0, then *cigsPerDay* would be 0. These two features seemed to be redundant in the dataset so *currentSmoker* was dropped in favour of *cigsPerDay*  as it was considered that the number of smoked cigarettes per day could be influence more the outcome.
Our target  is *TenYearCHD* which is the result of the Framingham risk score that determines whether a person is at risk of developing coronary heart disease in 10 years. The values of the target are categorical as int64 (0=is not at risk of developing  CHD in ten years/1=at risk of developing CHD in ten years).
The features are: *sex, age, education, currentSmoker, cigsPerDay, BPMeds, prevalentStroke, prevalentHyp, diabetes, totChol, sysBP, diaBP, BMI, heartRate* and *glucose*.

![image](https://user-images.githubusercontent.com/104289098/192667920-794bb7bd-c80a-417e-8d6a-baa11260ddbe.png)

Given that the dataset is imbalanced we resampled the data using *RandomOverSampler* from the *imblearn* library.

![image](https://user-images.githubusercontent.com/104289098/192668888-0989a737-0c4a-4e3d-9da3-0c72fc12ecf5.png)

- Description for how data was split into training and testing sets. The data was split into training and testing sets using the *scikitlearn* module *test_train_split*. Given the imbalance in the dataset in the target class (*TenYearCHD*) the data was stratified (*stratify=y*) during the split.

![image](https://user-images.githubusercontent.com/104289098/192670375-6409bf48-3dad-4c74-b983-a464bc215167.png)


- Explanation of model choice, including limitations and benefits. The first Machine Learning  model we chose is *Logistic Regression* as we are trying to predict a discrete binary outcome. Logistic regression is easier to implement, interpret, and very efficient to train. It can have good accuracy for many simple data sets and it performs well when the dataset is linearly separable. 
*Limitations* 
