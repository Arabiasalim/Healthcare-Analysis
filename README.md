# Healthcare-Analysis

## Table of contents 
- [Introduction](introduction)
- [Data Overview](data-overview)
- [Data cleaning/Transformation](Data-cleaning/Transformation)
- [Data Analysis](Data-Analysis)
- [Data Visualization](Data-visualization)
- [Challenges](Challenges)
- [Recommendations](Recommendations)
- [Conclusion](Conclusions)

### Introduction
The purpose of this analysis is to provide insights into patient charges, provider information ,ICD10 diagnosis and hospital performance for inpatient and outpatient services across the years 2011 to 2013. The assessment aims to showcase skills in data cleaning, SQL querying, data visualization,data enrichment and deriving actionable insights.

### Data Overview 
#### Description of Data Sources
- Inpatient Data (2011-2013): Three JSON files converted to CSV format, covering hospital inpatient information.
- outpatient Data: Stored in an SQLite database (outpatient_charges.db).
- Hospital General Information: An XLS and XLSX file containing details on hospital facilities.

#### Data Preparation Process

The raw data files were downloaded, converted, and imported into Pandas and Jupyter Notebook for cleaning. Subsequently, cleaned data was uploaded to BigQuery for more robust analysis and aggregation.

### Data Cleaning and Transformation
- Data Conversion: Converted JSON files to CSV using Pandas.
- Handling Missing Values: Missing data was addressed by filling nulls where appropriate or removing records when necessary to maintain data integrity.
- Data Standardization: Standardized date formats, column names, and data types across datasets.
- Merging Tables: Merged related tables using keys such as Patient ID.
- Using queries to merge Tables.

  
### Tools
1. Jupiter Notebook
2. Pandas
3. Python
4. SQLite Studio
5. Bigquery
6. Looker Studio
   
### Exploratory Data Analysis 

EDA involved exploring the data to answer key questions such as better understanding of the structure, distribution and the quality of the datasets. This step helped identify potential issues and opportunities for deeper analysis

### Data Analysis and SQL Queries in BigQuery

#### Combining and Aggregating Inpatient Data

Using SQL queries with Common Table Expressions (CTEs), inpatient data from 2011, 2012, and 2013 was combined into a single table. A year column was added to distinguish data points across years, and aggregations were performed to obtain total payments and patient trends.
```Query
```

#### Combining and Aggregating Outpatient Data

Outpatient data from 2011-2013 was extracted from the SQLite database and uploaded to BigQuery. Similar transformations as described for inpatient data were applied, with CTEs used to combine data across years.

#### Merging with Hospital General Information

The combined inpatient and outpatient datasets were joined with hospital general information to enhance context and provide a holistic view of hospital performance.

### Results/Findings 
#### Key Visualizations
Using looker studio, I developed a comprehensive dashboard, including
- Bar Chart comparison of average payments
- Trends over time
- top 10 and bottom 10 average charges 

### Challenges Encountered

### Recommendations
-Further analysis could be performed on patient demographics to offer deeper insights.
- Machine learning models may be explored for predictive analytics.
- Additional data on hospital services, patient ID and  patient feedback  would enhance the analysis.

### Limitations
- Data Completeness - The datasets only coverd inpatient and outpatient data from 2011-2013, which limits the ability to assess long tem trends or challenges beyond this period.
  

### Reference 
1. [ICD documentation](icd.who.int)
2. various online resources for SQL and data analysis best practises
3. Savannah Informatics official website for color analysis 


### Conclusion
This assessment demonstrated the ability to transform raw data into meaningful insights using data engineering, SQL querying, and data visualization techniques. The final dashboard offers a useful tool for monitoring trends and decision-making support.

