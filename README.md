**Project Title**
Implementing Data Analytic Platform for Council Voting Records in AWS

**Objective**
The goal of this project is to develop a comprehensive data analytic platform using AWS to manage, analyze, and visualize the Council Voting Records dataset from the City of Vancouver. This platform will enable efficient data handling and provide valuable insights into council voting patterns, facilitating informed decision-making and transparency.

**Dataset**

The dataset comprises detailed records of council meetings and votes, including:

•	Meeting ID: Unique identifier for each council meeting.

•	Vote ID: Unique identifier for each vote within a meeting.

•	Councilor ID: Identifier for the councilor casting the vote.

•	Vote Date: Date on which the vote was cast.

•	Agenda Item: Description of the item or issue being voted on.

•	Vote Result: Outcome of the vote (e.g., Yes, No, Abstain).

**Methodology**

**1.	****Data Collection and Preparation:**

Data Collection and Preparation:

Steps:

AWS Glue Setup:

I started by setting up AWS Glue, accessing the console to create a Glue service role with the appropriate permissions needed to interact with data sources such as Amazon S3 or relational databases containing the dataset.

I proceeded to create a crawler within AWS Glue, which is designed to automatically discover and extract metadata from the dataset. This dataset could be stored in sources like Amazon S3, Amazon RDS, or Amazon Redshift.

During setup, I specified the data source where the dataset is located, and provided details about the file format and data structure (such as CSV, JSON, or Parquet) to ensure proper dataset interpretation.
Configuring the Crawler:

The crawler was configured to either run on a schedule or be manually triggered as needed. This ensures it can detect updates to the dataset, such as new data entries or schema changes.
As the crawler runs, it detects the schema, including details like columns, data types, and partitions.
Metadata Cataloging:

After running the crawler, AWS Glue extracted the schema information and stored it as metadata tables within the AWS Glue Data Catalog, which acts as a central metadata repository for the dataset.
The Data Catalog maintains information such as table names, column structures, data types, and partitioning details.
Data Management and Organization:

This metadata catalog allows for streamlined organization and accessibility of the dataset across other AWS services, such as AWS Athena, AWS Redshift, or AWS EMR.

The Glue Data Catalog provides a centralized view, enabling users and applications to easily query and interact with the dataset without needing to manually review its structure.
Schema Verification and Quality Assurance:

Once the metadata was cataloged, I verified the schema by querying it through AWS Athena or running a Glue job to analyze the dataset.

If any issues or discrepancies in the metadata were found, I adjusted the crawler settings (e.g., file formats, partitioning) and re-ran the crawler to ensure accuracy.

By utilizing AWS Glue, I was able to create an efficient, scalable, and automated process for data collection and preparation, ensuring the dataset is well-organized and easily accessible for downstream processing.

**2.	Data Discovery:**


Steps:

After AWS Glue had cataloged the metadata, I reviewed the schema and metadata that the crawler discovered to ensure it accurately represented the dataset.

This involved verifying that all necessary fields were correctly identified, including checking the data types for each column and ensuring that the field names matched the expected schema.

I also checked for missing fields, incorrect data types, and other potential issues in the metadata. Any discrepancies were addressed by reconfiguring the crawler or manually modifying the metadata entries.

If necessary, I added manual annotations or corrections to the metadata to ensure it was correctly categorized and ready for downstream processes.

**3.	Data Storage Design:**

Steps:

I created an Amazon S3 bucket as the primary storage location for the dataset. Amazon S3 was chosen for its scalability, durability, and ease of integration with AWS Glue and other AWS services.

To ensure data security and compliance with organizational or regulatory standards, I configured encryption settings using Amazon S3’s server-side encryption (SSE-S3 or SSE-KMS).

I applied access controls using IAM policies and S3 bucket policies to ensure that only authorized users and services could access or modify the dataset.

Versioning and logging were also enabled for data auditability and disaster recovery.


**4.	Dataset Preparation:**

Steps:

I utilized AWS Glue ETL (Extract, Transform, Load) jobs to clean and transform the raw data into a format suitable for analysis.

