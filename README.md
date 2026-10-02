# 📊 Data Analysis & Visualization

<p align="center">
  <img src="https://img.shields.io/badge/Data%20Analysis-Python-blue?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white" />
  <img src="https://img.shields.io/badge/NumPy-Numerical%20Computing-013243?style=for-the-badge&logo=numpy&logoColor=white" />
  <img src="https://img.shields.io/badge/Matplotlib-Visualization-orange?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Seaborn-Statistical%20Visualization-4C72B0?style=for-the-badge" />
</p>

<p align="center">
  <b>🐍 Python • 🐼 Pandas • 🔢 NumPy • 📈 Matplotlib • 🎨 Seaborn</b>
</p>

---

## 🌟 Overview

The **Data_Analysis** folder contains practical examples and projects focused on **data analysis and visualization using Python**.

The main objective is to understand how raw datasets can be:

```text
📂 Collected
   ↓
🧹 Cleaned
   ↓
🔍 Explored
   ↓
📊 Analyzed
   ↓
📈 Visualized
   ↓
💡 Converted into Insights
```

This folder demonstrates fundamental Data Science techniques using popular Python libraries.

---

# 🎯 Objectives

The key objectives of this folder are:

* Understand real-world datasets
* Perform data cleaning
* Handle missing values
* Explore data distributions
* Perform statistical analysis
* Identify relationships between variables
* Create meaningful visualizations
* Extract useful insights from data
* Build a strong foundation for Machine Learning

---

# 🛠️ Technologies Used

| Technology          | Purpose                        |
| ------------------- | ------------------------------ |
| 🐍 Python           | Core programming               |
| 🐼 Pandas           | Data manipulation and analysis |
| 🔢 NumPy            | Numerical operations           |
| 📈 Matplotlib       | Data visualization             |
| 🎨 Seaborn          | Statistical visualization      |
| 📓 Jupyter Notebook | Interactive analysis           |

---

# 🐼 Pandas

**Pandas** is used for working with structured datasets.

Common operations include:

* Reading datasets
* DataFrame creation
* Selecting columns
* Filtering rows
* Sorting data
* Handling missing values
* Grouping data
* Aggregation
* Merging datasets

### Example

```python
import pandas as pd

df = pd.read_csv("data.csv")

print(df.head())
print(df.info())
print(df.describe())
```

---

# 🔢 NumPy

**NumPy** is used for numerical computing and array-based operations.

Common operations include:

* Arrays
* Mathematical calculations
* Statistical calculations
* Numerical transformations
* Random data generation

### Example

```python
import numpy as np

numbers = np.array([10, 20, 30, 40, 50])

print("Mean:", np.mean(numbers))
print("Maximum:", np.max(numbers))
print("Minimum:", np.min(numbers))
```

---

# 📈 Matplotlib

**Matplotlib** is used to create customizable visualizations.

The projects can include:

* 📊 Bar charts
* 📈 Line charts
* 🥧 Pie charts
* 📉 Histograms
* 🔵 Scatter plots
* 📦 Box plots

### Example

```python
import matplotlib.pyplot as plt

plt.plot(df["Sales"])

plt.title("Sales Trend")
plt.xlabel("Index")
plt.ylabel("Sales")

plt.show()
```

---

# 🎨 Seaborn

**Seaborn** is a statistical visualization library built on top of Matplotlib.

It is useful for:

* Distribution analysis
* Correlation analysis
* Categorical analysis
* Statistical visualization
* Heatmaps

### Example

```python
import seaborn as sns
import matplotlib.pyplot as plt

sns.histplot(df["Sales"], kde=True)

plt.title("Sales Distribution")
plt.show()
```

---

# 🔍 Exploratory Data Analysis

Exploratory Data Analysis (**EDA**) is used to understand the structure and characteristics of a dataset.

Typical EDA workflow:

```text
Dataset
   ↓
Shape
   ↓
Columns
   ↓
Data Types
   ↓
Missing Values
   ↓
Duplicates
   ↓
Statistics
   ↓
Distributions
   ↓
Relationships
   ↓
Insights
```

---

# 🧹 Data Cleaning

The projects demonstrate common data-cleaning operations.

### Missing Values

```python
df.isnull().sum()
```

Fill missing values:

```python
df["Age"] = df["Age"].fillna(df["Age"].mean())
```

### Remove Duplicates

```python
df = df.drop_duplicates()
```

### Rename Columns

```python
df.rename(
    columns={"old_name": "new_name"},
    inplace=True
)
```

---

# 📊 Statistical Analysis

Basic statistical analysis can be performed using Pandas and NumPy.

```python
print(df.describe())
```

Important statistics include:

* Mean
* Median
* Standard deviation
* Minimum
* Maximum
* Quartiles
* Variance

---

# 📈 Visualization Techniques

## 📊 Bar Chart

Used to compare categories.

```python
df.groupby("Category")["Sales"].sum().plot(
    kind="bar"
)

plt.title("Sales by Category")
plt.show()
```

---

## 📈 Line Chart

Used to identify trends over time.

