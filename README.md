# 📊 Customer Churn Analysis

## 📌 Project Overview

This project analyzes **customer churn** using Python, Pandas, Seaborn, Matplotlib, and a SQLite database.

The analysis works with customer information, subscription details, and customer support data to understand customer behavior and identify factors associated with churn.

The project focuses on **data extraction, data cleaning, preprocessing, exploratory data analysis, and visualization**.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## 🎯 Objectives

* Extract customer data from a SQLite database.
* Explore and understand different database tables.
* Clean and preprocess customer and subscription data.
* Handle missing values and inconsistent data.
* Standardize categorical values such as gender.
* Convert date columns into appropriate datetime formats.
* Analyze subscription and cancellation information.
* Explore customer support and satisfaction data.
* Understand factors related to customer churn.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## 🗄️ Database

The project uses a SQLite database:

```text
customer_churn.db
```

The database contains three main tables:

### db_customer

Contains customer information such as:

* Customer ID
* Customer Name
* Country
* State
* Gender
* Date of Birth
* Interests
* Pincode

### db_subscription

Contains subscription-related information:

* Customer ID
* Subscription Start Date
* Subscription Type
* Renewal Date
* Plan Type
* Contract Type
* Cancellation Date
* Cancellation Reason
* Monthly Charges
* CLTV
* Churn Score

### db_support

Contains customer support information:

* Customer ID
* Complaint Date
* Escalations
* CSAT Score
* Comments

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## 🛠️ Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **SQLite**
* **Jupyter Notebook**

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## 🔄 Data Analysis Process

### 1. Database Connection

The project connects to the SQLite database using Python's `sqlite3` library.

```python
conn = sqlite3.connect('customer_churn.db')
```

The database tables are identified using SQL and loaded into Pandas DataFrames.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### 2. Data Exploration

The project examines:

* Table names
* Column names
* Data types
* Number of records
* Missing values
* Customer and subscription information

For example:

```python
df_db_customer.info()
df_db_subscription.info()
```

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### 3. Customer Data Cleaning

The customer table is cleaned by:

* Renaming `name` to `customer_name`
* Removing `interests` and `pincode`
* Converting `dob` to datetime
* Handling missing country values
* Standardizing gender values

For example:

```python
df_db_customer.rename(
    columns={'name': 'customer_name'},
    inplace=True
)
```

Gender values such as:

```text
Men → Male
Women → Female
```

are standardized for consistent analysis.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### 4. Subscription Data Preprocessing

Subscription date columns are converted from object/string format to datetime:

```python
df_db_subscription['subscription_start_date'] = \
    pd.to_datetime(df_db_subscription['subscription_start_date'])

df_db_subscription['cancellation_date'] = \
    pd.to_datetime(df_db_subscription['cancellation_date'])
```

This allows the dates to be used effectively for further analysis.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## 📈 Analysis Areas

The project explores customer churn through different aspects of the available data, including:

* Customer demographics
* Customer location
* Gender
* Subscription information
* Contract type
* Plan type
* Monthly charges
* Customer lifetime value (CLTV)
* Churn score
* Cancellation dates
* Cancellation reasons
* Customer complaints
* Escalations
* Customer satisfaction (CSAT)

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## 🔍 Key Data Analysis Concepts Demonstrated

This project demonstrates practical skills in:

* SQL database connection
* SQL queries
* Pandas DataFrames
* Data extraction
* Data cleaning
* Missing value handling
* Data type conversion
* Date/time manipulation
* Column renaming
* Column removal
* Data standardization
* Exploratory Data Analysis (EDA)
* Data visualization
* Customer churn analysis

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## 📂 Project Structure

```text
Churn-Analysis/
│
├── churn_analysis (1).ipynb
├── customer_churn.db
└── README.md
```

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## 🚀 How to Run

### 1. Clone the repository

```bash
git clone <your-repository-url>
```

### 2. Navigate to the project

```bash
cd Churn-Analysis
```

### 3. Install required libraries

```bash
pip install pandas numpy matplotlib seaborn
```

### 4. Open the notebook

```bash
jupyter notebook
```

Open:

```text
churn_analysis (1).ipynb
```

Make sure `customer_churn.db` is located in the same project directory.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## 🔮 Future Improvements

The project can be extended by:

* Creating a complete churn dashboard using **Power BI**
* Calculating overall churn rate
* Performing deeper churn segmentation
* Analyzing churn by contract and plan type
* Studying the relationship between monthly charges and churn
* Analyzing customer satisfaction and churn
* Creating customer retention recommendations
* Building a machine learning model to predict customer churn

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## 👨‍💻 Author

**Dev Joshi**

B.Tech – Computer Science Engineering

**Skills:** Python | Pandas | NumPy | SQL | Data Analysis | Data Visualization
