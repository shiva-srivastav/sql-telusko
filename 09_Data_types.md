# Data Types in SQL

Data types define the type of data that can be stored in a table column. Choosing the right data type ensures efficient storage and data integrity.

### Common Data Types
#### 1. Numeric Data Types
- **INT**: Used to store non-decimal numeric data. It can hold both positive and negative numbers.
  ```sql
  CREATE TABLE employees (
      id INT PRIMARY KEY,
      age INT
  );
  ```
- **FLOAT**: Used to store real numbers with decimal values.
  ```sql
  CREATE TABLE products (
      product_id INT PRIMARY KEY,
      price FLOAT
  );
  ```

#### 2. String Data Types
- **CHAR(n)**: Used to store fixed-length text data. The length `n` must be specified.
  ```sql
  CREATE TABLE users (
      username CHAR(10)
  );
  ```
- **VARCHAR(n)**: Used to store variable-length text data, where `n` is the maximum length.
  ```sql
  CREATE TABLE customers (
      name VARCHAR(50)
  );
  ```

#### 3. Date & Time Data Types
- **DATE**: Stores date values in the format `YYYY-MM-DD`.
  ```sql
  CREATE TABLE events (
      event_date DATE
  );
  ```
- **TIME**: Stores time values in the format `HH:MI:SS`.
  ```sql
  CREATE TABLE shifts (
      shift_time TIME
  );
  ```
- **DATETIME**: Stores both date and time values.
  ```sql
  CREATE TABLE logs (
      log_time DATETIME
  );
  ```

#### 4. Boolean Data Type
- **BOOLEAN**: Stores `TRUE` or `FALSE` values.
  ```sql
  CREATE TABLE users (
      is_active BOOLEAN
  );
  ```

### Summary
- Use **INT** for whole numbers where decimals are not needed.
- Use **FLOAT** for values requiring decimal precision, like prices.
- Use **CHAR** when all values are of a fixed length, and **VARCHAR** when lengths vary.
- Use **DATE**, **TIME**, or **DATETIME** depending on the specific requirement of storing time-related information.
- Use **BOOLEAN** for storing true/false values efficiently.

By selecting the correct data type, we can optimize storage, improve performance, and maintain data integrity.
