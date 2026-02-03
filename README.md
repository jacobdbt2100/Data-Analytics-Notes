# Data Analytics

## 1. Introduction

**Data analysis** is a process of `modelling`, `analyzing`, and `interpreting` data to extract insights. A **Data Analyst** `collects`, `process`, and `analyze` data to identify trends/patterns and make informed decisions.

**Data mining:** The analytical process of applying statistical and machine-learning techniques to prepared data to uncover patterns, relationships, and predictive insights for decision-making.

**Data profiling:** The process of examining data structure, content, and quality to assess fitness for use and prevent issues in downstream analytics.

**Data validation:** The process of enforcing predefined rules and constraints to ensure data meets required standards as it flows through a pipeline.

Summarily, **data profiling** tells what the data looks like; **data validation** ensures the data meets what it should look like.

**Data lifecycle**: `Use case` > `Data collection` > `Storage` > `Processing` > `Analysis` > `Visualization` > `Reporting`

**Types of analytics**:

- **Descriptive:** `What happened?` e.g., A skincare brand sees 15,000 people clicked their Instagram ad last week, but only 500 purchased.
- **Diagnostic:** `Why did it happen?` e.g., Analysis shows that shipping costs made many customers abandon their carts at checkout.
- **Predictive:** `What will likely happen?` e.g., If nothing changes, the model forecasts cart drop-offs will keep increasing as shipping prices rise.
- **Prescriptive:** `What should we do?` e.g., The system recommends offering free shipping above $40 to increase checkout conversions.
- **Exploratory:** `What hidden opportunities exist?` e.g., Data reveals customers who buy face cleansers often buy serums within a week, suggesting a personalised follow-up email can boost revenue.

### 1.1 Data Cleaning

**Data cleaning** is the process of identifying and correcting errors in a dataset to improve its reliability for analysis.

**Data Cleaning Steps:**

**1. Data Types:** `Text`, `Dates`, `Decimals/Floats`, `Integer`

**2. Irrelevant Data:** `Unused fields/entries`, `Constant values`

**3. Missing Values:** `NULLs / NaNs / Blanks`

**4. Duplicates:** `Repeated entries` (none unique rows)

**5. Special / Non-printable Characters:** `Unwanted characters/symbols` (punctuation, emojis, currency), `Extra spaces` (tabs, newline artefacts)

**6. Data Formats (Structural errors):** `Inconsistent date formats` (DD/MM vs MM/DD), `Mixed units` (kg vs g, ₦ vs $), `Spacing inconsistencies` ("Transfer", "Transfer "), `Case inconsistencies` (“Male”, “male”, "MALE", “M”)

**7. Invalid Data:** `Out-of-range values` (negative age, future dates, time <= 0), `Logical conflicts` (discharge date < admission date), `Failed reference integrity checks` (invalid IDs/keys)

**8. Outliers:** Outliers are values that differ significantly from the mean of characteristic features of a dataset.

**Outlier Detection Methods:**
- **Box Plot (IQR) Method:** A value is an outlier if it exceeds or falls below `1.5×IQR (interquartile range)`. That is, if it lies above the top quartile (Q3) or below the bottom quartile (Q1).
- **Standard Deviation Method:** A value is an outlier if it is greater or lower than the `mean±(3×standard deviation)`

A **box plot** is a graphical representation of the distribution of a dataset showing the median, quartiles, and possible outliers.

### 1.2 Data Modelling Concepts

- **Semantic model:** a layer that defines metrics, relationships, and logic (calculations) for easy analysis and reporting.
- **Schema:** a structured plan of how data is organized in a database. It defines tables, columns, data types, relationships, constraints (not null, unique)
- **Granularity:** level of detail stored in a table. `Higher granularity` (e.g., individual transactions), `Lower granularity` (e.g., monthly sales totals).
- **Slowly Changing Dimensions (SCD):** describes attributes in a dimension table that change over time, but not frequently.
 
