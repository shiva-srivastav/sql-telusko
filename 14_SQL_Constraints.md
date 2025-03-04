# SQL Constraints

SQL constraints are rules applied to table columns to enforce data integrity and maintain accurate and reliable data in the database.

### Types of SQL Constraints:
1. **NOT NULL** → Ensures that a column cannot have a NULL (empty) value.
2. **CHECK** → Enforces a condition on the values allowed in a column.
3. **DEFAULT** → Sets a default value for a column if no value is provided during an `INSERT` operation.
4. **UNIQUE** → Ensures all values in a column (or combination of columns) are unique across the entire table.
5. **FOREIGN KEY** → Establishes a link between data in two tables.
6. **PRIMARY KEY** → Uniquely identifies each record in a table.

📌 **Note:** A table can have only **one** primary key, but it can have **multiple unique columns**.

---

### Example: Implementing SQL Constraints

**Step 1: Create Table with Constraints**
```sql
CREATE TABLE studentInfo (
    id INT NOT NULL,
    name VARCHAR(40) NOT NULL,
    age INT NOT NULL CHECK (age >= 18),
    gender VARCHAR(10) NOT NULL,
    phone VARCHAR(10) NOT NULL UNIQUE,
    city VARCHAR(20) DEFAULT 'Bengaluru',
    PRIMARY KEY (id)
);
```

**Step 2: Insert Data into `studentInfo` Table**
```sql
-- Inserting a valid record
INSERT INTO studentInfo (id, name, age, gender, phone, city) 
VALUES (1, 'Rahul', 19, 'M', '423146', 'Bengaluru');

-- Using DEFAULT constraint (city will automatically be 'Bengaluru')
INSERT INTO studentInfo (id, name, age, gender, phone) 
VALUES (2, 'Rohit', 20, 'M', '425146');

-- Violating UNIQUE constraint (phone number must be unique)
INSERT INTO studentInfo (id, name, age, gender, phone, city) 
VALUES (3, 'Sushil', 22, 'M', '425146'); -- ❌ This will cause an error

-- Using CHECK constraint (age must be 18 or above)
INSERT INTO studentInfo (id, name, age, gender, phone, city) 
VALUES (4, 'Harsh', 18, 'M', '424156');
```

### Error Handling:
**1. UNIQUE Constraint Violation:**
```plaintext
ERROR 1062 (23000): Duplicate entry '425146' for key 'phone'
```
**Solution:** Ensure that phone numbers are unique before inserting.

**2. CHECK Constraint Violation (if age < 18):**
```plaintext
ERROR 3819 (HY000): Check constraint 'studentInfo_chk_1' is violated.
```
**Solution:** Insert only records where `age >= 18`.

---

SQL constraints help maintain **data integrity** and **consistency** by enforcing rules on columns. Using constraints effectively prevents invalid data entry and ensures database reliability.
