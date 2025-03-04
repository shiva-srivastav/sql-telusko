# SELECT Command: Retrieving Data & Using Aliases

SQL provides the `SELECT` statement to retrieve data from one or more tables.

### Retrieving Data from Tables

#### Select All Columns
To fetch all columns from a table, use:
```sql
SELECT * FROM table_name;
```
**Example:**
```sql
SELECT * FROM employees;
```
This query retrieves all columns from the `employees` table.

#### Select Specific Columns
To fetch specific columns, specify their names:
```sql
SELECT column1, column2 FROM table_name;
```
**Example:**
```sql
SELECT id, emp_name, emp_age, emp_city FROM employee;
```
This query retrieves only the `id`, `emp_name`, `emp_age`, and `emp_city` columns from the `employee` table.


### Using Aliases in SQL
- Aliases are temporary names assigned to columns or tables in a query to improve readability.
- Aliases can be assigned using the `AS` keyword.
- If an alias consists of multiple words, double quotes ("") or backticks (`\``) are used.

#### Using Column Aliases
```sql
SELECT column_name AS alias_name FROM table_name;
```
**Example:**
```sql
SELECT id AS "Emp ID", 
       emp_name AS "Employee Name", 
       emp_age AS Age, 
       emp_city AS City 
FROM employee;
```

 **Explanation:**
- `id` is displayed as **Emp ID**
- `emp_name` is displayed as **Employee Name**
- `emp_age` is displayed as **Age**
- `emp_city` is displayed as **City**

#### Using Table Aliases
Table aliases are useful when working with **joins** or **self-joins**.
```sql
SELECT t1.column_name 
FROM table_name AS t1;
```
**Example:**
```sql
SELECT e.id, e.emp_name 
FROM employee AS e;
```

**Explanation:**
- The `employee` table is temporarily renamed as `e`, so column names can be prefixed with `e.`

### Conclusion
Using **SELECT** effectively helps retrieve the necessary data, while **aliases** improve query readability and efficiency, especially in complex queries.

