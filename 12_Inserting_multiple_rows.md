# Inserting Data into a Table

### 2. Inserting Multiple Rows
- Multiple records can be inserted into a table using a **single query** using comma-separated values.
- This improves performance as it reduces the number of database calls.
- The syntax for inserting multiple rows at once is:

```sql
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...),
       (value1, value2, ...),
       (value1, value2, ...);
```

- Example:

```sql
INSERT INTO personalInfo (id, name, date_of_birth, city) 
VALUES (6, 'Ramesh', '1990-04-14', 'Pune'), 
       (4, 'Suresh', '1990-04-16', 'Mysuru'), 
       (5, 'Ramesh', '1990-04-15', 'Mumbai');
```
