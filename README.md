Council Voting Records Analysis Project
Project Description
This project implements a Data Analytics Platform (DAP) to analyze council voting records for the City of Vancouver. The DAP is designed to process, analyze, and visualize voting patterns and trends, providing insights to support data-driven decision-making for city officials.
Objective:
To develop a comprehensive analysis of council voting patterns, focusing on the average number of votes per agenda item for different types of meetings. This analysis aims to enhance transparency in city governance and provide valuable insights into council decision-making processes.
Data:
The primary dataset used in this project is the "Council voting records" obtained from the City of Vancouver's Open Data Portal. Key data points include:
Vote ID
Vote result
Date
Meeting type
Agenda items

Methodology:

Data Ingestion: Raw data is extracted from the city's records and loaded into Amazon S3 using AWS Data Pipeline.
Data Cleaning & Structuring: AWS Glue is used to clean and structure the data, removing duplicates and addressing data entry errors.
Data Storage: Processed data is stored in Amazon S3 and Amazon Redshift for efficient retrieval and analysis.
Data Analysis: Utilizing Amazon Athena and QuickSight to perform queries and generate insights.
Data Visualization: Creating visual representations of voting patterns and trends using QuickSight.

Deliverables:

Cleaned and structured dataset of council voting records
Analysis report detailing voting patterns and trends
Interactive dashboard for exploring voting data
Visualizations of key metrics, including average votes per agenda item

Tools and Technologies:

AWS Services: S3, Redshift, Glue, Athena, QuickSight, Data Pipeline
Python for data processing and analysis
Jupyter Notebooks for exploratory data analysis
GitHub for version control and project management

Type of Analysis:
The project primarily involves descriptive and exploratory data analysis, focusing on:

Calculating average number of votes per agenda item
Analyzing voting patterns across different meeting types
Identifying trends in voting behavior over time
Visualizing vote distributions and outcomes
