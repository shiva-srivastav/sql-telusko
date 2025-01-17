# IN Operator in SQL

### Definition
The **IN** operator in SQL is used to filter records based on whether a column's value matches any value in a specified list. It simplifies writing multiple `OR` conditions in a query.

### Syntax
```sql
SELECT column1, column2, ...
FROM tableName
WHERE columnName IN (value1, value2, ...);
```

### Example 1: Using IN Operator
#### Table: Student
| sid | name   | age | gender |
|-----|--------|-----|--------|
| 1   | Rohan  | 19  | M      |
| 2   | Rohit  | 20  | M      |
| 3   | Rahul  | 18  | M      |
| 4   | Raksha | 22  | F      |

#### Query
```sql
SELECT *
FROM studentinfo
WHERE age IN (18, 19);
```

#### Output
| id | name   | age | gender | city       |
|----|--------|-----|--------|------------|
| 1  | Rohan  | 19  | M      | Bengaluru  |
| 3  | Rahul  | 18  | M      | London     |
| 4  | Varsha | 18  | F      | Mumbai     |

### Example 2: Using NOT IN Operator
The **NOT IN** operator excludes rows where a column's value matches any value in a specified list.

#### Query
```sql
SELECT *
FROM studentinfo
WHERE id NOT IN (1, 2, 3);
```

#### Output
| id | name    | age | gender | city       |
|----|---------|-----|--------|------------|
| 4  | Varsha  | 18  | F      | Mumbai     |
| 5  | Sushil  | 20  | M      | Bengaluru  |
| 6  | Raksha  | 21  | F      | Pune       |

### Notes
- The **IN** operator is a concise way to filter specific values, as opposed to writing multiple `OR` conditions.
- The **NOT IN** operator is useful when excluding specific values from the results.

