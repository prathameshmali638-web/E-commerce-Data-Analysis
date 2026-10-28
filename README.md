# 🛒 E-commerce Data Analysis

A Python-based exploratory data analysis project focused on understanding online shopping data, identifying customer and sales patterns, and transforming raw e-commerce records into actionable insights.

<p align="center">
  <img src="https://img.shields.io/badge/🐍_Python-3776AB?style=for-the-badge" />
  <img src="https://img.shields.io/badge/🐼_Pandas-150458?style=for-the-badge" />
  <img src="https://img.shields.io/badge/🔢_NumPy-013243?style=for-the-badge" />
  <img src="https://img.shields.io/badge/📈_Matplotlib-11557C?style=for-the-badge" />
  <img src="https://img.shields.io/badge/🎨_Seaborn-2E8B57?style=for-the-badge" />
  <img src="https://img.shields.io/badge/📓_Jupyter-F37626?style=for-the-badge" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Project-E--commerce%20Analysis-8A2BE2?style=flat-square" />
  <img src="https://img.shields.io/badge/Level-Beginner%20Friendly-brightgreen?style=flat-square" />
  <img src="https://img.shields.io/badge/Status-Completed-success?style=flat-square" />
  <img src="https://img.shields.io/badge/Data-100K%2B%20Orders-orange?style=flat-square" />
</p>

---

## 📌 Project Overview

Online shops collect a lot of data every day: who is buying, what they are buying, how they pay and how fast the orders reach the customer. But what does all this data actually tell us? 🤔

This project studies an **e-commerce dataset** to answer one simple question:

> 🛍️ **How are customers, sales and products performing?**

The data is spread across 6 files and has missing values, just like real life. So the project shows the full journey: **load → clean → fix missing values → explore → find insights**, using only basic Python tools.

---

## 🎯 Project Objectives

- 🧹 Clean the raw e-commerce data
- 🩹 Fix the missing values
- 📊 Explore the data using simple charts
- 🔎 Find what drives customers and sales
- 💡 Share insights that anyone can understand

---

## 🧰 Skills & Tools Used

**🛠️ Tools**

- 🐍 Python
- 🐼 Pandas
- 🔢 NumPy
- 📈 Matplotlib
- 🎨 Seaborn
- 📓 Jupyter Notebook

**🧠 Skills**

- 🧹 Data Cleaning & Preprocessing
- 🩹 Missing Value Treatment
- 📊 Exploratory Data Analysis (EDA)
- 🎨 Data Visualization
- 💼 Business Analytics

---

## 📂 Dataset Information

The original data is kept inside the `data` folder as 6 CSV files (each file is under 25 MB):

- 👥 **customers** – customer city and state
- 📦 **orders** – order dates and status
- 🧾 **order_items** – products in each order, price and freight
- 🏷️ **products** – product category and details
- 🏪 **sellers** – seller information
- 💳 **payments** – payment type, value and installments

---

## 🔄 Project Workflow

### 1️⃣ Load & Understand the Data 📥
- Read all 6 files using Pandas
- Checked the shape, data types and missing values

### 2️⃣ Clean the Data 🧹
- Fixed a column name (`product category` → `product_category`)
- Made category names clean and in the same format
- Changed date columns to proper date format
- Checked every table for duplicate rows (none found)

### 3️⃣ Fix Missing Values 🩹

Missing values were found in two tables:

- 📦 **orders:** 4,908 missing values (approval and delivery dates)
- 🏷️ **products:** 2,448 missing values (category, size, weight, description)

How they were treated:

- 🔤 **Product category** → filled with `"unknown"`
- 🔢 **Product numbers** (weight, size, photos...) → filled with the **median**
- ✅ **Approval date** → filled with the purchase date
- 🚚 **Delivery dates** → kept empty on purpose, because those orders were cancelled or not delivered yet. A new `is_delivered` column was added instead

### 4️⃣ Join the Tables 🔗
- Joined orders, items, products and customers into one `sales` table
- Removed cancelled and unavailable orders from the sales analysis

### 5️⃣ Explore with Charts 📊
- Bar charts, line charts, histogram, scatter plot and a correlation heatmap

