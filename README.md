mysql_commands_common
=====================

It seems I use a lot of these MySQL commands when managing my databases.  You must be in the MySQL interpreter to run these.

For examples, the database is called testdb, the user is called admin

--Create and Drop Database--
```
create database foo;

drop database foo;
```
--Triggers--

Showing Triggers
```
show triggers from <database name>;
```
Deleting Triggers
```
drop trigger <trigger name>;
```

--Views--

List Database Views
```
SHOW FULL TABLES IN hw WHERE TABLE_TYPE LIKE 'VIEW';
```

Create Database View
```
DROP VIEW IF EXISTS testview;

CREATE VIEW testview AS

SELECT a.id, b.table1_id, a.name, b.order
FROM table1 a, table2 b
WHERE a.id = b.table1_id;
```
Alter Database View
```
ALTER VIEW testview AS

SELECT a.id, b.table1_id, a.name, b.order, b.create_date
FROM table1 a, table2 b
WHERE a.id = b.table1_id;
```
--Backup Databases--

All databases
```
mysqldump --user=<id> --password=<password> --all-databases  > mydb_dump.sql
```
Single database
```
mysqldump --user=<id> --password=<password> testdb  > testdb_dump.sql
```

--Restore Databases--

Note: You need to run the create database command first, or have a valid database available, albeit empty it, or whatever.

```
mysql -uroot -p foo_db < hw_aws_prod.sql 
```
