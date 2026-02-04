# Data Analytics

## 1. Foundation

**Data analysis** is a process of `modelling`, `analyzing`, and `interpreting` data to extract insights. A **Data Analyst** `collects`, `process`, and `analyze` data to identify trends/patterns and make informed decisions.

**Data lifecycle**: `Use case` > `Data collection` > `Storage` > `Processing` > `Analysis` > `Visualization` > `Reporting`

### 1.1 Types of Analysis

- **Descriptive:** `What happened?` e.g., A skincare brand sees 15,000 people clicked their Instagram ad last week, but only 500 purchased.
- **Diagnostic:** `Why did it happen?` e.g., Analysis shows that shipping costs made many customers abandon their carts at checkout.
- **Predictive:** `What will likely happen?` e.g., If nothing changes, the model forecasts cart drop-offs will keep increasing as shipping prices rise.
- **Prescriptive:** `What should we do?` e.g., The system recommends offering free shipping above $40 to increase checkout conversions.
- **Exploratory:** `What hidden opportunities exist?` e.g., Data reveals customers who buy face cleansers often buy serums within a week, suggesting a personalised follow-up email can boost revenue.

### 1.2 Data Cleaning

**Data cleaning** is the process of correcting errors in a dataset to improve its reliability for analysis.

**Data Cleaning Steps:**

- **Data Types:** `Text`, `Dates`, `Decimals/Floats`, `Integer`
- **Irrelevant Data:** `Unused fields/entries`, `Constant values`
- **Missing Values:** `NULLs / NaNs / Blanks`
- **Duplicates:** `Repeated entries` (none unique rows)
- **Special Characters:** `Unwanted characters/symbols` (punctuation, emojis, currency), `Extra spaces` (tabs, newline artefacts)
- **Data Formats:** `Inconsistent date formats` (DD/MM vs MM/DD), `Mixed units` (kg vs g, ₦ vs $), `Case inconsistencies` (“Male”, “male”, "MALE", “M”)
- **Invalid Data:** `Out-of-range values` (negative age, future dates, time <= 0), `Logical conflicts` (discharge date < admission date), `Failed reference integrity checks` (invalid IDs/keys)
- **Outliers:** Outliers are values that differ significantly from the mean of characteristic features of a dataset.

**Outlier Detection Methods:**
- **Box Plot (IQR) Method:** A value is an outlier if it exceeds or falls below `1.5×IQR (interquartile range)`. That is, if it lies above the top quartile (Q3) or below the bottom quartile (Q1). A **box plot** is a graphical representation of the distribution of a dataset showing the median, quartiles, and possible outliers.
- **Standard Deviation Method:** A value is an outlier if it is greater or lower than the `mean±(3×standard deviation)`

### 1.3 Data Modelling Concepts

- **Semantic model:** a layer that defines metrics, relationships, and logic (calculations) for easy analysis and reporting.
- **Schema:** a structured plan of how data is organized in a database. It defines tables, columns, data types, relationships, constraints (not null, unique)
- **Granularity:** level of detail stored in a table. `Higher granularity` (e.g., individual transactions), `Lower granularity` (e.g., monthly sales totals).
- **Slowly Changing Dimensions (SCD):** describes attributes in a dimension table that change over time, but not frequently.
 
**Benefits of data modelling:**
- Data Quality: ensures clean, structured, and consistent data
- Performance: improves query speed
- Accuracy: reduces duplication and errors
- Reusability: reuse of data structures, logic, and definitions across multiple reports and systems.

### 1.4 Data Terms

- **Data mining:** The process of applying statistical and machine-learning techniques on data to uncover patterns.
- **Data profiling:** The process of examining data to assess fitness for use; **tells what the data looks like.**
- **Data validation:** The process of enforcing predefined rules and constraints to ensure data meets required standards; **ensures the data meets requirement.**

## 2. Excel for Data Analysis

### 2.1 Functions & Conditional Formatting