During the transformation process, I handled missing values by applying techniques such as imputation (filling with median, mean, or mode) or removing records with incomplete data.

Inconsistent or erroneous data points were standardized or corrected. This involved addressing inconsistencies in formats, units, or categorizations to ensure uniformity across the dataset.

I applied necessary transformations such as filtering, aggregation, and data normalization to prepare the data for ingestion into analytical platforms like Redshift.

**5.	Data Ingestion:**

Steps:

I configured AWS Glue jobs to ingest the prepared data from the Amazon S3 bucket into AWS Redshift, a high-performance cloud data warehouse.

During ingestion, I set up transformation pipelines to process the data before it was loaded into Redshift. This included partitioning, format conversion (e.g., from CSV to Parquet), and index creation for efficient querying.

The data was loaded using COPY commands in Redshift, optimized for high-speed data loading.


**6.	Data Storage:**

Steps:

Once the data was ingested into AWS Redshift, I created tables that mirrored the structure of the dataset. The table schema was carefully designed based on the type of queries that would be run during analysis.

I implemented indexes to ensure faster querying, particularly for large datasets. This included primary keys, foreign keys, and compound indexes where necessary to optimize query performance.

Partitioning strategies were used to organize data by key dimensions (e.g., date or category), improving query efficiency by allowing Redshift to scan only relevant portions of the data during queries.

**7.	Data Pipeline Design:**

Steps:

I designed and implemented end-to-end data pipelines using a combination of AWS Glue for ETL and AWS Step Functions for orchestration.

The data pipeline automated the processes of data ingestion, transformation, and loading, ensuring that data flows seamlessly from S3 into Redshift without manual intervention.

AWS Step Functions enabled the coordination of multiple Glue jobs, handling retries, error notifications, and conditional logic for a robust and streamlined workflow.


**8.	Data Cleaning:**

Steps:

Additional data cleaning was applied using AWS Glue scripts. These scripts were written in PySpark and processed large volumes of data to address any data quality issues not resolved during the initial preparation.

Validation checks were conducted to confirm the completeness and accuracy of the data, including verifying that no important fields were missing, ensuring there were no duplicate records, and checking for outlier values.

Any discrepancies were logged, and the data was reprocessed to meet quality standards.


**9.	Data Structuring:**

Steps:

The data within AWS Redshift was structured to optimize query performance. This involved designing efficient table structures, using the correct distribution keys and sort keys based on the query patterns.

I created views and materialized views to support complex queries and accelerate read performance. Views allowed for the abstraction of complex queries into simplified access points for analysts, while materialized views precomputed and stored query results for quick retrieval.

**10.	Data Pipeline Implementation:**

Steps:

The data pipeline was deployed and configured for production use. AWS Glue and AWS Step Functions orchestrated the end-to-end process from data ingestion to transformation and loading.

I set up monitoring and alerting using AWS CloudWatch to track the performance and status of the data pipeline. CloudWatch monitored logs and metrics for Glue jobs, alerting in case of failures or performance bottlenecks.

Regular data processing schedules were configured to ensure that data was always up-to-date and processed in a timely manner.

**11.	Data Analysis:**

Steps:

With the data fully prepared and loaded into AWS Redshift, I performed data analysis using SQL queries to extract insights.

The analysis included looking into voting patterns, trends, and other behaviors related to council voting, using aggregate functions, window functions, and joins to gather meaningful insights.

These insights were then used to create reports and findings that would inform stakeholders about council behavior and trends.


**12.	Data Visualization:**

Steps:

I designed visualizations and interactive dashboards using Amazon QuickSight to present the results of the analysis.

Charts, graphs, and other visual aids were created to effectively convey voting trends, patterns, and insights in a more accessible format.

The dashboards were made interactive, allowing stakeholders to explore the data through filters and drill-downs, providing them with more flexibility in interpreting the data.


**13.	Data Publishing:**

Steps:

The final reports and dashboards were published for stakeholder access through Amazon QuickSight.

I configured access controls within QuickSight to ensure that only authorized users could view and interact with the reports and dashboards. This included defining permissions for different user roles.