**Benefits of data modelling:**
- Data Quality: ensures clean, structured, and consistent data
- Performance: improves query speed
- Accuracy: reduces duplication and errors
- Reusability: reuse of data structures, definitions, and logic across multiple reports and systems.

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
- **DAX:** enables more omplex, dynamic calculations across related tables than **`Calculated fields`** can handle.
- **Descriptive Statistics** (with formulas & Data Analysis ToolPak)

## 3. SQL

### 3.1 SQL Basics & Database Foundations

**SQL (Structured Query Language)** is a standard programming language used to communicate with **relational databases**.

A **`database`** is an organized collection of data stored and accessed electronically.

**SQL Clauses**
- **Query Logical Written Order:** SELECT, TOP, DISTINCT, FROM, WHERE, GROUP BY, HAVING, ORDER BY, LIMIT
- **Query Logical Execution Order:** FROM, ON, JOIN, WHERE, GROUP BY, HAVING, SELECT, DISTINCT, ORDER BY, TOP/LIMIT/OFFSET/FETCH

Filter with **logical operators **(AND, OR, NOT, BETWEEN, IN, LIKE)

### 3.2 SQL Functions

- Aggregate Functions: COUNT, SUM, AVG, MIN, MAX, MEDIAN, MODE, STDDEV; summarise or aggregate data, often with GROUP BY
- String Functions: CONCAT, REPLACE, UPPER, LOWER, LTRIM, RTRIM, TRIM, SUBSTRING, LEN/LENGTH; manipulate and clean text
- Date & Time Functions: GETDATE, CURRENT_DATE, YEAR, MONTH, DAY, DATEDIFF, DATEADD, DATE_TRUNC, DATE_FORMAT; handle and format date/time values
- Cleaning & Transformation: CAST, CONVERT, COALESCE, NULLIF, CASE WHEN, IFNULL, IIF, LISTAGG; format data, handle nulls, apply conditional logic
- Set Operations: UNION, UNION ALL, INTERSECT; combine or compare results from multiple queries
- Window Functions: ROW_NUMBER, RANK, DENSE_RANK, LEAD, LAG, SUM OVER, AVG OVER; perform calculations across rows without grouping

### 3.3 Data Cleaning, Joins & CTEs

- Data cleaning with TRIM, LOWER, UPPER, REPLACE
- Handling NULLs with COALESCE, IS NULL, IS NOT NULL
- JOINS in SQL

**Join** is an operation used to combine rows from two or more tables based on related columns. Types: `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`, `FULL JOIN`, `CROSS JOIN`, `SELF JOIN`.

**Subquery** is a query nested inside another query. A `correlated subquery` is a subquery that depends on the outer query. It runs once for each row returned by the outer query.

**CTE (Common Table Expression)** is a temporary named result set that can be referenced within a SQL query. It makes complex queries easier to read and manage, especially when using subqueries or recursion. A **recursive CTE** is a CTE that refers to itself to handle hierarchical or sequential data, such as organization charts, family trees, or folder structures.

### 3.4 Query Optimization

**Query performance techniques (basics)**
- LIMIT
- Indexes
- Avoiding `SELECT *`
- Partitioning

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

### 3.6 Terms in SQL Databases

**DELETE** removes specific rows from a table using a condition. **TRUNCATE** removes all rows from a table.

**UNION and UNION ALL** are used to combine the result sets of two or more SELECT statements. **UNION** removes duplicate rows from the combined result set. **UNION ALL** includes all rows, including duplicates.

**Transaction** is a sequence of SQL statements that are executed as a single logical unit of work. It ensures data consistency and integrity by either committing all changes or rolling them back if an error occurs.

**ACID in database transactions:** Atomicity, Consistency, Isolation, and Durability. It is a set of properties that guarantee reliable processing of database transactions.

**Stored Procedure** is a saved set of SQL commands that perform a specific task like retrieving, inserting, updating, or deleting data, and can be executed repeatedly. Can be with or without **parameters**.