- **Math & Stats:** SUM, AVERAGE, MEDIAN, MODE, COUNT, MAX, MIN, STDEV, VAR
- **Logical:** IF, IFS, AND, OR
- **Conditional:** SUMIF, SUMIFS, AVERAGEIF, AVERAGEIFS, COUNTIFS
- **Lookup & Reference:** VLOOKUP, XLOOKUP, INDEX-MATCH
- **Text functions:** TRIM, CLEAN, LEFT, RIGHT, MID, FIND, LEN, TEXTSPLIT
- **Error handling:** IFERROR, ISBLANK, IFNA
- **Dynamic Array Functions:** FILTER, SORT, UNIQUE, SEQUENCE
- **Conditional Formatting:** Highlight trends and outliers

### 2.2 Data Exploration

- **Pivot Tables & Charts**: a data summarization tool to aggregate and filter data in a spreadsheet. Key features: `Grouping data`, `Filtering & Slicing`, `Sorting`, `Calculated fields:` for quick calculations; ratios, percentages, averages, sums, differences, etc., directly within the pivot table, `Visualization`.
- **Power Query** for automated data cleaning & transformation
- **Power Pivot:** to create relationships between multiple tables for advanced analysis. Sheet formulas become inefficient with large datasets.
- **DAX:** enables more omplex, dynamic calculations across related tables than **Calculated fields** can handle.
- **Descriptive Statistics:** with formulas & Data Analysis ToolPak.

## 3. SQL

### 3.1 SQL Basics & Database Foundation

**SQL (Structured Query Language)** is a standard programming language used to communicate with **relational databases**.

A **database** is an organized collection of data stored and accessed electronically.

**SQL Clauses**
- **Query Logical Written Order:** SELECT, TOP, DISTINCT, FROM, WHERE, GROUP BY, HAVING, ORDER BY, LIMIT
- **Query Logical Execution Order:** FROM, ON, JOIN, WHERE, GROUP BY, HAVING, SELECT, DISTINCT, ORDER BY, TOP/LIMIT/OFFSET/FETCH

### 3.2 SQL Functions

- **Data Retrieval & Filtering:** SELECT, FROM, WHERE, ORDER BY, LIMIT, AND, OR, NOT, LIKE
- **Aggregations:** COUNT, SUM, AVG, MIN, MAX, MEDIAN, MODE, STDDEV, GROUP BY, HAVING; summarise or aggregate data, often with GROUP BY
- **Window Functions:** ROW_NUMBER, RANK, DENSE_RANK, LEAD, LAG, NTILE, SUM OVER, AVG OVER; perform calculations across rows without grouping
- **String Functions:** CONCAT, REPLACE, UPPER, LOWER, LTRIM, RTRIM, TRIM, SUBSTRING, LEN/LENGTH; manipulate and clean text
- **Date & Time Functions:** GETDATE, CURRENT_DATE, YEAR, MONTH, DAY, DATEDIFF, DATEADD, DATE_TRUNC, DATE_FORMAT; handle and format date/time values
- **Data Cleaning & Transformation:** CAST, CONVERT, COALESCE, NULLIF, CASE WHEN, IFNULL, IIF, LISTAGG; format data, handle nulls, apply conditional logic
- **Set Operations:** UNION, UNION ALL, INTERSECT; combine or compare results from multiple queries

### 3.3 Joins, Subqueries, and CTEs

- **Join** is an operation used to combine rows from two or more tables based on related columns. Types: `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`, `FULL JOIN`, `CROSS JOIN`, `SELF JOIN`.
- **Subquery** is a query nested inside another query. A `correlated subquery` is a subquery that depends on the outer query. It runs once for each row returned by the outer query.
- **CTE (Common Table Expression)** is a temporary named result set that can be referenced within a SQL query. It makes complex queries easier to read and manage, especially when using subqueries or recursion. A **recursive CTE** is a CTE that refers to itself to handle hierarchical or sequential data, such as organization charts, family trees, or folder structures.

### 3.4 Query Performance Optimization

**Query optimization techniques (basics)**
- LIMIT
- Indexes
- Avoiding `SELECT *`
- Partitioning
- `EXPLAIN` plans

### 3.5 SQL Commands

SQL commands are statements used to define database structures, retrieve data, modify data, control access, and manage transactions in a database.

**DDL (Data Definition Language):** define, alter, or remove database structures.
- CREATE: creates a database object
- ALTER: modifies an existing object
- DROP: permanently deletes an object
- TRUNCATE: deletes all rows while keeping the structure
- RENAME: changes an object’s name

