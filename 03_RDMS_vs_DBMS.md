# RDBMS vs DBMS

### **DBMS (Database Management System)**
- A DBMS is a software system that provides an organized way to store, manage, and retrieve data efficiently.
- It ensures that data can be stored in an **organized** manner and is **accessible anytime**.
- DBMS allows CRUD operations (Create, Read, Update, Delete) on databases.


### **RDBMS (Relational Database Management System)**
- RDBMS is an advanced version of DBMS where data is stored in the form of **relations (tables)**.
- Data is maintained using **structured tables** and relationships among them.
- It provides **data integrity, normalization, and relationships** between multiple tables, increasing efficiency.
- Storing data in multiple tables **improves performance and reduces redundancy**.


### **Example of RDBMS Schema**
Example of how data is stored in a relational model:

 **Student Table** (Table 1)
| sid | sname | sage | city |
|----|------|-----|------|
| 1  | Rohan | 18  | 1    |

 **City Table** (Table 2)
| id | city-name |
|----|-----------|
| 1  | Pune      |

Here, `city` in the **Student Table** is a **foreign key** referencing `id` in the **City Table**, forming a relationship between the two tables.

### **Popular RDBMS Databases**
- MySQL
- Oracle
- Microsoft SQL Server