**View** is a virtual table based on the result of an SQL statement. A **materialized view** is a physical copy of the view's result set stored in the database, which is updated periodically.

**Data Warehouse** is a large, centralized repository that stores and manages data from various sources designed for efficient analysis and reporting.

**Candidate key** is a set of one or more columns that could potentially become the primary key.

**Primary key** is a chosen candidate key that uniquely identifies a row in a table.

**COALESCE** returns the first non-null expression from a list of expressions. It is often used to handle null values effectively.

**ROW_NUMBER()** assigns a unique incremental number to each row in the result set.

## 4. Power BI










### 4.1 Power BI Basics

**Data visualization:** the practice of presenting data in graphical or pictorial formats—such as charts, graphs, maps, and dashboards—to clearly communicate patterns, trends, and insights.

**Power BI:** is a business intelligence tool developed by Microsoft that allows users to connect, transform, analyze, and visualize data from multiple sources.

- `Power BI` main Components:
  - `Desktop:` Windows application for building reports and data models.
  - `Service (Power BI Online):` cloud-based platform for publishing, sharing, and collaborating on reports and dashboards.
  - `Mobile:` mobile apps for viewing and interacting with reports on phones and tablets.
  - `Gateway:` a bridge that connects on-premises data sources to Power BI Service for scheduled refreshes.
  - `Report Server:` on-premises server for hosting and managing Power BI reports within an organization’s own infrastructure.
  - `Embedded:` a service for developers to embed Power BI reports and dashboards into custom applications.
  - `Power Query:` data connection and transformation engine used across Power BI for data cleaning and preparation.
  - `Power Pivot:` data modelling engine that allows creating relationships, measures, and calculated columns using DAX.

- Power BI Desktop, with three main views (or panes), each serving a different purpose:
  - `Report View:` build and design dashboards using visuals, charts, and slicers.
  - `Data View:` see and explore loaded tables after data has been imported.
  - `Model View:` define relationships between tables.

- Data import from Excel, CSV, and SQL databases
- Understanding Power Query Editor
- Data profiling (column quality, distribution, profile)
- Cleaning and transforming data:
  - Remove duplicates, split columns, replace values, fill blanks
  - Merge and append queries
- Basic data model setup (naming conventions, data types, relationships)

### 4.2 Data Modelling & DAX Fundamentals

- Star schema design: fact and dimension tables
- Relationships (one-to-many, cross filter direction)
- Calculated columns vs. measures
- DAX basics:
  - SUM, AVERAGE, COUNTROWS, DISTINCTCOUNT, CALCULATE, FILTER, ALL
- Conditional logic: IF, SWITCH
- Time intelligence:
  - TOTALYTD, SAMEPERIODLASTYEAR, DATEADD

### 4.3 Data Visualisation & Interactivity

- Chart types and when to use them:
  - Bar/Column, Line, Card, Pie, Map, Matrix
- Hierarchies (e.g., Year > Quarter > Month)
- Slicers, Filters, and Drill-throughs
- Conditional formatting and custom tooltips
- Using bookmarks for dynamic storytelling

### 4.4 Dashboard Design, Publishing & Storytelling

- Dashboard layout and design principles:
  - Consistent alignment, colours, and typography
- Clear KPIs at the top, supporting visuals below
- Storytelling techniques for business insights
- Using Power BI Service:
- Publishing reports
- Creating and managing workspaces
- Sharing dashboards and setting permissions
- Report refresh and basic automation
- Export options (PDF, PowerPoint, shared link)
- Final **interactive dashboard** project

## 5. Python for Data Analysis

# PYTHON SUMMARY

A visual summary of Python features that show up most in everyday code
When people start learning Python, they often feel stuck.

Too many videos.
Too many topics.
No clear idea of what to focus on first.

This summary sheet works because it shows the parts of Python you actually use when writing code.

A quick breakdown in plain terms:

**Basics and variables**

