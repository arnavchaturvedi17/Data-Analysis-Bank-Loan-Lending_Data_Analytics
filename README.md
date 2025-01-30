# Portfolio Project (Data Analysis): Bank Loan Lending Data Analytics.
### Arnav Chaturvedi
### Project Role: Data Analyst – Financial Bank.


The Tableau Dashboard. Please visit my Tableau Public account.
Use CTRL+click (on Windows and Linux) or CMD+click (on MacOS) on the link to open in a new browser tab. 
* Dashboard Link:  https://public.tableau.com/app/profile/arnav.chaturvedi/viz/BankLoan-LendingDataAnalytics/OVERVIEW

## Portfolio Project Overview:
A financial bank wants to utilize their available loan lending data to analyze and gain insights for financial planning. These insights from loan data provide key information for making decisions for future lending planning, managing risks and improving bank load recovery etc.
Available lending data comes from another department in the form of csv data file which needs to be cleansed/prepared using SQL and loaded into Microsoft SQL server database before it can be used for visualization using Tableau. 
This data analytics application is a key tool for bank managers for their planning and decision making.
As a data analyst, I created this end-to-end financial bank loan analysis project starting from data collection, cleansing, and preparation using SQL. Also, data visualizations are created with an interactive/dynamic dashboard using Tableau.

## Business Problem Scenarios, Objectives and KPIs:
The financial bank management team would like to analyze and get data insights from available loan lending data available in their system. On this interactive dashboard, bank management and finance analysts would like to see a few KPIs (Key Performance Indicators) such as loan issued, total applications, total funded loans as well as detailed information about current loans. 
-	What are key KPI as-on-date? 
* Total Loan Applications, Total Funded Amount, Total Amount Received, Average Interest Rate, Average TDI (…)
-	What is the status of loan issued (with good and bad standing)?
-	How loan data can be dynamically viewed by various business areas such as loan by grade, loan by purpose etc.
-	For details, please refer uploaded document: Business Requirements-BankLoan-LendingDataAnalysis.pdf

## Target Stakeholders:
This dynamic analysis dashboard will be used for the following job roles to increase their productivity and achieve business goals. 
* Bank Managers
* Financial Analysts
* Loan Officers

## Skills and Applications used: 
* SME (Subject Matter Expertise – Finance Domain knowledge)
  * Business requirement gathering skill and techniques.
  * UI/UX – Guidelines that define how a user interface/user experience should look, feel, and behave. They help ensure that users have consistent and predictable experience when interacting with a dashboard.
* SQL (Structured Query Language) using mySQL.
  * Data cleaning, pre-processing.
  * DDL (Data Definition Language) for database, Schema and tables objects (Create, Alter etc).
  * DML (Data Manipulation Language) for data preparation (Update, Set etc)   
  * ETL (Extract-Transform-Load) from csv data files to mySQL database.
  * Data validation for UAT (User Acceptance Testing). Matching data between displayed values on Tableau dashboard v/s data in source table/Excel sheet (data source).
* Tableau – Desktop and Public.
  * Data Import as ‘Tableau tables’ – data source (CSV data file, mySQL Database Tables)
  * Data Visualization - Interactive Dashboard Filters which allows one to toggle between various metrics.
* Microsoft Excel 
  * Knowledge of formulas and functions to be used in any typical data analytical solutions.

## Solution Approach and Process to build this project:
* Defining the problem
  * Clearly define the issue with stakeholders (bank managers, loan officer and analysts), and gather business requirements.
* Data collection
  * Gather data (csv data files) from another system in bank. 
  * Data cleansing/preparation.
  * Analyze and validate csv file for accuracy of data, validate data format and identify columns for data cleansing.
  * Identify and remove duplicates, missing data, and outliers to ensure the data is accurate and ready for analysis.
  * Fix date formatting issues in date related column values in csv file and convert them into mySQL database compliant date format. 
* Data visualization
  * Create visual representations of the data, such as charts, graphs, and plots, to help understand patterns and relationships
  * Interpreting the results
  * Use the data to answer questions and implement insights.
* UAT (User Acceptance Testing) and Deployment
* Use the data to answer questions and implement insights.

## Dataset Overview: Data Preparation Process (Data gathering, Data Cleaning, Data Transformation): 
* Data Gathering – The Dataset (Microsoft Excel/ CSV File); mySQL Database Table.
  * Data Sheet: 1 CSV files (‘Financial_Loan_Data_Import.csv’)
  * DB Server: MySQL 8.4 Server 
  * Database: bankloandb
  * DB Table Name: bank_loan_data
  * For details, please refer uploaded document: SQL Script-BankLoan-LendingDataAnalysis.pdf
* ETL (Extract-Transform-Load)  
  * Created mySQL database, table for loading data (using SQL DDL commands).
  * Data loaded from csv data file into Microsoft mySQL database.
  * Transformed data for date format conversion (using SQL DML commands).
  * Validate imported and transformed data and accuracy and UAT (User Acceptance Testing) planning.
  * Please refer to the attached document for all related SQL queries and gathered results from imported data. SQL Script-BankLoan-LendingDataAnalysis.pdf
