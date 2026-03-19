# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
<img width="811" height="441" alt="image" src="https://github.com/user-attachments/assets/62f5faa9-5967-44da-bf6e-416478966555" />


```sql
select * from Medications where dosage=(
select MAX(dosage) from Medications
);

```

**Output:**

<img width="800" height="390" alt="image" src="https://github.com/user-attachments/assets/757b7a46-4ac6-42e5-825a-5404bbc2e11e" />


**Question 2**
---
<img width="1151" height="506" alt="image" src="https://github.com/user-attachments/assets/96d21779-4f03-4228-bcf6-6cbd39a3a2b7" />

```sql
SELECT student_name,grade FROM Grades g1 where grade=(
SELECT MIN(grade) FROM Grades g2 WHERE g2.subject=g1.subject
);
```

**Output:**
<img width="708" height="421" alt="image" src="https://github.com/user-attachments/assets/dbcb80c1-b35b-4f1a-9e92-58680c5c68f5" />



**Question 3**
---
<img width="923" height="649" alt="image" src="https://github.com/user-attachments/assets/a7bb9f94-b605-46ab-b9cb-6c9fd25153ce" />


```sql
SELECT * FROM Customers WHERE salary>1500;
```

**Output:**
<img width="1020" height="553" alt="image" src="https://github.com/user-attachments/assets/d5e6b4e2-4d31-4783-8291-03503ee02b0d" />


**Question 4**
---
<img width="1109" height="514" alt="image" src="https://github.com/user-attachments/assets/819c885a-7412-451b-8bd5-309f245a4ff8" />


```sql
SELECT * FROM Customers Where salary<2500;
```

**Output:**

<img width="1134" height="419" alt="image" src="https://github.com/user-attachments/assets/13fefcd5-33be-4840-9451-cc0493173ab1" />

**Question 5**
---
<img width="868" height="584" alt="image" src="https://github.com/user-attachments/assets/331700c3-e162-4cb2-8d71-28ba4e0f1735" />

```sql
SELECT * FROM Customers Where salary<2500;
```

**Output:**

<img width="1170" height="448" alt="image" src="https://github.com/user-attachments/assets/1020ea9a-55cf-4273-8b2e-92b1c3ebda4e" />


**Question 6**
---
<img width="1118" height="499" alt="image" src="https://github.com/user-attachments/assets/c668b544-5b0b-4e06-be0c-6b552b3c5889" />

```sql
SELECT name FROM customer c1 WHERE  (

SELECT count(*) FROM customer c2 WHERE c2.phone=c1.phone

)=1;
```

**Output:**

<img width="446" height="430" alt="image" src="https://github.com/user-attachments/assets/c35aa0e7-9d1a-49f8-9584-e0fb3d8b6355" />



**Question 7**
---
<img width="1192" height="534" alt="image" src="https://github.com/user-attachments/assets/e8b6af49-0ca6-4912-b92c-109a6d46b17f" />

```sql
SELECT * FROM Orders WHERE salesman_id IN(
SELECT salesman_id FROM Salesman WHERE city='London'

);
```

**Output:**

<img width="1042" height="410" alt="image" src="https://github.com/user-attachments/assets/9ee934e6-1b29-4137-ba5d-5b5aad97a3be" />

**Question 8**
---
<img width="949" height="492" alt="image" src="https://github.com/user-attachments/assets/f30259d0-538c-4f99-9113-22e1bde0f664" />

```sql
SELECT name,city FROM customer WHERE city IN(

SELECT city FROM customer WHERE id=3 or id=7
);
```

**Output:**

<img width="588" height="425" alt="image" src="https://github.com/user-attachments/assets/14f442d3-02b4-45c0-95d6-054995b8372d" />


**Question 9**
---
<img width="879" height="540" alt="image" src="https://github.com/user-attachments/assets/61126faf-9d44-4426-8f5a-bf9d954b70ee" />


```sql
SELECT * FROM Customers WHERE salary=1500;
```

**Output:**

<img width="1035" height="335" alt="image" src="https://github.com/user-attachments/assets/cc82e30e-171a-4ea2-ad0e-6649312f5dc6" />


**Question 10**
---
<img width="1166" height="685" alt="image" src="https://github.com/user-attachments/assets/02a9f49f-f25e-4da9-b076-94651588d51a" />


```sql
SELECT ord_no,purch_amt,ord_date,salesman_id
FROM orders o WHERE o.salesman_id IN(

SELECT s.salesman_id FROM salesman s WHERE s.commission=(
SELECT MAX(commission) FROM salesman)
);
```

**Output:**
<img width="925" height="440" alt="image" src="https://github.com/user-attachments/assets/ca522155-adb4-48a9-aba8-ca0fcf17375e" />




## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
