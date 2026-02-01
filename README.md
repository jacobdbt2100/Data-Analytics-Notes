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

### 1.1 Data Sources
- Databases, spreadsheets, APIs, streaming data, SaaS applications (Salesforce, HubSpot, Shopify, etc.)
- Structured, Semi-structured, Unstructured data
- Data file formats: csv, xlsx, json, parquet
- Keys & relationships:
  - **Primary**: a unique identifier for each record in a table.
  - **Foreign keys**: a field in a table that refers to the primary key of another table, establishing a relationship between the two tables.
  - 1–1, 1–Many, Many–Many

### 1.2 Data Preparation (Cleaning & Transformation)

**Cleaning:**
- Duplicates
- Missing Values
- Data Types
- Data Formats
- Invalid Data
- Irrelevant Data
- Special Characters
- Outliers (statistical analysis)

**Transformation:**
- **Append:** combines data by adding rows. It stacks datasets with the same structure into one larger dataset, increasing the number of records without changing the columns.
- **Merge:** combines data by adding columns. It links datasets using a common field to bring related information from one dataset into another.
- Normalization vs Standardization (model building)

### 1.3 Exploratory Data Analysis (EDA)
- Descriptive statistics (mean, median, mode, std, percentiles)
- Distributions & variability
- Correlations
- Segmentation
  - `Demographic` (age, gender, income level, education, occupation, marital status)
  - `Geographic` (country, state, city, climate zones, urban vs rural, population density)
  - `Psychographic` (values & beliefs, interests/attitudes)
  - `Behavioural` (recency, frequency, monetary-RFM)

An unsupervised machine learning technique, `K-Means Clustering`, groups customers based on similarity in behaviour (advanced RFM analysis)
- Market basket analysis
- Cohort analysis

### 1.4 Business Understanding & Metrics
- KPIs
- Essential business metrics (marketing):
  - Engagement rate: measure/compare success of creating awareness about a product or service
  - Conversion rate: measure/compare sucess of users' completion of the desired business action (purchase, subscription)
  - Return on Ad Spend (ROAS)
  - Retention rate
 
### 1.5 Data Modelling Concepts
- `Schema:`a structured plan of how data is organized in a database. It defines:
  - `Tables (entities):` `Fact` vs `Dimension` tables
  - `Columns (attributes)`
  - `Data types:` integer, string, date, etc.
  - `Relationships:` between tables (primary keys, foreign keys)
  - `Constraints:` rules like NOT NULL, UNIQUE, etc.

- `Granularity:` level of detail stored in a dataset or table. `Higher granularity` means more detailed data (e.g., individual transactions). `Lower granularity` means summarized or aggregated data (e.g., monthly sales totals). Choosing the right granularity affects storage cost, query performance, and analytical usefulness.
  > `Example:`
    - Suppose you have a `Sales table`
      - `High granularity:` One row per item sold (e.g., “1 bottle of Coke sold at 10:05 AM”).
      - `Low granularity:` One row per day summarizing all items sold (e.g., “500 items sold on Monday”).
    - Choosing granularity depends on the analysis:
        - Analyse peak shopping hours > `High granularity`
        - Show monthly performance > `Low granularity`
  
- `Slowly Changing Dimensions (SCD):` describes attributes in a dimension table that change over time, but not frequently. `SCD techniques` ensure historical data remains accurate when those attributes change. There are different types (e.g., `Type 1:` overwrite old data; `Type 2:` add a new record to preserve history). SCDs are key to maintaining correct historical reporting and trend analysis.
  > `Example:`
        - A customer changes their `address` or `marital status`
        - Change in `cost` or `sales price`
- `Benefits of data modelling:`
  - `Data Quality:` ensures clean, structured, and consistent data
  - `Performance:` improves query speed
  - `Accuracy:` reduces duplication and errors
  - `Reusability:` reuse of data structures, definitions, and logic across multiple reports and systems

### 1.6 Data Visualisation & Insight Communication
- Chart selection best practices
- Storytelling with data
- Dashboards & Reports

### 1.7 Documentation
- Meta data
- Code, Queries (with comments)
- Version control basics (git)
- Communicating assumptions, limitations, and data decisions

### 1.8 Data Privacy and Security Concerns
- Data protection regulations
- Anonymizing sensitive data
- Secure data storage and transfer methods
- Access controls

## 2. Excel for Data Analysis

### 2.1 Excel Basics, Data Cleaning & Transformation

- Importing data (CSV, TXT, Excel files) 
- Data types, duplicates, missing values, invalid data, etc.
- **Text functions:** TRIM, CLEAN, LEFT, RIGHT, MID, FIND, LEN, TEXTSPLIT
- **Error handling:** IFERROR, ISBLANK, IFNA
- Combining text columns using CONCATENATE
- Data Validation (drop-down lists)
- Flash Fill for quick transformations
- Introduction to **`Power Query`** for automated data cleaning & transformation

### 2.2 Functions & Conditional Formatting

- **Math & Stats:** SUM, AVERAGE, MEDIAN, MODE, COUNT, MAX, MIN, STDEV, VAR
- **Logical:** IF, IFS, AND, OR
- **Conditional:** SUMIF, SUMIFS, AVERAGEIF, AVERAGEIFS, COUNTIFS
- **Lookup & Reference:** VLOOKUP, XLOOKUP, INDEX-MATCH
- **Dynamic Array Functions:** FILTER, SORT, UNIQUE, SEQUENCE
- **Conditional Formatting:** Highlight trends and outliers

### 2.3 Data Exploration

- **Pivot Tables & Charts**: a data summarization tool to aggregate and filter data in a spreadsheet. Key features:
  - `Grouping data`
  - `Filtering & Slicing`
  - `Sorting`
  - `Calculated fields:` for quick calculations—ratios, percentages, averages, sums, differences; directly within the pivot table.
  - `Visualization`
- **Descriptive Statistics** (with formulas & Data Analysis ToolPak)
- **Power Query:** combining multiple tables (merge & append)
- **Power Pivot:** to create relationships between multiple tables for advanced analysis. **`VLOOKUP`** or **`XLOOKUP`** become inefficient with large datasets.
- **DAX (Data Analysis Expressions):** enables more omplex, dynamic calculations across related tables than **`Calculated fields`** can handle.

### 2.4 Visualization & Dashboard Building

- Chart types and use cases:
  - Column, Bar, Line, Pie, Scatter, Histogram, Combo
- Dynamic charts with Excel Tables or named ranges
- Slicers and Timelines for interactive reports
- Dashboard design principles:
  - Layout consistency
  - Minimal colour palette
  - Clear KPI presentation
- Final **interactive dashboard** project

















