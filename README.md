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

- Average outpatient(inclusive of copayments) and inpatient medicare payments ranked per provider for each year of available data.

- Time series analysis on the average charge on different APC services per provider over the three years

- Geographical analysis by state on affordable providers that offer emergency charges

- Analyze the top 10 prominent inpatient ICD10 diagnosis based on state using their ICD10 Chapter and Block Descriptions


### Data Analysis and SQL Queries in BigQuery

#### Combining and Aggregating Inpatient Data

Using SQL queries with Common Table Expressions (CTEs), inpatient data from 2011, 2012, and 2013 was combined into a single table. A year column was added to distinguish data points across years, and aggregations were performed to obtain total payments and patient trends.
```Query
SELECT 
  *,
  2011 AS year
FROM 
  `savannah-patients.savannah_dataset.raw_inpatient_2011`

UNION ALL
SELECT 
  *,
  2012 AS year
FROM 
  `savannah-patients.savannah_dataset.raw_inpatient_2012`

UNION ALL
SELECT 
  *,
  2013 AS year
FROM 
  `savannah-patients.savannah_dataset.raw_inpatient_2013`
`
```

#### Combining and Aggregating Outpatient Data

Outpatient data from 2011-2013 was extracted from the SQLite database and uploaded to BigQuery. Similar transformations as described for inpatient data were applied, with CTEs used to combine data across years.

#### Merging with Hospital General Information

The combined inpatient and outpatient datasets were joined with hospital general information to enhance context and provide a holistic view of hospital performance.

### Results/Findings 
#### Key Visualizations
Using looker studio, I developed a comprehensive dashboard, including: 
- Bar Chart comparison of average payments
 ![bar graph](https://github.com/user-attachments/assets/1c007b94-1b9a-46ab-91f5-5407b1a9ab1a)
- Trends over time
- top 10 and bottom 10 average charges
- Diagnosis over time
- top 10 icd chapters and block description by state
- Top ICD categories by provider 

### Challenges Encountered
- ICD code merging issue- merging ICD codes with the combined inpatient and outpatient data proved difficult due to mismatches.
 - Resolution/ learning - careful analysis and mapping was applied, ensuring consistent and accurate merging to allow meaningful diagnosis focused visualization.
- Time constraints-meeting the deadline for the assessment while maintaining high quality analysis and visualizationwas demanding
 - I managed my time by breaking down the tasks into smaller milestones, prioritizing critical analysis area first and ensuring consistent progress through well defineddaily goals
### Recommendations
- Further analysis could be performed on patient demographics to offer deeper insights.
- Machine learning models may be explored for predictive analytics.
- Additional data on hospital services, patient ID and  patient feedback  would enhance the analysis.

### Limitations
- Data Completeness - The datasets only covered inpatient and outpatient data from 2011-2013, which limits the ability to assess long tem trends or challenges beyond this period.
  

### Reference 
1. [ICD documentation](icd.who.int)
2. various online resources for SQL and data analysis best practises
3. Savannah Informatics official website for color analysis 


### Conclusion
This assessment demonstrated the ability to transform raw data into meaningful insights using SQL querying, and data visualization techniques. The final dashboard offers a useful tool for monitoring trends and decision-making support.

