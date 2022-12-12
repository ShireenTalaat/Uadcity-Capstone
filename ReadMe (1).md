## Data Engineering Capstone Project 

Udacity provided four datasets to be explored through this project. The main dataset will include data on immigration to the United States, 
and supplementary datasets will include data on airport codes, U.S. city demographics, and temperature data.

The goal of this project is to create an ETL pipeline using using these datasets. 


### Instructions
THIS project is broken down into a series of steps.

#### Step 1: Scope the Project and Gather Data
Since the scope of the project will be highly dependent on the data, these two things happen simultaneously.
In this step data will be identified and gathered.

#### Step 2: Explore and Assess the Data
Explore the data to identify data quality issues, like missing values, duplicate data, etc.
Document steps necessary to clean the data

#### Step 3: Define the Data Model
Map out the conceptual data model with model explaintion. 
List the steps necessary to pipeline the data into the chosen data model
![diagrame](capstone.png)


#### Step 4: Run ETL to Model the Data
- Create the data pipelines and the data model
- Include a data dictionary
- Run data quality checks to ensure the pipeline ran as expected
- Integrity constraints on the relational database (e.g., unique key, data type, etc.)
- Unit tests for the scripts to ensure they are doing the right thing
- Source/count checks to ensure completeness

#### Step 5: Complete Project Write Up
What's the goal?
The goal is to check the flow of immigrants to the US using airport data, temperature data, demographic data, and a huge dataset from the US National Tourism and Trade Office. 

How often the data should be updated and why?
The data should be updated monthly in conjunction with the current raw file format.

Spark was chosen since it can easily handle multiple file formats (including SAS) containing large amounts of data. Spark SQL was chosen to process the large input files into dataframes and manipulated via standard SQL join operations to form additional tables.

If the data needs to populate a dashboard daily to meet an SLA then we could use a scheduling tool such as Airflow to run the ETL pipeline overnight.

If I had 100x times the size of the processed files I would load the data into AWS S3, then use spark to do EDA, load it back to S3 and finally ETL into Redshift.

Redshift is a good fit if 100 persons would need to access the data, it should be able to handle this with no problem. We could increase the specs of our cluster if it was not fast enough to serve everyone.