You use these everywhere. Store values. Print results.
If this feels shaky, everything else feels harder than it should.

**Data structures**

Lists, tuples, sets, dictionaries.
Most real problems come down to choosing the right one.
Pick the wrong structure and your code becomes messy fast.

**Conditionals**

This is how Python makes decisions.
Questions like:
– Is this value valid?
– Does this row meet my rule?

**Loops**

Loops help you work with many things at once.
Rows in a file. Items in a list.
They save you from writing the same line again and again.

**Functions**

This is where good habits start.
Functions help you reuse logic and keep code readable.
Almost every real project relies on them.

**Strings**

Text shows up everywhere.
Names, emails, file paths.
Knowing how to handle text saves a lot of time.

**Built-ins and imports**

Python already gives you powerful tools.
You don’t need to reinvent them.
You just need to know they exist.

**File handling**

Real data lives in files.
You read it, clean it, and write results back.
This matters more than beginners usually realize.

**Classes**

Not needed on day one.
But seeing them early helps later.
They’re just a way to group data and behavior together.

Don’t try to memorize this sheet.

Write small programs from it.
Make mistakes.
Fix them.

That’s when Python starts to feel normal.

### 5.1 Python Fundamentals & Data Structures (Building a strong foundation in syntax, data types, and logic)

- Variables, input/output, and indentation
- Data types: `int`, `float`, `str`, `bool`
- Lists, tuples, sets, dictionaries
- Control statements (`if`, `for`, `while`)
- Functions and `lambda` expressions

**Sample Codes:**
```python
# Basic data types
x = 10
y = 3.5
name = "Jacob"
is_active = True
print(type(x), type(name))  # <class 'int'> <class 'str'>

# Conditional statement
if x > 5:
    print("x is greater than 5")

# Loop example
for i in range(3):
    print("Loop count:", i)

# Function example
def greet(name):
    return f"Hello, {name}!"

print(greet("Jacob"))

# Lambda function
square = lambda n: n**2
print(square(4))  # 16
```

**Mini Project:**

Create a small program to summarise student scores from a CSV file using lists and dictionaries.

### 5.2 Working with Data, NumPy, and Pandas (Importing, cleaning, and analyzing structured data)

- Importing data from CSV, Excel, and other sources
- Introduction to NumPy arrays
- Creating, slicing, and reshaping arrays
- Pandas DataFrames — creation, selection, filtering
- Handling missing values (`.fillna()`, `.dropna()`)
- Aggregation and grouping
- Basic statistics and correlation

**Sample Codes:**
```python
import numpy as np
import pandas as pd

# Importing data
df_csv = pd.read_csv('sales_data.csv')
df_excel = pd.read_excel('sales_data.xlsx')

# Inspecting data
print(df_csv.head())
print(df_csv.info())

# NumPy example
arr = np.array([10, 20, 30, 40])
print(arr.mean())  # 25.0

# Pandas DataFrame from dictionary
data = {'Name': ['Ayo', 'Tunde', 'Jane'], 'Score': [80, 75, 90]}
df = pd.DataFrame(data)
print(df.head())

# Filtering
print(df[df['Score'] > 80])

# Grouping example
df['Category'] = ['A', 'B', 'A']
print(df.groupby('Category')['Score'].mean())
```

**Mini Project:**

Perform exploratory data analysis (EDA) on a Sales dataset — import, clean, and summarise totals, averages, and missing values.

### 5.3 Data Visualization with Matplotlib & Seaborn (Creating visual insights for presentation and storytelling)

- Introduction to Matplotlib
- Seaborn plots: countplot, scatterplot, heatmap
- Customizing charts (titles, labels, legends)
- Comparing relationships between variables

**Sample Codes:**
```python
import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd

# Sample data
data = {'Product': ['A', 'B', 'C'], 'Sales': [200, 150, 300]}
df = pd.DataFrame(data)

# Bar chart
plt.bar(df['Product'], df['Sales'])
plt.title("Sales by Product")
plt.xlabel("Product")
plt.ylabel("Sales")
plt.show()

# Seaborn scatter plot
sns.scatterplot(x='Product', y='Sales', data=df)
plt.show()
```

