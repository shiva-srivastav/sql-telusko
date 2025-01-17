# SQL CROSS JOIN

### Definition
The **CROSS JOIN** clause in SQL is used to combine every row from the first table with every row from the second table. It produces the Cartesian product of the two tables.

### Syntax
```sql
SELECT column1, column2, ...
FROM table1
CROSS JOIN table2;
```

### Key Properties
- Produces a Cartesian product of the two tables.
- The number of rows in the result set equals the product of the number of rows in the two tables.
- No condition is required for a CROSS JOIN.

### Example: CROSS JOIN with City and Student Tables
#### Tables:
##### City Table
| id | city_name   |
|----|-------------|
| 1  | Pune        |
| 2  | Bengaluru   |
| 3  | Mumbai      |

##### Student Table
| id | name   | age |
|----|--------|-----|
| 1  | Nikhil | 20  |
| 2  | Rahul  | 22  |

#### Query
```sql
SELECT student.name, student.age, city.city_name
FROM student
CROSS JOIN city;
```

#### Output
| name   | age | city_name   |
|--------|-----|-------------|
| Nikhil | 20  | Pune        |
| Nikhil | 20  | Bengaluru   |
| Nikhil | 20  | Mumbai      |
| Rahul  | 22  | Pune        |
| Rahul  | 22  | Bengaluru   |
| Rahul  | 22  | Mumbai      |

### Condition
- A CROSS JOIN does not require a matching condition between the two tables.
- To filter the results, you can use a **WHERE** clause after the join.

### Notes
- Use **CROSS JOIN** cautiously as it can produce a large number of rows if the tables are large.
- Useful for scenarios like generating combinations or pairing data from two unrelated tables.

