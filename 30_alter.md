# SQL ALTER Command

### Definition
The **ALTER** command in SQL is used to modify the structure of an existing table. It allows you to add, delete, or modify columns, as well as add or drop constraints.

### Syntax
```sql
ALTER TABLE tableName
<modification>;
```

### Use Cases with Examples and Outputs

#### 1. Adding a Column
- Use the **ADD** clause to add a new column to a table.
```sql
ALTER TABLE student
ADD phone_number VARCHAR(15);
```
**Before Execution:**
| id | name   | age |
|----|--------|-----|
| 1  | Rahul  | 20  |
| 2  | Meera  | 22  |

**After Execution:**
| id | name   | age | phone_number |
|----|--------|-----|--------------|
| 1  | Rahul  | 20  | NULL         |
| 2  | Meera  | 22  | NULL         |

#### 2. Modifying a Column
- Use the **MODIFY** clause (MySQL) or **ALTER COLUMN** (SQL Server) to change the data type or properties of an existing column.
```sql
ALTER TABLE student
MODIFY phone_number CHAR(10);
```
**Before Execution:**
| id | name   | age | phone_number |
|----|--------|-----|--------------|
| 1  | Rahul  | 20  | NULL         |
| 2  | Meera  | 22  | NULL         |

**After Execution:**
| id | name   | age | phone_number |
|----|--------|-----|--------------|
| 1  | Rahul  | 20  | NULL         |
| 2  | Meera  | 22  | NULL         |
(Note: Data type changed to CHAR(10))

#### 3. Renaming a Column
- Use the **RENAME COLUMN** clause (MySQL 8.0+, Oracle) to rename a column.
```sql
ALTER TABLE student
RENAME COLUMN phone_number TO contact_number;
```
**Before Execution:**
| id | name   | age | phone_number |
|----|--------|-----|--------------|
| 1  | Rahul  | 20  | NULL         |
| 2  | Meera  | 22  | NULL         |

**After Execution:**
| id | name   | age | contact_number |
|----|--------|-----|----------------|
| 1  | Rahul  | 20  | NULL           |
| 2  | Meera  | 22  | NULL           |

#### 4. Dropping a Column
- Use the **DROP** clause to remove a column from a table.
```sql
ALTER TABLE student
DROP COLUMN contact_number;
```
**Before Execution:**
| id | name   | age | contact_number |
|----|--------|-----|----------------|
| 1  | Rahul  | 20  | NULL           |
| 2  | Meera  | 22  | NULL           |

**After Execution:**
| id | name   | age |
|----|--------|-----|
| 1  | Rahul  | 20  |
| 2  | Meera  | 22  |

#### 5. Adding Constraints
- Use the **ADD CONSTRAINT** clause to add a primary key.
```sql
ALTER TABLE student
ADD CONSTRAINT pk_student PRIMARY KEY (id);
```
**Before Execution:**
| id | name   | age |
|----|--------|-----|
| 1  | Rahul  | 20  |
| 2  | Meera  | 22  |

**After Execution:**
The column `id` is now the primary key of the table.

#### 6. Dropping Constraints
- Use the **DROP CONSTRAINT** clause to remove constraints.
```sql
ALTER TABLE student
DROP CONSTRAINT pk_student;
```
**Before Execution:**
The column `id` is the primary key of the table.

**After Execution:**
The `id` column no longer has a primary key constraint.

#### 7. Renaming a Table
- Use the **RENAME TO** clause to rename a table.
```sql
ALTER TABLE student
RENAME TO student_info;
```
**Before Execution:**
The table name is `student`.

**After Execution:**
The table name is now `student_info`.

### Notes
- Changes made with **ALTER** are permanent and cannot be undone without explicit commands.
- Always test **ALTER** commands on a backup or test environment before applying to a production database.
- Not all ALTER functionalities are supported in every RDBMS. Check your database's documentation for specific syntax.

This command is essential for maintaining and evolving database schema as application requirements change.

