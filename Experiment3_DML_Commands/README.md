# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
<img width="788" height="486" alt="image" src="https://github.com/user-attachments/assets/b7c50a54-ab31-4d78-a132-dedbabf9a241" />


```sql
UPDATE products
SET sell_price=ROUND(sell_price*1.10,2)
WHERE supplier_id='6';
```

**Output:**

<img width="1283" height="496" alt="image" src="https://github.com/user-attachments/assets/748c3566-e6a3-4499-ba51-0f6898b97b4f" />


**Question 2**
---
<img width="797" height="548" alt="image" src="https://github.com/user-attachments/assets/a572858f-0dca-40ab-a110-845b0620f1ef" />


```sql
SELECT * FROM emp 
WHERE strftime('%Y',hiredate)='2022';
```

**Output:**

<img width="1291" height="365" alt="image" src="https://github.com/user-attachments/assets/74baceb4-3a90-42d6-b242-303ca8edca3e" />


**Question 3**
---
<img width="1289" height="502" alt="image" src="https://github.com/user-attachments/assets/38ad602b-a506-446c-acac-ce2901ba130b" />


```sql
ALTER TABLE Calculations
ADD COLUMN performance TEXT;
UPDATE Calculations
SET performance=CASE
    WHEN value2<30 THEN 'Poor'
    WHEN value2<=70 THEN 'Average'
    ELSE 'Excellent'
END;
SELECT id,value2,performance FROM Calculations
```

**Output:**

<img width="730" height="358" alt="image" src="https://github.com/user-attachments/assets/0ffc291a-3414-4d90-8d04-36fc3b7c27cc" />


**Question 4**
---
<img width="752" height="432" alt="image" src="https://github.com/user-attachments/assets/62832f3b-494e-49b8-ad8f-7cfc7f8ed1e0" />


```sql
SELECT order_no,order_date,purch_amt FROM orders
WHERE salesman_id='5001';
```

**Output:**

<img width="732" height="394" alt="image" src="https://github.com/user-attachments/assets/70ecd4d2-8fcc-4a80-a357-084b8e76d500" />


**Question 5**
---
<img width="1086" height="521" alt="image" src="https://github.com/user-attachments/assets/20b17dec-9c1e-4bf9-a833-6b03ba13d905" />


```sql
ALTER TABLE Products
ADD COLUMN discounted_price FLOAT;
UPDATE Products
SET discounted_price=original_price*(1-discount_percentage);

SELECT product_id,original_price,discount_percentage,discounted_price FROM Products
ORDER BY discount_percentage DESC LIMIT 3;
```

**Output:**

<img width="1132" height="276" alt="image" src="https://github.com/user-attachments/assets/e949c690-1637-44bd-a1dc-2c040b06eb23" />

**Question 6**
---
<img width="917" height="427" alt="image" src="https://github.com/user-attachments/assets/41813d4d-2272-409d-8373-3da6fe7cf2a2" />

```sql
UPDATE Products
SET category='Household'
WHERE product_name LIKE '%DetergenT%';
```

**Output:**
<img width="1244" height="336" alt="image" src="https://github.com/user-attachments/assets/fe7ba3e9-c7cc-48e9-9fca-0664f2a27ba8" />



**Question 7**
---
<img width="1254" height="376" alt="image" src="https://github.com/user-attachments/assets/ca3434bb-9429-490f-9203-e9a04475a418" />


```sql
DELETE FROM Customer
WHERE GRADE=2 AND CUST_NAME LIKE '%M%' AND PAYMENT_AMT<3000;
```

**Output:**

<img width="1289" height="371" alt="image" src="https://github.com/user-attachments/assets/6b74d93e-5341-4bbe-ae50-cfe923ac1011" />


**Question 8**
---
<img width="668" height="477" alt="image" src="https://github.com/user-attachments/assets/c8f8212b-473b-4aab-949f-1c84a382bf42" />


```sql
DELETE FROM Doctors
WHERE last_name IS NULL;
```

**Output:**

<img width="1202" height="627" alt="image" src="https://github.com/user-attachments/assets/85d5b81b-431b-4988-9953-83d81982f1b9" />


**Question 9**
---
<img width="1001" height="411" alt="image" src="https://github.com/user-attachments/assets/9a008ef1-9b55-420b-8912-5973e1b97a0f" />


```sql
UPDATE sales
SET total_sell_price=quantity*sell_price
WHERE product_id=10;
```

**Output:**

<img width="1299" height="486" alt="image" src="https://github.com/user-attachments/assets/8baa392b-c029-4437-9a1c-415261b42586" />


**Question 10**
---
<img width="1280" height="397" alt="image" src="https://github.com/user-attachments/assets/3745fb48-19e0-4786-b0ca-b105cf8c19a3" />


```sql
SELECT customer_id,cust_name,city,grade,salesman_id FROM customer
WHERE city='New York' or grade<=100;
```

**Output:**

<img width="1129" height="399" alt="image" src="https://github.com/user-attachments/assets/d6f5e805-534f-45d8-8ea7-29160fa475fd" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
