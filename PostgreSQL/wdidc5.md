## Learning Objectives

- explain what a database is and why you would use one
- explain the difference between a database managment system and a database
- explain how a DBMS, a database and SQL relate to own another
- Describe the basic parts of a schema(using ERD's), entities and attributes
- Create ERD's for domain/database modeling
- Explain ACID in laymans terms
- describe a database schema and how it relates to tables, rows and columns
- explain what primary keys are and how they are used
- define CRUD and the 4 different ways data can be manipulated
- explain database normalization and how it relates to DRY
- describe how database index works
- Set up a PostgreSQL database schema with a saved SQL file
- Seed a PostgreSQL database with a saved SQL file
- Execute basic SQL commands to execute CRUD actions in a database
  - CREATE/DROP DATABASE
  - CREATE/DROP TABLE
  - INSERT - Create
  - SELECT - Read
  - UPDATE - Update
  - DELETE - Destroy

### Relationships
- one-to-one
- one-to-many
- many-to-many

### ERD(Entity Relationship Diagram)
- Entities(tables/models)
- Relationships
- Attributes

### Installing PostgreSQL
```bash
$ brew update
$ brew doctor
$ brew install postgresql
$ initdb /usr/local/var/postgres -E utf8
$ mkdir -p ~/Library/LaunchAgents
$ cp /usr/local/Cellar/postgresql/<<<YOUR_PSQL_VERSION_NUMBER>>>/homebrew.mxcl.postgresql.plist ~/Library/LaunchAgents/
$ launchctl load -w ~/Library/LaunchAgents/homebrew.mxcl.postgresql.plist
$ gem install pg
```

### Databases
#### Why do we need them?
- persistence
- querying
- concurrency
- scalability

#### ACID
- atomicity
- consistency
- isolation
- durability

#### CRUD
- Create
- Read
- Update
- Destroy

### Relational Databases

#### Database Schema
- How a relational database is typically organized
  - tables
    - columns- attributes and fields for the content you're storing
    - rows- individual records of data
- Primary Keys
- Indexing

### SQL(Structured Query Language)

#### SQL Data Types
There are lots, these are some of the ones we'll use
- boolean
- integer
- float
- text/varchar
- null
- date
- time
- [lots more](http://www.postgresql.org/docs/9.3/interactive/datatype.html)

#### SQL Syntax
- all statements end with a semicolon
- white space doesn't matter
- use only single quotes to denote strings, double quotes are for table or column identifiers
- groups things with parentheses
- [Postgres docs](http://www.postgresql.org/docs/9.4/interactive/index.html)
- [style guide for SQL](http://leshazlewood.com/software-engineering/sql-style-guide/)

#### Creating a DB
- `CREATE DATABASE <database_name>`
- connecting to a database `\c <database_name`
- accessing tables once in a database `\d`
- creating a table(example):
```sql
CREATE TABLE students (
  id SERIAL PRIMARY KEY,
  first_name TEXT NOT NULL,
  last_name TEXT NOT NULL,
  age INT NOT NULL,
  job TEXT
);
```
- the format for arguments for attributes in a table creation is:
`attribute_name TYPE_OF_FIELD CONSTRAINT1 CONSTRAINT2`

To load a schema or another SQL file:
```bash
$ psql -d database_name < schema_file.sql
```

#### CRUD in SQL
##### Creating Records
- `INSERT INTO students (first_name, last_name, age) VALUES ('andy', 'kim', 29);`

##### Reading records
- `SELECT * FROM students`
- the `WHERE` clause
  - To use the where clause, we need a field to compare, an operator specifying the type of comparison to be made, and a value that represents our criterion
  - `SELECT * FROM students WHERE last_name = 'Shannon'`
  - `SELECT * FROM students WHERE age >= 25`

##### Updating Records
- UPDATE students SET job = 'developer' WHERE name = 'andy';

##### Deleting Records
- DELETE FROM students WHERE age > 25;
