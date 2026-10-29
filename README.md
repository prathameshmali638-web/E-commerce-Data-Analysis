# E-commerce Data Analysis

A Python-based exploratory data analysis project focused on understanding online shopping data, identifying customer and sales patterns, and transforming raw e-commerce records into actionable insights.

**Tools:** Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook

---

## Project Overview

Online shops collect a lot of data every day: who is buying, what they are buying, how they pay and how fast the orders reach the customer. This project studies an e-commerce dataset to answer one simple question:

**How are customers, sales and products performing?**

The data is spread across 6 files and has missing values, just like real life. The project follows these steps: load, clean, fix missing values, explore and find insights, using only basic Python tools.

---

## Project Objectives

- Clean the raw e-commerce data
- Fix the missing values
- Explore the data using simple charts
- Find what drives customers and sales
- Share insights that anyone can understand

---

## Skills and Tools Used

**Tools**

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

**Skills**

- Data Cleaning and Preprocessing
- Missing Value Treatment
- Exploratory Data Analysis (EDA)
- Data Visualization
- Business Analytics

---

## Dataset Information

The original data is kept inside the `data` folder as 6 CSV files (each file is under 25 MB):

- **customers** - customer city and state
- **orders** - order dates and status
- **order_items** - products in each order, price and freight
- **products** - product category and details
- **sellers** - seller information
- **payments** - payment type, value and installments

---

## Project Workflow

**1. Load and understand the data**
- Read all 6 files using Pandas
- Checked the shape, data types and missing values

**2. Clean the data**
- Fixed a column name (`product category` to `product_category`)
- Made category names clean and in the same format
- Changed date columns to proper date format
- Checked every table for duplicate rows (none found)

**3. Fix missing values**

Missing values were found in two tables:

- orders: 4,908 missing values (approval and delivery dates)
- products: 2,448 missing values (category, size, weight, description)

How they were treated:

- Product category: filled with `"unknown"`
- Product numbers (weight, size, photos): filled with the median
- Approval date: filled with the purchase date
- Delivery dates: kept empty on purpose, because those orders were cancelled or not delivered yet. A new `is_delivered` column was added instead

**4. Join the tables**
- Joined orders, items, products and customers into one `sales` table
- Removed cancelled and unavailable orders from the sales analysis

**5. Explore with charts**
- Bar charts, line charts and a histogram

**6. Save cleaned data and reports**
- Saved the cleaned `orders` and `products` tables in the `data` folder (files ending with `_cleaned`)
- Saved the main results in a separate `reports` folder (5 CSV files and 5 charts)

---

## Questions and Answers

**Q: How many orders were placed in 2017 and 2018?**
A: 45,101 in 2017 and 54,011 in 2018.

**Q: Which state has the most customers?**
A: SP, with about 42% of all customers.

**Q: Which product category earns the most?**
A: Health and Beauty (about 9.3% of sales).

**Q: What are the other top categories?**
A: Watches and Gifts (8.9%) and Bed, Table and Bath (7.7%).

**Q: How many payments are in installments?**
A: About 49%.

**Q: Does a higher price mean more purchases?**
A: No, there is only a slight negative link (-0.11).

**Q: How did sales grow?**
A: Jan-Aug 2018 sales were about 138% higher than Jan-Aug 2017.

**Q: How fast are orders delivered?**
A: About 12 days on average (10 days median).

**Q: How many customers buy again?**
A: Only about 3%.

The notebook answers 12 questions in total, including top sellers and top customers.

---

## Key Insights

1. About 42% of customers live in one state (SP), so it is the biggest market
2. Health and Beauty, Watches and Gifts and Bed/Table/Bath are the top 3 categories
3. Credit card is the most used payment type, and about half of the payments are in installments
4. Price alone does not decide how often a product is bought
5. Sales grew strongly from 2017 to 2018
6. Only about 3% of customers buy more than once

---

## Business Recommendations

- **Sellers:** Focus on the top categories like health, beauty and gifts
- **Shops:** Keep the installment options, customers use them a lot
- **Marketing:** Use offers and reminders to bring customers back for a second order
- **Business:** Give extra attention to the SP state, it has the most customers

---

## Limitations

- Only basic analysis, no prediction model
- Data for 2016 and after August 2018 is very small, so those months are left out of the monthly charts
- Prices are not adjusted for inflation

---

## Files in this Project

```
E-commerce-Data-Analysis
|-- Ecommerce_Data_Analysis.ipynb
|-- README.md
|-- data
|   |-- customers.csv
|   |-- orders.csv
|   |-- order_items.csv
|   |-- products.csv
|   |-- sellers.csv
|   |-- payments.csv
|   |-- orders_cleaned.csv
|   `-- products_cleaned.csv
`-- reports
    |-- key_summary.csv
    |-- missing_values_report.csv
    |-- category_sales.csv
    |-- customers_by_state.csv
    |-- top_10_sellers.csv
    |-- top_categories.png
    |-- orders_per_month.png
    |-- customers_by_state.png
    |-- payment_types.png
    `-- delivery_days.png
```

---

## How to Run

1. Clone the project and install the libraries
   ```bash
   git clone https://github.com/your-username/E-commerce-Data-Analysis.git
   cd E-commerce-Data-Analysis
   pip install pandas numpy matplotlib seaborn jupyter
   ```
2. Open the notebook
   ```bash
   jupyter notebook Ecommerce_Data_Analysis.ipynb
   ```
3. Click Kernel, then Restart and Run All

No need to unzip anything or install any database, just run the notebook.

---

## Conclusion

This project turns raw e-commerce data with missing values into clean data and simple insights using only Python. It shows which categories earn the most, how customers pay, how fast orders arrive and how sales grow, which can help sellers and online shops make better decisions.