**Mini Project:**

Create visuals showing sales trends, top categories, and correlation heatmaps to highlight patterns and insights from a dataset.

### 5.4 Introduction to Machine Learning with Scikit-learn (Building a simple predictive model)

- Introduction to Scikit-learn
- Train-test split
- Linear Regression model
- Model evaluation (R², MAE, RMSE)
- Saving and loading models with `joblib`

**Sample Codes:**
```python
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_absolute_error
import joblib
import pandas as pd

# Sample dataset
df = pd.DataFrame({
    'Hours_Studied': [2, 3, 4, 5, 6],
    'Score': [50, 60, 65, 70, 80]
})

X = df[['Hours_Studied']]
y = df['Score']

# Split data
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Train model
model = LinearRegression()
model.fit(X_train, y_train)

# Predict
predictions = model.predict(X_test)
print("MAE:", mean_absolute_error(y_test, predictions))

# Save model
joblib.dump(model, 'score_predictor.pkl')
```
**Final Project:**

Build a simple model to predict sales or customer churn using Scikit-learn.

### MISCELLANEOUS

#### `Key Tools:`

| Library | Purpose | Notes |
|--------|---------|------|
| Pandas | Data analysis and wrangling | Equivalent to Excel/SQL tables |
| NumPy | Efficient numerical operations | Supports Pandas under the hood |
| Matplotlib | Customizable visualizations | Base layer for plotting in Python |
| Seaborn | Statistical visualizations | Built on Matplotlib; cleaner defaults |
| Plotly | Interactive visuals | Dashboard-friendly |

> Workflow: Pandas > Seaborn for quick insights > Matplotlib for fine-tuning > Plotly for dashboards

#### `Modules:`
In Python, modules are files that contain Python code — such as functions, classes, and variables — that can be reused in other programs.

#### `Matplotlib vs Seaborn:`

| Aspect            | **Matplotlib**                                                   | **Seaborn**                                                                                            |
| ----------------- | ---------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| **Purpose**       | A low-level plotting library for detailed control over plots.    | A high-level library built on top of Matplotlib for easier, more attractive statistical visualization. |
| **Ease of Use**   | Requires more code and manual styling.                           | Simpler syntax and automatic styling for better visuals.                                               |
| **Customization** | Extremely flexible—fine control over every plot element.         | Limited flexibility but integrates easily with Matplotlib for custom tweaks.                           |
| **Default Style** | Basic and less aesthetic by default.                             | Comes with appealing themes and colour palettes.                                                       |
| **Best For**      | Creating highly customized plots and complex figure layouts.     | Quick, beautiful plots for statistical data exploration.                                               |
| **Integration**   | Foundation for Seaborn and other libraries like pandas plotting. | Works seamlessly with pandas DataFrames and Matplotlib.                                                |

#### `Pandas Summary Codes:`

1. **`Import / Export Data`**

```python
# Read from a CSV file
pd.read_csv(filename)

# Read from a delimited text file
pd.read_table(filename)

# Read from an Excel file
pd.read_excel(filename)

# Read from a SQL table/database
pd.read_sql(query, connection_object):

# Read from a JSON formatted string, URL, or file
pd.read_json(json_string)

# Parse an HTML URL, string, or file to extract tables to a list of DataFrames
pd.read_html(url)

# Create a DataFrame from a dictionary (keys as column names, values as lists)
pd.DataFrame(dict)

# Write to a CSV file
df.to_csv(filename)

# Write to an Excel file
df.to_excel(filename)

# Write to a SQL table
df.to_sql(table_nm, connection_object)

# Write to a file in JSON format
df.to_json(filename)
```

2. **`Inspect Data`**

