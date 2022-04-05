## Databases

<summary></summary>
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
<summary>What is a stored procedure?</summary>

A **stored procedure** is a piece of SQL code that is saved on a file, so the code can be reused over and over again.
</details>

<details>
<summary>What is a view?</summary>

A database **view** is a searchable object in a database that is defined by a query. A view can combine data from two
or more tables.
</details>

<details>
<summary>What are the differences between primary and foreign keys?</summary>

The **primary key** is a unique or non-null key that uniquely identifies every record in a table or relation. Each database needs a unique identifier for every row of a table, and the primary key plays a vital role in identifying rows in the table uniquely. The primary key column can't store duplicate values. It is also called a minimal super key; therefore, we cannot specify more than one primary key in any relationship.

The **foreign key** is a group of one or more columns in a database to uniquely identify another database record in some other table to maintain the referential integrity. It is also known as the referencing key that establishes a relationship between two different tables in a database. A foreign key always matches the primary key column in another table. It means a foreign key column in one table refers to the primary key column of another table. A foreign key is beneficial in relational database normalization, especially when we need to access records from other tables.
<details>>