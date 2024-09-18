Project Title
Implementing Data Analytic Platform for Council Voting Records
Objective
The goal of this project is to develop a comprehensive data analytic platform using AWS to manage, analyze, and visualize the Council Voting Records dataset from the City of Vancouver. This platform will enable efficient data handling and provide valuable insights into council voting patterns, facilitating informed decision-making and transparency.
Dataset
The dataset comprises detailed records of council meetings and votes, including:
•	Meeting ID: Unique identifier for each council meeting.
•	Vote ID: Unique identifier for each vote within a meeting.
•	Councilor ID: Identifier for the councilor casting the vote.
•	Vote Date: Date on which the vote was cast.
•	Agenda Item: Description of the item or issue being voted on.
•	Vote Result: Outcome of the vote (e.g., Yes, No, Abstain).
Methodology
1.	Data Collection and Preparation:
o	Steps: Utilized AWS Glue to create a crawler that detects and extracts the schema of the dataset. Configured Glue to catalog this metadata in the AWS Glue Data Catalog, ensuring organized and accessible data management.
2.	Data Discovery:
o	Steps: Reviewed the metadata and schema that AWS Glue discovered to ensure it accurately represents the dataset. Verified that all necessary fields were correctly identified and categorized for further use.
3.	Data Storage Design:
o	Steps: Established an S3 bucket to securely store the dataset. Configured access controls and encryption settings to protect the data and ensure compliance with data security requirements.
4.	Dataset Preparation:
o	Steps: Employed AWS Glue ETL jobs to clean and transform the data. This process included handling missing values, correcting inconsistencies, and applying necessary transformations to prepare the data for analysis.
5.	Data Ingestion:
o	Steps: Set up AWS Glue jobs to ingest data from the S3 bucket into AWS Redshift, a data warehousing solution. Configured transformation pipelines to process and load the data efficiently into Redshift.
6.	Data Storage:
o	Steps: Loaded the cleaned and transformed data into AWS Redshift. Created tables and indexes to facilitate efficient querying and data retrieval, ensuring the data was well-organized for analysis.
7.	Data Pipeline Design:
o	Steps: Designed and implemented data pipelines using AWS Glue and AWS Step Functions. These pipelines automate the processes of data ingestion, transformation, and loading, ensuring a streamlined and automated workflow.
8.	Data Cleaning:
o	Steps: Applied additional data cleaning techniques using AWS Glue scripts. Conducted validation checks to confirm data quality and completeness, addressing any discrepancies found during the cleaning process.
9.	Data Structuring:
o	Steps: Structured the data within AWS Redshift to optimize for query performance. Created views and materialized views to facilitate complex queries and support efficient data analysis.
10.	Data Pipeline Implementation:
o	Steps: Deployed the data pipelines and configured monitoring using AWS CloudWatch. This setup ensures that the data processing is regularly executed and any issues are promptly identified and addressed.
11.	Data Analysis:
o	Steps: Performed data analysis using SQL queries in AWS Redshift. Analyzed voting patterns, trends, and other insights to provide valuable information on council voting behavior.
12.	Data Visualization:
o	Steps: Created visualizations and interactive dashboards using Amazon QuickSight. Designed charts and graphs to effectively illustrate voting trends and patterns, making the data more accessible and interpretable.
13.	Data Publishing:
o	Steps: Published the final reports and dashboards for stakeholder access through Amazon QuickSight. Configured access controls to ensure that only authorized users can view and interact with the reports.
Tools and Technologies
•	AWS Glue: Used for data crawling, ETL jobs, and metadata cataloging.
•	Amazon S3: Provided scalable and secure storage for the dataset.
•	AWS Redshift: Enabled data warehousing and efficient querying and analysis.
•	AWS CloudWatch: Monitored data processing and pipeline performance.
•	Amazon QuickSight: Facilitated data visualization and reporting.
Deliverables
•	Report: A detailed document summarizing the implementation steps, processes, and findings from the analysis.
•	Dashboards: Interactive visualizations created in Amazon QuickSight, showcasing key trends and insights from the voting records.

