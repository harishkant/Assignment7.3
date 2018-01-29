# Assignment7.3





Hive Data Defination
HiveQL DDL statements are documented here, including:

CREATE DATABASE/SCHEMA, TABLE, VIEW, FUNCTION, INDEX
DROP DATABASE/SCHEMA, TABLE, VIEW, INDEX
TRUNCATE TABLE
ALTER DATABASE/SCHEMA, TABLE, VIEW
MSCK REPAIR TABLE (or ALTER TABLE RECOVER PARTITIONS)
SHOW DATABASES/SCHEMAS, TABLES, TBLPROPERTIES, VIEWS, PARTITIONS, FUNCTIONS, INDEX[ES], COLUMNS, CREATE TABLE
DESCRIBE DATABASE/SCHEMA, table_name, view_name
PARTITION statements are usually options of TABLE statements, except for SHOW PARTITIONS.

------------------------------------------------------------------------------------------------------

Hive Data Manipulation Language
In this chapter, you will learn about the following recipes:

Loading files into tables

Inserting data into Hive tables from queries

Inserting data into dynamic partitions

Writing data into files from queries

Enabling transactions in Hive

Inserting values into tables from SQL

Updating data

Deleting data

-----------------------------------------------------------------------------------------------------------

HiveQL: Data Manipulation
Loading Data into Managed Tables
Since Hive has no row-level insert, update, and delete operations, the only way to put data into an table is to use one of the “bulk” load operations. Or you can just write files in the correct directories by other means.

We saw an example of how to load data into a managed table in Partitioned, Managed Tables, which we repeat here with an addition, the use of the OVERWRITE keyword:

LOAD DATA LOCAL INPATH 'user/acadgild'
OVERWRITE INTO TABLE employees
PARTITION (country = 'US', state = 'CA');
This command will first create the directory for the partition, if it doesn’t already exist, then copy the data to it.

If the target table is not partitioned, you ...