### 6️⃣ Save Cleaned Data & Reports 💾
- Saved the cleaned `orders` and `products` tables in the `data` folder (files ending with `_cleaned`)
- Saved the main results in a separate `reports` folder (5 CSV files and 4 charts)

---

## 🔍 Questions & Answers

| ❓ Question | ✅ Answer |
|---|---|
| How many orders were placed in 2017 and 2018? | 45,101 in 2017 and 54,011 in 2018 |
| Which state has the most customers? | SP, with about 42% of all customers |
| Which product category earns the most? | Health & Beauty (about 9.3% of sales) |
| What are the other top categories? | Watches & Gifts (8.9%) and Bed, Table & Bath (7.7%) |
| How many payments are in installments? | About 49% |
| Does a higher price mean more purchases? | No, there is only a slight negative link (-0.11) |
| How did sales grow? | Jan-Aug 2018 sales were about 138% higher than Jan-Aug 2017 |
| How fast are orders delivered? | About 12 days on average (10 days median) |
| How many customers buy again? | Only about 3% |

> 📓 The notebook answers 12 questions in total, including top sellers, top customers and the correlation heatmap.

---

## 💡 Key Insights

1. 🏙️ About 42% of customers live in one state (SP), so it is the biggest market
2. 🛍️ Health & Beauty, Watches & Gifts and Bed/Table/Bath are the top 3 categories
3. 💳 Credit card is the most used payment type, and about half of the payments are in installments
4. 💰 Price alone does not decide how often a product is bought
5. 📈 Sales grew strongly from 2017 to 2018
6. 🔁 Only about 3% of customers buy more than once

---

## 📈 Business Recommendations

- 🏷️ **Sellers:** Focus on the top categories like health, beauty and gifts
- 💳 **Shops:** Keep the installment options, customers use them a lot
- 🔁 **Marketing:** Use offers and reminders to bring customers back for a second order
- 🗺️ **Business:** Give extra attention to the SP state, it has the most customers

---

## ⚠️ Limitations

- 🔍 Only basic analysis, no prediction model
- 📅 Data for 2016 and after August 2018 is very small, so those months are left out of the monthly charts
- 💸 Prices are not adjusted for inflation

---

## 📁 Files in this Project

```
📦 E-commerce-Data-Analysis
 ┣ 📓 Ecommerce_Data_Analysis.ipynb
 ┣ 📂 data
 ┃  ┣ 📄 customers.csv
 ┃  ┣ 📄 orders.csv
 ┃  ┣ 📄 order_items.csv
 ┃  ┣ 📄 products.csv
 ┃  ┣ 📄 sellers.csv
 ┃  ┣ 📄 payments.csv
 ┃  ┣ 📄 orders_cleaned.csv
 ┃  ┗ 📄 products_cleaned.csv
 ┣ 📂 reports
 ┃  ┣ 📄 key_summary.csv
 ┃  ┣ 📄 missing_values_report.csv
 ┃  ┣ 📄 category_sales.csv
 ┃  ┣ 📄 customers_by_state.csv
 ┃  ┣ 📄 top_10_sellers.csv
 ┃  ┣ 🖼️ top_categories.png
 ┃  ┣ 🖼️ sales_growth.png
 ┃  ┣ 🖼️ orders_per_month.png
 ┃  ┗ 🖼️ customers_by_state.png
 ┗ 📘 README.md
```

---

## 🚀 How to Run

1. Clone the project and install the libraries 📦
   ```bash
   git clone https://github.com/your-username/E-commerce-Data-Analysis.git
   cd E-commerce-Data-Analysis
   pip install pandas numpy matplotlib seaborn jupyter
   ```
2. Open the notebook 📓
   ```bash
   jupyter notebook Ecommerce_Data_Analysis.ipynb
   ```
3. Click **Run All** ▶️

> 💡 No need to unzip anything or install any database, just run the notebook.

---

## ✅ Conclusion

This project turns raw e-commerce data with missing values into clean data and simple insights using only Python. It shows which categories earn the most, how customers pay, how fast orders arrive and how sales grow, which can help sellers and online shops make better decisions. 🛒

