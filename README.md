# Customer Shopping Behavior Analysis
## Dashboard Preview

![Customer Shopping Behavior Dashboard](dashboard.png)

An end-to-end data analysis project exploring customer shopping behavior, purchasing patterns, product reviews, discounts, subscriptions, and revenue distribution using Python, PostgreSQL, and Power BI.

## Overview

This project analyzes customer shopping data to explore purchasing habits, customer segmentation, product performance, and potential relationships between shopping behavior and subscription status.

The workflow combines Python for data preparation, PostgreSQL for analytical queries, and Power BI for data visualization and business insights.

## Objectives

* Analyze revenue distribution across customer demographics.
* Investigate purchasing patterns and product popularity.
* Compare average spending between shipping methods.
* Examine spending behavior among subscribers and non-subscribers.
* Evaluate discount usage across products.
* Segment customers based on previous purchase history.
* Explore purchasing behavior across age groups.
* Analyze product review ratings and customer preferences.

## Technologies

* **Python** — Data preparation and transformation.
* **Pandas** — Data cleaning, exploration, and feature engineering.
* **Jupyter Notebook** — Interactive data analysis.
* **PostgreSQL** — Data storage and analytical queries.
* **SQLAlchemy** — Database connection and data loading.
* **SQL** — Aggregations, subqueries, CTEs, window functions, and conditional logic.
* **Power BI** — Interactive dashboards and data visualization.

## Project Workflow

### 1. Data Exploration and Preparation

The initial analysis was performed in Python using Pandas.

Key steps included:

* Exploring the dataset structure and descriptive statistics.
* Identifying missing values.
* Handling missing product review ratings using category-level averages.
* Standardizing column names.
* Creating age groups using quantile-based binning with `pd.qcut()`.
* Converting purchase frequency categories into numerical day intervals.
* Removing a redundant promotional-code column after checking its relationship with the discount indicator.

### 2. Database Integration

After preparation, the dataset was loaded into PostgreSQL for further analysis.

The integration used SQLAlchemy to connect Python to the database and persist the processed DataFrame in the `customer` table.

### 3. SQL Analysis

The SQL queries investigate several business questions:

| Analysis              | Business question                                                                         |
| --------------------- | ----------------------------------------------------------------------------------------- |
| Revenue by gender     | How is total revenue distributed across genders?                                          |
| Discount usage        | Which customers used discounts while spending at or above the average purchase amount?    |
| Product ratings       | Which products have the highest average review ratings?                                   |
| Shipping methods      | How do average purchase amounts compare between Standard and Express shipping?            |
| Subscription status   | How do average spending and total revenue differ between subscribers and non-subscribers? |
| Product discounts     | Which products have the highest proportion of purchases involving discounts?              |
| Customer segmentation | How are customers distributed across New, Returning, and Loyal segments?                  |
| Product popularity    | Which three products have the highest purchase counts within each category?               |
| Repeat purchases      | How are repeat buyers distributed by subscription status?                                 |
| Age groups            | How is total revenue distributed across age groups?                                       |

The queries use SQL aggregation, `CASE` expressions, subqueries, Common Table Expressions (CTEs), and window functions such as `ROW_NUMBER()`.

### 4. Power BI Dashboard

Power BI is used to transform the prepared data into visualizations that support exploration of customer behavior and purchasing patterns.

The dashboard complements the Python and SQL workflow by presenting the data in a format suitable for communicating analytical findings.

## Repository Structure

The main project files include:

```text
customer-behavior-analysis/
├── Analysis.ipynb
├── SQL querys.sql
├── customer_shopping_behavior.csv
├── customer_behavior.pbix
└── README.md
```

The CSV dataset must be available locally to execute the notebook. The Power BI file can be opened with Power BI Desktop.

## Getting Started

### Prerequisites

Install or prepare the following:

* Python
* Jupyter Notebook
* PostgreSQL
* Power BI Desktop

### 1. Clone the repository

```bash
git clone <repository-url>
cd customer-behavior-analysis
```

### 2. Create a Python environment

```bash
python -m venv .venv
```

Activate the environment:

**Windows**

```bash
.venv\Scripts\activate
```

**Linux/macOS**

```bash
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install pandas sqlalchemy "psycopg2-binary" jupyter
```

### 4. Prepare the database

Create a PostgreSQL database named `customer_behavior`.

Configure the database connection in the notebook using your local credentials. Avoid hardcoding passwords in files committed to GitHub; use environment variables or another secure configuration method.

### 5. Run the notebook

Start Jupyter Notebook:

```bash
jupyter notebook
```

Open `Analysis.ipynb` and execute the cells to explore, prepare, and load the dataset.

### 6. Execute the SQL queries

Once the data has been loaded into PostgreSQL, execute the queries in `SQL querys.sql` using a PostgreSQL client, such as pgAdmin or `psql`.

### 7. Open the dashboard

Open `customer_behavior.pbix` in Power BI Desktop to explore the visualizations.

## Skills Demonstrated

* Exploratory Data Analysis (EDA)
* Data cleaning and preprocessing
* Feature engineering
* Python and Pandas
* Relational databases and PostgreSQL
* Analytical SQL and data aggregation
* Window functions and CTEs
* Python-to-database integration
* Data visualization and business intelligence
* Translating business questions into analytical queries

## Key Takeaway

This project demonstrates a practical data analysis workflow, from raw customer data preparation to SQL-based investigation and Power BI visualization. It brings together programming, database querying, and business intelligence to explore purchasing behavior and customer trends.

---

**Author:** Leandro Mendieta
