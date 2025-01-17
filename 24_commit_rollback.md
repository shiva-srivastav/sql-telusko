# COMMIT and ROLLBACK in SQL

### Definition
**COMMIT** and **ROLLBACK** are SQL commands used to manage transactions:
- **COMMIT**: Saves all the changes made during the current transaction permanently to the database.
- **ROLLBACK**: Reverts all the changes made during the current transaction back to the state before the transaction started.

### Syntax
#### COMMIT
```sql
COMMIT;
```

#### ROLLBACK
```sql
ROLLBACK;
```

### Key Points
- A **transaction** is a sequence of operations performed as a single logical unit of work.
- Transactions begin automatically when a DML (Data Manipulation Language) statement like `INSERT`, `UPDATE`, or `DELETE` is executed.
- Changes made during a transaction are temporary until a **COMMIT** or **ROLLBACK** is issued.
- **COMMIT** makes the changes permanent, while **ROLLBACK** undoes the changes.

### Example 1: Using COMMIT
#### Scenario
You want to add a new employee to the `employee` table.

#### Query
```sql
BEGIN;
INSERT INTO employee (id, emp_name, emp_age, emp_city)
VALUES (4, 'Anjali', 22, 'Pune');
COMMIT;
```

#### Before Transaction
| id | emp_name | emp_age | emp_city   |
|----|----------|---------|------------|
| 1  | Rohan    | 28      | Delhi      |
| 2  | Rohit    | 24      | Bengaluru  |
| 3  | Ravi     | 28      | Mumbai     |

#### After COMMIT
| id | emp_name | emp_age | emp_city   |
|----|----------|---------|------------|
| 1  | Rohan    | 28      | Delhi      |
| 2  | Rohit    | 24      | Bengaluru  |
| 3  | Ravi     | 28      | Mumbai     |
| 4  | Anjali   | 22      | Pune       |

### Example 2: Using ROLLBACK
#### Scenario
You mistakenly update the city of an employee and want to undo the change.

#### Query
```sql
BEGIN;
UPDATE employee
SET emp_city = 'Hyderabad'
WHERE id = 3;
ROLLBACK;
```

#### Before Transaction
| id | emp_name | emp_age | emp_city   |
|----|----------|---------|------------|
| 1  | Rohan    | 28      | Delhi      |
| 2  | Rohit    | 24      | Bengaluru  |
| 3  | Ravi     | 28      | Mumbai     |

#### After ROLLBACK
| id | emp_name | emp_age | emp_city   |
|----|----------|---------|------------|
| 1  | Rohan    | 28      | Delhi      |
| 2  | Rohit    | 24      | Bengaluru  |
| 3  | Ravi     | 28      | Mumbai     |

### When to Use COMMIT and ROLLBACK
- **COMMIT**:
  - After completing a sequence of operations successfully.
  - To ensure changes are saved permanently.
  - Use when you're confident that no errors exist in the transaction.
- **ROLLBACK**:
  - To undo unintended changes or errors during a transaction.
  - To ensure the database remains in a consistent state if an operation fails.

### Why Use COMMIT and ROLLBACK
- To maintain **data integrity** and prevent accidental or incomplete changes.
- To give flexibility in testing and undoing operations during a transaction.
- To ensure consistency in multi-step processes where all operations must succeed or none should be applied.

### Notes for Beginners
- Always use **COMMIT** or **ROLLBACK** explicitly if working in transactional mode.
- If auto-commit mode is on (default in some databases), each DML statement is automatically committed.
- Use **BEGIN** to start a transaction explicitly in environments where auto-commit is enabled.
- Carefully test queries in a transaction before committing to avoid unwanted changes.

