# Inserting Data into a Table

### 1. Single Row Insertion
- A row in a table is referred to as a **record**.
- The `INSERT INTO` statement is used to insert data into a table.
- The syntax for inserting a single record into a table is:

```sql
INSERT INTO table_name (column1, column2, ...) VALUES (value1, value2, ...);
```

- Example:

```sql
INSERT INTO personalInfo (id, name, date_of_birth, city) 
VALUES (1, 'Rohan', '1990-06-14', 'Bengaluru');
```

- **Note:** Column names are optional in the INSERT statement. However, when omitted, values should be provided in the exact order of the table's column definitions.

```sql
INSERT INTO personalInfo VALUES (1, 'Rohan', '1990-06-14', 'Bengaluru');

