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

- ``` psql --version ```

- Check if it is working using this command 
-  ``` service postgresql status ```

# How to install it 

- ``` sudo -u postgres psql ```

- If you see 
- ``` postgres=# ```
- You can then type in this command
- ``` \l ```
- You can now see the list of databases in the system 
- If stuck use ``` Ctrl l ``` if press ``` q ```
  
  # How to Create a database

  - Type in 
  - ``` CREATE DATABASE ``` Then what you would like to call it for example ``` CREATE DATABASE college; ``` always use a semicolumn when using a query operation otherwise you can write it as is. 
  
# How to see the connnection information

- Type in ``` \conninfo ```
  
  # How to move into a different database

- To move up into a different database use the ``` \c ``` command for example if you would like to go into the "college" database you would type in ``` \c college ``` this should give you a message saying " You are now connected to the database "college" as user "postgres". "
