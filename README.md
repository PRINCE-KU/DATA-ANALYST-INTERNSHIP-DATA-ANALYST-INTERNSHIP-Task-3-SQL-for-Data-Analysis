# DATA-ANALYST-INTERNSHIP-DATA-ANALYST-INTERNSHIP-Task-3-SQL-for-Data-Analysis
# 📊 Task 3 – SQL for Data Analysis

## 🎯 Objective
The goal of this task is to perform data analysis using SQL queries on an eCommerce dataset. This helps in understanding how to query structured data and derive business insights using relational databases.

---

## 📁 Dataset Used
I used the **Olist Brazilian E-Commerce Public Dataset** from Kaggle, which contains real transaction data of customers, products, sellers, and orders.

### 📦 Tables in the dataset:
- `customers.csv` – Customer ID, location, and region
- `orders.csv` – Order ID, status, purchase & delivery timestamps
- `order_items.csv` – Product-level order details with prices
- `products.csv` – Product IDs and categories
- `payments.csv` – Payment methods, installments, and amounts
- `sellers.csv` – Seller ID and location
- `geolocation.csv` – (Optional) Zip code and lat/long info

---

## 🧰 Tools Used
- **Database:** MySQL (You can use SQLite or PostgreSQL)
- **IDE:** MySQL Workbench / DBeaver
- **Dataset Format:** CSV

---

## 🔧 Steps Performed

### 1️⃣ Table Creation
Created tables for each CSV file using `CREATE TABLE` statements. Data types were chosen carefully to match the actual data format (e.g., VARCHAR, INT, DECIMAL, DATETIME).

### 2️⃣ Data Import
Imported all `.csv` files into the respective tables using DBeaver's import wizard or MySQL's `LOAD DATA` command.

### 3️⃣ Query Writing
Wrote SQL queries using:
- `SELECT`, `WHERE`, `ORDER BY`, `GROUP BY`
- Aggregate functions: `SUM`, `AVG`, `COUNT`
- Joins between multiple tables
- Subqueries
- Views for better analysis

---

## 📊 Sample SQL Queries Included

| # | Description |
|---|-------------|
| 1 | Total number of orders per order status |
| 2 | Top 5 most sold products |
| 3 | Total revenue per seller |
| 4 | Average payment value per order |
| 5 | Most popular payment methods |
| 6 | Create a view to join customer and product info |
| 7 | Subquery to find high-value orders |

> 📸 All outputs of these queries are saved as screenshots in the `screenshots/` folder.

---

## 📂 Folder Structure

✅ STEP 2: Create Tables in SQL
🔨 1. Use this SQL to create all 7 tables:
-- customers
CREATE TABLE customers (
    customer_id VARCHAR(50) PRIMARY KEY,
    customer_unique_id VARCHAR(50),
    customer_zip_code_prefix INT,
    customer_city VARCHAR(100),
    customer_state VARCHAR(5)
);

-- orders
CREATE TABLE orders (
    order_id VARCHAR(50) PRIMARY KEY,
    customer_id VARCHAR(50),
    order_status VARCHAR(50),
    order_purchase_timestamp DATETIME,
    order_delivered_customer_date DATETIME
);

-- order_items
CREATE TABLE order_items (
    order_id VARCHAR(50),
    order_item_id INT,
    product_id VARCHAR(50),
    seller_id VARCHAR(50),
    shipping_limit_date DATETIME,
    price DECIMAL(10,2),
    freight_value DECIMAL(10,2)
);

-- payments
CREATE TABLE payments (
    order_id VARCHAR(50),
    payment_sequential INT,
    payment_type VARCHAR(50),
    payment_installments INT,
    payment_value DECIMAL(10,2)
);

-- products
CREATE TABLE products (
    product_id VARCHAR(50) PRIMARY KEY,
    product_category_name VARCHAR(100)
);

-- sellers
CREATE TABLE sellers (
    seller_id VARCHAR(50) PRIMARY KEY,
    seller_zip_code_prefix INT,
    seller_city VARCHAR(100),
    seller_state VARCHAR(5)
);

-- geolocation (optional)
CREATE TABLE geolocation (
    geolocation_zip_code_prefix INT,
    geolocation_lat FLOAT,
    geolocation_lng FLOAT,
    geolocation_city VARCHAR(100),
    geolocation_state VARCHAR(5)
);

![Screenshot (311)](https://github.com/user-attachments/assets/49840a8d-11ae-447a-b2a3-238a84eb4c21)
![Screenshot (312)](https://github.com/user-attachments/assets/ed2ba476-631d-4e8e-ad0a-51ed77e6cc9c)
![Screenshot (313)](https://github.com/user-attachments/assets/e0f30ce9-43c4-4c68-9ec7-f0a4b425fb03)


🔍 1. Total Orders by Status
![Screenshot (314)](https://github.com/user-attachments/assets/cac59f4f-059d-43b4-850b-d8bee3ea3113)
💰 2. Total Revenue per Product
![Screenshot (315)](https://github.com/user-attachments/assets/91ad9342-e9fe-4b7f-85fb-828ddafe75bd)

👨‍💻 3. Orders per Customer

![Screenshot (316)](https://github.com/user-attachments/assets/27f8195e-22e2-4f66-bf1e-8f2a8316fafe)
📦 4. Top 5 Most Sold Products
![Screenshot (317)](https://github.com/user-attachments/assets/cf2b8cc6-3d28-4f2d-827f-1ed8eebb9ac3)
🧾 5. Payment Method Usage
![Screenshot (318)](https://github.com/user-attachments/assets/9f6f2256-707e-455b-ad1d-851fca8c583c)

📊 6. Revenue Per Seller (JOIN)
![Screenshot (319)](https://github.com/user-attachments/assets/12c02c5b-ad5c-4273-8d1a-a2670a79ca6b)
 7. Create a View for Customer Purchases
 

![Screenshot (321)](https://github.com/user-attachments/assets/e0e228c8-9a64-4cee-a2a2-200ef8f58855)
![Screenshot (322)](https://github.com/user-attachments/assets/491941ab-bb2b-4dc5-b13f-3fd8030312b3)
