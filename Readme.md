# NYC311 - Customer Service Requests Analysis

## DESCRIPTION

**Background of Problem Statement :**

NYC 311's mission is to provide the public with quick and easy access to all New York City government services and information while offering the best customer service. Each day, NYC311 receives thousands of requests related to several hundred types of non-emergency services, including noise complaints, plumbing issues, and illegally parked cars. These requests are received by NYC311 and forwarded to the relevant agencies such as the police, buildings, or transportation. The agency responds to the request, addresses it, and then closes it.

**Problem Objective :**

Perform a service request data analysis of New York City 311 calls. 

## DATASET EXPLORATION & DATA WRANGLING 
The 311 dataset spanned from month-yyy to month-yyy, i.e., Moreover, the following explores more about the dataset:
- The orignal dataset has 300,698 rows and 53 columns `df.shape`
- Data type of column date was changed to datetime, to easily work with datetime in pandas 
- Used `df.isna().sum()` to determine the missing values in each column. `df.info()` also provides the Non-Null Count and datatype for each column. Dropped the following columns with no data. 
```Python
drop_columns=["Landmark","School or Citywide Complaint","Vehicle Type","Taxi Company Borough"
             ,"Taxi Pick Up Location","Bridge Highway Name","Bridge Highway Direction",
             "Road Ramp","Bridge Highway Segment","Garage Lot Name","Ferry Direction",
             "Ferry Terminal Name"]
```
- Find and replace NYPD to New York City Police Department in the Agenct Name column. 
- Merged the geopandas NYC Burough geometry with the orignal dataset to get the burough multipolygon geometry

## DATA ANALYSIS & INSIGHT
The following analysis were performed on the dataset
- Number of records by Complaint Type. 
The following table tells us that blocked driveway, illegal parking, noise (street, commercial & vehicle) are amongst the highest complaint type received by 311  
- Number of records by Status & Complaint Type
- Number of records/tickets by Burough
The highest number of requests came from Brooklyn 
- Number of records/tickets by Month & Burrough
Highest number of tickets created by month and burrogh.
- Avg response time by Complaint Type and  Location Type
response time is defined as 
```python
df['Request_Closing_Time']=df['Closed Date'] - df['Created Date']
```
- Avg response time by Borough and Complaint Type

### Python Libraries utilized
- Pandas
- Numpy
- geopandas
- contextiy