```python
# View the first 5 rows of the DataFrame
df.head()

# View the last 5 rows of the DataFrame
df.tail()

# View random 5 rows of the DataFrame
df.sample()

# Get the dimensions of the DataFrame
df.shape

# Get a concise summary of the DataFrame
df.info()

# Summary statistics for numerical columns
df.describe()

# Check data types of columns
df.dtypes

#  List column names
df.columns

# Display the index range
df.index
```

3. **`Select Index Data`**

```python
# Select a single column
df['column']

# Select multiple columns
df[['col1', 'col2']]

# Select the first row by position
df.iloc[0]

# Select the first row by index label
df.loc[0]

# Select a specific element by position
df.iloc[0, 0]

# Select a specific element by label
df.loc[0, 'column']

# Filter rows where column > 5
df[df['col'] > 5]

# Slice rows and columns
df.iloc[0:5, 0:2]

# Set a column as the index
df.set_index('column')
```

4. **`Cleaning Data`**

```python
# Check for null values
df.isnull()

# Check for non-null values
df.notnull()

# Drop rows with null values
df.dropna()

# Replace null values with a specific value
df.fillna(value)

# Replace specific values
df.replace(1, 'one')

# Rename columns
df.rename(columns={'old': 'new'})

# Change data type of a column
df.astype('int')

# Remove duplicate rows
df.drop_duplicates()

# Reset the index
df.reset_index()
```

5. **`Sort & Filter Data`**

```python
# Sort by column in ascending order
df.sort_values('col')

# Sort by column in descending order
df.sort_values('col', ascending=False)

# Sort by multiple columns
df.sort_values(['col1', 'col2'], ascending=[True, False])

# Filter rows based on condition
df[df['col'] > 5]

# Filter using a query string
df.query('col > 5')

# Randomly select 5 rows
df.sample(5)

# Get top 3 rows by column
df.nlargest(3, 'col')

# Get bottom 3 rows by column
df.nsmallest(3, 'col')

# Filter columns by substring
df.filter(like='part')
```

6. **`Group Data`**

```python
# Group by a column
df.groupby('col')

# Mean of groups
df.groupby('col').mean()

# Sum of groups
df.groupby('col').sum()

# Count non-null values in groups
df.groupby('col').count()

# Max value in another column for groups
df.groupby('col')['other_col'].max()

# Create a pivot table
df.pivot_table(values='col', index='group', aggfunc='mean')

# Aggregate multiple columns
df.agg({'col1': 'mean', 'col2': 'sum'})

# Apply a function to columns
df.apply(np.mean)

# Transform data column-wise
df.transform(lambda x: x + 10)
```

7. **`Merge / Join Data`**

```python
# Concatenate DataFrames vertically
pd.concat([df1, df2])


# Concatenate DataFrames horizontally
pd.concat([df1, df2], axis=1)

# Merge two DataFrames on a key
df1.merge(df2, on='key')

# SQL-style join
df1.join(df2)

# Append rows of one DataFrame to another
df1.append(df2)

# Outer join
pd.merge(df1, df2, how='outer', on='key')

# Inner join
pd.merge(df1, df2, how='inner', on='key')

# Left join
pd.merge(df1, df2, how='left', on='key')

# Right join
pd.merge(df1, df2, how='right', on='key')
```

8. **`Statistical Operations`**

```python
# Column-wise mean
df.mean()

# Column-wise median
df.median()

# Column-wise standard deviation
df.std()

# Column-wise variance
df.var()

# Column-wise sum
df.sum()

# Column-wise minimum
df.min()

# Column-wise maximum
df.max()

# Count of non-null values per column
df.count()

# Correlation matrix
df.corr()
```

9. **`Data Visualization`**

```python
# Line plot
df.plot(kind='line')

# Vertical bar plot
df.plot(kind='bar')

# Horizontal bar plot
df.plot(kind='barh')

# Histogram
df.plot(kind='hist')

# Box plot
df.plot(kind='box')

# Kernel density estimation plot
df.plot(kind='kde')

# Pie chart
df.plot(kind='pie', y='col')

# Scatter plot
df.plot.scatter(x='c1', y='c2')

# Area plot
df.plot(kind='area')
```

