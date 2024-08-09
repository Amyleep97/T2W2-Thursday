# T2W2-Thursday

# What is a PostgreSQL?

- It is a structured query languages, they are used to deal with data base in a well formated way.
- They have their own documentation it will have in depth information
- It's a powerful, open source object-relational database system that uses and extends the SQL language combined with many features that safely store and scale the most complicated data workloads.
- Has different data types

# Data types it supports

- Primitives: Integer, Numeric, String, Boolean
- Structured: Date/Time, Array, Range/Multirange, UUID
- Document: JSON/JSONB, XML, Key-value (Hstore)
- Geometry: Point, Line, Circle, Polygon
- Customizations: Composite, Custom Types
  
# Why use PostgreSQL

- Data types
- Data Integrity
- Concurrency, Performance
- Reliablity, Disaster Recovery 
- Security 
- Extensibility 
- Internationalisation, Text Search

# How to check if you have it installed in WSL

``` 
psql --version 
```

- Check if it is working using this command 
``` 
service postgresql status 
```

# How to install it 

```
sudo -u postgres psql 
```
- If you see 
```
postgres=# 
```
- You can then type in this command
``` 
  \l 
```
- You can now see the list of databases in the system 
- If stuck use 
```
Ctrl + l 
 ```
``` 
q 
```
  
# How to Create a database

  - Type in 
``` 
CREATE DATABASE 
``` 
- Then what you would like to call it for example 
``` 
CREATE DATABASE college; 
``` 
- Always use a semicolumn unless its a query command
  
# Example of some Query commands:

``` 
\c 
\l
\comminfo 
```
  
 # How to see the connnection information

- Type in 
  

```
\conninfo 
 ```

 # How to move into a different database

- To move up into a different database use this command  
```
\c 
```
- For example if you would like to go into the "college" database you would type in
```
\c college 
```
- This should give you a message saying 
``` 
" You are now connected to the database "college" as user "postgres". "
```


# How to see List of Users

- Use this command 
```
\du
```
# How to see list of Tables

- Use this command

```
\dt
```

# How to Create a table

- Type in 

```
CREATE TABLE
```
- Then the name of what you would like to name it same as when you created a Database.

# Example of making a table:

```
college=# CREATE TABLE student(
college(# student_id SERIAL PRIMARY KEY,
college(# student_name VARCHAR(100) NOT NULL,
college(# age INTEGER NOT NULL
college(# );
``` 

# How to view your table that has been created

``` 
\d student
```
# How to see your errors and clear out the buffer

``` 
Ctrl + c
```

# Inserting into a table 

- Example of inserting the student age:
  
```
INSERT INTO student (student_name, age) VALUES ('David', 20), ('John', 22);
```

# How to view everything in the table

``` 
SELECT * FROM student;
```
- The astrict stands for "everything"

# How to alter the values

```
ALTER TABLE student ADD COLUMN address VARCHAR(255);
```
- To change the name of a column (could be a spelling error) type in 

```
ALTER TABLE student RENAME COLUMN sudent_id TO student_id;
```

- If you want to add in more to the table type in:
  
```
INSERT INTO student (student_name, age, address) VALUES ('Alice', 25, NULL), ('Bob', 19, 'Sydney'), ('Jack', 20, 'Melbourne');
```

# How to write a condition

``` 
SELECT * FROM student WHERE address='Sydney';
```

- You can have a conditional select as well for example in this case:

``` 
 SELECT * FROM student WHERE age >21;
```
- It will give you this result:
  
``` 
student_id | student_name | age | address
------------+--------------+-----+---------
          2 | John         |  22 |
          5 | Alice        |  25 |
(2 rows)
```

# How to set the address in the table

```
 UPDATE student SET address='Brisbane' WHERE student_name='David';
```

- What ever changes are made to the table it will always be displayed at the end, if you want it to be in order use this command:
  
```
college=# SELECT * FROM student ORDER BY student_id;
```
# Setting different address for different"student_id"

```
UPDATE student SET address='Sydney' WHERE student_id=2 OR student_id=3 ;
```

