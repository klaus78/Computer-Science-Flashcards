## Databases
<details>
<summary>What is a logical backup?</summary>

A **logical backup**, sometimes called also a *textual dump* or *SQL backup*, is a set of SQL instructions used to re-create and re-populate a database.
</details>

<details>
<summary>What is a phisycal backup?</summary>

A **phisycal backup**, also called *binary backup*, is a consistent copy of the database storage in a way that can be restored when needed. Usually this kind of backup is used for very large databases and in disaster recovery scenarios.
</details>

<details>
<summary>What is a disaster recovery?</summary>

A **disaster recovery** is a set of guidelines and infrastructures able to recover a whole system from a disaster.
Usually the components of a disaster recovery system must be kept in sync, so that when a system fails the other is able to start immediately.

As an example, an HTTP server can have an identical machine, with the same software, configuration and running states, ready to jump in if the primary machine fails.
</details>

<details>
<summary>What is a DBMS?</summary>

A **Database Management System (DBMS)** is a collection of programs that enables users to store, retrieve, update, and delete information from a database.
</details>



### Relational databases

<details>
<summary>What is a relational database?</summary>

A **relational database** stores data in tables that can be queried with the SQL language. Each entry in a table is called row or tuple or record.

Before relational databases came around,  data was stored in  long texts, in which the entries were separated with a vertical bar and this was pretty inefficient.
</details>


<details>
<summary>What is a RDBMS?</summary>

A **Relational Database Management system (RDBMS)** is a type of DBMS that is based on the relational model. One can access or reassemble the data from the relational databases in many different ways without having to reorganize the database tables.
</details>

<details>
<summary>What are the types of relationships in a database?</summary>
There are four relationships in database.

* **One to One**: One entity is associated with another entity. For Ex: Each employee is associated with one department
* **One to Many**: One entity is associated with many other entities. For Ex: A company is associated with all working employees in one branch/office/country.
* **Many to One**: Many entities are associated with only one entity. For Ex: Many employees are associated with one project.
* **Many to Many**: Many entities are associated with many other entities. For Ex: In a company many employees are associated with multiple projects(completed/existing), and at the same time, projects are associated with multiple employees.
</details>


<details>
<summary>What are the ACID properties?</summary>

**ACID** stands for Atomicity Consistency Isolation Durability. ACID properties are the rules that need to be fulfilled by every database transaction to maintain integrity. The ACID properties are:

* **Atomicity**: it means that either all transactions take place and run to completion in one go or no execution occurs at all. 
* **Consistency**: it means that the database must be consistent before and after the transaction.
* **Isolation**: it means that multiple transactions can be executed simultaneously without interfering with each other.
* **Durability**: it means that a successful transaction will be stored in the non-volatile memory and will not be affected by system failure. 

</details>

<details>
<summary>What is a stored procedure?</summary>

A **stored procedure** is a piece of SQL code that is saved on a file, so the code can be reused over and over again.
</details>

<details>
<summary>What is a view?</summary>

A database **view** is a searchable object in a database that is defined by a query. A view can combine data from two
or more tables.
</details>


<details>
<summary>What is a trigger?</summary>

A **trigger** is a database object, usually implemented with some procedure-like logic, that reacts to specific events that happen to the data. For instance, a trigger can be *fired* after a tuple is inserted into a specific table, or when a tuple containing specific data is updated, and so on.

A trigger is *attached* to an event that, in turn, is defined by an operation performed on a data table (e.g., an `INSERT`).
The trigger can be fired before the data is committed, being able to change the data content before it hits the table, or after the data has been placed into the table, having therefore the chance to modify other dependent data.

Moreover, a trigger can be defined on *per-statement* basis, meaning that it will be fired once per every SQL command, or on a *per-tuple* basis, meaning it will be fired once for every tuple that makes the set.

Different databases provide different or partial support to triggers.
</details>

<details>
<summary>What are the differences between primary and foreign keys?</summary>

The **primary key** is a unique or non-null key that uniquely identifies every record in a table or relation. Each database needs a unique identifier for every row of a table, and the primary key plays a vital role in identifying rows in the table uniquely. The primary key column can't store duplicate values. It is also called a minimal super key; therefore, we cannot specify more than one primary key in any relationship.

The **foreign key** is a group of one or more columns in a database to uniquely identify another database record in some other table to maintain the referential integrity. It is also known as the referencing key that establishes a relationship between two different tables in a database. A foreign key always matches the primary key column in another table. It means a foreign key column in one table refers to the primary key column of another table. A foreign key is beneficial in relational database normalization, especially when we need to access records from other tables.
</details>

### No-sql databases

<details>
<summary>What are the differences between relational databases and No-SQL databases?</summary>

The main difference between **relational databases** and **No-SQL databases** is that relational databases are structured, which means that the data is stored in tables. Non-relational database are document-oriented, which means that all data is saved in text form. 
</details>

<details>
<summary>What are the main types of No-SQL databases?</summary>

There are four **main types of No-SQL databases**:
* **document databases**: it stores data in JSON, BSON , or XML documents.
* **key-value stores**: is the simplest type of No-SQL database and is similar to a relational databases with two columns.
* **column-oriented databases**: rather than having a table with colums ``id,col1, col2, col3``, with column oriented databases we have three tables ``col1,id``, ``col2,id`` and ``col3,id``. In a SQL database, all of the information about a particular entry is stored in the form of a record across a row, split into columns. All of the data for that record is stored together in memory. In a columnar database, all of the information for a particular field (say, addresses) is stored together in memory. Because of this, columns not relevant to your query are ignored when searching. The drive head doesn’t have to seek (or move) as far across the platter to read a record, and so query times are much shorter.
* **graph databases**: each element is stored as a node (such as a person in a social media graph). The connections between elements are called links or relationships. 
</details>

