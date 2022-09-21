# Personal Key Indicators of Heart Disease


## Database

The database to store data during the project is postgrSQL on AWS web service.

- Data in .csv format:&nbsp; [heart_2020_cleaned.csv](heart_2020_cleaned.csv)
- Database Link on AWS:&nbsp; [postgreSQL Database](dataanalyticsdb.cxnhjzyey4ka.us-east-2.rds.amazonaws.com) 
- Data Link on AWS:&nbsp; [Data.csv](https://classprojectdata.s3.amazonaws.com/data.csv)
- RDS Link for Spark:&nbsp;  jdbc:postgresql://dataanalyticsdb.cxnhjzyey4ka.us-east-2.rds.amazonaws.com:5432/coursefinalproject


## Work Process

- Database has been created on AWS and 
- Succesfully linked to the postgreSQL database server, and 
- Been tested using Spark on Google Colab.
- Connect to RDS PostgreSQL Database : <br/> conn = sa.create_engine('postgresql://root:postgres@dataanalyticsdb.cxnhjzyey4ka.us-east-2.rds.amazonaws.com:5432/coursefinalproject')

### Read Data into Google Colab

![readData.png](Images/readData.png)


### Connect to the RDS Databse

![rdsConnect.png](Images/rdsConnect.png)

### Test the Connection

![testConnection.png](Images/testConnection.png)


