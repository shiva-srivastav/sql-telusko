# BETWEEN and NOT BETWEEN Operator in SQL

### Definition
The **BETWEEN** operator in SQL is used to filter records where a column's value lies within a specified range, inclusive of the range's boundaries.

### Syntax
```sql
SELECT column1, column2, ...
FROM tableName
WHERE columnName BETWEEN value1 AND value2;
```

### Example 1: Using BETWEEN Operator
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
WHERE age BETWEEN 18 AND 20;
```

#### Output
| id | name   | age | gender | city       |
|----|--------|-----|--------|------------|
| 1  | Rohan  | 18  | M      | Bengaluru  |
| 2  | Rawal  | 19  | M      | London     |
| 3  | Rohit  | 20  | M      | Pune       |

### NOT BETWEEN Operator in SQL

### Definition
The **NOT BETWEEN** operator excludes records where a column's value lies within the specified range.

### Syntax
```sql
SELECT column1, column2, ...
FROM tableName
WHERE columnName NOT BETWEEN value1 AND value2;
```

### Example 2: Using NOT BETWEEN Operator
#### Query
```sql
SELECT *
FROM studentinfo
WHERE id NOT BETWEEN 1 AND 4;
```

#### Output
| id | name    | age | gender | city       |
|----|---------|-----|--------|------------|
| 5  | Sushil  | 20  | M      | Bengaluru  |
| 6  | Raksha  | 21  | F      | Pune       |

### Notes
- The **BETWEEN** operator is inclusive of the boundary values.
- The **NOT BETWEEN** operator helps exclude rows that fall within a specific range.

