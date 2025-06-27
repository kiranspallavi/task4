# 📊 Task 4 – Aggregate Functions and Grouping

This SQL script demonstrates the use of aggregate functions and grouping techniques on a bookstore database.

---

## 📁 File

- `task4_aggregate_queries_with_output.sql`:  
  Contains SQL queries with inline comments showing expected output.

---

## 🧪 Concepts Used

### ✅ Aggregate Functions
- `COUNT()` – To count rows (e.g., number of users, books).
- `SUM()` – To compute totals (e.g., revenue, stock).
- `AVG()` – To find average values (e.g., average book price).
- `ROUND()` – Used to round off average or sum values.

### ✅ Grouping
- `GROUP BY` – To group rows based on:
  - Authors (books per author)
  - Categories (books per category)
  - Orders (items or revenue per order)
  - Payment methods (average per method)

### ✅ Filtering Groups
- `HAVING` – To filter after aggregation, such as:
  - Authors who have written more than one book.

### ✅ Joins
- `JOIN` – To combine data from multiple tables.
- `LEFT JOIN` – To include authors with no books as well.

### ✅ Other SQL Features
- `IS NOT NULL` – To exclude null payment values.
- Column Aliasing (`AS`) – For readable column names in results.

---

## 🔧 Tables Involved

- `Users`
- `Authors`
- `Books`
- `Orders`
- `OrderItems`
- `Payments`
- `Categories`
- `BookCategories`

---

## ▶️ Example Queries

```sql
-- Total number of users
SELECT COUNT(*) FROM Users;

-- Average price of all books
SELECT ROUND(AVG(price), 2) FROM Books;

-- Total revenue per order
SELECT order_id, SUM(price * quantity) FROM OrderItems GROUP BY order_id;

-- Authors with more than 1 book
SELECT author_id, COUNT(*) FROM Books GROUP BY author_id HAVING COUNT(*) > 1;
