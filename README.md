# MSSQL-CheatSheet

### General Syntax

| Action              | Command Example                                                |
|---------------------|----------------------------------------------------------------|
| **Select Data**     | `SELECT column1, column2 FROM table_name;`                     |
| **Insert Data**     | `INSERT INTO table_name (column1, column2) VALUES (val1, val2);` |
| **Update Data**     | `UPDATE table_name SET column1 = val1 WHERE condition;`        |
| **Delete Data**     | `DELETE FROM table_name WHERE condition;`                     |
| **Filter Data**     | `SELECT * FROM table_name WHERE column = 'value';`            |
| **Sort Data**       | `SELECT * FROM table_name ORDER BY column1 ASC/DESC;`         |


### DDL (Data Definition Language)

| Action                   | Command Example                                           |
|--------------------------|----------------------------------------------------------|
| **Create Database**      | `CREATE DATABASE db_name;`                               |
| **Create Table**         | `CREATE TABLE table_name (column1 datatype, column2 datatype);` |
| **Alter Table (Add Column)** | `ALTER TABLE table_name ADD column_name datatype;`   |
| **Drop Table**           | `DROP TABLE table_name;`                                 |
| **Truncate Table**       | `TRUNCATE TABLE table_name;`                             |



### DML (Data Manipulation Language)

| Action                   | Command Example                                           |
|--------------------------|----------------------------------------------------------|
| **Insert Data**          | `INSERT INTO table_name VALUES (val1, val2, ...);`       |
| **Bulk Insert**          | `INSERT INTO table_name SELECT * FROM other_table;`      |
| **Update Data**          | `UPDATE table_name SET column1 = value WHERE condition;` |
| **Delete Data**          | `DELETE FROM table_name WHERE condition;`               |



### Query Clauses

| Clause         | Command Example                                                   |
|----------------|-------------------------------------------------------------------|
| **WHERE**      | `SELECT * FROM table_name WHERE column = 'value';`               |
| **ORDER BY**   | `SELECT * FROM table_name ORDER BY column1 DESC, column2 ASC;`   |
| **GROUP BY**   | `SELECT column, COUNT(*) FROM table_name GROUP BY column;`       |
| **HAVING**     | `SELECT column, COUNT(*) FROM table_name GROUP BY column HAVING COUNT(*) > 1;` |
| **TOP**        | `SELECT TOP 10 * FROM table_name;`                               |

---

### Joins

| Type            | Command Example                                                |
|------------------|---------------------------------------------------------------|
| **Inner Join**   | `SELECT * FROM A INNER JOIN B ON A.id = B.id;`                |
| **Left Join**    | `SELECT * FROM A LEFT JOIN B ON A.id = B.id;`                 |
| **Right Join**   | `SELECT * FROM A RIGHT JOIN B ON A.id = B.id;`                |
| **Full Join**    | `SELECT * FROM A FULL JOIN B ON A.id = B.id;`                 |
| **Cross Join**   | `SELECT * FROM A CROSS JOIN B;`                               |

---

### Functions

#### Aggregate Functions
| Function   | Example                            |
|------------|------------------------------------|
| **SUM**    | `SELECT SUM(column) FROM table;`  |
| **AVG**    | `SELECT AVG(column) FROM table;`  |
| **COUNT**  | `SELECT COUNT(*) FROM table;`     |
| **MAX**    | `SELECT MAX(column) FROM table;`  |
| **MIN**    | `SELECT MIN(column) FROM table;`  |

#### String Functions
| Function              | Example                               |
|-----------------------|---------------------------------------|
| **LEN**               | `SELECT LEN(column) FROM table;`     |
| **SUBSTRING**         | `SELECT SUBSTRING(column, 1, 3) FROM table;` |
| **CONCAT**            | `SELECT CONCAT(col1, ' ', col2) FROM table;` |
| **REPLACE**           | `SELECT REPLACE(column, 'old', 'new') FROM table;` |
| **UPPER / LOWER**     | `SELECT UPPER(column) FROM table;`   |

#### Date Functions
| Function         | Example                                      |
|------------------|----------------------------------------------|
| **GETDATE()**    | `SELECT GETDATE();`                         |
| **DATEADD**      | `SELECT DATEADD(day, 7, GETDATE());`         |
| **DATEDIFF**     | `SELECT DATEDIFF(day, '2023-01-01', GETDATE());` |
| **FORMAT**       | `SELECT FORMAT(GETDATE(), 'yyyy-MM-dd');`    |



### Indexes

| Action                   | Command Example                                            |
|--------------------------|-----------------------------------------------------------|
| **Create Index**         | `CREATE INDEX idx_name ON table_name (column);`           |
| **Unique Index**         | `CREATE UNIQUE INDEX idx_name ON table_name (column);`    |
| **Drop Index**           | `DROP INDEX idx_name ON table_name;`                      |


### Views, Stored Procedures, and Triggers

| Action                       | Command Example                                        |
|------------------------------|-------------------------------------------------------|
| **Create View**              | `CREATE VIEW view_name AS SELECT * FROM table_name;`  |
| **Stored Procedure**         | `CREATE PROCEDURE proc_name AS BEGIN SELECT * FROM table_name; END;` |
| **Trigger**                  | `CREATE TRIGGER trg_name AFTER INSERT ON table_name FOR EACH ROW AS BEGIN ... END;` |


### Backup and Restore

| Task                | Command Example                                               |
|---------------------|---------------------------------------------------------------|
| **Backup Database** | `BACKUP DATABASE db_name TO DISK = 'C:\backup.bak';`          |
| **Restore Database**| `RESTORE DATABASE db_name FROM DISK = 'C:\backup.bak';`       |


### Admin Commands

| Task                    | Command Example                                           |
|-------------------------|-----------------------------------------------------------|
| **List Databases**      | `SELECT name FROM sys.databases;`                        |
| **List Tables**         | `SELECT TABLE_NAME FROM INFORMATION_SCHEMA.TABLES;`      |
| **Check Indexes**       | `SELECT * FROM sys.indexes WHERE object_id = OBJECT_ID('table_name');` |
| **Kill Process**        | `KILL session_id;`                                       |

