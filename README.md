# data-analyst-koumudhi
Project Title:
Data Wrangling for Enhanced Customer Analytics for The City of Vancouver

Objective:
The objective of this project was to prepare a clean, consolidated dataset of the City of Vancouver's council voting records. The wrangling process aimed to improve data consistency, accuracy, and usability, ultimately enabling deeper insights such as calculating the average vote count. The project was implemented on AWS to ensure scalability and performance efficiency.

Background:
The City of Vancouver has voting records accumulated from council sessions, which are often inconsistent or fragmented. Data wrangling was necessary to clean, merge, and standardize the datasets to allow for effective analysis. This process also included migrating and working on AWS for improved analytics capabilities.

Datasets:
Council Voting Records Dataset (Excel): Records of council members’ votes across various sessions.
Council Voting Records in Favor (CSV): A subset focusing on votes in favor.
Methodology:
Step 1: Data Collection
Action in AWS: Data was collected from two sources: an Excel file and a CSV file. Both were uploaded to AWS S3 for storage and easy access within the analytic platform.
Screenshot Explanation: The screenshot shows the files uploaded into AWS S3 buckets, ensuring data is stored in a centralized location and ready for further processing.
Step 2: Data Assessment
Initial Assessment: I used AWS Glue DataBrew for a quick assessment of the data, looking for missing values, duplicates, and format inconsistencies (such as date formats).
Screenshot Explanation: The screenshot displays the data profile in AWS Glue DataBrew, where issues such as null values, duplicates, and format inconsistencies were identified.
Step 3: Data Cleaning
Handling Missing Values: Missing vote counts were handled using AWS Glue's data cleaning transformations. For critical fields, rows with missing data were excluded.
Deduplication: Using AWS Glue Studio, I applied a deduplication process to remove any repeated entries.
Format Consistency: AWS Glue was also used to standardize dates and text fields (e.g., council member names were aligned for consistency).
Screenshot Explanation: Screenshots show transformations performed in AWS Glue Studio, highlighting steps for deduplication, data filtering, and standardizing fields.
Step 4: Data Transformation
Data Type Conversion: Using AWS Lambda, I converted all date fields from strings to datetime objects to enable proper time-based analytics.
Feature Engineering: AWS Glue helped derive key metrics, such as the average vote count per session. Additionally, I computed total votes and votes in favor for each session.
Aggregation: The dataset was aggregated to give insights on council voting patterns across time periods.
Screenshot Explanation: Screenshots display AWS Lambda functions converting data types and AWS Glue aggregating vote counts into useful metrics.
Step 5: Data Consolidation
Merging Datasets: AWS Glue's job orchestrator merged the Excel and CSV files based on session ID, creating a unified dataset that encompassed all votes, including those in favor.
Screenshot Explanation: The screenshot captures the AWS Glue process for merging datasets, showing successful consolidation and verification of unique session IDs.
Step 6: Documentation and Validation
Documentation: The entire wrangling process was documented using Jupyter Notebooks in AWS SageMaker, describing every step, including cleaning methods and transformations.
Validation: AWS SageMaker was used to run exploratory data analysis (EDA) to confirm the dataset’s accuracy and completeness. Key metrics like average vote counts were validated visually through Matplotlib and Seaborn charts.
Screenshot Explanation: Screenshots demonstrate the Jupyter Notebook documentation and charts generated in AWS SageMaker, showing voting trends, distribution of votes in favor, and overall vote counts.
Tools and Technologies Used:
AWS S3: For data storage.
AWS Glue: For data cleaning, transformation, and merging.
AWS Lambda: For data type conversion and feature engineering.
AWS SageMaker: For documentation, EDA, and visualization.
Excel and CSV: The initial formats of council voting records.
Python (Pandas, NumPy): For additional data manipulation.
Matplotlib and Seaborn: Used within AWS SageMaker for visualization.
Deliverables:
Cleaned and Transformed Dataset: A consolidated dataset, including metrics such as total votes, average votes per session, and votes in favor, is now ready for analysis.
Comprehensive Report: A detailed report describing the data wrangling steps, tools used, and challenges faced was created, with explanations of AWS services utilized at each stage.
Visualizations: Key insights, including trends in voting behavior, were represented through visual charts in AWS SageMaker, offering a quick glance at the final dataset’s quality.
Timeline:
Week 1: Data collection and storage in AWS S3.
Week 2: Data assessment and initial cleaning in AWS Glue.
Week 3-4: Data transformation and feature engineering using AWS Lambda and Glue.
Week 5: Data consolidation and validation in AWS SageMaker.
Week 6: Final documentation and reporting, including visualizations.
Screenshots:
AWS S3 Storage: Screenshots showing the uploaded datasets in S3.
AWS Glue DataBrew: Screenshots of the initial data assessment.
AWS Glue Studio: Screenshots of the data cleaning and transformation steps.
AWS Lambda Functions: Screenshots of data type conversions and feature engineering.
AWS SageMaker Jupyter Notebooks: Screenshots documenting the process and showing validation charts.
Conclusion:
This project successfully used AWS to perform end-to-end data wrangling on the City of Vancouver’s council voting records. Through cleaning, transforming, and consolidating datasets, we derived valuable metrics like the average vote count per session. AWS's scalable and powerful tools allowed for a smooth, efficient process, ensuring a robust final dataset for deeper analysis.
