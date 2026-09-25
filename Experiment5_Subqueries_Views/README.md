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
SELECT *
FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);

**Output:**

<img width="970" height="322" alt="image" src="https://github.com/user-attachments/assets/8abb4916-faaf-4230-9666-c552681c6f3f" />


**Question 2**
CREATE TABLE employees (
    emp_id NUMBER PRIMARY KEY,
    emp_name VARCHAR2(50),
    department VARCHAR2(50),
    salary NUMBER
);

**Output:**

<img width="1032" height="402" alt="image" src="https://github.com/user-attachments/assets/392bfbfe-ca2d-413f-9359-5ff7646aa0f9" />


**Question 3**
SELECT *
FROM employees
WHERE department IN (
    SELECT department
    FROM employees
    WHERE salary > 40000
);

**Output:**

<img width="1043" height="417" alt="image" src="https://github.com/user-attachments/assets/777c6991-09ee-47ec-9360-b8358bb9feac" />

**Question 4**
SELECT *
FROM employees
WHERE salary > ANY (
    SELECT salary
    FROM employees
    WHERE department = 'HR'
);

**Output:**

<img width="942" height="422" alt="image" src="https://github.com/user-attachments/assets/c8e2356a-128f-4bc9-80de-f446b2857595" />

**Question 5**
SELECT *
FROM employees
WHERE salary > ALL (
    SELECT salary
    FROM employees
    WHERE department = 'HR'
);

**Output:**

<img width="1105" height="412" alt="image" src="https://github.com/user-attachments/assets/005003b4-3a33-4d0f-b232-75bc706613ba" />


**Question 6**
SELECT e.emp_id, e.emp_name, e.department, e.salary
FROM employees e
WHERE e.salary > (
    SELECT AVG(e2.salary)
    FROM employees e2
    WHERE e2.department = e.department
);

**Output:**

<img width="1012" height="328" alt="image" src="https://github.com/user-attachments/assets/8e05fde3-0183-4710-888a-bc7fae3bdf53" />


**Question 7**
CREATE VIEW it_employees AS
SELECT emp_id, emp_name, salary
FROM employees
WHERE department = 'IT';

SELECT * FROM it_employees;

**Output:**

<img width="965" height="343" alt="image" src="https://github.com/user-attachments/assets/b8d80e7c-98c8-4a55-ba03-69f0eba7849d" />


**Question 8**
CREATE VIEW high_salary_employees AS
SELECT emp_id, emp_name, department, salary
FROM employees
WHERE salary > 40000;

SELECT * FROM high_salary_employees;


**Output:**

<img width="992" height="465" alt="image" src="https://github.com/user-attachments/assets/15b7f299-a333-4d53-9488-8ec255a69793" />


**Question 9**
CREATE VIEW department_avg_salary AS
SELECT department, AVG(salary) AS average_salary
FROM employees
GROUP BY department;

SELECT * FROM department_avg_salary;


**Output:**

<img width="877" height="345" alt="image" src="https://github.com/user-attachments/assets/da5b797b-0d5b-48e6-9e1e-3455a1dc4d01" />


**Question 10**
DROP VIEW high_salary_employees;

**Output:**

<img width="937" height="390" alt="image" src="https://github.com/user-attachments/assets/a119f979-bd57-4f82-945a-328fb884c345" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
