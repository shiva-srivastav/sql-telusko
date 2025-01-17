# DISTINCT Operator in SQL

### Definition
The **DISTINCT** operator in SQL is used to remove duplicate records from the result set. It ensures that only unique values are returned for the specified column(s).

### Syntax
```sql
SELECT DISTINCT column1, column2, ...
FROM tableName;
```

### Key Points
- It applies to the selected columns and filters out duplicate rows.
- Can be combined with the **ORDER BY** clause to sort the unique results.

### Example 1: Basic DISTINCT Usage
#### Query
```sql
SELECT DISTINCT city
FROM studentinfo;
```

#### Table: Student
| sid | name   | age | gender | city       |
|-----|--------|-----|--------|------------|
| 1   | Rohan  | 19  | M      | Pune       |
| 2   | Anjali | 18  | F      | Bengaluru  |
| 3   | Mehtab | 18  | M      | Pune       |
| 4   | Raksha | 22  | F      | Bengaluru  |

#### Output
| city       |
|------------|
| Pune       |
| Bengaluru  |

### Example 2: DISTINCT with ORDER BY
#### Query
```sql
SELECT DISTINCT city
FROM studentinfo
ORDER BY city;
```

#### Output
| city       |
|------------|
| Bengaluru  |
| Pune       |

### Notes
- The **DISTINCT** operator is useful for analyzing unique values in a column.
- When combined with **ORDER BY**, it sorts the unique values in ascending (default) or descending order.
- Applies to the result set after the SELECT clause is processed.

