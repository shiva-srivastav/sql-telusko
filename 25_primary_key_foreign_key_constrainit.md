# Primary Key and Foreign Key Constraints in SQL

### Definition
#### Primary Key
- A **Primary Key** is a column (or combination of columns) in a table that uniquely identifies each row.
- A table can only have one primary key.

#### Foreign Key
- A **Foreign Key** is a column (or combination of columns) in one table that establishes a link to the **Primary Key** of another table.
- It is used to maintain referential integrity between tables.

### Key Points
#### Primary Key
- Must contain unique values.
- Cannot have NULL values.

#### Foreign Key
- References the primary key in another table.
- The values in the foreign key column must match the values in the referenced primary key column or be NULL.

### Syntax
#### Creating a Primary Key
```sql
CREATE TABLE tableName (
    column1 DataType,
    column2 DataType,
    PRIMARY KEY (column1)
);
```

#### Creating a Foreign Key
```sql
CREATE TABLE tableName (
    column1 DataType,
    column2 DataType,
    FOREIGN KEY (column2) REFERENCES otherTable(column1)
);
```

### Example 1: Primary Key
#### Query
```sql
CREATE TABLE city (
    id INT AUTO_INCREMENT,
    city_name VARCHAR(20),
    PRIMARY KEY (id)
);

INSERT INTO city (city_name)
VALUES ('Pune'), ('Bengaluru'), ('Mumbai'), ('London');
```

#### Output
| id | city_name   |
|----|-------------|
| 1  | Pune        |
| 2  | Bengaluru   |
| 3  | Mumbai      |
| 4  | London      |

### Example 2: Foreign Key
#### Query
```sql
CREATE TABLE student (
    id INT AUTO_INCREMENT,
    name VARCHAR(50),
    age INT,
    city INT,
    PRIMARY KEY (id),
    FOREIGN KEY (city) REFERENCES city(id)
);

INSERT INTO student (name, age, city)
VALUES ('Nikhil', 20, 3), ('Rahul', 22, 1);
```

#### Output
| id | name   | age | city |
|----|--------|-----|------|
| 1  | Nikhil | 20  | 3    |
| 2  | Rahul  | 22  | 1    |

### Conditions for Primary Key
- Unique constraint on the column(s).
- Column(s) cannot have NULL values.

### Conditions for Foreign Key
- The referenced table must have a primary key.
- Values in the foreign key column must match values in the referenced primary key column or be NULL.

### Why Use Primary and Foreign Keys
- **Primary Key** ensures data uniqueness and prevents duplicate records.
- **Foreign Key** establishes relationships between tables, enabling data consistency and referential integrity.

### Notes
- A single table can have multiple foreign keys, but only one primary key.
- Violating foreign key constraints (e.g., inserting a non-existent reference) will result in an error.