**DML (Data Manipulation Language):** manipulate data stored in tables.
- INSERT: adds new records
- UPDATE: modifies existing records
- DELETE: Removes specified records
- MERGE: Inserts, updates, or deletes records in one statement (used for upserts)

**DCL (Data Control Language):** control access and privileges.
- GRANT: gives user permission
- REVOKE: removes user permissions

**TCL (Transaction Control Language):** manage transactions and maintain data integrity.
- COMMIT: saves changes made in a transaction
- ROLLBACK: reverses changes before commit
- SAVEPOINT: sets a point to roll back to within a transaction

**DQL (Data Query Language):** query and retrieve data.
- SELECT: retrieves data from tables

### 3.6 SQL Database Terms

- **DELETE** removes specific rows from a table using a condition. **TRUNCATE** removes all rows from a table.
- **UNION and UNION ALL** are used to combine the result sets of two or more SELECT statements. **UNION** removes duplicate rows from the combined result set. **UNION ALL** includes all rows, including duplicates.
- **Transaction** is a sequence of SQL statements that are executed as a single logical unit of work. It ensures data consistency and integrity by either committing all changes or rolling them back if an error occurs.
- **ACID in database transactions:** Atomicity, Consistency, Isolation, and Durability. It is a set of properties that guarantee reliable processing of database transactions.
- **Stored Procedure** is a saved set of SQL commands that perform a specific task like retrieving, inserting, updating, or deleting data, and can be executed repeatedly. Can be with or without **parameters**.
- **View** is a virtual table based on the result of an SQL statement. A **materialized view** is a physical copy of the view's result set stored in the database, which is updated periodically.
- **Data Warehouse** is a large, centralized repository that stores and manages data from various sources designed for efficient analysis and reporting.
- **Candidate key** is a set of one or more columns that could potentially become the primary key.
- **Primary key** is a chosen candidate key that uniquely identifies a row in a table.
- **COALESCE** returns the first non-null expression from a list of expressions. It is often used to handle null values effectively.
- **ROW_NUMBER()** assigns a unique incremental number to each row in the result set.

### 3.7 Sample Questions
- Write a query to calculate the rolling 7-day sales per product.
- Find top 3 customers by revenue in each region.
- Identify duplicate rows and suggest a way to remove them.

## 4. Power BI

**Data visualization:** the practice of presenting data in graphical or pictorial formats—such as charts, graphs, maps, and dashboards—to clearly communicate patterns, trends, and insights.

**Power BI:** is a business intelligence tool developed by Microsoft that allows users to connect, transform, analyze, and visualize data from multiple sources.

### 4.1 Power BI main Components

- `Desktop:` Windows application for building reports and data models.
- `Service (Power BI Online):` cloud-based platform for publishing, sharing, and collaborating on reports and dashboards.
- `Mobile:` mobile apps for viewing and interacting with reports on phones and tablets.
- `Gateway:` a bridge that connects on-premises data sources to Power BI Service for scheduled refreshes.
- `Report Server:` on-premises server for hosting and managing Power BI reports within an organization’s own infrastructure.
- `Embedded:` a service for developers to embed Power BI reports and dashboards into custom applications.
- `Power Query:` data connection and transformation engine used across Power BI for data cleaning and preparation.
- `Power Pivot:` data modelling engine that allows creating relationships, measures, and calculated columns using DAX.

**Power BI Desktop views (panes):**
- `Report View:` build and design dashboards.
- `Data View:` see and explore loaded tables.
- `Model View:` define relationships between tables.

## 5. Python for Data Analysis

### 5.1 Python Fundamentals

- Variables: a named reference to a value (an object) stored in memory.
- Data Structures: Lists, tuples, sets, dictionaries
- Data types: int, float, str, bool
- Conditional statements: if, elif, else
- Loops: for, while
- Functions (with Lambda expressions)
- String handling
- Built-ins and imports
- File handling
- Modules: files that contain python code - such as functions, classes, and variables - that can be reused in other programs.
- Classes

### 5.2 Import, Clean, and Analyse Data with Pandas & NumPy

