
# ☕ Starbucks Coffee Sales Dashboard

> **Interactive sales analytics dashboard for exploring Starbucks coffee shop performance, sales trends, product insights, and key business KPIs.**

---

## 📌 Overview

**Starbuck Coffee Dashboard** is a data analytics and visualization project designed to analyze coffee shop sales data and transform raw business data into meaningful insights through an interactive dashboard.

The project focuses on understanding:

* 📊 Overall sales performance
* ☕ Product and category performance
* 📅 Sales trends over time
* 🏪 Store/location performance
* 💰 Revenue and transaction analysis
* 📈 Customer purchasing patterns
* 🔎 Business KPIs and trends

The dashboard helps users explore sales data interactively instead of relying only on static reports.

---

## 🎯 Project Objectives

The main objectives of this project are to:

* Analyze Starbucks coffee sales data
* Identify high-performing products and categories
* Understand sales trends across different time periods
* Analyze store or location-level performance
* Create meaningful business KPIs
* Build interactive visualizations
* Convert raw data into actionable business insights
* Practice real-world data analysis and dashboard development

---

## 🚀 Key Features

### 📊 Sales Overview

Provides an overall view of business performance using important KPIs such as:

* Total Sales
* Total Orders/Transactions
* Average Order Value
* Total Quantity Sold
* Product Performance

### ☕ Product Analysis

Analyze products based on:

* Product category
* Product type
* Quantity sold
* Revenue generated
* Product popularity

### 📅 Time-Based Analysis

Explore sales patterns based on:

* Daily sales
* Monthly sales
* Weekly trends
* Day-of-week performance
* Hourly sales patterns

### 🏪 Store/Location Analysis

Compare business performance across different stores or locations using:

* Total sales
* Number of transactions
* Product demand
* Revenue contribution

### 📈 Interactive Visualizations

The dashboard can include visualizations such as:

* Bar charts
* Line charts
* Pie/Donut charts
* KPI cards
* Tables
* Trend charts
* Category comparisons

---

## 🔄 Data Analysis Workflow

```text
Raw Starbucks Dataset
        │
        ▼
Data Loading
        │
        ▼
Data Cleaning
        │
        ▼
Data Transformation
        │
        ▼
Exploratory Data Analysis
        │
        ▼
KPI Calculation
        │
        ▼
Data Visualization
        │
        ▼
Interactive Dashboard
        │
        ▼
Business Insights
```

---

## 🛠️ Technologies Used

| Technology                     | Purpose                      |
| ------------------------------ | ---------------------------- |
| 🐍 Python                      | Data analysis and processing |
| 🐼 Pandas                      | Data manipulation            |
| 🔢 NumPy                       | Numerical operations         |
| 📊 Matplotlib                  | Data visualization           |
| 🎨 Seaborn                     | Statistical visualization    |
| 📈 Plotly                      | Interactive charts           |
| 🖥️ Streamlit / Dashboard Tool | Interactive dashboard        |

---

## 🧹 Data Preparation

Before creating the dashboard, the dataset can be prepared through several steps:

### 1. Data Loading

```python
import pandas as pd

df = pd.read_csv("starbucks_sales.csv")
```

### 2. Inspect Dataset

```python
print(df.head())
print(df.info())
print(df.describe())
```

### 3. Check Missing Values

```python
print(df.isnull().sum())
```

### 4. Remove Duplicates

```python
df = df.drop_duplicates()
```

### 5. Convert Date Columns

```python
df["date"] = pd.to_datetime(df["date"])
```

---

## 📊 Important KPIs

The dashboard can calculate important business metrics such as:

### Total Sales

```text
Total Sales = Sum of Sales
```

### Total Quantity

```text
Total Quantity = Sum of Quantity Sold
```

### Total Transactions

```text
Total Transactions = Count of Transactions
```

### Average Order Value

```text
Average Order Value =
Total Sales / Total Transactions
```

These KPIs provide a quick overview of overall business performance.

---

## 📈 Example Analysis

### Monthly Sales Trend

```python
monthly_sales = (
    df.groupby(df["date"].dt.to_period("M"))["sales"]
    .sum()
)

print(monthly_sales)
```

### Product Performance

```python
product_sales = (
    df.groupby("product")["sales"]
    .sum()
    .sort_values(ascending=False)
)

print(product_sales)
```

### Category Analysis

