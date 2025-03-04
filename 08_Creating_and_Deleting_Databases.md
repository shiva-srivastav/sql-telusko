# Creating and Deleting Databases
Creating and deleting databases are fundamental operations in SQL. These commands allow users to manage databases efficiently. SQL commands are **case-insensitive**, meaning they can be written in either uppercase or lowercase. However, by convention, SQL commands are usually written in **uppercase** to enhance readability.

### 1. Creating a Database
To create a new database, use one of the following commands:
```sql
CREATE DATABASE db_name;
CREATE SCHEMA db_name;
```
Both commands perform the same function: creating a new database.

### Conditional Creation
If you want to create a database **only if it does not already exist**, use:
```sql
CREATE DATABASE IF NOT EXISTS db_name;
```
This ensures that the database is created only if it is not already present, preventing errors when running the command multiple times.

### Example:
```sql
CREATE SCHEMA telusko_db;
CREATE DATABASE IF NOT EXISTS telusko_db;
```

### 2. Deleting a Database
To delete an existing database, use one of the following commands:
```sql
DROP DATABASE db_name;
DROP SCHEMA db_name;
```
These commands permanently remove the database and all of its associated data, so they should be used with caution.

### Example:
```sql
DROP DATABASE telusko_db;
```

### Important Notes:
- **Dropping a database is irreversible**—ensure you have a backup if necessary.
- Deleting a database will remove all tables and data within it.
