# Introduction to SQL

## What is SQL? 

SQL, or Structured Query Language, is a language designed to allow both technical and non-technical
users query, manipulate, and transform data from a relational database. And due to its simplicity, 
SQL databases provide safe and scalable storage for millions of websites and mobile applications.

There are many popular SQL databases including SQLite, MySQL, Postgres, Oracle and Microsoft SQL Server.
All of them support the common SQL language standard, which is what this site will be teaching, 
but each implementation can differ in the additional features and storage types it supports.

## Relational databases

Before learning the SQL syntax, it's important to have a model for what a relational database actually is. A relational database represents a collection of related (two-dimensional) tables. Each of the tables are similar to an Excel spreadsheet, with a fixed number of named columns (the attributes or properties of the table) and any number of rows of data.

For example, if the Department of Motor Vehicles had a database, you might find a table containing all the known vehicles that people in the state are driving. This table might need to store the model name, type, number of wheels, and number of doors of each vehicle for example.

![Screenshot_3](https://user-images.githubusercontent.com/55560502/116148948-3e237000-a6ea-11eb-932c-2876df6b52b7.png)

# SQL Lesson 1: SELECT queries 101

To retrieve data from a SQL database, we need to write SELECT statements, which are often colloquially refered to as queries. A query in itself is just a statement which declares what data we are looking for, where to find it in the database, and optionally, how to transform it before it is returned. It has a specific syntax though, which is what we are going to learn in the following exercises.

As we mentioned in the introduction, you can think of a table in SQL as a type of an entity (ie. Dogs), and each row in that table as a specific instance of that type (ie. A pug, a beagle, a different colored pug, etc). This means that the columns would then represent the common properties shared by all instances of that entity 

And given a table of data, the most basic query we could write would be one that selects for a couple columns (properties) of the table with all the rows (instances).

![Screenshot_1](https://user-images.githubusercontent.com/55560502/116148958-42e82400-a6ea-11eb-86ae-27516aac6ffd.png)

The result of this query will be a two-dimensional set of rows and columns, effectively a copy of the table, but only with the columns that we requested.

If we want to retrieve absolutely all the columns of data from a table, we can then use the asterisk (*) shorthand in place of listing all the column names individually.

![Screenshot_2](https://user-images.githubusercontent.com/55560502/116148983-48456e80-a6ea-11eb-84ec-44b812fe3fbf.png)

# SQL Lesson 2: Queries with constraints (Pt. 1)

Now we know how to select for specific columns of data from a table, but if you had a table with a hundred million rows of data, reading through all the rows would be inefficient and perhaps even impossible.

In order to filter certain results from being returned, we need to use a WHERE clause in the query. The clause is applied to each row of data by checking specific column values to determine whether it should be included in the results or not.

![Screenshot_4](https://user-images.githubusercontent.com/55560502/116148993-4d0a2280-a6ea-11eb-9dcb-35aa6a2b8fcf.png)

More complex clauses can be constructed by joining numerous AND or OR logical keywords (ie. num_wheels >= 4 AND doors <= 2). And below are some useful operators that you can use for numerical data (ie. integer or floating point):

![Screenshot_5](https://user-images.githubusercontent.com/55560502/116149015-51ced680-a6ea-11eb-9aca-c0868e06a209.png)

# SQL Lesson 3: Queries with constraints (Pt. 2)

When writing WHERE clauses with columns containing text data, SQL supports a number of useful operators to do things like case-insensitive string comparison and wildcard pattern matching. We show a few common text-data specific operators below:

![Screenshot_6](https://user-images.githubusercontent.com/55560502/116149033-55625d80-a6ea-11eb-87b4-632deb9a3151.png)

# SQL Lesson 4: Filtering and sorting Query results

Even though the data in a database may be unique, the results of any particular query may not be – take our Movies table for example, many different movies can be released the same year. In such cases, SQL provides a convenient way to discard rows that have a duplicate column value by using the DISTINCT keyword.

![Screenshot_7](https://user-images.githubusercontent.com/55560502/116149069-5eebc580-a6ea-11eb-89ad-d92201ffc849.png)

When an ORDER BY clause is specified, each row is sorted alpha-numerically based on the specified column's value. In some databases, you can also specify a collation to better sort data containing international text.

## Limiting results to a subset 
Another clause which is commonly used with the ORDER BY clause are the LIMIT and OFFSET clauses, which are a useful optimization to indicate to the database the subset of the results you care about.
The LIMIT will reduce the number of rows to return, and the optional OFFSET will specify where to begin counting the number rows from.

![Screenshot_8](https://user-images.githubusercontent.com/55560502/116149087-63b07980-a6ea-11eb-8944-38110bd92259.png)

# SQL Lesson 13: Inserting rows

## What is a Schema?

We previously described a table in a database as a two-dimensional set of rows and columns, with the columns being the properties and the rows being instances of the entity in the table. In SQL, the database schema is what describes the structure of each table, and the datatypes that each column of the table can contain.

## Inserting new data

When inserting data into a database, we need to use an INSERT statement, which declares which table to write into, the columns of data that we are filling, and one or more rows of data to insert. In general, each row of data you insert should contain values for every corresponding column in the table. You can insert multiple rows at a time by just listing them sequentially.


# SQL Lesson 14: Updating rows

In addition to adding new data, a common task is to update existing data, which can be done using an UPDATE statement. Similar to the INSERT statement, you have to specify exactly which table, columns, and rows to update. In addition, the data you are updating has to match the data type of the columns in the table schema.

![Screenshot_9](https://user-images.githubusercontent.com/55560502/116149105-690dc400-a6ea-11eb-99dc-0af0ad6d8cdb.png)

## Taking care

Most people working with SQL will make mistakes updating data at one point or another. Whether it's updating the wrong set of rows in a production database, or accidentally leaving out the WHERE clause (which causes the update to apply to all rows), you need to be extra careful when constructing UPDATE statements.

One helpful tip is to always write the constraint first and test it in a SELECT query to make sure you are updating the right rows, and only then writing the column/value pairs to update.


## SQL Lesson 15: Deleting rows

When you need to delete data from a table in the database, you can use a DELETE statement, which describes the table to act on, and the rows of the table to delete through the WHERE clause.

Delete statement with condition
DELETE FROM mytable
WHERE condition;


If you decide to leave out the WHERE constraint, then all rows are removed, which is a quick and easy way to clear out a table completely (if intentional).

## Taking extra care

Like the UPDATE statement from last lesson, it's recommended that you run the constraint in a SELECT query first to ensure that you are removing the right rows. Without a proper backup or test database, it is downright easy to irrevocably remove data, so always read your DELETE statements twice and execute once.


## SQL Lesson 16: Creating tables

When you have new entities and relationships to store in your database, you can create a new database table using the CREATE TABLE statement.

Create table statement w/ optional table constraint and default value

`CREATE TABLE IF NOT EXISTS mytable (`
    `column DataType TableConstraint DEFAULT default_value,`
   ` another_column DataType TableConstraint DEFAULT default_value,`
    …
`);`


The structure of the new table is defined by its table schema, which defines a series of columns. Each column has a name, the type of data allowed in that column, an optional table constraint on values being inserted, and an optional default value.

If there already exists a table with the same name, the SQL implementation will usually throw an error, so to suppress the error and skip creating a table if one exists, you can use the IF NOT EXISTS clause.


Table data types
Different databases support different data types, but the common types support numeric, string, and other miscellaneous things like dates, booleans, or even binary data. Here are some examples that you might use in real code.


![Screenshot_10](https://user-images.githubusercontent.com/55560502/116149144-732fc280-a6ea-11eb-9024-cd735e3a0c2b.png)


## Table constraints

We aren't going to dive too deep into table constraints in this lesson, but each column can have additional table constraints on it which limit what values can be inserted into that column. This is not a comprehensive list, but will show a few common constraints that you might find useful.

![Screenshot_11](https://user-images.githubusercontent.com/55560502/116149176-7dea5780-a6ea-11eb-8f41-6f781fed67a9.png)

# SQL Lesson 17: Altering tables

As your data changes over time, SQL provides a way for you to update your corresponding tables and database schemas by using the ALTER TABLE statement to add, remove, or modify columns and table constraints.

## Adding columns

The syntax for adding a new column is similar to the syntax when creating new rows in the CREATE TABLE statement. You need to specify the data type of the column along with any potential table constraints and default values to be applied to both existing and new rows. In some databases like MySQL, you can even specify where to insert the new column using the FIRST or AFTER clauses, though this is not a standard feature.

![Screenshot_12](https://user-images.githubusercontent.com/55560502/116149185-80e54800-a6ea-11eb-87fe-60a1ec218ad7.png)

## Removing columns

Dropping columns is as easy as specifying the column to drop, however, some databases (including SQLite) don't support this feature. Instead you may have to create a new table and migrate the data over.

![Screenshot_13](https://user-images.githubusercontent.com/55560502/116149210-880c5600-a6ea-11eb-8fe0-da9fd1dd18c7.png)


## Renaming the table

If you need to rename the table itself, you can also do that using the RENAME TO clause of the statement.

![Screenshot_14](https://user-images.githubusercontent.com/55560502/116149221-8b9fdd00-a6ea-11eb-926e-6503a3ba8800.png)



# SQL Lesson 18: Dropping tables

In some rare cases, you may want to remove an entire table including all of its data and metadata, and to do so, you can use the DROP TABLE statement, which differs from the DELETE statement in that it also removes the table schema from the database entirely.

`DROP TABLE IF EXISTS mytable;`

Like the CREATE TABLE statement, the database may throw an error if the specified table does not exist, and to suppress that error, you can use the IF EXISTS clause.

In addition, if you have another table that is dependent on columns in table you are removing (for example, with a FOREIGN KEY dependency) then you will have to either update all dependent tables first to remove the dependent rows or to remove those tables entirely.


