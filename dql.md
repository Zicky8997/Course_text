```mysql
-- 1. Display all customer data
SELECT * FROM Customer;

-- 2. Display product_name and category for products with prices between 5000 and 10000
SELECT product_name, category 
FROM Product 
WHERE Price BETWEEN 5000 AND 10000;

-- 3. Display all product data sorted by price in descending order
SELECT * FROM Product 
ORDER BY Price DESC;

-- 4. Display the total number of orders, average amount, highest amount, and lowest amount
SELECT 
    COUNT(*) AS Total_Orders, 
    AVG(total_amount) AS Average_Amount, 
    MAX(total_amount) AS Highest_Amount, 
    MIN(total_amount) AS Lowest_Amount 
FROM Orders
GROUP BY Product_id;

-- 5. Display the customer_id of customers who have placed more than 2 orders
SELECT Customer_id 
FROM Orders 
GROUP BY Customer_id 
HAVING COUNT(*) > 2;

-- 6. For each month of the year 2020, display the number of orders
SELECT MONTH(OrderDate) AS Order_Month, COUNT(*) AS Number_of_Orders 
FROM Orders 
WHERE YEAR(OrderDate) = 2020 
GROUP BY MONTH(OrderDate);

-- 7. For each order, display the product name, customer name, and order date
SELECT p.product_name, c.customer_Name, o.OrderDate 
FROM Orders AS o
JOIN Product AS p ON o.Product_id = p.Product_id
JOIN Customer AS c ON o.Customer_id = c.Customer_id;

-- 8. Display all orders placed exactly three months ago
SELECT * FROM Orders 
WHERE MONTH(OrderDate) = MONTH(CURRENT_DATE - INTERVAL 3 MONTH)
  AND YEAR(OrderDate) = YEAR(CURRENT_DATE - INTERVAL 3 MONTH);

-- 9. Display customers (customer_id) who have never ordered a product
SELECT Customer_id 
FROM Customer 
WHERE Customer_id NOT IN (SELECT DISTINCT Customer_id FROM Orders);
```
