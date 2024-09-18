Council Voting Records Analysis Project

Koumudhi Mekala ( 2306301)
BUSI 653 : Cloud Computing Technologies
Professor : Mahmood Mortazavi Dehkordi
August 27, 2024
Table of Contents

Introduction	4
Need for DAP	4
DAP Design and Implementation (Individual work)	4
1.	Data Analytical Question Formulation	4
2.	Data Discovery	9
3.	Data Storage Design	15
4.	Data Preparation	18
5.	Data Ingestion	19
6.	Data Storage	20
7.	Data Pipeline Design	23
8.	Data Cleaning & Structuring	25
9.	Data Pipeline Implementation	39
10.	Data Analysis	46
11.	Data Visualization	48
12.	Data Publishing	51
Estimated Cost Calculation	55
References	57


Introduction
For the City of Vancouver, employing a Data Analytic Platform for processing and handling various records is crucial after the integration process in May 2024 tore standardized business categories. This DAP will enable the business to monitor the growth of such firms, forecast economic conditions, and ascertain compliance with municipal laws(Mahmood,2024).
Need for DAP
Consider an example where the city stores, processes, and analyse big data; AWS makes this achievable and gives valuable information that may help the city's economic development or policies.
The City of Vancouver is increasingly leveraging data to improve its operations and services to citizens. This document outlines the implementation of an AWS Data Analytic Platform (DAP) designed to address the city's needs in various areas, including Animal control inventory register analysis, voting records analysis, 3-1-1 contact center analysis,business licences,. The DAP offers a secure, scalable, and cost-effective solution for data management, processing, and analysis, empowering city officials to make data-driven decisions for the benefit of Vancouver residents.
The DAP is component which contains data gathering and processing about various dataset’s data intake. Dedicated by AWS’s powerful cloud computing, the platform guarantees that data is updated as often as possible depending on changes occurring in the network with minimal error. It also allows city engineers and decision-makers who need the data for maintenance and improvement of water distribution system, to be able to access and analyze it in the simplest way possible.
DAP Design and Implementation (Individual work)
Data Analytical Question Formulation
In this the DAP is designed and implemented in which specific data analytical questions are formulated, and data preparation and data discovery of datasets shall be conducted based on the questions formulated. 
Dataset 1 (Prathap): In this dataset Prathap will be using the 3-1-1 Contact center services. The main metric we will be suing here will be about “What is the count of Calls Abandoned for each month of the year respectively.” For calculating this we can use the ‘BI_ID’, ‘Calls_Abandoned’, ‘Date’ columns.
Figure 1-1
Dataset 1 Analysis-2023

Note: The above image shows the data analysis of 2023 from (City of Vancouver, n.d) portal.
Figure 1-2
Dataset 1 Analysis-2024

