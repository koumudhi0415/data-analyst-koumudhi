# Data-Analyst-Koumudhi

Voting Council Records Analysis
This project builds a Data Analytic Platform (DAP) using AWS services for analyzing council voting records and other datasets from the City of Vancouver. The platform automates data ingestion, cleaning, storage, and analysis while ensuring security and data governance. AWS S3, Glue, Redshift, Athena, and QuickSight are used to build a scalable, secure, and reliable data processing pipeline.

Objective
The project aims to answer key analytical questions such as:

What is the average number of votes per agenda item across different meetings?
How do voting patterns vary over time and across different agenda types?
The objective is to create a comprehensive solution for analyzing council voting data and providing meaningful insights for decision-making.

Significance
The significance of this platform lies in:

Improved Transparency: It makes council voting data accessible and easier to understand.
Data-Driven Decision Making: By providing insights, it helps officials make informed decisions.
Enhanced Security and Governance: The platform is designed with encryption, data versioning, and robust access controls to ensure the integrity and security of sensitive city data.
Project Entities
This project includes several components, each addressing different aspects of data processing and analysis:

Data Ingestion:

Automated ingestion of raw voting records from the City of Vancouver's open data portal to AWS S3.
Datasets include council voting records
Data Cleaning & Structuring:

AWS Glue jobs are used to clean and structure the data, removing duplicates and handling data inconsistencies.
Data Storage:

Processed data is stored in AWS Redshift for efficient querying and retrieval.
Cross-region replication and versioning are enabled for redundancy and disaster recovery.
Data Security:

KMS Encryption: AWS KMS keys are used to encrypt all data stored in S3 buckets and Redshift.
Versioning: Versioning is enabled on all S3 buckets to protect against accidental data loss.
Data Governance:

The project includes a well-defined governance structure, such as creating trusted folders in S3, applying lifecycle policies, and enforcing data retention rules.
Data Analysis:

AWS Athena is used to run SQL queries to analyze voting patterns and trends.
ETL Jobs: AWS Glue jobs execute regular ETL (Extract, Transform, Load) tasks, scheduled to run weekly.
Data Visualization:

AWS QuickSight visualizes the analysis results, such as voting trends over time, average votes per agenda item, and more.
Dashboards in CloudWatch monitor metrics like estimated charges and S3 object counts.
Data Publishing:

The analysis results are shared via QuickSight dashboards or downloadable reports from S3.
Monitoring and Auditing:

AWS CloudWatch and AWS CloudTrail are configured to track user activities and monitor estimated charges, S3 object counts, and error logs.
Dataset Used
Source: City of Vancouver Open Data Portal
Key Dataset:
Council Voting Records: Tracks voting results and agenda items.
Security Features
KMS Encryption: Symmetric KMS keys for encrypting datasets.
Bucket Versioning: Protects against accidental data loss by maintaining multiple versions of objects.
Cross-Region Replication: Ensures data durability and availability in case of a regional disaster.
Data Governance & Compliance
Data Governance: Folders like "trusted" are created for organizing backup files.
ETL Jobs: Data compliance is enforced through automated AWS Glue ETL jobs that manage sensitive data.
Technologies Used
AWS S3: For storing raw and processed datasets.
AWS Glue: For ETL (Extract, Transform, Load) jobs to clean and structure data.
AWS Redshift: For storing and querying structured data.
AWS Athena: For analyzing the datasets using SQL queries.
AWS QuickSight: For visualizing the analysis results.
AWS KMS: For encryption and security of stored data.
AWS CloudWatch: For monitoring and tracking performance, billing, and security metrics.
AWS CloudTrail: For auditing user activities and API calls.
How to Use the Project
Clone the repository and configure your AWS credentials.
Upload the datasets to the S3 bucket.
Run the provided scripts for data ingestion, cleaning, and structuring.
Use Athena to query and analyze the data.
Visualize results using AWS QuickSight dashboards.
Contributing
Contributions are welcome! Fork the repository, create a new branch for your feature or bugfix, and submit a pull request for review.

License
This project is licensed under the MIT License. See the LICENSE file for more details.