```python
plt.plot(df["Date"], df["Sales"])

plt.title("Sales Trend")
plt.xlabel("Date")
plt.ylabel("Sales")

plt.show()
```

---

## 🥧 Pie Chart

Used to visualize proportions.

```python
df["Category"].value_counts().plot(
    kind="pie",
    autopct="%1.1f%%"
)

plt.title("Category Distribution")
plt.ylabel("")

plt.show()
```

---

## 🔵 Scatter Plot

Used to understand relationships between numerical variables.

```python
sns.scatterplot(
    data=df,
    x="Quantity",
    y="Sales"
)

plt.title("Quantity vs Sales")
plt.show()
```

---

## 📦 Box Plot

Useful for understanding distributions and potential outliers.

```python
sns.boxplot(
    data=df,
    x="Category",
    y="Sales"
)

plt.xticks(rotation=45)
plt.show()
```

---

## 🔥 Correlation Heatmap

Used to identify relationships between numerical variables.

```python
correlation = df.corr(numeric_only=True)

sns.heatmap(
    correlation,
    annot=True
)

plt.title("Correlation Heatmap")
plt.show()
```

---

# 📂 Folder Structure

```text
Data_Analysis/
│
├── 📁 datasets/
│   └── data.csv
│
├── 📁 notebooks/
│   ├── data_analysis.ipynb
│   └── visualization.ipynb
│
├── 📁 visualizations/
│   ├── bar_chart.png
│   ├── line_chart.png
│   ├── histogram.png
│   └── heatmap.png
│
├── 📄 analysis.py
└── 📄 README.md
```

> Update the filenames and folders according to the actual contents of your repository.

---

# 🔄 Complete Data Analysis Workflow

```text
                 📂 RAW DATA
                     │
                     ▼
              🐼 Load Dataset
                     │
                     ▼
              🔍 Understand Data
                     │
                     ▼
              🧹 Clean Data
                     │
                     ▼
             📊 Exploratory Analysis
                     │
                     ▼
              📐 Statistical Analysis
                     │
                     ▼
              📈 Visualization
                     │
                     ▼
               🔎 Find Patterns
                     │
                     ▼
                💡 Insights
```

---

# 🧪 Example Complete Analysis

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Load dataset
df = pd.read_csv("data.csv")

# Display first records
print(df.head())

# Dataset information
print(df.info())

# Statistical summary
print(df.describe())

# Missing values
print(df.isnull().sum())

# Remove duplicates
df = df.drop_duplicates()

# Numerical correlation
correlation = df.corr(numeric_only=True)

# Heatmap
sns.heatmap(correlation, annot=True)

plt.title("Correlation Heatmap")
plt.show()
```

---

# 📚 Concepts Covered

### 🐍 Python

* Variables
* Data types
* Lists
* Dictionaries
* Functions
* Loops
* Conditional statements

### 🐼 Pandas

* Series
* DataFrames
* CSV handling
* Filtering
* Sorting
* GroupBy
* Aggregation
* Missing values
* Duplicate handling

### 🔢 NumPy

* Arrays
* Mathematical operations
* Statistics
* Array manipulation

### 📈 Visualization

* Line plots
* Bar charts
* Histograms
* Pie charts
* Scatter plots
* Box plots
* Heatmaps

---

# 🎯 Skills Demonstrated

```text
🐍 Python
   +
🐼 Pandas
   +
🔢 NumPy
   +
📊 Exploratory Data Analysis
   +
📈 Data Visualization
   +
🎨 Statistical Visualization
   =
💡 Data Analysis Skills
```

---

# 🔮 Future Improvements

This folder can be expanded with:

* 📊 More real-world datasets
* 📈 Advanced statistical analysis
* 📉 Time-series analysis
* 🧹 Advanced data-cleaning techniques
* 🤖 Machine Learning projects
* 📊 Interactive Plotly dashboards
* 🚀 Streamlit applications
* 📈 Business Intelligence projects

---

# 📚 Learning Outcomes

By working through these projects, you can develop practical knowledge of:

* Data preprocessing
* Exploratory Data Analysis
* Statistical analysis
* Data visualization
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Finding patterns in datasets
* Communicating data insights

---

# 👨‍💻 Author

## Nodan Bhatia

🎓 **BTech CSE — Data Science**

💡 **Data Science | Machine Learning | AI | NLP | Agentic AI**

<p align="center">

<a href="https://github.com/nodanbhatia">
<img src="https://img.shields.io/badge/GitHub-Nodan%20Bhatia-black?style=for-the-badge&logo=github" />
</a>

<a href="https://www.linkedin.com/in/nodan-bhatia-888951424/">
<img src="https://img.shields.io/badge/LinkedIn-Nodan%20Bhatia-blue?style=for-the-badge&logo=linkedin" />
</a>

</p>

---

# ⭐ Support

If you find this repository useful:

⭐ **Star the repository**

🍴 **Fork the repository**

📢 **Share the project**

---

<p align="center">
  <b>📊 Turning Raw Data into Meaningful Insights 🚀</b>
</p>
