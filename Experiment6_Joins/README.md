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
Display employee names along with their department names using INNER JOIN.
```
SELECT employees.employee_name, departments.department_name
FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id;
```
**Output:**

<img width="950" height="386" alt="image" src="https://github.com/user-attachments/assets/f2a9410a-d962-4ed0-af6d-d3ff96fda7c3" />


**Question 2**
Display all employees along with their department names using LEFT JOIN.
```
SELECT employees.employee_name, departments.department_name
FROM employees
LEFT JOIN departments
ON employees.department_id = departments.department_id;
```


**Output:**

<img width="967" height="402" alt="image" src="https://github.com/user-attachments/assets/8786bb69-a63f-4319-ac7a-ae6e1465ad67" />


**Question 3**
Display all departments along with the employees working in them using RIGHT JOIN.
```
SELECT employees.employee_name, departments.department_name
FROM employees
RIGHT JOIN departments
ON employees.department_id = departments.department_id;
```

**Output:**

<img width="940" height="382" alt="image" src="https://github.com/user-attachments/assets/30c291e1-b6cd-42aa-861c-2ea7bb1f56ad" />


**Question 4**
Display all employees and departments using FULL OUTER JOIN.
```
SELECT employees.employee_name, departments.department_name
FROM employees
FULL OUTER JOIN departments
ON employees.department_id = departments.department_id;
```

**Output:**

<img width="941" height="455" alt="image" src="https://github.com/user-attachments/assets/9cf232da-3374-45d6-bdae-c65b7378e8d1" />



**Question 5**
Display employee names, department names, and salaries using INNER JOIN.
```
SELECT employees.employee_name,
       departments.department_name,
       employees.salary
FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id;
```

**Output:**

<img width="956" height="448" alt="image" src="https://github.com/user-attachments/assets/f61c597c-68ec-4f24-ac2c-92339f0bfe24" />



**Question 6**
Display employees who are assigned to a department.
```
SELECT employees.employee_name, departments.department_name
FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id;
```

**Output:**


<img width="977" height="432" alt="image" src="https://github.com/user-attachments/assets/63720ee6-6200-4414-a43d-be98fadc1537" />


**Question 7**
Display all employees, including employees who are not assigned to any department
```
SELECT employees.employee_name, departments.department_name
FROM employees
LEFT JOIN departments
ON employees.department_id = departments.department_id;
```

**Output:**


<img width="922" height="441" alt="image" src="https://github.com/user-attachments/assets/0f225c01-8e48-4d28-a8a2-6d3337d697dd" />


**Question 8**
Display all departments, including departments that have no employees.
```
SELECT departments.department_name, employees.employee_name
FROM employees
RIGHT JOIN departments
ON employees.department_id = departments.department_id;
```

**Output:**


<img width="931" height="437" alt="image" src="https://github.com/user-attachments/assets/2b1f0704-a9e8-49fd-9fd1-7d230a7801a5" />


**Question 9**
---

Display the employee name, department name, and salary for employees earning more than 50,000.

```
SELECT employees.employee_name,
       departments.department_name,
       employees.salary
FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id
WHERE employees.salary > 50000;
```

**Output:**

<img width="885" height="385" alt="image" src="https://github.com/user-attachments/assets/faae84d2-fc0d-4438-9343-baafbf99e3f8" />



**Question 10**
---
Display the number of employees in each department using JOIN and GROUP BY.

```
SELECT departments.department_name,
       COUNT(employees.employee_id) AS employee_count
FROM departments
LEFT JOIN employees
ON departments.department_id = employees.department_id
GROUP BY departments.department_name;
```

**Output:**


<img width="942" height="421" alt="image" src="https://github.com/user-attachments/assets/d648a79b-8847-4877-9ba4-6e0df491ef91" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
