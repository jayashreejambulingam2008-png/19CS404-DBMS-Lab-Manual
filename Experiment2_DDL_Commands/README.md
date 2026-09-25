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
CREATE TABLE STUDENT (
    STUDENT_ID NUMBER(5),
    NAME VARCHAR2(30),
    DEPARTMENT VARCHAR2(20),
    MARKS NUMBER(3)
);

DESC STUDENT;

**Output:**

<img width="973" height="227" alt="image" src="https://github.com/user-attachments/assets/f7df2cf7-8f8a-46e5-b01d-18e8eef05f24" />


**Question 2**
ALTER TABLE STUDENT
ADD (ADDRESS VARCHAR2(30));

DESC STUDENT;

**Output:**

<img width="957" height="371" alt="image" src="https://github.com/user-attachments/assets/3614b026-29e4-4007-a511-8cfe9d8d3ba3" />


**Question 3**
ALTER TABLE STUDENT
MODIFY (NAME VARCHAR2(50));

DESC STUDENT;

**Output:**

<img width="987" height="235" alt="image" src="https://github.com/user-attachments/assets/50b80d0c-483b-43e0-97f2-fbd74db11ddb" />


**Question 4**
ALTER TABLE STUDENT
DROP COLUMN ADDRESS;

DESC STUDENT;

**Output:**
<img width="990" height="378" alt="image" src="https://github.com/user-attachments/assets/8e186014-b054-4e16-a474-15144a74e1e0" />



**Question 5**
ALTER TABLE STUDENT
RENAME COLUMN NAME TO STUDENT_NAME;

DESC STUDENT;

**Output:**

<img width="960" height="205" alt="image" src="https://github.com/user-attachments/assets/d7489732-e7a4-46d7-aaac-af39e36771e9" />


**Question 6**
CREATE TABLE EMPLOYEE (
    EMP_ID NUMBER(5) PRIMARY KEY,
    EMP_NAME VARCHAR2(30) NOT NULL,
    SALARY NUMBER(8,2)
);

DESC EMPLOYEE;

**Output:**

<img width="972" height="377" alt="image" src="https://github.com/user-attachments/assets/861a5a9a-7312-4965-b4b7-3d8b64ab943f" />


**Question 7**
CREATE TABLE COURSE (
    COURSE_ID NUMBER(5) PRIMARY KEY,
    COURSE_NAME VARCHAR2(30) UNIQUE,
    DURATION NUMBER(2) CHECK (DURATION > 0)
);

DESC COURSE;
INSERT INTO COURSE VALUES (101, 'Python', 6);
INSERT INTO COURSE VALUES (102, 'Java', 4);

SELECT * FROM COURSE;

**Output:**

<img width="992" height="352" alt="image" src="https://github.com/user-attachments/assets/332647f7-2ac0-4af5-93ca-796ba5387d77" />


**Question 8**
CREATE TABLE DEPARTMENT (
    DEPT_ID NUMBER(3) PRIMARY KEY,
    DEPT_NAME VARCHAR2(30)
);

CREATE TABLE STUDENT_DEPT (
    STUDENT_ID NUMBER(5) PRIMARY KEY,
    STUDENT_NAME VARCHAR2(30),
    DEPT_ID NUMBER(3),
    FOREIGN KEY (DEPT_ID) REFERENCES DEPARTMENT(DEPT_ID)
);

DESC STUDENT_DEPT;


**Output:**

<img width="932" height="392" alt="image" src="https://github.com/user-attachments/assets/858d9b61-3235-4b29-ae8b-1e328f68bce2" />


**Question 9**
CREATE TABLE CUSTOMER (
    CUSTOMER_ID NUMBER(5) PRIMARY KEY,
    CUSTOMER_NAME VARCHAR2(30) NOT NULL,
    CITY VARCHAR2(20) DEFAULT 'Chennai'
);

INSERT INTO CUSTOMER (CUSTOMER_ID, CUSTOMER_NAME)
VALUES (101, 'Ravi');

SELECT * FROM CUSTOMER;

**Output:**

<img width="992" height="417" alt="image" src="https://github.com/user-attachments/assets/848d1259-8294-4cdc-812d-b6401586aa1b" />


**Question 10**
CREATE TABLE TEMP_STUDENT (
    ID NUMBER(5),
    NAME VARCHAR2(30)
);

RENAME TEMP_STUDENT TO STUDENT_DETAILS;

DESC STUDENT_DETAILS;

DROP TABLE STUDENT_DETAILS;

**Output:**

<img width="962" height="392" alt="image" src="https://github.com/user-attachments/assets/d5c30fac-f619-4b46-a5de-a78b142e42df" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