#### `loc vs iloc:`

| Feature               | **loc**                                     | **iloc**                                       |
| --------------------- | ------------------------------------------- | ---------------------------------------------- |
| **Purpose**           | Label-based selection                       | Integer position-based selection               |
| **Access by**         | Row/column **labels**                       | Row/column **index positions**                 |
| **Syntax**            | `df.loc[row_label, column_label]`           | `df.iloc[row_index, column_index]`             |
| **Example (row)**     | `df.loc[2]` → row with index label `2`      | `df.iloc[2]` → 3rd row (index position 2)      |
| **Example (range)**   | `df.loc[1:3]` → includes both 1 and 3       | `df.iloc[1:3]` → includes 1 but **excludes 3** |
| **Boolean filtering** | Accepts boolean masks with **labels**       | Accepts boolean masks with **positions**       |
| **Use case**          | When you know the **index names** or labels | When you know the **row/column order**         |

## 6. Statistics Basics for Data Analysis

### 6.1	Descriptive Statistics
    - Mean, median, mode
    - Variance and standard deviation
    - Percentiles and quartiles
    - Data visualization

### 6.2	Inferential Statistics
    - Confidence intervals
    - Hypothesis testing (A/B testing, t-tests, chi-square tests, z-tests, etc.)
    - Correlation and covariance

### 6.3	Linear Regression

### 6.4	Classification

### 6.5	Probability Basics
    - Basic probability rules
    - Distributions (normal, uniform, binomial)
    - Sampling techniques

**Histogram**: a graphical representation of the distribution of a dataset showing the frequency of data points in specified intervals.

**Box plot**: a graphical representation of the distribution of a dataset showing the median, quartiles, and possible outliers.

**Linear Regression**: a statistical method used to model the relationship between a dependent variable and one or more independent varaibles.

**R-squared**: measures the proportion of variation in the dependent variable explained by the independent variables.

**Adjusted R-squared**: adjusts for the number of independent varaibles in the model.

## 7. Machine Learning Basics

**Normal Distribution**: A normal distribution is a symmetric, bell-shaped distribution where data cluster around the mean.

It’s important in data analysis and machine learning because many statistical methods assume normality and real-world data often approximate this pattern, especially through the Central Limit Theorem.

**Linear Regression**: a statistical method used to model the relationship between a dependent variable and one or more independent varaibles.

**Overfitting**: occurs when a model is too complex and performs too well.

**Confusion Matrix**: a table used to evaluate the performance of a classification model showing the true positives, true negatives, false positives, and false negatives.

## Types of Machine Learning
- Supervised: Predict output using labelled data (e.g., Linear Regression, Logistic Regression, Random Forest, SVM, XGBoost)
  > **Example tasks**: Classification, Regression
- Unsupervised: Discover patterns from unlabelled data (e.g., K-Means, Hierarchical Clustering, PCA)
  > **Example tasks**: Clustering, Dimensionality Reduction
- Semi-supwervised: Use small labelled + large unlabelled data

## Normalization vs Standardization
> `Normalisation` rescales data to a fixed range; `Standardization` rescales data to have a fixed mean and variance. Choose based on algorithm assumptions and feature scale sensitivity.

| Feature      | **Normalization**                      | **Standardization**     |
| ------------ | -------------------------------------- | ----------------------- |
| Purpose      | Scale to a fixed range                 | Scale to mean 0, std 1  |
| Formula      | (x − min) / (max − min)                | (x − μ) / σ             |
| Output Range | Usually 0–1                            | No fixed range          |
| Distribution | Preserved                              | Centered & rescaled     |
| Outliers     | Highly sensitive                       | Moderately sensitive    |
| Best For     | Distance-based & neural network models | Linear models, PCA, SVM |




