## Framingham 10 year risk of future (CHD) coronary heart disease.

## Step One: Database

The database to store data during the project is postgrSQL, a fully managed SQL relational database, deployable in the cloud and programmable via API and/or CLI. The PostgreSQL can be integrated with [Python](https://stackabuse.com/working-with-postgresql-in-python/) using [psycopg2](https://www.tutorialspoint.com/postgresql/postgresql_python.htm), [sqlAlchemy](https://docs.sqlalchemy.org/en/14/dialects/postgresql.html) and [Spark](https://spark.apache.org/docs/latest/) modules. <br/>

<br>

- Raw dataset:&nbsp; [framingham.csv](framingham.csv)
- Clean dataset:&nbsp; [fragmingham.csv](fragmingham.csv)
- Tables structure:&nbsp; [ERD](Images/ERD.png)
- Database Link on AWS:&nbsp; [postgreSQL Database](dataanalyticsdb.cxnhjzyey4ka.us-east-2.rds.amazonaws.com) 
- Data Link on AWS:&nbsp; [csv file](https://classprojectdata.s3.amazonaws.com/framingham.csv)
- RDS Link for Spark:&nbsp;  jdbc:postgresql://dataanalyticsdb.cxnhjzyey4ka.us-east-2.rds.amazonaws.com:5432/coursefinalproject
- Database connection for Python: <br/> conn = sa.create_engine('postgresql://root:postgres@dataanalyticsdb.cxnhjzyey4ka.us-east-2.rds.amazonaws.com:5432/coursefinalproject')


## Work Flow
### on AWS
- __Create AWS RDS__
- __Connect database to postgreSQL__
- __Create temp tables__ <br/>
  to avoid errors while importing data, we should make temp tables with only varchar data type for each field
  <br/>
  ![tempTable.png](Images/tempTable.png)
  <br/>
  
- __Create final tables with appropriate data types__

  
  ![mainTable.png](Images/mainTable.png)
  <br/>
  
- __Import CSV files__

  
  ![importCSV2.png](Images/importCSV2.png)
  <br/>
  
- __Check data imported properly__

  
  ![checkPostgresData.png](Images/checkPostgresData.png)
  <br/>
  
- __Clean and normalize data and copy into final table__

  
  ![normalizeData1.png](Images/normalizeData1.png)
  <br/>
  
  ![normalizeData2.png](Images/normalizeData2.png)
  <br/>
  
- __Join two tables and copy into a postgres view__

  
  ![joinTables.png](Images/joinTables.png)
  <br/>
  
### in Python

- __Read data in Jupyter Notebook and make a DataFrame__

  
  ![fromAWS.png](Images/fromAWS.png)
  <br/>
  
- __Remove records with null value in the fields__
  
  ![removeNulls.png](Images/removeNulls.png)
  
  <br/>
  
- __Copy cleaned data into framingham table on AWS database__

  
  ![toAWS.png](Images/toAWS.png)
  <br/>
  
- __Check the data in table__

  <br/>
  
  ![checkDataTable.png](Images/checkDataTable.png)

<br/>
  

## Step Two: Generating Images to use in the Presentation and Dashboard
Using [matplot](https://chartio.com/resources/tutorials/how-to-save-a-plot-to-a-file-using-matplotlib/) method &nbsp; .savefig()  we can output the chart to a file. <br/> [graphs.ipynb]()

ex. &nbsp; plt.savefig('correlation_plot.png') <br/>






