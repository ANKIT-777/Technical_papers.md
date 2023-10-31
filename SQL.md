# SQL->>>

**SQL** is a powerful language for managing and working with data in relational databases. It is widely used in web applications, business intelligence, data analysis, and more.

1. **Relational Databases**:
   - SQL is used with relational databases that organize data into structured tables.
   - Example:
     ```sql
     CREATE TABLE Employees (
         ID INT PRIMARY KEY,
         Name VARCHAR(50),
         Salary DECIMAL(10, 2)
     );
     ```

2. **Data Definition Language (DDL)**:
   - DDL commands create, modify, and delete database structures.
   - Example:
     ```sql
     CREATE TABLE Products (ID INT, Name VARCHAR(50));
     ALTER TABLE Products ADD COLUMN Price DECIMAL(10, 2);
     DROP TABLE Products;
     ```

3. **Data Manipulation Language (DML)**:
   - DML commands manipulate data within tables.
   - Example:
     ```sql
     INSERT INTO Employees (ID, Name, Salary) VALUES (1, 'John', 50000);
     UPDATE Employees SET Salary = 55000 WHERE ID = 1;
     DELETE FROM Employees WHERE ID = 1;
     ```

4. **Data Querying**:
   - The `SELECT` statement retrieves data from tables.
   - Example:
     ```sql
     SELECT Name, Salary FROM Employees WHERE Salary > 50000;
     ```

5. **Join Operations**:
   - SQL supports joining data from multiple tables.
   - Example:
     ```sql
     SELECT Orders.OrderID, Customers.CustomerName
     FROM Orders
     INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID;
     ```

6. **Constraints**:
   - Constraints enforce rules on data integrity.
   - Example:
     ```sql
     CREATE TABLE Students (
         ID INT PRIMARY KEY,
         Name VARCHAR(50) NOT NULL,
         Age INT CHECK (Age >= 18),
         CourseID INT REFERENCES Courses(CourseID)
     );
     ```

7. **Transactions**:
   - Transactions ensure data consistency and integrity.
   - Example:
     ```sql
     BEGIN;
     UPDATE Account SET Balance = Balance - 100 WHERE AccountID = 123;
     UPDATE Account SET Balance = Balance + 100 WHERE AccountID = 456;
     COMMIT;
     ```

8. **Views**:
   - Views are saved queries that act like virtual tables.
   - Example:
     ```sql
     CREATE VIEW HighSalaryEmployees AS
     SELECT Name, Salary FROM Employees WHERE Salary > 60000;
     ```

9. **Stored Procedures and Functions**:
   - Stored procedures and functions are reusable SQL code blocks.
   - Example:
     ```sql
     CREATE PROCEDURE sp_GetEmployeeName(IN empID INT)
     BEGIN
         SELECT Name FROM Employees WHERE ID = empID;
     END;
     ```

10. **Indexing**:
    - Indexes enhance query performance.
    - Example:
      ```sql
      CREATE INDEX idx_EmployeeName ON Employees(Name);
      ```