```python
category_sales = (
    df.groupby("category")["sales"]
    .sum()
    .sort_values(ascending=False)
)

print(category_sales)
```

---

## 📊 Visualization Example

```python
import seaborn as sns
import matplotlib.pyplot as plt

sns.barplot(
    data=df,
    x="category",
    y="sales"
)

plt.title("Sales by Category")
plt.xticks(rotation=45)
plt.show()
```

---

## 🖥️ Dashboard Structure

A possible dashboard structure:

```text
Starbucks Coffee Dashboard
│
├── 📊 Overview
│   ├── Total Sales
│   ├── Total Orders
│   ├── Total Quantity
│   └── Average Order Value
│
├── ☕ Product Analysis
│   ├── Product Sales
│   ├── Product Quantity
│   └── Category Performance
│
├── 📅 Time Analysis
│   ├── Daily Sales
│   ├── Monthly Sales
│   ├── Weekly Sales
│   └── Hourly Sales
│
├── 🏪 Store Analysis
│   ├── Store Performance
│   └── Location Comparison
│
└── 🔎 Insights
    ├── Top Products
    ├── Sales Trends
    └── Business KPIs
```

---

## 📁 Suggested Project Structure

```text
Starbuck_Coffee_Dashboard/
│
├── 📄 README.md
├── 📊 starbucks_sales.csv
├── 🐍 app.py
├── 📓 analysis.ipynb
├── 📁 data/
│   └── starbucks_sales.csv
│
├── 📁 images/
│   └── dashboard.png
│
└── 📁 requirements.txt
```

---

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/nodanbhatia/Starbuck_Coffee_Dashboard.git
```

Move into the project directory:

```bash
cd Starbuck_Coffee_Dashboard
```

Install required libraries:

```bash
pip install pandas numpy matplotlib seaborn plotly streamlit
```

---

## ▶️ Run the Dashboard

If the dashboard is built using Streamlit:

```bash
streamlit run app.py
```

The application will open in your browser.

---

## 🔍 Business Questions Answered

This dashboard can help answer questions such as:

* Which products generate the most sales?
* Which product categories perform best?
* How do sales change over time?
* Which days have higher sales?
* What are the busiest selling hours?
* Which stores or locations generate more revenue?
* Which products have lower demand?
* What is the average transaction value?
* How does product demand vary across different periods?

---

## 📚 Data Analytics Concepts Demonstrated

This project demonstrates practical knowledge of:

* Data Cleaning
* Data Preprocessing
* Exploratory Data Analysis
* GroupBy Operations
* Aggregation
* Feature Creation
* KPI Development
* Time-Series Analysis
* Data Visualization
* Business Analytics
* Interactive Dashboard Development

---

## 💡 Skills Demonstrated

### Technical Skills

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Plotly
* Streamlit
* Exploratory Data Analysis
* Data Visualization

### Analytical Skills

* Business KPI analysis
* Sales trend analysis
* Product performance analysis
* Time-based analysis
* Data-driven decision support

---

## 🔮 Future Improvements

Possible future improvements include:

* 🤖 Add sales forecasting using Machine Learning
* 📈 Add demand prediction
* 🔮 Implement time-series forecasting
* 🧠 Add customer segmentation
* 📊 Add advanced KPI filtering
* 🗺️ Add geographic visualization
* 🔐 Add dashboard authentication
* ☁️ Deploy the dashboard online
* 📱 Improve mobile responsiveness
* 📥 Add CSV/Excel export functionality

---

## 🎓 Learning Outcomes

Through this project, I practiced how to:

* Work with real-world business datasets
* Clean and transform raw data
* Perform exploratory data analysis
* Create meaningful KPIs
* Analyze sales trends
* Build interactive visualizations
* Design an analytics dashboard
* Communicate data-driven business insights

---

## 👨‍💻 Author

### Nodan Bhatia

**BTech CSE — Data Science**

Interested in:

* 🤖 Artificial Intelligence
* 🧠 Machine Learning
* 📊 Data Science
* 📈 Data Analytics
* 🔥 Generative AI
* ⚡ Agentic AI

---

## ⭐ Support

If you find this project useful, consider giving the repository a ⭐ on GitHub.

---

## 📌 Disclaimer

This project is created for **educational and portfolio purposes**. Business insights depend on the dataset used and should be interpreted within the context of the available data.
