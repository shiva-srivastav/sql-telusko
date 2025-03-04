# Creating Tables in the Database

- While creating a table, it is required need to specify:
  - **Table name**
  - **Column names**
  - **Data types** for each column
- Each column has a specific data type that defines the kind of data it can store.
- Multiple tables can be created within a single database.

### Syntax for Creating a Table
```sql
CREATE TABLE table_name (
    columnName datatype,
    columnName datatype
);
```

### Selecting a Database
Before creating tables, you must specify the database you want to use:
```sql
USE db_name;
```
This ensures that the tables are created in the correct database.

### Viewing Table Structure
To view the structure of a table in a database, use:
```sql
SELECT * FROM db_name.table_name;
```

### Example: Creating Tables
#### Step 1: Use the Database
```sql
USE telusko_db;
```

#### Step 2: Create `personalInfo` Table
```sql
CREATE TABLE personalInfo (
    id INT, 
    name VARCHAR(40),
    date_of_birth DATE,
    city VARCHAR(40)
);
```

#### Step 3: Create another `personalEducation` Table
```sql
CREATE TABLE personalEducation (
    eid INT,
    Courses VARCHAR(30),
    city_of_Education VARCHAR(40)
);
```
