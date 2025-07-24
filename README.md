# Market-Basket-Analysis
# 🛒 Market Basket Analysis System

A simple market basket analysis project combining Python (Tkinter front-end) with MySQL back-end for transaction data storage. This project performs association rule mining on purchase transactions to find useful item co-occurrence patterns—ideal for billing systems or retail analytics.

---

## 📌 Features

- GUI-based billing interface using Python (Tkinter)
- SQL-based item and transaction data management
- Customer billing with dynamic transaction records
- Association rule mining using Apriori or FP-Growth (add-on)
- Item suggestion based on market basket logic

---

## 🧱 Tech Stack

| Layer        | Technology    |
|-------------|----------------|
| Front-End   | Python (Tkinter) |
| Back-End    | MySQL Database  |
| Optional    | Python libraries: `pandas`, `mlxtend`, `matplotlib` (for MBA) |

---

## 🗃️ Database Schema

Four key tables:

- **`bills`**: Stores bill ID, customer name, contact number, and bill date.
- **`items`**: Catalog of items with name and price.
- **`transaction`**: Links items to bills with quantity.
- **`login`**: Simple login table for user authentication.

```sql
CREATE TABLE bills (
  bill_id INT AUTO_INCREMENT PRIMARY KEY,
  name CHAR(30),
  phone CHAR(15),
  bill_date DATE
);

CREATE TABLE items (
  id INT AUTO_INCREMENT PRIMARY KEY,
  item_name CHAR(30),
  price FLOAT(8,2)
);

CREATE TABLE login (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name CHAR(30),
  pwd CHAR(30)
);

CREATE TABLE transaction (
  id INT AUTO_INCREMENT PRIMARY KEY,
  item_id INT,
  qty INT,
  bill_id INT
);
