# Database 
It is a shared collection of data.

### File-based system
1. Data Redundancy.
2. Data inconsistency.
3. Difficult data access.
4. Security.
5. Data concurrent access.

## Database Management System (DBMS)
DBMS helps us to create, fetch and maintain data in the databases.

#### What it does?
1. Define data.
2. Manipulate data.
3. Data sharing.

#### What problems Database management system controls?
1. Control data redundancy (Normalization).
2. It helps us to put constraints.
3. Restriction to unauthorised access.
4. Easy backup and recovery functionality.

### Relational Database Management System (RDBMS)
RDBMS maintains data in the form of tables.
For ex: MySQL, pgSQL, sqlite and OracleSQL etc.

### SQL (Structured query langauage): 
It is a declarative language.

##### List all the databases
```
    SHOW DATABASES;
```

#### Create new Database

```
    CREATE DATABASE <name_of_the_database>;

    // For eg:
    CREATE DATABASE BLOGGING;
```

#### Start working on a database

```
    USE <name_of_the_database>;

    // For eg:
    USE BLOGGING;
```

#### Delete the whole database

```
    DROP DATABASE <name_of_the_db>

    // For eg:
    DROP DATABASE MIDAS;
```

#### List all the tables of the database

```
    SHOW TABLES;
```

#### Create a Table

```
    CREATE TABLE <name_of_the_table>(attribute1_name attribute1_type extra_properties, 
    attribute2_name, attribute2_type, extra_properties...);

    // For eg:
    CREATE TABLE BLOG(ID INT, TITLE VARCHAR(30), CONTENT VARCHAR(1200)); 

    // create table with properties to attribute
    CREATE TABLE ACTORS(NAME VARCHAR(20) NOT NULL, GENDER ENUM("MALE", "FEMALE", "OTHERS") 
    NOT NULL, NETWORTH DECIMAL, ID INT AUTO_INCREMENT, PRIMARY KEY(ID));

    // create table if not exist
    CREATE TABLE IF NOT EXISTS ACTORS(NAME VARCHAR(20) NOT NULL, GENDER ENUM("MALE", 
    "FEMALE", "OTHERS") NOT NULL, NETWORTH DECIMAL, ID INT AUTO_INCREMENT, PRIMARY KEY(ID));

```

#### Drop a table

```
    DROP TABLE <name_of_the_table>;

    // For eg:
    DROP TABLE BLOG;
```

#### Data types

```
    NUMERIC -> INT, DECIMAL, BIGINT etc...
    STRING -> CHAR, VARCHAR, ENUM etc...
    DATETIME -> DATE, TIME, DATETIME
    JSON
```

#### Get details about a table and it’s attribute

```
    DESCRIBE <table_name>
        or
    DESC <table_name>      

    // For eg:
    DESC BLOG;
```

#### Insert data in a table

```
    INSERT INTO <table_name> (column1_name, column2_name, column3_name) VALUES ("val1", 
    "val2", "val3");

    // for eg:
    // insert single data
    insert into actors(Name, Gender, Networth) values ("Shahrukh_Khan", "Male", 
    "7000000000");
    
    // insert multiple data
    insert into actors(Name, Gender, Networth) values ("Ranveer singh", "Male", 
    300000000), ("Salman Khan", "Male", 4000000), ("Aamir Khan", "Male", 900000000);
```

#### Retrieve everything from the table

```
    SELECT <attribute1> <attribute12> FROM <table_name>;

    // for getting all the attributes 
    SELECT * FROM <table_name>;
```

#### Where clause

```
    SELECT * FROM ACTORS WHERE NAME = "Aamir Khan";

    // for eg
    SELECT * FROM ACTORS WHERE NETWORTH > 50000000 AND ID > 3;
```

#### Operators used in MySQL

```
    >, <, >=, <=, !=, <> (not equal), =, IN etc.
```

#### Like

```
    SELECT col1, col2, .... FROM ACTORS WHERE col1 LIKE %some_string%;

    // for eg
    // here it denotes prefix matching i.e, get me all the rows where the name starts from
    // s and after that it can have anything.
    SELECT * FROM ACTORS WHERE NAME LIKE "S%";     // prefix match
    
    // here it denotes suffix matching i.e, get me all the rows where the name ends with
    // n and before that it can have anything.
    SELECT * FROM ACTORS WHERE NAME LIKE "%n";     // suffix match        
    
    // substring match 
    SELECT * FROM ACTORS WHERE NAME LIKE "%k%";

    // For databases
    SHOW DATABASES LIKE %<database_name>%
```

#### Combining query filters

```
    SELECT * FROM ACTORS WHERE NOT (NETWORTH > 50000000 AND ID > 3);

    SELECT * FROM ACTORS ORDER BY NETWORTH DESC, NAME DESC;
```

#### Update

```
    UPDATE ACTORS SET NAME = "SRK" WHERE NAME = "Shahrukh_Khan";
```

#### Make changes to structure of a table

```
    ALTER TABLE ACTORS ADD DOB DATETIME;

    // IFf you want to delete a column
    ALTER TABLE ACTORS DROP DOB;
```

#### Sort the data

```
    SELECT * FROM ACTORS ORDER BY NETWORTH DESC;

    SELECT * FROM ACTORS ORDER BY NETWORTH DESC, NAME DESC;
```

#### Get limited number of data

```
    SELECT * FROM ACTORS ORDER BY NETWORTH DESC, NAME DESC LIMIT 2;
```

#### Define the starting point from which we have to fetch the data

```
    SELECT * FROM ACTORS ORDER BY NETWORTH DESC, NAME DESC LIMIT 2 OFFSET 1;
```

#### ORM

```
    Object Relational Mapper

    Libraries that help you to actually do database queries but instead write SQL syntax, 
    you write object oriented syntax. 
```