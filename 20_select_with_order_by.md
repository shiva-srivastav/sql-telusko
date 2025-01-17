# SELECT with ORDER BY in SQL

### Definition
The **ORDER BY** clause in SQL is used to sort the result set of a query by one or more columns. It can sort the data in ascending (default) or descending order.

### Syntax
```sql
SELECT columns
FROM tableName
ORDER BY column1 [ASC | DESC], column2 [ASC | DESC], ...;
```

### Key Points
- **ASC**: Sorts the data in ascending order (default).
- **DESC**: Sorts the data in descending order.
- Can be used with one or multiple columns.
- Can be combined with the **WHERE** clause to filter and sort results.

### Example 1: Basic ORDER BY
#### Query
```sql
SELECT *
FROM studentinfo
ORDER BY name;
```

#### Output
| id | name    | age | gender | city       |
|----|---------|-----|--------|------------|
| 5  | Anjali  | 21  | F      | Pune       |
| 3  | Mehtab  | 20  | M      | Pune       |
| 2  | Rawal   | 19  | M      | London     |
| 1  | Rohan   | 18  | M      | Bengaluru  |
| 4  | Varsha  | 18  | F      | Mumbai     |

### Example 2: ORDER BY with DESC
#### Query
```sql
SELECT *
FROM studentinfo
ORDER BY age DESC;
```

#### Output
| id | name    | age | gender | city       |
|----|---------|-----|--------|------------|
| 5  | Sushil  | 22  | F      | Bengaluru  |
| 6  | Anjali  | 21  | F      | Pune       |
| 3  | Mehtab  | 20  | M      | Pune       |
| 2  | Rawal   | 19  | M      | London     |
| 1  | Rohan   | 18  | M      | Bengaluru  |

### Example 3: ORDER BY with WHERE Clause
#### Query
```sql
SELECT *
FROM studentinfo
WHERE age = 18
ORDER BY name;
```

#### Output
| id | name   | age | gender | city       |
|----|--------|-----|--------|------------|
| 4  | Varsha | 18  | F      | Mumbai     |
| 1  | Rohan  | 18  | M      | Bengaluru  |

### Notes
- By default, **ORDER BY** sorts in ascending order.
- To sort by multiple columns, specify them in the order you want, separated by commas.
- When used with **WHERE**, it first filters the records and then sorts them.
- Sorting with **DESC** is helpful when the latest or largest values are needed first.

