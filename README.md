E-Commerce Sales Analytics Dashboard
A practical Data Analytics + Power BI project using an e-commerce dataset sourced from Kaggle.

The project demonstrates the complete workflow from raw data preparation to PostgreSQL and Power BI, with practical testing of Import Mode vs DirectQuery and source-data change behavior.

🎯 Project Objective
Understand how an analytics dashboard is created and how data flows through a BI system:

Kaggle Dataset
      ↓
Python / Pandas
      ↓
Data Cleaning & Transformation
      ↓
Fact + Dimension Tables
      ↓
PostgreSQL
      ↓
Power BI
      ↓
Data Model
      ↓
DAX & Visuals
      ↓
Dashboard
      ↓
Import Mode / DirectQuery
      ↓
Source Data Change Testing
This is a practice and portfolio project focused on learning the complete analytics workflow.

🛠️ Tools & Technologies
Python

Pandas

Jupyter Notebook

PostgreSQL

SQLAlchemy

Power BI Desktop

Power Query

DAX

Useful Development Extensions
Python

Jupyter

SQL/PostgreSQL

📂 Project Files
E-Commerce-Sales-Analytics/
│
├── README.md
├── ESS(1).ipynb
├── Ecommerce Sales Dashboard.pbix
│
├── ecommerce_sales_data(5).csv
├── Ecommerce_sales_fact(5).csv
├── Ecommerce_sales_products(5).csv
├── Ecommerce_sales_Customer(5).csv
├── Ecommerce_sales_time(5).csv
└── append file.csv
File	Purpose
ESS(1).ipynb	Python data preparation workflow
Ecommerce Sales Dashboard.pbix	Power BI dashboard
ecommerce_sales_data(5).csv	Raw/source e-commerce data
Ecommerce_sales_fact(5).csv	Sales transaction/fact data
Ecommerce_sales_products(5).csv	Product dimension
Ecommerce_sales_Customer(5).csv	Customer dimension
Ecommerce_sales_time(5).csv	Date dimension
append file.csv	Source-data change practice
📊 Dataset
The project starts with an e-commerce dataset from Kaggle containing information related to:

Customers

Products

Categories

Price

Quantity

Sales

Purchase date

Purchase time

The raw data is prepared in Python before being used for PostgreSQL and Power BI.

🔄 1. Data Preparation
The raw Kaggle data is processed in the Jupyter Notebook.

Raw CSV
   ↓
Load Data
   ↓
Understand Data
   ↓
Check Missing Values
   ↓
Check Duplicates
   ↓
Clean Data
   ↓
Transform Data
   ↓
Create Analytical Fields
   ↓
Create Fact & Dimension Tables
Main preparation activities:

Data inspection

Duplicate checking

Missing-value checking

Column standardization

Data-type conversion

Date/time preparation

Customer age-group preparation

Product identification

Date attributes

Fact and dimension creation

⭐ 2. Data Modeling
The project uses a star-schema-style model:

                 dim_customer
                      │
                      │
                      ▼
dim_product ───► fact_sales ◄─── dim_date
Table	Purpose
fact_sales	Central transaction and sales data
dim_customer	Customer information
dim_product	Product and category information
dim_date	Date and time analysis
Relationships:

dim_customer ── 1 : * ── fact_sales

dim_product  ── 1 : * ── fact_sales

dim_date     ── 1 : * ── fact_sales
Dimensions are used to filter and analyze the central sales transactions.

🗄️ 3. PostgreSQL
After data preparation, the structured tables are stored in PostgreSQL.

Python / Pandas
       ↓
PostgreSQL
       ↓
dim_customer
dim_product
dim_date
fact_sales
PostgreSQL acts as the central database/source for Power BI.

This creates a practical analytics architecture:

Data Preparation
       ↓
Database
       ↓
Business Intelligence
📈 4. Power BI Dashboard
The Power BI report contains two main pages.

The dashboard analyzes sales performance, customers, products and purchasing patterns.

Page 1 — Sales Overview
The first page provides a high-level business overview.

KPI Section
Total Sales

Total Orders

Total Quantity

Total Customers

Average Order Value

Sales Analysis
Sales by Age Group

Sales by Category

Sales by Gender

Monthly Sales Trend

Slicers
Gender

Age Group

Month

Day

Category

Page 1 Purpose
Overall Sales
     ↓
Orders & Quantity
     ↓
Customer Contribution
     ↓
Category Performance
     ↓
Sales Trend
The first page is intended to give a quick understanding of overall business performance.

Page 2 — Product & Customer Analysis
The second page provides deeper analysis.

Product Analysis
Product sales distribution

Product performance

Category performance

Average product price

