# Updating Records in SQL

### Definition
The **UPDATE** statement in SQL is used to modify existing records in a table. It allows changes to one or more columns for specific rows or the entire table, based on a specified condition.

### Syntax
```sql
UPDATE tableName
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

### Key Points
- The **SET** clause specifies the columns and their new values.
- The **WHERE** clause specifies which rows should be updated.
- Without a **WHERE** clause, all rows in the table will be updated.

### Example 1: Updating a Single Column
#### Query
```sql
UPDATE employee
SET emp_age = 28
WHERE id = 1;
```

#### Before Update
| id | emp_name | emp_age | emp_city   |
|----|----------|---------|------------|
| 1  | Rohan    | 26      | Bengaluru  |
| 2  | Rohit    | 24      | Pune       |
| 3  | Ravi     | 28      | Mumbai     |

#### After Update
| id | emp_name | emp_age | emp_city   |
|----|----------|---------|------------|
| 1  | Rohan    | 28      | Bengaluru  |
| 2  | Rohit    | 24      | Pune       |
| 3  | Ravi     | 28      | Mumbai     |

### Example 2: Updating Multiple Columns
#### Query
```sql
UPDATE employee
SET emp_age = 28, emp_city = 'Delhi'
WHERE id = 1;
```

#### After Update
| id | emp_name | emp_age | emp_city |
|----|----------|---------|----------|
| 1  | Rohan    | 28      | Delhi    |
| 2  | Rohit    | 24      | Pune     |
| 3  | Ravi     | 28      | Mumbai   |

### Caution
- **Always use the WHERE clause:** Omitting the **WHERE** clause will update all rows in the table.
- **Backup your data:** Before performing updates, ensure that data is backed up to avoid accidental loss.
- **Test the query:** Test your **UPDATE** statement on a small sample or in a test environment.
- **Verify changes:** After the update, run a **SELECT** query to verify that the intended changes were applied correctly.

### Notes
- The **UPDATE** statement is powerful for maintaining and modifying data.
- Combine with conditions carefully to avoid unintended updates.
- Changes can be made to one or multiple columns simultaneously.

