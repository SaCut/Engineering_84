# SQL_Mini_Project
A small project written in SQL on the Sparta Northwind Database

USE Northwind


## EXERCISE 1 

#### 1.1 Write a query that lists all Customers in either Paris or London. Include Customer ID, Company Name and all address fields.
```SQL
SELECT
    ContactName,
    CustomerID,
    CompanyName,
    City,
    Address,
    PostalCode,
    Country
    FROM Customers
    WHERE City IN ('Paris', 'London');
```


#### 1.2 List all products stored in bottles. 
```SQL
SELECT
    ProductName
    FROM Products
    WHERE CHARINDEX('bottle', QuantityPerUnit) != 0;
```


#### 1.3 Repeat question above, but add in the Supplier Name and Country. 
```SQL
SELECT
    pr.ProductID,
    pr.ProductName,
    sp.CompanyName,
    sp.Country
FROM Products pr
FULL JOIN Suppliers sp
    ON pr.SupplierID = sp.SupplierID
WHERE QuantityPerUnit LIKE '%bottle%';
```


#### 1.4 Write an SQL Statement that shows how many products there are in each category. Include Category Name in result set and list the highest number first. 
```SQL
SELECT
    c.CategoryName,
    COUNT(p.ProductID)
        AS "Products in category"
FROM Products p 
INNER JOIN Categories c
    ON p.CategoryID = c.CategoryID
GROUP BY c.CategoryName 
ORDER BY [Products In Category] DESC;
```


#### 1.5 List all UK employees using concatenation to join their title of courtesy, first name and last name together. Also include their city of residence. 
```SQL
SELECT
    CONCAT(TitleOfCourtesy, ' ', FirstName, ' ', LastName),
    City
FROM Employees
WHERE Country LIKE '%UK%';
```


#### 1.6 List Sales Totals for all Sales Regions (via the Territories table using 4 joins) with a Sales Total greater than 1,000,000. Use rounding or FORMAT to present the numbers.
```SQL
SELECT
    r.RegionDescription,
    FORMAT(SUM(od.UnitPrice*od.Quantity-(od.UnitPrice*od.Discount)), '$#,###,###.##')
        AS "Total"
    FROM [Order Details] od
    INNER JOIN Orders o ON od.OrderID = o.OrderID
    INNER JOIN [EmployeeTerritories] e ON o.EmployeeID = e.EmployeeID
    INNER JOIN Territories t ON e.TerritoryID = t.TerritoryID
    INNER JOIN Region r ON t.RegionID = r.RegionID
    GROUP BY r.RegionDescription
        HAVING SUM(od.UnitPrice*od.Quantity-(od.UnitPrice*od.Discount)) >= 1000000
    ORDER BY [Total] DESC;
```


#### 1.7 Count how many Orders have a Freight amount greater than 100.00 and either USA or UK as Ship Country.
```SQL
SELECT
    COUNT(OrderID)
        AS "Order over 100"
FROM Orders
WHERE
    Freight > 100.00
    AND ShipCountry IN ('USA', 'UK');
```


#### 1.8 Write an SQL Statement to identify the Order Number of the Order with the highest amount(value) of discount applied to that order.
```SQL
SELECT TOP 1
    OrderID,
    FORMAT(ROUND(UnitPrice*Quantity*Discount), '$#,###,###.##')
        AS "Higest Discount Value"
FROM [Order Details]
GROUP BY OrderID
ORDER BY SUM(UnitPrice*Quantity*Discount) DESC;
```


## EXERCISE 2 

#### 2.1 Write the correct SQL statement to create the following table: 
Spartans Table – include details about all the Spartans on this course. Separate Title, First Name and Last Name into separate columns, and include University attended, course taken and mark achieved. Add any other columns you feel would be appropriate.  
``` SQL
CREATE TABLE spartan_table
(
    spartan_id INT IDENTITY(1,1) PRIMARY KEY,
    first_name VARCHAR(20),
    middle_name VARCHAR(20),
    last_name VARCHAR(20),
    university_attended VARCHAR(30),
    course_name VARCHAR(30),
    mark_achieved CHAR(3),
    sparta_course VARCHAR(20)
);
```


#### 2.2 Write SQL statements to add the details of the Spartans in your course to the table you have created.
```SQL
INSERT INTO spartan_table
    (first_name,    middle_name,    last_name,  university_attended,    course_name,    mark_achieved,  sparta_course)
VALUES
    ('Alice', 'Laura', 'Smith', 'Goldsmith University', 'Computer Science', '100', 'Engineering 82'),
    ('Bob', 'Jay', 'Stevenson', 'Royal College of Arts', 'Origami', '60', 'Engineering 84'),
    ('Charlie', '', 'Brown', 'Kingston University', 'Software Engineering', '1st', 'BA');
```


## EXERCISE 3 

#### 3.1 List all Employees from the Employees table and who they report to. No Excel required. Please mention the Employee Names and the Report To names.
```SQL
SELECT
    CONCAT(r.FirstName, ' ', r.LastName)
        AS "Employee Name",
    CONCAT(e.FirstName, ' ', e.LastName)
        AS "Reports To"
FROM Employees e
RIGHT JOIN Employees r
    ON e.EmployeeID = r.ReportsTo
```


#### 3.2 List all Suppliers with total sales over $10,000 in the Order Details table. Include the Company Name from the Suppliers Table and present as a bar chart as below
```SQL
SELECT
    DISTINCT s.SupplierID,
    S.CompanyName,
    SUM((od.UnitPrice*od.Quantity)-(od.UnitPrice*od.Discount))
        AS "Total Sales"
FROM Suppliers s
INNER JOIN Products p
    ON s.SupplierID = p.SupplierID
INNER JOIN [Order Details] od
    ON p.ProductID = od.ProductID
GROUP BY s.SupplierID, s.CompanyName
HAVING SUM((od.UnitPrice*od.Quantity)-(od.UnitPrice*od.Discount)) > 10000
ORDER BY "Total Sales";
```
![alt text](https://imgur.com/EHarzWv.png)


#### 3.3 List the Top 10 Customers YTD for the latest year in the Orders file. Based on total value of orders shipped. No Excel required.
```SQL
SELECT TOP 10
    c.CustomerID
        AS "Customer ID",
    c.CompanyName
        AS "Company",
    FORMAT(SUM(UnitPrice * Quantity * (1-Discount)), 'C')
        AS "YearToDate Sales"
FROM Customers c
INNER JOIN Orders o
    ON o.CustomerID=c.CustomerID
INNER JOIN [Order Details] od
    ON od.OrderID=o.OrderID
WHERE YEAR(OrderDate) = (SELECT MAX(YEAR(OrderDate)) From Orders)
AND o.ShippedDate IS NOT NULL
GROUP BY c.CustomerID, c.CompanyName
ORDER BY SUM(UnitPrice * Quantity * (1-Discount)) DESC;
```


#### 3.4 Plot the Average Ship Time by month for all data in the Orders Table using a line chart as below.
```SQL
SELECT 
    CONCAT(YEAR(o.OrderDate),'/',MONTH(o.OrderDate))
        AS "Year-Month",
    AVG(DATEDIFF(d, o.OrderDate,o.ShippedDate))
        AS "Average Ship Time"
    FROM Orders o 
    GROUP BY YEAR(o.OrderDate), MONTH(o.OrderDate)
    ORDER BY YEAR(o.OrderDate), MONTH(o.OrderDate);
```
![alt text](https://imgur.com/adgskM1.png)