Customer Analysis
Customer age

Age-group performance

Gender-based performance

Customer contribution

Time Analysis
Sales by day

Sales by hour

Purchasing patterns

Page 2 Purpose
Product Performance
        +
Customer Behavior
        +
Time-Based Analysis
        ↓
Detailed Business Analysis
🔗 5. Dashboard Interaction
The dashboard is interactive.

User selects a filter
        ↓
Power BI filters the model
        ↓
Measures recalculate
        ↓
KPI cards update
        ↓
Charts update
Filters such as Category, Gender, Age Group, Month and Day allow users to explore different business segments.

📥 6. Import Mode
One major purpose of this project is to practice Power BI Import Mode.

How it works
PostgreSQL
     ↓
Power BI Import
     ↓
Power BI Model
     ↓
Dashboard
Power BI loads a copy of the source data into its model.

Practical Test
Create Dashboard
      ↓
Record KPI Values
      ↓
Change/Add Data in PostgreSQL
      ↓
Check Dashboard
      ↓
Refresh Power BI
      ↓
Check KPI Values Again
Learning
When PostgreSQL source data changes, the imported Power BI model generally needs a refresh to load the changed data.

⚡ 7. DirectQuery
The second major purpose is to practice Power BI DirectQuery.

How it works
Power BI Visual
      ↓
Power BI Query
      ↓
PostgreSQL
      ↓
Query Result
      ↓
Dashboard Visual
The source database remains the main data source instead of importing the entire source dataset into the Power BI model.

Practical Test
Create DirectQuery Dashboard
          ↓
Record KPI Values
          ↓
Change/Add Data in PostgreSQL
          ↓
Refresh / Query Visuals
          ↓
Check KPI Values
          ↓
Compare with Import Mode
DirectQuery is used here to learn source-based reporting. It should not be described as guaranteed real-time streaming because actual behavior depends on Power BI queries, refresh behavior, caching, settings and database performance.

🔄 8. Source Data Change Practice
The project includes additional data for practicing source-data changes.

Additional Data
      ↓
Validate Structure
      ↓
Add to PostgreSQL
      ↓
Database Changes
      ↓
Test Import
      ↓
Test DirectQuery
      ↓
Compare Dashboard
Observe:

Total Sales

Total Orders

Total Quantity

Important: The supplied append file.csv contains date-dimension fields. To demonstrate changes in sales KPIs, additional transaction data should match the fact_sales structure.

⚖️ 9. Import vs DirectQuery
Area	Import	DirectQuery
Main data location	Power BI model	PostgreSQL
Source data	Imported copy	Database source
Source change	Model refresh generally required	Source is queried
Main learning	Import and refresh workflow	Database-based query workflow
Project purpose	Compare behavior	Compare behavior
The purpose is to understand the practical difference between both connectivity methods.

💻 10. Python Environment
The project uses a virtual environment instead of a requirements.txt file.

Create venv
    ↓
Activate venv
    ↓
Install required packages
    ↓
Open Jupyter
    ↓
Run ESS(1).ipynb
Useful Python packages:

Pandas

NumPy

SQLAlchemy

psycopg2-binary

Jupyter

Matplotlib

Seaborn

Power BI Desktop and PostgreSQL are installed separately.

▶️ 11. How to Run the Project
1. Create and activate Python virtual environment
              ↓
2. Install required Python packages
              ↓
3. Open ESS(1).ipynb
              ↓
4. Run data preparation workflow
              ↓
5. Prepare fact and dimension tables
              ↓
6. Load tables into PostgreSQL
              ↓
7. Open Ecommerce Sales Dashboard.pbix
              ↓
8. Connect Power BI to PostgreSQL
              ↓
9. Create/verify relationships
              ↓
10. Build/verify dashboard pages
              ↓
11. Test Import Mode
              ↓
12. Test DirectQuery
              ↓
13. Change source data
              ↓
14. Compare dashboard results
❓ Business Questions
The dashboard is designed to answer:

What is the total sales performance?

How many orders and quantities were sold?

Which categories generate the most sales?

Which products perform best?

Which age group contributes the most sales?

How does sales vary by gender?

Which months perform better?

Which days have higher sales?

Which hours have higher purchasing activity?

What happens when source data changes?

How does Import differ from DirectQuery?

🎓 Skills Demonstrated
Data Analytics
Python, Pandas, data cleaning, transformation and analysis

Database
PostgreSQL, SQLAlchemy and relational data modeling

Data Modeling
Fact table, dimension tables, star schema and relationships

Power BI
Power Query, DAX, KPI cards, slicers, charts and interactive dashboards

BI Connectivity
Import Mode, DirectQuery, refresh and source-data change testing
