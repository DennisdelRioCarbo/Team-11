## Framingham 10 year risk of future (CHD) coronary heart disease.



## Database

The database to store data during the project is postgrSQL, a fully managed SQL relational database, deployable in the cloud and programmable via API and/or CLI. The PostgreSQL can be integrated with [Python](https://stackabuse.com/working-with-postgresql-in-python/) using [psycopg2](https://www.tutorialspoint.com/postgresql/postgresql_python.htm), [sqlAlchemy](https://docs.sqlalchemy.org/en/14/dialects/postgresql.html) and [Spark](https://spark.apache.org/docs/latest/) modules. <br/>

<br>

- Data in .csv format:&nbsp; [framingham.csv](framingham.csv)
- Database Link on AWS:&nbsp; [postgreSQL Database](dataanalyticsdb.cxnhjzyey4ka.us-east-2.rds.amazonaws.com) 
- Data Link on AWS:&nbsp; [csv file](https://classprojectdata.s3.amazonaws.com/framingham.csv)
- RDS Link for Spark:&nbsp;  jdbc:postgresql://dataanalyticsdb.cxnhjzyey4ka.us-east-2.rds.amazonaws.com:5432/coursefinalproject
- Database connection for Python: <br/> conn = sa.create_engine('postgresql://root:postgres@dataanalyticsdb.cxnhjzyey4ka.us-east-2.rds.amazonaws.com:5432/coursefinalproject')


## Work Flow
### In AWS
- __Create AWS RDS__
- __Connect database to postgreSQL__
- __Create temp tables__ <br/>
  to avoid errors while importing data, we should make temp tables with only varchar data type for each field
  <br/>
  ![step3.png](Images/step3.png)
  <br/>
- __Create final tables with appropriate data types__

  <br/>
  ![step4.png](Images/step4.png)
  <br/>
- __Import CSV files__

  <br/>
  ![step4_2.png](Images/step4_2.png)
  <br/>
  
- Check data imported properly

  <br/>
  ![step5.png](Images/step5.png)
  <br/>
  
- __Clean and normalize data and copy into final table__

  <br/>
  ![step6_1.png](Images/step6_1.png)
  <br/>
  ![step6_2.png](Images/step6_2.png)
  <br/>
  
- __Join two tables and copy into a postgres view__

  <br/>
  ![step8.png](Images/step8.png)
  <br/>
  
### in Python

- __Read data in Jupyter Notebook and make a DataFrame__

  <br/>
  ![step9.png](Images/step9.png)
  <br/>
  
- __Remove records with null value in the fields__

  <br/>
  ![step10_1.png](Images/step10_1)
  ![step10_2.png](Images/step10_2)
  <br/>
  
- __Copy cleaned data into framingham table on AWS database__

  <br/>
  ![step11.png](Images/step12.png)
  <br/>
  
- __Check the data in table__

  <br/>
  ![step12.png](Images/step12.png)
  <br/>
  




