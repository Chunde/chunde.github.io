---
layout: post  
title: MySQL Management Commands  
date: 2025-07-05 21:30:46  
description: A reference table of essential MySQL administration commands with explanations  
tags: MySQL Database SQL Administration  
tabs: true  
---  

| Command | Explanation |  
|---------|-------------|  
| `mysql -u [username] -p` | Connects to MySQL server with username/prompt for password |  
| `SHOW DATABASES;` | Lists all databases on the server |  
| `USE [database_name];` | Selects a database for operations |  
| `SHOW TABLES;` | Displays all tables in the current database |  
| `DESCRIBE [table_name];` | Shows the structure of a table (columns, types, etc.) |  
| `CREATE DATABASE [db_name];` | Creates a new database |  
| `DROP DATABASE [db_name];` | Permanently deletes a database |  
| `CREATE TABLE [table_name] (...);` | Creates a new table with specified columns |  
| `ALTER TABLE [table_name] ADD [column] [type];` | Adds a column to an existing table |  
| `GRANT ALL ON [db_name].* TO '[user]'@'[host]';` | Grants full privileges to a user on a database |  
| `FLUSH PRIVILEGES;` | Reloads privilege tables after permission changes |  
| `SHOW PROCESSLIST;` | Displays active server threads/queries |  
| `KILL [process_id];` | Terminates a running MySQL process |  
| `mysqldump -u [user] -p [db_name] > backup.sql` | Creates a database backup file |  
| `SOURCE backup.sql;` | Restores database from backup file |  
| `SELECT User, Host FROM mysql.user;` | Lists all MySQL user accounts |  

**Key Notes:**  
1. Most commands require semicolon `;` termination  
2. Administrative commands often require root/administrative privileges  
3. Backup/restore operations are typically run from system shell (not MySQL prompt)  

For user management, common commands include:  
- `CREATE USER`  
- `DROP USER`  
- `SET PASSWORD`  
- `RENAME USER`  

For performance monitoring:  
- `SHOW STATUS`  
- `SHOW VARIABLES`  
- `EXPLAIN [query]`  

Remember to always backup databases before major operations like `DROP` or structural changes.