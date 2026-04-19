# 🛒 Retail Sales Data Cleaning & Preprocessing (Dirty Dataset)

## 📌 Project Overview

This project focuses on cleaning and preprocessing a **real-world dirty retail sales dataset**.
The dataset contains inconsistencies such as mixed data types, categorical variations, and potential data quality issues.

The goal is to transform raw transactional data into a **clean, structured, and machine learning-ready dataset** using an industry-standard preprocessing pipeline.

---

## 🎯 Objectives

* Clean and standardize dirty data
* Handle missing and inconsistent values
* Detect and analyze outliers
* Perform feature engineering for business insights
* Encode categorical variables for ML models
* Scale numerical features for better model performance

---

## 📂 Dataset Information

The dataset contains:

* 🧾 Transaction Details: Transaction ID, Customer ID
* 🛍️ Product Info: Category, Item
* 💰 Pricing: Price Per Unit, Quantity, Total Spent
* 💳 Payment Info: Payment Method
* 📍 Location Data
* 🎁 Discount Information

---

## ⚙️ Project Workflow

---

### 🔰 Step 0: Data Extraction

* Extracted dataset from ZIP file using Python `zipfile`

---

### 📥 Step 1: Data Loading

* Loaded dataset into pandas DataFrame
* Verified:

  * Shape
  * Column names
  * Sample records

---

### 🔍 Step 2: Data Inspection

* Used:

  * `df.info()`
  * `df.describe()`
  * `df.isnull().sum()`
* Identified:

  * Mixed data types
  * Categorical columns
  * Potential inconsistencies

---

### 🧹 Step 3: Data Cleaning

* Cleaned **Discount Applied** column:

  * Standardized values (Yes/No → 1/0)
* Checked and corrected inconsistencies in numeric columns
* Ensured proper formatting

---

### 🔁 Step 4: Removing Duplicates

* Detected duplicate records using `df.duplicated()`
* Removed duplicates to ensure accurate analysis

---

### 🔄 Step 5: Data Type Verification

* Verified numeric columns:

  * Price Per Unit
  * Quantity
  * Total Spent
* Confirmed dataset structure for further processing

---

### 📊 Step 6: Outlier Detection

* Applied **IQR method** to detect outliers
* Visualized using boxplots
* Decision:

  * Retained outliers as they represent real purchasing behavior (bulk buying)

---

### 🧠 Step 7: Feature Engineering

Created new business-driven features:

* **Calculated_Total**

  * Validates transaction consistency

* **Discount_Impact**

  * Measures effect of discounts on revenue

* **High_Value**

  * Identifies high-spending customers

* **Purchase_Size**

  * Categorizes purchases (Small, Medium, Large, Bulk)

* **Avg_Price**

  * Average price per transaction

---

### 🔢 Step 8: Encoding

* Label Encoding:

  * Purchase_Size (ordered category)

* One Hot Encoding:

  * Category
  * Item
  * Payment Method
  * Location

* Avoided dummy variable trap using `drop_first=True`

---

### 📏 Step 9: Feature Scaling

* Applied **StandardScaler** on:

  * Price Per Unit
  * Quantity
  * Total Spent
  * Avg_Price
  * Calculated_Total

* Ensured:

  * Mean ≈ 0
  * Standard deviation ≈ 1

---

### ✅ Step 10: Final Dataset

* Verified:

  * No missing values
  * No duplicates
  * Fully numeric dataset

* Saved clean dataset:

  ```
  clean_sales_data.csv
  ```

---

## 📊 Key Insights

* Customer spending behavior varies significantly
* Bulk purchases contribute to high outliers
* Discounts directly impact revenue patterns
* Majority of purchases fall under small to medium categories
* Certain categories and locations dominate sales

---

## ⏱️ Time Series Analysis

* This dataset **does not contain a Date/Time column**
* Therefore, time series analysis is not applicable

👉 However, if a Date column were present:

* Trend analysis (daily/monthly sales)
* Seasonal patterns
* Forecasting models could be applied

---

## 🛠️ Technologies Used

* Python 🐍
* Pandas
* NumPy
* Matplotlib
* Scikit-learn

---

## 🚀 Future Work

* Build **Sales Prediction Model**
* Perform advanced EDA (customer segmentation)
* Create dashboard (Power BI / Tableau)
* Add time-based features if data is extended

---

## 💡 Interview-Ready Summary

This project demonstrates a complete **data preprocessing pipeline**, including:

* Data cleaning (handling dirty values)
* Duplicate removal
* Outlier detection
* Feature engineering (business insights)
* Encoding and scaling
* Preparing ML-ready dataset

---

## 👨‍💻 Author

**Satish**
Computer Science Student | DSCE Bangalore
Aspiring Data Scientist

---

## ⭐ Support

If you found this project useful, give it a ⭐ on GitHub and share your feedback!
