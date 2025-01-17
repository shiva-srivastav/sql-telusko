# SQL RIGHT JOIN

### Definition
The **RIGHT JOIN** clause in SQL is used to retrieve all records from the right table (Table 2) and the matching records from the left table (Table 1). If there is no match, NULL values are returned for the columns from the left table.

### Syntax
```sql
SELECT column1, column2, ...
FROM table1
RIGHT JOIN table2
ON table1.common_column = table2.common_column;
```

### Key Properties
- Retrieves all rows from the right table.
- Retrieves matching rows from the left table.
- If there is no match, the columns from the left table will contain NULL values.

### Example: RIGHT JOIN with City and Student Tables
#### Tables:
##### City Table
| id | city_name   |
|----|-------------|
| 1  | Pune        |
| 2  | Bengaluru   |
| 3  | Mumbai      |
| 4  | London      |

##### Student Table
| id | name   | age | city |
|----|--------|-----|------|
| 1  | Nikhil | 20  | 3    |
| 2  | Rahul  | 22  | 1    |
| 3  | Meera  | 19  | 2    |
| 4  | Suman  | 21  | 5    |

#### Query
```sql
SELECT student.name, student.age, city.city_name
FROM student
RIGHT JOIN city
ON student.city = city.id;
```

#### Output
| name   | age | city_name   |
|--------|-----|-------------|
| Rahul  | 22  | Pune        |
| Meera  | 19  | Bengaluru   |
| Nikhil | 20  | Mumbai      |
| NULL   | NULL| London      |

### Condition
- The **ON** clause specifies the condition for matching rows in both tables (e.g., `student.city = city.id`).
- Rows from the right table with no match in the left table will still appear in the result set, with NULL values for the left table columns.

### Notes
- Use **RIGHT JOIN** when you want all rows from the right table regardless of whether there is a match in the left table.
- Useful for scenarios where you want to include all data from one table while optionally matching it with another table.

