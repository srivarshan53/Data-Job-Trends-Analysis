
---

# 📊 Data Science Job Market Analysis Dashboard

This project provides a comprehensive analysis of the data science job market using job postings data. The analysis focuses on **job roles**, **company profiles**, **skills demand**, and **salary insights**, presented through an interactive Power BI dashboard.

---

## 🔧 Technologies & Tools Used

* **Python** (Pandas, NumPy, Regex) for data cleaning and feature engineering
* **Power BI** for interactive dashboard creation
* **Jupyter Notebook** for exploratory data analysis
* **Data Sources**: Glassdoor job postings dataset from Kaggle

---

## 📂 Project Highlights

### 🧹 Data Cleaning & Feature Engineering (Python)

Performed in `Glassdoor.ipynb`, this step involved:

* Standardizing job role names (e.g., converting variations like "sr data scientist" → "Senior Data Scientist")
* Extracting consistent role titles using regex
* Dropping intermediate columns post-transformation
* Creating derived columns like `Company Age Category` and skill binary indicators (e.g., `Python`, `SQL`, `Machine Learning`)
* Handling location parsing by removing suffixes (e.g., `, NY`)
* Calculating average salaries

<details>
<summary>Sample Code Snippet</summary>

```python
df1['Job Role'] = df1['Job Role'].str.replace(r'sr data scientist','Senior Data Scientist', case=False, regex=True)
df1['Extracted'] = df1['Job Role'].str.extract(r'(Senior Data Scientist|Data Scientist|Associate Data Scientist|Principal Data Scientist)')
df1['Job Role1'] = df1['Extracted'].combine_first(df1['Job Role'])
df1.drop(['Extracted','Job Role1'], axis=1, inplace=True)
```

</details>

---

## 📈 Dashboard Overview

### 💼 Job Market Insights

* **Most in-demand role**: `Data Scientist`
* **Top hiring city**: `San Francisco`
* **Company size trends**: Most roles are from companies with 51–200 employees
* **Ownership**: 70% of jobs are from private organizations

### 🔧 Skill Demand Analysis

* **Most in-demand skill**: `Python`
* **Senior roles demand**: `Machine Learning`, `SQL`, `Deep Learning`
* **Visualization tools** (Power BI, Tableau) are more relevant for analyst roles

### 🏢 Company Profile Trends

* **Company age categories**:

  * Growing: Most job postings
  * Legacy: Significant presence
  * Emerging: Niche demand with high-tech requirements
* **Ownership vs Salary**: Public companies offer the highest average salaries
* **Skill specialization in startups**: Emerging companies prioritize Deep Learning and ML

### 💰 Salary & Rating Insights

* **Highest paying roles**: Managerial roles in Data Science/Analytics
* **Senior vs Junior roles**: Senior roles have significantly higher pay
* **Skill combinations**: Deep Learning + ML commands top salary brackets

---

## 📌 Key Performance Indicators (KPIs)

* Average, Maximum, and Minimum Salary
* Job Count by Title, City, and Company Size
* Skill Usage Frequency
* Ownership Type Distribution
* Company Age Category Distribution


## 🏁 Conclusion

This project showcases:

* End-to-end **data analysis workflow**
* Proficiency in **data cleaning & feature engineering** with Python
* **Interactive data storytelling** using Power BI
* Insight generation based on real-world job market trends

---

## 📎 Repository Contents

* `Glassdoor.ipynb`: Data cleaning and preparation
* `PowerBI Dashboard`: Visual insights and storytelling
* `README.md`: Project overview
