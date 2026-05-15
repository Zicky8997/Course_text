```mysql
INSERT INTO Product (Product_id, Product_name, Category, Price)
VALUES 
('P01','Samsung Galaxy S20','Smartphone', 3299), 
('P02','Asus Notebook','PC',4599);

INSERT INTO Customer (Customer_id, Customer_name, Customer_tel)
VALUES 
('C01','ALI',71321009), 
('C02','ASMA', 77345823);

INSERT INTO Orders(Customer_id, Product_id, OrderDate, Quantity, Total_amount)
VALUES
('C01','P02', NULL, 2, 9198),
	('C02','P01',"28/05/2020",1,3299)
```
