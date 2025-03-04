# Primary Key Constraint in SQL

The Primary Key constraint uniquely identifies each record in a table. It ensures that no duplicate or null values exist in the designated column.

### Key Features:
- A Primary Key provides a unique identity to each record in the table.
- The primary key column must only contain **unique** values.
- A table can have only **one** primary key.
- A primary key **cannot have NULL** values.


### Example: Implementing Primary Key Constraint

**Step 1: Create Database (if not already created)**
```sql
CREATE DATABASE telusko_db;
USE telusko_db;
```

**Step 2: Create `employee` Table with Primary Key**
```sql
CREATE TABLE employee (
    id INT,
    emp_name VARCHAR(40),
    emp_age INT,
    emp_city VARCHAR(40),
    PRIMARY KEY (id)
);
```

Here, the `id` column is defined as the **Primary Key**, ensuring unique and non-null values.

**Step 3: Insert Data into `employee` Table**
```sql
INSERT INTO employee (id, emp_name, emp_age, emp_city) 
VALUES (3, 'Rohan', 15, 'Bengaluru'),
       (2, 'Rohan', 15, 'Bengaluru'),
       (4, 'Rohan', 15, 'Bengaluru');
```

**Step 4: Attempting to Insert Duplicate Values**<br>
If we try to execute the same `INSERT` query again, it will fail because the `id` column is a Primary Key and must contain unique values.

```sql
INSERT INTO employee (id, emp_name, emp_age, emp_city) 
VALUES (3, 'Rohan', 15, 'Bengaluru');  -- This will cause an error
```

#### Error Message:
```plaintext
ERROR 1062 (23000): Duplicate entry '3' for key 'PRIMARY'
```
This error occurs because `id = 3` already exists in the table.

---
