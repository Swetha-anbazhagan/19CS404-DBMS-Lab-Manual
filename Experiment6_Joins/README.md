# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
<img width="1259" height="541" alt="image" src="https://github.com/user-attachments/assets/a58840f1-e8f1-470b-b8e9-017f1ac1a5d0" />


```sql
SELECT c.customer_id,cust_name,city,grade,c.salesman_id
FROM customer AS c
LEFT JOIN  Orders AS o
ON c.customer_id=o.customer_id
WHERE o.ord_date BETWEEN '2012-07-01' AND '2012-07-30';


```

**Output:**

<img width="1278" height="382" alt="image" src="https://github.com/user-attachments/assets/630a9c3b-a1d5-4c2d-877d-6130b89ff1ab" />



**Question 2**
---

<img width="1188" height="821" alt="image" src="https://github.com/user-attachments/assets/56b487db-e6ce-4dd0-8a5b-91a343dcf711" />

```sql
SELECT c.cust_name as "Customer Name",c.city,s.name as Salesman,s.commission
FROM customer as c
INNER JOIN salesman as s
WHERE c.salesman_id=s.salesman_id

```

**Output:**

<img width="1129" height="802" alt="image" src="https://github.com/user-attachments/assets/a7f34ac7-ce24-4208-ac04-3c64703a46be" />



**Question 3**
---

<img width="1283" height="583" alt="image" src="https://github.com/user-attachments/assets/90b8a982-feba-4608-9406-da339138072a" />


```sql
SELECT p.first_name as patient_name,t.test_name
FROM Patients as p
INNER JOIN Test_results as t
ON p.patient_id=t.patient_id
```

**Output:**

<img width="777" height="505" alt="image" src="https://github.com/user-attachments/assets/5d4d8957-3c9a-4f2e-98c1-2db42065388f" />


**Question 4**
---

<img width="1272" height="541" alt="image" src="https://github.com/user-attachments/assets/83157a47-4a9b-4f5c-a648-e91b6d08ff11" />

```sql
SELECT c.*
from customer as c
left join orders as o
ON c.customer_id=o.customer_id
WHERE ord_date BETWEEN '2012-08-01' and '2012-08-30';
```

**Output:**

<img width="1282" height="431" alt="image" src="https://github.com/user-attachments/assets/a2e9980c-665e-4437-aa38-0508bcf54008" />



**Question 5**
---

<img width="1232" height="508" alt="image" src="https://github.com/user-attachments/assets/6f806151-03b9-4a54-8c01-5d75b4f73101" />


```sql
SELECT t.*
FROM test_results as t
INNER JOIN patients as p
ON p.patient_id=t.patient_id
WHERE first_name='Alice'
```

**Output:**


<img width="1304" height="401" alt="image" src="https://github.com/user-attachments/assets/2b02f9de-56ac-4044-81b3-a82ad59312ff" />


**Question 6**
---

<img width="1262" height="567" alt="image" src="https://github.com/user-attachments/assets/09a475cc-409d-486c-91a7-69981838a24b" />


```sql
SELECT c.*
FROM customer as c
LEFT JOIN salesman as s
ON c.salesman_id=s.salesman_id
WHERE name='Mc Lyon'
```

**Output:**

<img width="1270" height="406" alt="image" src="https://github.com/user-attachments/assets/7e96bb1e-1d13-470a-8026-96ab2a899a73" />


**Question 7**
---

<img width="1274" height="767" alt="image" src="https://github.com/user-attachments/assets/40afa90a-a6d5-44b4-ae5d-2a38e0cdacf6" />


```sql
SELECT c.cust_name as "Customer Name",c.city,s.name as Salesman,s.commission
FROM CUSTOMER AS c
INNER JOIN SALESMAN AS s
ON c.salesman_id=s.salesman_id
WHERE commission>0.12;
```

**Output:**


<img width="1136" height="682" alt="image" src="https://github.com/user-attachments/assets/62e79f0a-a507-4445-8c25-9e3677aa83a4" />


**Question 8**
---

<img width="1246" height="614" alt="image" src="https://github.com/user-attachments/assets/d7fd7bf1-82a3-483d-ad82-6aa463ddeee9" />


```sql
SELECt s.name,c.cust_name,c.city,c.grade,c.salesman_id
FROM customer as c
LEFT JOIN salesman as s
ON c.salesman_id=s.salesman_id
WHERE grade<=100;
```

**Output:**


<img width="1292" height="514" alt="image" src="https://github.com/user-attachments/assets/b0279122-a112-42e6-b4fd-adfa40a0a93d" />


**Question 9**
---

<img width="1261" height="673" alt="image" src="https://github.com/user-attachments/assets/4b4221fd-cd3a-4ad0-9587-3f0755c590fb" />


```sql
SELECT p.first_name,s.surgery_id,p.patient_id,s.surgeon_id,s.surgery_date
FROM Surgeries as s
INNER JOIN patients as p
ON p.patient_id=s.patient_id
WHERE first_name='Alice'
```

**Output:**

<img width="1295" height="424" alt="image" src="https://github.com/user-attachments/assets/25843b31-532c-4a57-b1ae-c9590f47d1e4" />



**Question 10**
---

<img width="1259" height="502" alt="image" src="https://github.com/user-attachments/assets/c75ddf8f-9a5f-45c5-9503-9c215228212c" />

```sql
SELECT p.first_name AS patient_name,d.first_name as doctor_name
FROM patients as p
INNER JOIN doctors as d
on p.doctor_id=d.doctor_id
WHERE date_of_birth>'1990-01-01'
```

**Output:**

<img width="692" height="391" alt="image" src="https://github.com/user-attachments/assets/dcac3391-dc2b-49a0-a8b1-02ad3dacc085" />


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
