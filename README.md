# Personal Key Indicators of Heart Disease


## Database

The database to store data during the project is postgrSQL, a fully managed SQL relational database, deployable in the cloud and programmable via API and/or CLI. The PostgreSQL can be integrated with [Python](https://stackabuse.com/working-with-postgresql-in-python/) using [psycopg2](https://www.tutorialspoint.com/postgresql/postgresql_python.htm), [sqlAlchemy](https://docs.sqlalchemy.org/en/14/dialects/postgresql.html) and [Spark](https://spark.apache.org/docs/latest/) modules. <br/>

<br>

- Data in .csv format:&nbsp; [framingham.csv](framingham.csv)
- Database Link on AWS:&nbsp; [postgreSQL Database](dataanalyticsdb.cxnhjzyey4ka.us-east-2.rds.amazonaws.com) 
- Data Link on AWS:&nbsp; [csv file](https://classprojectdata.s3.amazonaws.com/framingham.csv)
- RDS Link for Spark:&nbsp;  jdbc:postgresql://dataanalyticsdb.cxnhjzyey4ka.us-east-2.rds.amazonaws.com:5432/coursefinalproject


## Work Process

- Database has been created on AWS
- Succesfully linked to the postgreSQL database server, and 
- Been tested using Spark on Google Colab and Panadas library.
- Connect to RDS PostgreSQL Database : <br/> conn = sa.create_engine('postgresql://root:postgres@dataanalyticsdb.cxnhjzyey4ka.us-east-2.rds.amazonaws.com:5432/coursefinalproject')

### Read the Data

![readData.png](Images/readData.png)

### Clean the Data

![cleanData.png](Images/cleanData.png)


### Copy the cleaned data into a table on Postgres

![copytoPostgres.png](Images/copytoPostgres.png)


### Connect to the RDS Databse

![rdsConnect.png](Images/rdsConnect.png)

### Test the Connection

![testConnection.png](Images/testConnection.png)


