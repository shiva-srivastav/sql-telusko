# SELECT Command: SELECT with WHERE Clause

The **`WHERE` clause** is used in SQL to filter records based on specified conditions. This allows users to retrieve only the necessary data instead of fetching the entire table.


### Syntax of `WHERE` Clause
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```

### Example Queries
#### Select with a Specific Condition
```sql
SELECT * FROM personalInfo WHERE id = 1;
```
Retrieves all columns for the record where `id` is 1.

#### Filtering by City
```sql
SELECT * FROM personalInfo WHERE city = 'Pune';
```
Retrieves all records where the city is **Pune**.

#### Using Comparison Operators
```sql
SELECT * FROM personalInfo WHERE age >= 18;
```
Retrieves all records where `age` is **18 or older**.


### Using `WHERE` with Aliases
```sql
SELECT id AS "Emp ID", emp_name AS "Employee Name", emp_age AS Age, emp_city AS City 
FROM employee WHERE id = 3;
```
**Explanation:**
- Retrieves employee details **only** where `id = 3`.
- Uses **aliases** to rename columns for readability.


### Common Operators in `WHERE` Clause
| Operator | Description |
|----------|-------------|
| `=`  | Equal to |
| `!=` or `<>` | Not equal to |
| `>`  | Greater than |
| `<`  | Less than |
| `>=` | Greater than or equal to |
| `<=` | Less than or equal to |
| `AND` | Combines multiple conditions (both must be true) |
| `OR`  | Combines multiple conditions (either can be true) |

#### Example of Multiple Conditions
```sql
SELECT * FROM employee WHERE id = 2 AND age > 18;
```
It will retrieves records where 'id' is 2 and 'age' is greater than 18.

### Conclusion
The `WHERE` clause is essential for fetching specific records based on conditions. Using it effectively helps improve query efficiency and data retrieval accuracy.


