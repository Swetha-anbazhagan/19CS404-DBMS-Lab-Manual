# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
<img width="947" height="398" alt="image" src="https://github.com/user-attachments/assets/f8e16706-8fc6-468e-acd6-a4296535837b" />


```sql
CREATE TABLE Orders
(OrderID INTEGER,
OrderDate TEXT,
CustomerID INTEGER
);
```

**Output:**
<img width="998" height="238" alt="image" src="https://github.com/user-attachments/assets/66105713-169a-475e-be21-982486b2c1ba" />



**Question 2**
---
<img width="1156" height="195" alt="image" src="https://github.com/user-attachments/assets/7663293c-df7d-4d44-84c4-bafb0f8faf24" />




```sql
INSERT INTO Customers VALUES(301,'Michael Jordan','123 Maple St','Chicago',60616);
```

**Output:**
<img width="1246" height="182" alt="image" src="https://github.com/user-attachments/assets/44aef7b8-8c06-4839-941c-36370b11e1dd" />


**Question 3**
---
<img width="729" height="210" alt="image" src="https://github.com/user-attachments/assets/c96e6bbb-5997-40c6-8384-d19c378fd1a9" />


```sql
ALTER TABLE Student_details 
ADD COLUMN Mobilenumber number;
```

**Output:**

<img width="1087" height="263" alt="image" src="https://github.com/user-attachments/assets/830fb9bb-6c67-4b87-b7e7-f19631a9d3a4" />

**Question 4**
---
<img width="1090" height="335" alt="image" src="https://github.com/user-attachments/assets/83d1be43-ae20-4360-9439-03d2abc8bd7d" />


```sql
CREATE TABLE Employees(
EmployeeID INTEGER PRIMARY KEY,
FirstName TEXT  NOT NULL,
LastName TEXT NOT NULL,
Email TEXT UNIQUE,
Salary INTEGER CHECK(Salary>0),
DepartmentID INTEGER,
FOREIGN KEY (DepartmentID) REFERENCES Departments(DepartmentID)
);
```

**Output:**

<img width="1281" height="403" alt="image" src="https://github.com/user-attachments/assets/1341dca8-13af-4ac2-8e88-9ddc635caf79" />


**Question 5**
---
<img width="751" height="321" alt="image" src="https://github.com/user-attachments/assets/0a6a1e3f-cb6a-4565-88df-7ea4e9dfc721" />


```sql
CREATE TABLE Orders
(OrderID INTEGER,
OrderDate TEXT,
CustomerID INTEGER
);
```

**Output:**

<img width="1000" height="299" alt="image" src="https://github.com/user-attachments/assets/5eb03f5a-619d-4911-852e-6634764baa9f" />


**Question 6**
---
<img width="1265" height="416" alt="image" src="https://github.com/user-attachments/assets/4497b877-ecc1-43f2-8e6e-178fa2f2ee07" />


```sql
ALTER TABLE employee
ADD department_id INTEGER;
ALTER TABLE employee
ADD manager_id INTEGER DEFAULT NULL;
```

**Output:**

<img width="1085" height="249" alt="image" src="https://github.com/user-attachments/assets/380e0edf-7ecc-46f6-9679-96cde820b6fc" />

**Question 7**
---
<img width="730" height="345" alt="image" src="https://github.com/user-attachments/assets/d0a72efb-a0ae-4a0a-bfa2-48b66c62191c" />


```sql
INSERT INTO Employee (EmployeeID,Name,Position,Department,Salary)
VALUES (2,'John Smith','Developer','IT',75000),
(3,'Anna Bell','Designer','Marketing',68000);
```

**Output:**

<img width="916" height="285" alt="image" src="https://github.com/user-attachments/assets/ed68005f-453d-424f-a3c8-003ff384d13b" />


**Question 8**
---
<img width="1066" height="204" alt="image" src="https://github.com/user-attachments/assets/c7b8e2fa-5bfa-43a1-b83b-65865d8323c3" />


```sql
INSERT INTO Books VALUES('978-1234567890','Data Science Essentials','Jane Doe','TechBooks',2024);
```

**Output:**

<img width="1153" height="168" alt="image" src="https://github.com/user-attachments/assets/9d211485-e281-4ba8-bcd3-29dbd0836206" />


**Question 9**
---
<img width="889" height="343" alt="image" src="https://github.com/user-attachments/assets/f1d21f68-d8e6-424e-83de-310637e222bc" />


```sql
CREATE TABLE Tasks
(TaskID INTEGER,
TaskName TEXT,
DueDate DATE

);
```

**Output:**
<img width="1081" height="272" alt="image" src="https://github.com/user-attachments/assets/b174a258-1712-4859-9bb2-768ba4b5c3cc" />


**Question 10**
---
<img width="834" height="332" alt="image" src="https://github.com/user-attachments/assets/d20b6fad-43bc-4556-9d2c-20f3f6fc4576" />


```sql
CREATE TABLE Locations
(LocationID INTEGER,
LocationName TEXT,
Address TEXT

);
```

**Output:**

<img width="1119" height="296" alt="image" src="https://github.com/user-attachments/assets/827f2660-b47b-4c46-8aa1-a6c69b1b74d3" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