* Data Cleaning (Common cleaning):
  * Data type conversion. Ensuring proper data types for each value to facilitate analysis.
  * In provided csv data file, values for date columns were not in proper format. The date values were provided in many inconsistent formats such as dd/mm/yyyy, dd-mmm-yy etc.
  * I used mySQL workbench and SQL queries to convert data from insistent date format to proper date format required by mySQL database using DDL and DML SQL commands.
  * Please refer to the attached document for all related SQL queries. SQL Script-BankLoan-LendingDataAnalysis.pdf
  * Handling Missing Values. Identifying and addressing missing data points to maintain data integrity.
  * Dealing with Duplicate Entries. Detecting and removing duplicate records to maintain dataset uniqueness.
  * Handling Outliers. Frequency analysis has been utilized to identify outliers in ordinal data. The analysis did not show significant evidence that less frequent levels should be considered as outliers.
* Data Pre-Processing and Transformation.
  * Cell formatting, spelling correction

## Data Analysis & Visualization – Dashboard, Reports, Charts, Key findings, Data Insights:
For overall development of this data analytics visualization, I created 3 dashboard, 33 worksheets, 3 filters and 3 navigation buttons.
* Three dashboards – 
  * Summary Dashboard – Summary, KPIs, Navigation links/buttons to go to other dashboards.
  * Overview Dashboard – Overview charts/visualizations for deeper data insights, Charts with Interactive filters, KPIs.
  * Detail Dashboard – View granular loan data.   
  * Please refer to the attached document for business requirement/problem statement document for detailed explanation of these 3 dashboards.
### Dashboard -1: SUMMARY
Developed first dashboard (SUMMARY) to show header KPIs (Key Performance Indicators). This shows overall performance of business.
  * Total Loan Application
  * Total Funded Amount
  * Total Amount Received
  * Average Interest Rate
  * Average DTI (Debt-To-Income) Ratio.
* Created multiple worksheets for above KPI calculations and placed in summary dashboard.
* Used calculated column formatting to match UI/UX requirements (ex: display numbers in thousands/millions)
* FIXED level of detail (LOD) expression: FIXED level of detail (LOD) expression computes a value using the specified dimensions, without reference to dimensions in the view.  For MTD Loan Applications, I used DATEDIFF function along with MAX function to calculate Month-To-Date KPI.  
* Used few tricks for faster development such as duplicating calculated column and changing expression/formatting.
* Used background images for better UI/UX organization of worksheets, calculated column displays.
* Created ‘Group’ (calculated column) for KPIs.
* Chart Visualization: Created custom donut chart since Tableau does not provide donut pie chart by default. 
* Dashboard Visualization: Used containers (vertical, horizontal) for better UI/UX organization in ‘Tiled’ or ‘Floating’ style.
* Created tabular/grid style display loan status data to show details with grand totals.
* Created 3 ‘Filters’ which apply to all data source and all worksheets.
### Dashboard -2: OVERVIEW
Developed second dashboard (OVERVIEW) and created various chart visualizations to provide overview of business. In this dashboard, data will show more granularity i.e. more detailed data insights.
  * Monthly Trend by Issue Date (Line/Area Chart)
  * Regional Analysis by State (Filled/Geospatial Map)
  * Loan Term Analysis (Donut Chart)
  * Employee Length Analysis (Bar Chart)
  * Loan Purpose Breakdown (Bar Chart)
  * Home Ownership Analysis (Tree Map)
* Used Tableau advanced feature called ‘Parameters’ for dynamic calculations for multiple charts.
* Used geospatial map (filled map) to show data values visualizations (dynamic measure selection). 
* Used Bar charts with labels and sorting to visualize data.
* I activated ‘filter’ feature of these charts to display changed data on dashboard. For example, i.e. data on other charts will change as we click on any state in map chart	.
### Dashboard -3: DETAILS
Developed third dashboard (DETAILS). I used grid view to display selected columns from table (detailed granular data).
### Navigation Buttons:
Created ‘Navigation’ buttons to navigate among various dashboards (Summary, Overview and Details).
 
### Refer to the screenshots below for the Tableau Dashboard for this solution.

## Portfolio Project Documentation (Final Conclusion):
### Documentation: 
* ReadMe-BankLoan-LendingDataAnalysis(SQL-Tableau).pdf
* SQL Script-BankLoan-LendingDataAnalysis.pdf
* Business Requirements-BankLoan-LendingDataAnalysis.pdf
### Output File (Published on my Tableau Public account):
* Tableau Public – Dashboard Link: https://public.tableau.com/app/profile/arnav.chaturvedi/viz/BankLoan-LendingDataAnalytics/OVERVIEW
The Tableau Dashboard. Please visit my Tableau Public account.
Use CTRL+click (on Windows and Linux) or CMD+click (on MacOS) on the link to open in a new browser tab.


## Dynamic and Interactive Dashboard (SUMMARY):
![image](https://github.com/user-attachments/assets/ceb5e64b-3719-4436-998c-537b8e4db617)

## Dynamic and Interactive Dashboard (OVERVIEW):
![image](https://github.com/user-attachments/assets/00cfbbb9-05dc-4fd5-a597-802f3e37f3e7)

## Dynamic and Interactive Dashboard (DETAILS):
![image](https://github.com/user-attachments/assets/91420105-0725-46f5-b5f0-84f7aadff866)