Note: The above image shows the data analysis of 2024 from (City of Vancouver, n.d) portal.
Dataset 2 (Koumudhi): In this dataset 2 koumudhi will be using council voting records. The main descriptive metric here will be about ‘What is the average number of votes per agenda item for different types of meetings?’ for calculating this we can use the Vote ID, Vote result, Date columns.
`Figure 1-3
Dataset 2 Analysis-2024


Note: The above image shows the data analysis of 2024 from (City of Vancouver, n.d) portal.
Dataset 3 (Kumudini): In this dataset 3 Kumudini will be using Animal control inventory register. The main descriptive metric here will be about ‘What is the distribution of male versus female animals across different types?’ for calculating this we can use the Animal ID, Animal sex, Date columns.
Dataset 4 (Suman): In this dataset 4 suman will be using Business licenses 2013 to 2024. The main descriptive metric here will be about ‘What is the distribution of male versus female animals across different types?’ for calculating this we can use the Animal ID, Animal sex, Date columns.





Fgure 1-4
Dataset 3 Analysis-2024


Note: The above image shows the data analysis of 2024 from (City of Vancouver, n.d) portal.

Dataset 5 (Yashika): In this dataset 5 Yashika will be using Multi capital project budget requests and Capital expenditure budget. The main descriptive metric here will be about ‘What is the budget achieved versus budget estimated?’
Figure 1-4
Dataset 5 Analysis-2024


Note: The above image shows the data analysis of 2024 from (City of Vancouver, n.d) portal.

Figure 1-5
Dataset 5 Analysis-2023

Note: The above image shows the data analysis of 2024 from (City of Vancouver, n.d) portal.

Data Discovery
After the identification of analytical questions above, the next step was the identification of data. Having a virtually developed data structure, the water distribution mains dataset was catalogued through AWS Glue Data Catalogue which enhanced the indexing. Such important fields as pipe location, diameter, material, installation date and history of maintenance were captured in the dataset. It was important to understand these fields to be able to design the succeeding data processing and analysis workflows.
Dataset 1: I have selected the information of “3-1-1 Contact Center” from (City of Vancouver, n.d) portal as displayed in figures ‘Figure 2-1’, and ‘Figure 2-2’ relevant data sources are identified and catalogued.
Figure 2-1
Dataset 1 Information-2023

Note: The above image shows the data analysis of 2024 from (City of Vancouver, n.d) portal.
Figure 2-2
Dataset 1 Information -2024

Note: The above image shows the data analysis of 2024 from (City of Vancouver, n.d) portal.
Dataset 2 : I have selected the information of “Council voting records” from (City of Vancouver, n.d) portal as displayed in figures ‘Figure 2-3’relevant data sources are identified and catalogued.
Figure 2-3
Dataset 2 Information-2024

Note: The above image shows the data analysis of 2024 from (City of Vancouver, n.d) portal.
Dataset 3 : I have selected the information of “Animal control inventory register” from (City of Vancouver, n.d) portal as displayed in figures ‘Figure 2-4’relevant data sources are identified and catalogued.
Figure 2-4
Dataset 3 Information-2024

Note: The above image shows the data analysis of 2024 from (City of Vancouver, n.d) portal.
Dataset 4: I have selected the information of “Business licenses 2013 to 2024” from (City of Vancouver, n.d) portal
Dataset 4 Information-2024

Note: The above image shows the data analysis of 2024 from (City of Vancouver, n.d) portal.







Dataset 4 Information-2023

Note: The above image shows the data analysis of 2023 from (City of Vancouver, n.d) portal.

Dataset 5: I have selected the information of Multi capital project budget requests and Capital expenditure budget from (City of Vancouver, n.d) portal
Dataset 4 Information-2023


Note: The above image shows the data analysis of 2023 from (City of Vancouver, n.d) portal.

Dataset 4 Information-2024

Note: The above image shows the data analysis of 2024 from (City of Vancouver, n.d) portal.
Data Storage Design
In this part we will mainly be discussing on storage. The storage design for the application is raw data storage, Amazon S3, structured data, and Amazon Redshift. This way, the data is retained at scale, and retrieval is very efficient. The calls data od 3-1-1 Contact center as mentioned above are stored in a separate table so that historical data does not get updated and modified and is easily accessible for comparisons. The basic storage information is displayed below.
Figure 3-1
Dataset 1 Storage Information

Note: The above image shows the data storage option of 3-1-1 contact center call details.
Figure 3-2
Dataset 2 Storage Information

Note: The above image shows the data storage option of Council Voting Records.
Figure 3-3
Dataset 3 Storage Information

Note: The above image shows the data storage option of Animal control inventory register.
Figure 3-4
Dataset 4 Storage Information

Note: The above image shows the data storage option of Business licenses.







Data Preparation
In this the data collected in raw format is then preprocessed to make it less erroneous and more standard. For example, ‘AveragespeedofAnswer’ is computed, and the results are organized into data categories according to the calls offered and calls handled. This step is essential to ensure the data will be clean and ready to offer good information during the analysis. Similarly other metrics were used in the rest of the datasets.
Figure 4-1
Dataset 1 Preparation Information

Note: The above image shows the data preparation of 3-1-1 contact center call details.
Figure 4-2
Dataset 2 Preparation Information

Note: The above image shows the data preparation of council voting records details.
Figure 4-3
Dataset 3 Preparation Information

Note: The above image shows the data preparation of Animal control inventory register.
Data Ingestion
In this, raw data is in the form of call logs extracted from the city's 3-1-1 contact center records and loaded to Amazon S3 using AWS Data Pipeline. This configuration permits daily updating of current year data and ensures that the medium provides the most recent calls data. It's set up to allow for regular bulk updates and live ingesting for real-time analytical purposes. This is also setup for rest of the datasets as well shown below.
Data Storage
In this the processed raw datasets are stored in Amazon S3/Redshift, making the processed data available for analysis. The data storage phase also has data security measures, such as encryption, to prevent unauthorized access to the data by any unauthorized personnel.
Figure 6-1
Dataset 1 Storage S3 Information-1

Note: The above image shows the data storage (S3) of 3-1-1 contact center call details.
Figure 6-2
Dataset 1 Storage S3 Information-2

Note: The above image shows the data storage (S3) of abandoned 3-1-1 call details.
Figure 6-3
Dataset 2 Storage S3 Information-1

Note: The above image shows the data storage (S3) of council voting records details.
Figure 6-4
Dataset 2 Storage S3 Information-2

Note: The above image shows the data storage (S3) of council voting records in favour details.
Figure 6-5
Dataset 3 Storage S3 Information-1

Note: The above image shows the data storage (S3) of Animal control inventory register details.
Figure 6-6
Dataset 3 Storage S3 Information-2

Note: The above image shows the data storage (S3) of Animal control inventory register details.
Figure 6-7
Dataset 4 Storage S3 Information-1

Note: The above image shows the data storage (S3) of Business Licenses details.
Data Pipeline Design
In this an AWS Glue/Step Functions data pipeline is created for the movement of data, which means that data can be processed automatically. All the processes, starting from the intake of data, processing it, storing it, and eventually analyzing it, are planned and in place to facilitate the movement of data and its subsequent processing.
Figure 7-1
Dataset 1 Pipeline Information

Note: The above image shows the data pipeline of 3-1-1 contact center call details.
Figure 7-2
Dataset 2 Pipeline Information

Note: The above image shows the data pipeline of Council Voting Records details.
Figure 7-3
Dataset 3 Pipeline Information


Note: The above image shows the data pipeline of Animal control inventory register details.
Figure 7-4
Dataset 4 Pipeline Information


Note: The above image shows the data pipeline of Business licenses details.
Data Cleaning & Structuring
In Cleaning preliminary cleaning of the data was explained as crucial for the desired quality of the data set. This consists of removing such records as duplicates, methods utilized to eliminate data entry errors, and gaps in the values. The data must be adequately cleaned so that correct analysis and correct decisions can be made.
In Structuring the collecting data is arranged in a rather formal format, which can be easily filtered and analysed. This is done to sort the data into tables or partitions, all in an attempt to have the key attributes of the database organized appropriately, like in this manner; Date_Recorded, Call_Abandoned, and Call_Offered to enhance quick and accurate data retrieval.
Figure 8-1-1
Dataset 1 Cleaning& Structuring Information

Note: The above image shows the data cleaning of 3-1-1 contact center call details.
Figure 8-1-2
Dataset 2 Cleaning& Structuring Information


Note: The above image shows the data cleaning of Council Voting Records details.
Figure 8-1-3
Dataset 3 Cleaning& Structuring Information

Note: The above image shows the data cleaning of Animal control inventory register
details.
Figure 8-1-4
Dataset 4 Cleaning& Structuring Information

Note: The above image shows the data cleaning of Business licenses details.
Figure 8-1-5
Dataset 5 Cleaning& Structuring Information

Note: The above image shows the data cleaning of Multi capital project budget requests and Capital expenditure budget
Figure 8-2-1
Dataset 1 Cleaning & Structuring Information

Note: The above image shows the data cleaning of 3-1-1 contact center call details.
Figure 8-2-2
Dataset 2 Cleaning& Structuring Information


Note: The above image shows the data cleaning of Council Voting Records details.
Figure 8-2-3
Dataset 3 Cleaning& Structuring Information

Note: The above image shows the data cleaning of Animal control inventory register
details.
Figure 8-2-4
Dataset 4 Cleaning& Structuring Information

Note: The above image shows the data cleaning of Business licenses details.
Figure 8-2-5
Dataset 5 Cleaning& Structuring Information

Note: The above image shows the data cleaning of Multi capital project budget requests and Capital expenditure budget.
Figure 8-3-1
Dataset 1 Cleaning & Structuring Information

Note: The above image shows the data cleaning of abandoned calls of 3-1-1 center.
Figure 8-3-2
Dataset 2 Cleaning& Structuring Information

Note: The above image shows the data cleaning of Council Voting Records  in favour details.
Figure 8-3-3
Dataset 3 Cleaning& Structuring Information

Note: The above image shows the data cleaning of Animal control inventory Male versus female details.
Figure 8-3-4
Dataset 4 Cleaning& Structuring Information

Note: The above image shows the data cleaning of Business licenses details.
Figure 8-3-5
Dataset 5 Cleaning& Structuring Information

Note: The above image shows the data cleaning of Multi capital project budget requests and Capital expenditure budget
Figure 8-4-1
Dataset 1 Cleaning & Structuring Information

Note: The above image shows the data cleaning of abandoned calls of 3-1-1 center.
Figure 8-4-2
Dataset 2 Cleaning& Structuring Information

Note: The above image shows the data cleaning of Council Voting Records in favour details.
Figure 8-4-3
Dataset 3 Cleaning& Structuring Information

Note: The above image shows the data cleaning of Animal control inventory male versus female details.
Figure 8-4-4
Dataset 4 Cleaning& Structuring Information

Note: The above image shows the data cleaning of Business licenses details.
Figure 8-5-1
Dataset 1 Cleaning & Structuring Job Information

Note: The above image shows the job details of data cleaning of abandoned calls of 3-1-1 center.
Figure 8-5-2
Dataset 2 Cleaning & Structuring Job Information

Note: The above image shows the job details data cleaning of Council Voting Records In favour details.
Figure 8-5-3
Dataset 3 Cleaning & Structuring Job Information

Note: The above image shows the job details data cleaning of Animal control inventory register Male versus Female details.
Data Pipeline Implementation
In this the data pipeline is the pipeline configuration for Data as explained above: This includes checking on the status of jobs and eliminating any issue that may occur during the job process. It also ensures that the data offered is well-processed and available for implementation promptly.
Figure 9-1-1
Dataset 1 Pipeline Information-1

Note: The above image shows the data ETL Pipeline for abandoned calls of 3-1-1 center.
Figure 9-1-2
Dataset 1 Pipeline Job Information-1


Note: The above image shows the data ETL Pipeline for abandoned calls of 3-1-1 center.
Figure 9-1-3
Dataset 1 Pipeline Output Stored in S3 Information-1

Note: The above image shows the data ETL Pipeline for abandoned calls of 3-1-1 center.
Figure 9-2-1
Dataset 2 Pipeline Information-1

Note: The above image shows the data ETL Pipeline for Council voting records in favour.
Figure 9-2-2
Dataset 2 Pipeline Job Information-1

Note: The above image shows the data ETL Pipeline for Council voting records in favour.
Figure 9-2-3
Dataset 2 Pipeline Job Information-1

Note: The above image shows the data ETL Pipeline for Council voting records in favour.
Figure 9-3-1
Dataset 3 Pipeline Information-1

Note: The above image shows the data ETL Pipeline for sex distribution details.
Figure 9-3-2
Dataset 3 Pipeline Job Information-1

Note: The above image shows the data ETL Pipeline for sex distribution details.
Figure 9-3-3
Dataset 3 Pipeline Job Information-1

Note: The above image shows the data ETL Pipeline for sex distribution details.
Figure 9-4-1
Dataset 4 Pipeline Information-1

Note: The above image shows the data ETL Pipeline for Business licenses 2013 to 2024
Figure 9-4-2
Dataset 4 Pipeline Job Information-1

Note: The above image shows the data ETL Pipeline for Business licenses details.
Figure 9-5-1
Dataset 5 Pipeline Information-1

Note: The above image shows the data ETL Pipeline for Multi capital project budget requests and Capital expenditure budget 
Figure 9-5-2
Dataset 5 Pipeline Job Information-1

Note: The above image shows the data ETL Pipeline for Multi capital project budget requests and Capital expenditure budget
Data Analysis
In this Data analysis is done, and to make queries such as those in the analytical question above, one can use Amazon Athena or QuickSight.
Figure 10-1
Dataset 1 Analysis Information-1

Note: The above image shows the data analysis for abandoned calls of 3-1-1 center.
Figure 10-2
Dataset 2 Analysis Information-1

Note: The above image shows the data analysis for council voting records in favour.
Figure 10-3
Dataset 3 Analysis Information-1

Note: The above image shows the data analysis for Sex distribution.
Data Visualization
These visualizations are ways the data analysis results are presented in an easily understood format. These renderings glance at the audiences by displaying a time series or the cross tab of trends over time or across kinds of work or regions.
Figure 11-1
Dataset 1 Visualization Information-1

Note: The above image shows the data Visualization for abandoned calls of 3-1-1 center.
Figure 11-2
Dataset 2 Visualization Information-1

Note: The above image shows the data Visualization for Average vote count.
Figure 11-3
Dataset 3 Visualization Information-1

Note: The above image shows the data Visualization for Sex distribution.
Figure 11-4
Dataset 4 Visualization Information-1

Note: The above image shows the data Visualization for Average fees paid.
Data Publishing
Data publishing can be defined as the grouping or disseminating of the analysis results to other parties(Alaimo et al.,2021). This could be in compressed files copied to an S3 bucket for consumption, pre-built and ready dashboards in QuickSight, or weekly, daily, or monthly summaries sent as email or dropped into a folder or S3 bucket.
Figure 12-1
Dataset 1 Web Server RDP Information-1

Note: The above image shows the data publishing .
Dataset 1 Web Server Role Information-1

Note: The above image shows the data publishing.
Figure 12-3
Dataset 1 Web Server File& Output Information-1

Note: The above image shows the data publishing.
Figure 12-4
Dataset 1 General Server RDP Information-1

Note: The above image shows the data publishing .
Figure 12-5
Dataset 1 General Server File& Output Information-1

Note: The above image shows the data publishing for abandoned calls of 3-1-1 center.
Figure 12-6
Dataset 1 General Server File& Output Information-1

Note: The above image shows the data publishing Business Licenses.

Figure 12-6
Dataset 1 General Server File& Output Information-1

Note: The above image shows the data publishing for Multi capital project budget requests and Capital expenditure budget.

Estimated Cost Calculation
The AWS Pricing Calculator was used to estimate the cost of setting up and the subsequent running of the data analytic platform. It costs approximately $ 630.84 to process and analyze the business license data every month using Amazon S3, Athena, Glue, and Quick Sight. This estimate will factor in the data's size, its quality in terms of storage, processing, and data visualization, and the frequency of updates of the business license records.
Figure 13
Cost Estimation

Note: The above image shows the cost estimation of City of Vancouver project.




References
Alaimo, C., & Kallinikos, J. (2021). Managing by data: Algorithmic categories and organizing. Organization Studies, 42(9), 1385-1407. https://journals.sagepub.com/doi/abs/10.1177/0170840620934062
City of Vancouver. (n.d.). Open Data Portal. Retrieved August 18, 2024, from https://opendata.vancouver.ca/pages/home/
Mahmood, H. S. (2024). Conducting In-Depth Analysis of AI, IoT, Web Technology, Cloud Computing, and Enterprise Systems Integration for Enhancing Data Security and Governance to Promote Sustainable Business Practices. Journal of Information Technology and Informatics, 3(2).

