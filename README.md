# pizza_sales--sql

# 🍕 Pizza Sales SQL Project

## 📖 Introduction
Hi! I'm **Adi Shettiar**, and this project involves analyzing a pizza sales dataset using **SQL (MySQL)**. The goal was to derive business insights such as sales trends, customer preferences, and product performance through structured queries and data analysis.

---

## 🧩 Objectives

This project explores a variety of business questions divided into three levels:

### 🔹 Basic
- Total number of orders placed
- Total revenue from pizza sales
- Highest-priced pizza
- Most common pizza size ordered
- Top 5 most ordered pizza types (by quantity)

### 🔸 Intermediate
- Total quantity of each pizza category ordered
- Distribution of orders by hour
- Category-wise pizza distribution
- Average pizzas ordered per day
- Top 3 pizza types by revenue

### 🔺 Advanced
- Revenue percentage by pizza type
- Cumulative revenue over time
- Top 3 revenue-generating pizzas per category

---

## 🗃️ Database Schema

The dataset contains the following tables:

| Table Name      | Description |
|------------------|-------------|
| `orders`         | Stores order ID, order date, and time |
| `order_details`  | Contains order details such as pizza and quantity |
| `pizzas`         | Contains pizza size and price information |
| `pizza_types`    | Contains pizza name and category |

---

## 🛠️ Technologies Used

- **MySQL** – Query writing and execution
- **Excel / CSV** – Data exploration
- **PowerPoint** – Visual presentation of results
- *(Optional)* Python or BI tools for future visualization

---

## 💡 Key Insights

- 📈 Peak order time: **6 PM to 8 PM**
- 🧀 Top-selling pizza: **Pepperoni**
- 💰 Highest revenue pizza: **Spicy Deluxe – $21.95**
- 🍕 Most common size: **Medium**
- 🧾 Approx. Revenue (Sample Output): **₹8+ Lakhs**

---

## 📎 Sample Query

```sql
SELECT pt.name, SUM(od.quantity * p.price) AS revenue
FROM order_details od
JOIN pizzas p ON od.pizza_id = p.pizza_id
JOIN pizza_types pt ON p.pizza_type_id = pt.pizza_type_id
GROUP BY pt.name
ORDER BY revenue DESC
LIMIT 3;
