# MySQL Workbench & CLI Client Overview

MySQL provides two main interfaces for database management:
1. **MySQL Workbench** - A graphical user interface (GUI) for managing databases.
2. **MySQL Command Line Interface (CLI)** - A text-based interface to execute SQL commands.

Both interfaces allow users to create, manage, and interact with databases.


### MySQL Workbench
#### Key Features:
- **Default Connection**: MySQL Workbench provides a default connection **(Local Instance MySQL80)**.
- **Localhost Connection**: The term `localhost` signifies that MySQL Workbench is connected to the MySQL Server running on the same system.
- **Creating a New Connection**:
  1. Open MySQL Workbench.
  2. Click on **+ (New Connection)**.
  3. Enter a **Connection Name**.
  4. Verify **Hostname** and **Username**.
  5. Store the password securely in **Vault**.
  6. Click **OK** to create the connection.
- **Multiple Connections**: Users can create multiple connections to different MySQL servers.
- **Viewing Available Databases**:
  ```sql
  SHOW DATABASES;
  ```
  This command lists all the databases available in the server.



### MySQL Command Line Interface (CLI)
#### Key Features:
- The CLI provides a text-based interface for executing MySQL commands.
- All operations that can be performed in MySQL Workbench can also be executed in the CLI.
- **Connecting to MySQL via CLI**:
  ```sh
  mysql -u root -p
  ```
  This command prompts for a password and connects to MySQL.
- **Viewing Available Databases in CLI**:
  ```sql
  SHOW DATABASES;
  ```
- **Selecting a Database**:
  ```sql
  USE database_name;
  ```
- **Displaying Tables in a Database**:
  ```sql
  SHOW TABLES;
  ```

  Both MySQL Workbench and CLI are powerful tools for database management. While the GUI is user-friendly for beginners, the CLI is essential for automation and scripting.
