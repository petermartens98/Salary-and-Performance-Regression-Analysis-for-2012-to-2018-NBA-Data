
# 🏀 NBA Salary & Performance Regression Analysis (2012–2018)

This repository contains a complete Python-based statistical analysis of **NBA team salaries and on-court performance** from **2012 to 2018**.

Using regression modeling, data visualization, and exploratory data analysis (EDA), this project examines whether higher payrolls lead to better winning percentages—and how factors such as previous-season performance and team identity influence outcomes.

---

## 📦 Project Overview

This study uses publicly available NBA salary and team performance data to:

### ✔ Evaluate

* Total team salaries
* Relative salaries within each season
* Team winning percentage (WPC)

### ✔ Model

* Relationship between **relative salary → win percentage**
* Impact of **lagged win percentage (previous year)**
* Differences across **individual teams**

### ✔ Visualize

* Regression plots
* Joint hexbin relationships
* Pairplots
* Salary and WPC distributions

---

## 📚 Technologies Used

This analysis was built entirely in **Python**, leveraging the following tools:

### 🐍 Core Python Libraries

* **pandas** – data cleaning, transformation, and merging
* **numpy** – numerical operations
* **matplotlib** & **seaborn** – statistical visualization and regression plots
* **statsmodels** – OLS regression modeling & statistical inference

### 🔍 Data Analysis Features

* Multi-season data merging
* Groupby aggregation (seasonal totals)
* Feature engineering (relative salary, lagged performance)
* Team fixed-effects modeling
* Multicollinearity diagnostics

---

## 📁 Data Preparation

Steps performed:

1. **Load data** from Excel (`12to18 NBA pay and performance.xlsx`)
2. Compute **season-level total salary**
3. Calculate each team’s **relative salary share** (`relsal`)
4. Insert **previous season’s winning percentage** (`wpc_lag`)
5. Join all features into a unified DataFrame

---

## 📊 Regression Models

### 📌 Model 1 – Salary Only

<img width="550" height="330" alt="image" src="https://github.com/user-attachments/assets/5bf70914-3ace-4291-860a-fd6231c8face" />


**wpc ~ relsal**

* R² = **0.172**
* Significant positive relationship between salary share and wins

---

### 📌 Model 2 – Salary + Previous Season

<img width="479" height="310" alt="image" src="https://github.com/user-attachments/assets/40f2da49-a4b7-487d-8dba-6a4b8e8fbc81" />

**wpc ~ relsal + wpc_lag**

* R² = **0.416**
* Adding `wpc_lag` greatly improves model fit
* Salary effect becomes statistically insignificant

---

### 📌 Model 3 – Salary + Lag + Team Fixed Effects

<img width="611" height="762" alt="image" src="https://github.com/user-attachments/assets/89c2aa13-9520-4631-8ed1-8d80e46f48e4" />

**wpc ~ relsal + wpc_lag + C(Team)**

* R² = **0.585**
* Team identity explains major additional variation
* Salary regains significance
* Some teams systematically outperform expectations (e.g., Spurs, Warriors)

---

## 📈 Visualizations

The notebook generates:

* **Regression plots** for salary vs win percentage
  <img width="722" height="474" alt="image" src="https://github.com/user-attachments/assets/10e13b2b-9517-49d1-bef4-2857b3b0e227" />

* **Joint hexbin plot** for density regions
  <img width="776" height="762" alt="image" src="https://github.com/user-attachments/assets/4561f2bc-3ce8-424f-9c7f-26c407ea84f7" />

* **Pairplots** for multi-variable relationships
  <img width="934" height="916" alt="image" src="https://github.com/user-attachments/assets/ca6c128e-b3e3-437f-9c6f-d7a84421f75a" />

These plots provide clear insights into league-wide patterns and the influence of spending.

---


## 🏁 Summary

This project shows that:

🏀 **Spending matters—but not as much as performance history or team identity.**
📈 Salary alone explains a small portion of team success.
📘 Adding lagged performance dramatically improves predictive accuracy.
🏆 Team culture, coaching, development, and consistency still dominate results.
