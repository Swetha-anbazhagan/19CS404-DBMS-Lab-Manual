# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
<img width="917" height="362" alt="image" src="https://github.com/user-attachments/assets/16a7cc32-6a02-46e0-bfd1-878b63d244f1" />


```sql
SELECT AVG(LENGTH(email)) as avg_email_length_below_30 FROM customer
GROUP BY city HAVING city=='Mumbai';
```

**Output:**

<img width="557" height="319" alt="image" src="https://github.com/user-attachments/assets/37a127fd-87b4-42d2-a1e6-43df02e74c6e" />


**Question 2**
---
<img width="632" height="417" alt="image" src="https://github.com/user-attachments/assets/f8b8d082-cb8e-4475-b353-ca00b960e456" />


```sql
SELECT count(*) as employees_in_california FROM employee
GROUP BY city HAVING city='California';
```

**Output:**

<img width="612" height="320" alt="image" src="https://github.com/user-attachments/assets/7928184c-3d53-4c0c-ae36-99a66889976b" />


**Question 3**
---
<img width="665" height="364" alt="image" src="https://github.com/user-attachments/assets/c97af95b-13df-4328-b470-ed9f906fc12e" />


```sql
SELECT AVG(LENGTH(email)) as avg_email_length FROM customer;
```

**Output:**

<img width="488" height="320" alt="image" src="https://github.com/user-attachments/assets/cb1df365-ee0c-45d6-95b7-da2f652826aa" />


**Question 4**
---
<img width="860" height="364" alt="image" src="https://github.com/user-attachments/assets/8512e8f7-2f35-4c29-9d40-174a6adbac15" />


```sql
SELECT Gender,count(*) as TotalPatients FROM Patients
GROUP BY Gender;
```

**Output:**

<img width="593" height="356" alt="image" src="https://github.com/user-attachments/assets/48bf5c62-01d6-478f-aade-bd22ab3f15e0" />

**Question 5**
---
<img width="912" height="453" alt="image" src="https://github.com/user-attachments/assets/61dbf534-0beb-420d-8ecd-be4a73fefead" />

```sql
SELECT 
    CASE
        WHEN age BETWEEN 20 and 30 THEN '20-30'
        WHEN age BETWEEN 31 and 40 THEN '31-40'
        WHEN age BETWEEN 41 and 50 THEN '41-50'
        ELSE "Above 50"
    END AS AgeGroup,
    COUNT(*) AS TotalPatients 
FROM (
    SELECT 
        CAST((julianday('now')-julianday(DateOfBirth))/365.25 AS INTEGER)AS age
        FROM Patients
    )
GROUP BY AgeGroup;
```

**Output:**

<img width="648" height="373" alt="image" src="https://github.com/user-attachments/assets/30039de0-13cf-4c69-b6e4-398284278ee3" />


**Question 6**
---
<img width="846" height="492" alt="image" src="https://github.com/user-attachments/assets/f89240e6-3170-43f3-b11d-f5bf961d5832" />


```sql
select Specialty,Gender,COUNT(*) AS TotalDoctors FROM Doctors
GROUP BY Specialty,Gender;
```

**Output:**
<img width="797" height="599" alt="image" src="https://github.com/user-attachments/assets/b0e4bcb2-a425-4681-81fe-f3c6bb035f76" />



**Question 7**
---
<img width="1289" height="443" alt="image" src="https://github.com/user-attachments/assets/e7d9bd92-3ff8-4171-87f0-8caf1003adaf" />

```sql
SELECT jdate,MAX(workhour) FROM employee1
GROUP BY jdate
HAVING MAX(workhour)>=12;
```

**Output:**

<img width="564" height="378" alt="image" src="https://github.com/user-attachments/assets/31705350-0038-47bb-a00e-4e677274f0bc" />

**Question 8**
---
<img width="1329" height="402" alt="image" src="https://github.com/user-attachments/assets/939f07d8-badd-40fe-8201-9bc742c89a9d" />


```sql
SELECT category_id,SUM(price) AS Total_Cost FROM products
GROUP BY category_id 
HAVING Total_cost>50;
```

**Output:**

<img width="483" height="346" alt="image" src="https://github.com/user-attachments/assets/35b41658-8b4c-47b0-9874-87cee536450e" />


**Question 9**
---
<img width="1243" height="446" alt="image" src="https://github.com/user-attachments/assets/275fe9bb-7d6a-4b6b-a605-8b0a9e62a9c8" />

```sql
SELECT age,MIN(income) FROM employee
GROUP BY age 
HAVING MIN(income)<=400000;
```

**Output:**

<img width="544" height="379" alt="image" src="https://github.com/user-attachments/assets/89c59cbd-346e-4c25-b29d-77f975851825" />

**Question 10**
---
<img width="1265" height="370" alt="image" src="https://github.com/user-attachments/assets/dff1d848-c32c-4615-9cc9-d88b79904596" />


```sql
SELECT (age/5)*5 AS age_group,MIN(age) FROM customer1
GROUP BY age_group
HAVING age<25;
```

**Output:**

<img width="516" height="317" alt="image" src="https://github.com/user-attachments/assets/95801173-c12b-4fce-9692-08541bfd7159" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
