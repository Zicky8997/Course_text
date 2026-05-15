```mysql
-- Create Customer Table
CREATE TABLE Customer (
    Customer_id VARCHAR(20) PRIMARY KEY,
    Customer_Name VARCHAR(20) NOT NULL,
    Customer_Tel INT
);

-- Create Product Table
CREATE TABLE Product (
    Product_id VARCHAR(20) PRIMARY KEY,
    Product_Name VARCHAR(20) NOT NULL,
    Price DECIMAL(10, 2) CHECK (Price > 0)
);

-- Create Orders Table
CREATE TABLE Orders (
    Customer_id VARCHAR(20),
    Product_id VARCHAR(20),
    Quantity INT,
    Total_amount DECIMAL(10, 2),
    CONSTRAINT fk_customer FOREIGN KEY (Customer_id) REFERENCES Customer(Customer_id),
    CONSTRAINT fk_product FOREIGN KEY (Product_id) REFERENCES Product(Product_id)
);
-- Add a column Category (VARCHAR2(20)) to the PRODUCT table.
ALTER TABLE Product 
ADD Category VARCHAR(20);

-- Add a column OrderDate (DATE)  to the ORDERS table which have SYSDATE as a default value.
ALTER TABLE Orders 
ADD OrderDate DATE DEFAULT (CURRENT_DATE);
```
