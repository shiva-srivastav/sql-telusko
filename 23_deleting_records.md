# Deleting Records in SQL

### Definition
The **DELETE** statement in SQL is used to remove one or more rows from a table. It allows you to delete specific records based on a condition or all rows when no condition is specified.

### Syntax
```sql
DELETE FROM tableName;
```
Deletes all records from the table.

```sql
DELETE FROM tableName WHERE condition;
```
Deletes specific records based on the condition.

### Key Points
- If no **WHERE** clause is provided, all rows in the table will be deleted.
- To delete only specific rows, include a **WHERE** clause with the appropriate condition.
- **DELETE** does not delete the table structure or its schema, only the data within the table.

### Example 1: Delete with Condition
#### Query
```sql
DELETE FROM employee WHERE id = 2;
```

#### Before Deletion
| id | emp_name | emp_age | emp_city   |
|----|----------|---------|------------|
| 1  | Rohan    | 15      | Bengaluru  |
| 2  | Rohit    | 15      | Bengaluru  |
| 3  | Ravi     | 15      | Bengaluru  |

#### After Deletion
| id | emp_name | emp_age | emp_city   |
|----|----------|---------|------------|
| 1  | Rohan    | 15      | Bengaluru  |
| 3  | Ravi     | 15      | Bengaluru  |

### Example 2: Delete All Records
#### Query
```sql
DELETE FROM employee;
```
#### Result
All rows in the table are removed, but the table structure remains intact.

### Caution
- **Always use the WHERE clause:** Omitting the **WHERE** clause will delete all rows in the table.
- **Backup data:** Ensure you have a backup before performing a delete operation to prevent accidental data loss.
- **Test on a subset:** Run your delete query on a smaller subset of data or a test environment before applying it to the full dataset.

### Notes
- Use **DELETE** for removing specific records while preserving the table structure.
- Use **TRUNCATE** if you want to delete all records faster without preserving individual delete logs (but it does not allow conditional deletion).
- Always review your delete queries carefully to avoid unintended data loss.

