# Technologies Used
## Data Cleaning and Analysis
Data cleaning is an essential step as it will dictate the flow of the entire project. It will allow for any step taken afterwards to be done efficiently. For our dataset, Pandas will be used to clean the data, to drop any unnecessary columns/rows.
## Database Storage
The database was created on AWS and then linked to postgresSQL, which is the database we intend to use. The data was tested using Spark on Google Colab. In the branch called “laleh”, there are links to where the data has been stored and points on the work process. There are also screenshots of the data being read using various dependencies and of the data being cleaned. The data cleaning included changing a column from “male” to “sex”, to make the data in that column clearer, also ensuring that there is no duplicates and dropping any null values. 
## Machine Learning
The machine learning algorithm that works best for the dataset we are planning to use for this project would be supervised machine learning, and we have a target variable present in the dataset. It is ideal as we would like our dataset to predict whether the patients would be at risk of having coronary heart disease in the next 10 years. We will map out a decision tree diagram to help us decide on the variables we will be using in order to successfully predict the outcomes.  
