
# 🛒 Walmart Data Analysis

> **Exploratory data analysis and business insights from Walmart sales data using Python, Pandas, NumPy, Matplotlib, and Seaborn.**

---

## 📌 Overview

**Walmart Data Analysis** is a data analytics project focused on exploring and understanding Walmart sales data.

The project uses **Python-based data analysis and visualization techniques** to transform raw sales data into meaningful business insights.

The analysis covers:

* 📊 Sales performance
* 🏪 Branch and city analysis
* 🛍️ Product/category performance
* 💰 Profitability
* 💳 Payment method analysis
* ⭐ Customer ratings
* 📅 Time-based sales trends
* 📈 Data visualization
* 🔎 Exploratory Data Analysis (EDA)

---

## 🎯 Objectives

The main objectives of this project are to:

* Understand Walmart sales data
* Clean and preprocess raw data
* Perform exploratory data analysis
* Identify sales and profitability patterns
* Analyze product categories
* Compare branches and cities
* Study payment methods
* Analyze customer ratings
* Discover time-based sales trends
* Present insights through effective visualizations

---

## 🛠️ Technologies Used

| Technology          | Purpose                      |
| ------------------- | ---------------------------- |
| 🐍 Python           | Data analysis                |
| 🐼 Pandas           | Data manipulation            |
| 🔢 NumPy            | Numerical operations         |
| 📊 Matplotlib       | Data visualization           |
| 🎨 Seaborn          | Statistical visualization    |
| 📓 Jupyter Notebook | Analysis and experimentation |

---

## 📂 Dataset

The dataset contains retail transaction information that can be used to analyze Walmart sales performance.

### Important Columns

| Column           | Description                                   |
| ---------------- | --------------------------------------------- |
| `Branch`         | Store/branch identifier                       |
| `City`           | City where the branch operates                |
| `Category`       | Product category                              |
| `Unit Price`     | Price of a single unit                        |
| `Quantity`       | Number of units sold                          |
| `Rating`         | Customer rating                               |
| `Payment Method` | Payment method used                           |
| `Profit Margin`  | Profit margin associated with the transaction |
| `Total Sales`    | Total transaction sales                       |

> Column names may vary depending on the dataset version.

---

# 🔄 Data Analysis Workflow

```text
Raw Walmart Dataset
        │
        ▼
Data Loading
        │
        ▼
Data Cleaning
        │
        ▼
Data Preprocessing
        │
        ▼
Exploratory Data Analysis
        │
        ▼
Statistical Analysis
        │
        ▼
Data Visualization
        │
        ▼
Business Insights
```

---

# 🧹 Data Cleaning

The dataset is prepared before analysis by checking and handling common data-quality issues.

### Check Dataset

```python
import pandas as pd

df = pd.read_csv("walmart_sales.csv")

print(df.head())
print(df.info())
print(df.shape)
```

### Check Missing Values

```python
print(df.isnull().sum())
```

### Check Duplicate Records

```python
print(df.duplicated().sum())
```

### Remove Duplicates

```python
df = df.drop_duplicates()
```

---

# 🔎 Exploratory Data Analysis

EDA is performed to understand the structure and behavior of the Walmart sales data.

### Basic Statistics

```python
print(df.describe())
```

This helps understand:

* Average values
* Minimum and maximum values
* Standard deviation
* Distribution of numerical variables

---

# 🛍️ Product Category Analysis

Product categories can be analyzed to understand their contribution to overall sales.

```python
category_sales = (
    df.groupby("Category")["Total Sales"]
    .sum()
    .sort_values(ascending=False)
)

print(category_sales)
```

This analysis helps identify categories with higher or lower sales contributions.

---

# 🏪 Branch Analysis

Branch-level analysis helps compare sales performance between different Walmart locations.

```python
branch_sales = (
    df.groupby("Branch")["Total Sales"]
    .sum()
    .sort_values(ascending=False)
)

print(branch_sales)
```

### Visualization

```python
import seaborn as sns
import matplotlib.pyplot as plt

sns.barplot(
    data=df,
    x="Branch",
    y="Total Sales"
)

plt.title("Sales by Branch")
plt.show()
```

---

# 🌆 City Analysis

Sales can also be analyzed according to city.

```python
city_sales = (
    df.groupby("City")["Total Sales"]
    .sum()
    .sort_values(ascending=False)
)

print(city_sales)
```

This provides a city-level view of business performance.

---

# 💳 Payment Method Analysis

The project analyzes how customers complete their purchases.

```python
payment_analysis = (
    df.groupby("Payment Method")["Total Sales"]
    .sum()
    .sort_values(ascending=False)
)

print(payment_analysis)
```

A visualization can be created using:

```python
sns.countplot(
    data=df,
    x="Payment Method"
)

plt.title("Payment Method Usage")
plt.xticks(rotation=45)
plt.show()
```

---

# ⭐ Customer Rating Analysis

Customer ratings can be analyzed to understand customer feedback patterns.

```python
average_rating = df["Rating"].mean()

print("Average Rating:", average_rating)
```

Ratings can also be compared across categories:

```python
category_rating = (
    df.groupby("Category")["Rating"]
    .mean()
    .sort_values(ascending=False)
)

print(category_rating)
```