- Importing data from CSV, Excel, and other sources
- Introduction to NumPy arrays
- Creating, slicing, and reshaping arrays
- Pandas DataFrames - creation, selection, filtering
- Handling missing values (`.fillna()`, `.dropna()`)
- Aggregation and grouping
- Basic statistics

### 5.3 Visualise Data with Matplotlib & Seaborn

- Matplotlib plots
- Seaborn plots: countplot, scatterplot, heatmap
- Customise charts (titles, labels, legends)

### 5.4 Introduction to Machine Learning with Scikit-learn (Building a simple predictive model)

- Introduction to Scikit-learn
- Train-test split
- Linear Regression model
- Model evaluation (R², MAE, RMSE)
- Saving and loading models with `joblib`

### 5.5 Python Programming Terms

## 6. Statistics for Data Analysis

### 6.1	Descriptive Statistics
- Mean, median, mode
- Variance and standard deviation
- Percentiles and quartiles

### 6.2	Inferential Statistics
- Hypothesis testing (A/B testing, t-tests, chi-square tests, z-tests, etc.)
- Confidence intervals
- Correlation and covariance

### 6.3	Probability Basics
- Basic probability rules
- Distributions (normal, uniform, binomial)
- Sampling techniques

### 6.4 Statistical Terms

- **Histogram**: a graphical representation of the distribution of a dataset showing the frequency of data points in specified intervals.
- **Box plot**: a graphical representation of the distribution of a dataset showing the median, quartiles, and possible outliers.
- **Linear Regression**: a statistical method used to model the relationship between a dependent variable and one or more independent varaibles.
- **R-squared**: measures the proportion of variation in the dependent variable explained by the independent variables.
- **Adjusted R-squared**: adjusts for the number of independent varaibles in the model.

## 7. Machine Learning Introduction

## 8. Interview Prep

### 8.1 Common Recruiter Questions

**Background and fit:**
- Walk me through your CV and current role in 2 minutes.
- What are your key strengths as a data professional?
- Why are you looking to move now?
- What does the ideal next role look like for you?

**Role and company motivation:**
- What interests you about this company and this role specifically?
- Which of your recent projects best maps to what we need here?
- How do you measure the impact of your work on the business?

**Technical screening:**
- What is your core stack day to day? (SQL, Python, dbt, Spark, Airflow, Power BI/Tableau, cloud)
- Rate your proficiency in SQL and Python and give examples of recent use.
- How have you modelled data for analytics? Star vs snowflake, facts and dimensions.
- Talk me through an end-to-end pipeline you’ve built or improved.
- How do you ensure data quality and reliability?

**Testing, observability, monitoring:**
- Experience with cloud platforms? (AWS Azure GCPWhat services did you use and why?
- Have you worked with stakeholders to define metrics or a semantic layer?
- Any exposure to machine learning or experimentation?
- What was your role and outcomes?
- How do you handle performance optimisation in SQL or Spark?
- Experience with data governance, privacy and GDPR in practice.

**Behavioural and delivery:**
- Tell me about a time you managed conflicting stakeholder priorities.
- Describe a tough data problem you solved under time pressure.
- A project that didn’t go to plan and what you learned.
- How do you plan work, estimate, and communicate risks?
- Example of influencing non-technical stakeholders to drive a decision.

**Product and business impact:**
- Which KPIs have you owned or improved?
- By how much and over what timeframe?
- How do you choose the right metric and avoid vanity metrics?
- Example where your analysis changed a roadmap or saved costs.

**Ways of working:**
- Preferred working style and team setup.
- Individual contributor vs mentoring.
- Experience in Agile.
- Ceremonies you participate in and how you handle sprint goals.
- Collaboration with engineering and product.
- Handover and documentation habits.

**Practicalities and eligibility:**
- Right to work in the UK and any need for visa sponsorship.
- Security clearance status or eligibility if applicable.
- Willingness to commute, preference for hybrid work, and tolerance for travel.
- Notice period and earliest start date.
- Salary expectations in £ base plus bonus and benefits.
- Openness to bands.
- Contracting vs permanent preference.

**Track record and references:**
- Which achievements are you most proud of and why?
- Who could speak to your recent performance and in what context?

**Closing checks:**
- Where else are you interviewing and how far along are you?
- What would make you accept an offer and what would be a red flag?
- Do you have any upcoming time off we should be aware of?
