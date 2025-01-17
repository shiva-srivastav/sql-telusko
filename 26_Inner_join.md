# INNER JOIN in SQL

### Definition
The **INNER JOIN** clause in SQL is used to combine rows from two or more tables based on a related column between them. It retrieves only the records that have matching values in both tables.

### Syntax
```sql
SELECT column1, column2, ...
FROM table1
INNER JOIN table2
ON table1.common_column = table2.common_column;
```

### Key Properties
- Combines rows from two or more tables where there is a match in the related column(s).
- If no match is found, the row is excluded from the result set.
- Represents the intersection of two tables in terms of data.

### Example: INNER JOIN with City and Student Tables
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
INNER JOIN city
ON student.city = city.id;
```

#### Output
| name   | age | city_name   |
|--------|-----|-------------|
| Nikhil | 20  | Mumbai      |
| Rahul  | 22  | Pune        |
| Meera  | 19  | Bengaluru   |

### Condition
- The **ON** clause specifies the condition for matching rows in both tables (e.g., `student.city = city.id`).
- Rows without a match in the other table are excluded from the result set.

### Venn Diagram Explanation
- **Inner Join** corresponds to the intersection area of the two circles representing the tables.
- Only the matching data that exists in both tables is retrieved.

### Notes
- Use **INNER JOIN** when you only need data that exists in both tables.
- Ensure the columns used in the **ON** clause have matching data types to avoid errors.
- For tables with no matching values, the result set will be empty.