Stakeholders could now securely access the dashboards, track real-time updates, and use the insights for decision-making.


**Tools and Technologies**

AWS Glue – For data crawling, ETL jobs, and metadata cataloging.

Amazon S3 – For scalable and secure data storage.

Amazon Redshift – For data warehousing and efficient querying.

Amazon CloudWatch – For monitoring data processing and pipeline performance.

Amazon QuickSight – For data visualization and reporting.

AWS Step Functions – For orchestrating data pipelines and automating workflows.

AWS Lambda – For running serverless functions to process data or trigger actions based on events.

Amazon RDS (Relational Database Service) – For managing relational databases like MySQL, PostgreSQL, or SQL Server.

AWS IAM (Identity and Access Management) – For managing user access and permissions to AWS resources.

Amazon Athena – For running SQL queries directly on data stored in Amazon S3 without needing to load it into a database.

Amazon Kinesis – For real-time data streaming and processing.

AWS Data Pipeline – For moving and processing data between different AWS services and on-premises data s

Amazon EMR (Elastic MapReduce) – For big data processing using frameworks like Apache Spark and Hadoop.

AWS Key Management Service (KMS) – For managing encryption keys to secure data.

AWS DMS (Database Migration Service) – For migrating databases to AWS Redshift, RDS, or other destinations.

**Deliverables**

Report:

Description: A comprehensive document detailing the entire data processing and analysis project.

Contents:
Overview: An introduction to the project, including its objectives and the business problem it aimed to solve (e.g., analyzing voting records to uncover trends and insights).

Data Collection and Preparation: A step-by-step explanation of how the dataset was collected, cataloged, and prepared for analysis. This includes details on using AWS Glue for schema discovery, metadata cataloging, and handling any data inconsistencies or missing values.

Data Ingestion and Storage: A description of how the data was ingested into Amazon S3 for storage and then processed and loaded into AWS Redshift for analysis, including details about the storage design, security measures (like encryption and access controls), and any challenges encountered.

Data Transformation and Cleaning: Detailed steps of how data was transformed using AWS Glue ETL jobs, including handling missing values, correcting inconsistencies, and preparing the data for analysis.

Data Pipeline Implementation: Documentation of the automated data pipelines designed using AWS Glue and AWS Step Functions to handle data ingestion, transformation, and loading into Redshift. The report includes information on pipeline scheduling, automation, and monitoring.

Analysis Findings: A summary of the findings from the analysis performed in AWS Redshift, highlighting key voting patterns, trends, and insights extracted from the data.

Challenges and Resolutions: A section that outlines any challenges faced during the data preparation and analysis process, along with the solutions implemented to overcome them.

Conclusion and Recommendations: A final section that summarizes the project's outcomes and provides actionable recommendations based on the analysis results, such as insights into voting behavior, areas for further analysis, or suggestions for improving data workflows.

Dashboards:

Description: Interactive data visualizations built using Amazon QuickSight to present the key insights and trends identified from the analysis of the voting records.

Contents:

Voting Patterns: Visualizations showing the distribution of votes across different periods, highlighting trends such as voting consistency, abstentions, or patterns across certain demographics or council members.

Comparative Analysis: Charts comparing voting behaviors across different groups, such as political parties, regions, or other categories relevant to the analysis. This could include bar charts, line graphs, or heatmaps that allow for easy comparison of trends.

Key Metrics: Dashboard elements that summarize important metrics, such as the most frequent voters, the percentage of abstentions, or trends in voting over time.

Interactive Filters: Users can interact with the data by applying filters (e.g., by date, council member, or vote outcome), enabling them to explore the data from different angles and drill down into specific areas of interest.

Real-time Updates: Dashboards that can be refreshed with new data, ensuring that stakeholders always have access to the most up-to-date insights.

Exporting and Sharing: The dashboards are configured to be easily shared with stakeholders, with controlled access permissions, allowing authorized users to view, interact with, and export reports.

These deliverables provide stakeholders with a clear understanding of the project, the insights derived from the data, and intuitive visualizations to explore and make data-driven decisions.








