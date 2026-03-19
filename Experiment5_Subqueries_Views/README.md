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

![Output4](output.png)

**Question 5**
---
-- Paste Question 5 here

```sql
SELECT name FROM customer c1 WHERE  (

SELECT count(*) FROM customer c2 WHERE c2.phone=c1.phone

)=1;
```

**Output:**

<img width="1092" height="415" alt="image" src="https://github.com/user-attachments/assets/43fc5e21-2bd1-4cb8-ae70-12dfa5ea4dfe" />

**Question 6**
---
<img width="933" height="583" alt="image" src="https://github.com/user-attachments/assets/c71fa938-352a-49dc-b0a9-86c10d7ba78c" />

```sql
SELECT * FROM Customers Where salary<2500;
```

**Output:**

<img width="1017" height="430" alt="image" src="https://github.com/user-attachments/assets/c641d77a-0dc9-4685-8f15-099f38d6b928" />


**Question 7**
---
<img width="1099" height="499" alt="image" src="https://github.com/user-attachments/assets/54ab20e0-c4a3-41ef-9139-76d91ec40000" />

```sql
SELECT name FROM customer c1 WHERE  (

SELECT count(*) FROM customer c2 WHERE c2.phone=c1.phone

)=1;
```

**Output:**

![Output7](output.png)

**Question 8**
---
-- Paste Question 8 here

```sql
-- Paste your SQL code below for Question 8
```

**Output:**

![Output8](output.png)

**Question 9**
---
-- Paste Question 9 here

```sql
-- Paste your SQL code below for Question 9
```

**Output:**

![Output9](output.png)

**Question 10**
---
-- Paste Question 10 here

```sql
-- Paste your SQL code below for Question 10
```

**Output:**

![Output10](output.png)


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