---

# 💰 Profitability Analysis

Profit-related fields can be analyzed to understand business profitability.

```python
profit_analysis = (
    df.groupby("Category")["Profit Margin"]
    .mean()
    .sort_values(ascending=False)
)

print(profit_analysis)
```

This can help identify categories with different profit-margin patterns.

---

# 📅 Time-Based Analysis

If the dataset contains transaction dates or timestamps, time-based features can be created.

```python
df["Date"] = pd.to_datetime(df["Date"])

df["Month"] = df["Date"].dt.month
df["Day"] = df["Date"].dt.day
df["Day_Name"] = df["Date"].dt.day_name()
```

### Monthly Sales

```python
monthly_sales = (
    df.groupby("Month")["Total Sales"]
    .sum()
)

print(monthly_sales)
```

### Sales Trend

```python
monthly_sales.plot(
    kind="line",
    marker="o"
)

plt.title("Monthly Sales Trend")
plt.xlabel("Month")
plt.ylabel("Total Sales")
plt.show()
```

---

# 📊 Visualizations

The project uses multiple visualization techniques to communicate insights effectively.

### Bar Chart

Used for comparing categories, branches, cities, and payment methods.

### Line Chart

Used for analyzing sales trends over time.

### Scatter Plot

Used to understand relationships between numerical variables.

### Box Plot

Used to identify distributions and potential outliers.

### Heatmap

Used to examine correlations between numerical variables.

Example:

```python
plt.figure(figsize=(10, 6))

sns.heatmap(
    df.corr(numeric_only=True),
    annot=True,
    cmap="coolwarm"
)

plt.title("Correlation Heatmap")
plt.show()
```

---

# 📈 Key Business Questions

This analysis can answer questions such as:

* Which product categories generate the most sales?
* Which branches contribute more to total sales?
* How does sales performance vary by city?
* Which payment methods are commonly used?
* What is the average customer rating?
* How do ratings vary across categories?
* Which categories have different profit-margin patterns?
* How do sales change over time?
* Which variables are strongly correlated with sales?
* Are there unusual values or potential outliers?

---

# 📊 Example KPI Analysis

Important KPIs can be calculated using Pandas.

### Total Sales

```python
total_sales = df["Total Sales"].sum()
print("Total Sales:", total_sales)
```

### Total Quantity Sold

```python
total_quantity = df["Quantity"].sum()
print("Total Quantity:", total_quantity)
```

### Average Rating

```python
avg_rating = df["Rating"].mean()
print("Average Rating:", avg_rating)
```

### Number of Transactions

```python
transactions = len(df)
print("Transactions:", transactions)
```

---

# 📁 Project Structure

```text
Walmart-Data-Analysis/
│
├── 📄 README.md
├── 📊 walmart_sales.csv
├── 📓 Walmart_Data_Analysis.ipynb
│
├── 📁 images/
│   ├── sales_analysis.png
│   ├── category_analysis.png
│   └── correlation_heatmap.png
│
└── 📄 requirements.txt
```

---

# ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/nodanbhatia/Walmart-Sales-Intelligence-System.git
```

Navigate to the project:

```bash
cd Walmart-Sales-Intelligence-System
```

Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

---

# ▶️ Run the Analysis

Start Jupyter Notebook:

```bash
jupyter notebook
```

Then open:

```text
Walmart_Data_Analysis.ipynb
```

Run the notebook cells sequentially to reproduce the analysis.

---

# 📚 Concepts Covered

This project demonstrates practical knowledge of:

* Python
* Pandas
* NumPy
* Data Cleaning
* Data Preprocessing
* Exploratory Data Analysis
* GroupBy
* Aggregation
* Statistical Analysis
* Correlation Analysis
* Outlier Analysis
* Data Visualization
* Business Analytics
* Time-Series Analysis

---

# 💼 Skills Demonstrated

### Data Analysis

* Data cleaning
* Data transformation
* EDA
* Statistical analysis
* KPI analysis

### Data Visualization

* Matplotlib
* Seaborn
* Distribution plots
* Comparison charts
* Trend analysis
* Correlation heatmaps

### Business Analysis

* Sales analysis
* Product analysis
* Branch analysis
* Customer analysis
* Payment analysis
* Profitability analysis

---

# 🔮 Future Improvements

Future versions of this project can include:

* 📊 Interactive Streamlit dashboard
* 🤖 Sales prediction using Machine Learning
* 🔮 Sales forecasting
* 📈 Demand prediction
* 👥 Customer segmentation
* 🏪 Advanced branch performance analysis
* 📍 Geographic sales visualization
* 📥 Automated report generation
* ☁️ Dashboard deployment

---

# 🎓 Learning Outcomes

By completing this project, I strengthened my ability to:

* Work with real-world retail datasets
* Clean and preprocess business data
* Perform exploratory data analysis
* Extract meaningful patterns from data
* Create professional visualizations
* Calculate business KPIs
* Analyze sales and profitability
* Communicate data-driven insights

---

# 👨‍💻 Author

## Nodan Bhatia

**BTech CSE — Data Science**

### Areas of Interest

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

This project is intended for **educational, analytical, and portfolio purposes**. The conclusions obtained from the analysis depend on the dataset and its quality.
