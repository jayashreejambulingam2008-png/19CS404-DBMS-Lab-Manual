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
SELECT MIN(salary) AS minimum_salary
FROM staff;


**Output:**

<img width="877" height="367" alt="image" src="https://github.com/user-attachments/assets/485a83cf-1928-4df9-a52f-ee1ffe2793c3" />


**Question 2**
SELECT MAX(salary) AS maximum_salary
FROM staff;


**Output:**

<img width="875" height="425" alt="image" src="https://github.com/user-attachments/assets/54e7616e-4a2e-4675-867b-45873591117e" />


**Question 3**
SELECT SUM(salary) AS total_salary
FROM staff;


**Output:**
<img width="898" height="355" alt="image" src="https://github.com/user-attachments/assets/18d88874-fea8-44c7-a605-e3091f0b11d9" />



**Question 4**
SELECT AVG(salary) AS average_salary
FROM staff;

**Output:**

<img width="762" height="412" alt="image" src="https://github.com/user-attachments/assets/1c6cc5d3-923c-4bff-af8c-0de06fc921b0" />


**Question 5**
SELECT COUNT(*) AS total_staff
FROM staff;


**Output:**

<img width="852" height="402" alt="image" src="https://github.com/user-attachments/assets/d52e78fe-bd6d-43e0-98d3-7dc02b1d0e90" />


**Question 6**
SELECT department, COUNT(*) AS staff_count
FROM staff
GROUP BY department;


**Output:**
<img width="842" height="391" alt="image" src="https://github.com/user-attachments/assets/bba91943-277c-4b58-abe9-4337890d1014" />

**Question 7**
SELECT department, SUM(salary) AS total_salary
FROM staff
GROUP BY department;


**Output:**

<img width="882" height="393" alt="image" src="https://github.com/user-attachments/assets/6917be05-80de-4f4f-9adf-562b4394ade8" />

**Question 8**
SELECT department, AVG(salary) AS average_salary
FROM staff
GROUP BY department;


**Output:**

<img width="901" height="355" alt="image" src="https://github.com/user-attachments/assets/835b9696-1dde-4e58-b537-211656404768" />


**Question 9**
SELECT department, COUNT(*) AS staff_count
FROM staff
GROUP BY department
HAVING COUNT(*) > 2;

**Output:**

<img width="842" height="367" alt="image" src="https://github.com/user-attachments/assets/9c721cdc-ea78-4100-9e1e-95f3b09a56a5" />


**Question 10**
SELECT department, SUM(salary) AS total_salary
FROM staff
GROUP BY department
HAVING SUM(salary) > 150000;


**Output:**
<img width="906" height="347" alt="image" src="https://github.com/user-attachments/assets/31029866-f540-418f-acfd-bbf7505dc71b" />




## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
