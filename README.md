# SQL-MONGODB
INTRODUCTION TO SQL
SQL (Structured Query Language):

SQL is a standardized language used to manage data in relational databases.
It allows you to perform various operations like:
Creating and manipulating databases and tables.
Inserting, updating, and deleting data.
Retrieving data based on specific criteria.
Managing user access and permissions.
Creating a Database:

The CREATE DATABASE statement is used to create a new database.
For example: CREATE DATABASE my_database;
Creating Tables:

Tables are the fundamental structures for storing data in a relational database.
Each table consists of rows and columns.
Rows represent individual records.
Columns represent specific attributes or characteristics of those records.
The CREATE TABLE statement is used to define the structure of a table.
You specify the table name, column names, and their data types (e.g., text, number, date).
For example:
CREATE TABLE customers (
  id INT PRIMARY KEY,
  name VARCHAR(255) NOT NULL,
  email VARCHAR(255) UNIQUE,
  city VARCHAR(255)
);
Inserting Data:

The INSERT INTO statement is used to add new records to a table.
You specify the table name and the values for each column in the new record.
For example:
INSERT INTO customers (id, name, email, city)
VALUES (1, 'John Doe', 'john.doe@example.com', 'New York');
Removing Data:

The DELETE statement is used to remove existing records from a table.
You can use a WHERE clause to specify which records to delete based on certain conditions.
For example:
DELETE FROM customers WHERE id = 2;

Describing Tables:

The DESCRIBE statement is used to get information about the structure of a table.
It shows the table name, column names, data types, constraints, and other details.
For example:
DESCRIBE customers;
Selecting Data:

The SELECT statement is the most fundamental operation in SQL.
It allows you to retrieve data from one or more tables based on specific criteria.
You can specify which columns to retrieve, filter data using WHERE clause, sort results using ORDER BY clause, and perform aggregations using functions like SUM, COUNT, and AVG.
For example:
SELECT id, name, city FROM customers WHERE email LIKE '%@gmail.com';

MONGODB

MongoDB Is A Flexible Document Database

MongoDB is a popular NoSQL database system that stores data in JSON-like documents, offering a flexible and scalable approach for modern applications. Unlike traditional relational databases with rigid table structures, MongoDB allows you to store data with varying schemas within documents.

Key Concepts In MongoDB

Document: The fundamental unit of data storage in MongoDB, similar to a JSON object with key-value pairs. Documents can contain nested structures for rich data representation.
Collection: A group of related documents, analogous to a table in a relational database. Collections hold documents that share a common purpose or theme.
Database: A container for collections, similar to a database in a relational system. MongoDB can manage multiple databases to organize data for different applications.
Creating a Database and Collections

You can interact with MongoDB through various tools and programming languages. Here's an illustrative example using the mongo shell:
1.Connect to the MongoDB server: mongo
2.Create a database (if it doesn't exist):use myDatabase  // Replace "myDatabase" with your desired name
3.Create a collection:db.myCollection.insertOne({})  // Replace "myCollection" with your desired name & // This creates an empty collection
4.Inserting Documents

To insert data into a collection, use the insertOne or insertMany methods:

insertOne: Adds a single document.:db.myCollection.insertOne({ name: "Alice", age: 30 })
insertMany: Inserts multiple documents at once.:db.myCollection.insertMany([  { name: "Bob", age: 25 }, { name: "Charlie", age: 42 }])
5.Removing Documents

You can remove documents using the deleteOne or deleteMany methods based on specific criteria:

deleteOne: Deletes the first document matching a query.:db.myCollection.deleteOne({ name: "Alice" })  // Removes the document with name "Alice"
deleteMany: Deletes all documents matching a query.:db.myCollection.deleteMany({ age: { $gt: 35 } })  // Removes documents where age > 35
Describing a Collection's Structure (Optional Schema)

While MongoDB doesn't enforce strict schemas like traditional databases, you can use the db.collectionName.find({}) query to see the structure of documents within a collection.

Selecting Documents (Finding Data)

Use the find method to retrieve documents based on specific criteria:

Finding all documents:db.myCollection.find({})
Finding documents with a specific field value:db.myCollection.find({ name: "Bob" })  // Finds documents with name "Bob"
Using logical operators (e.g., $and, $or):db.myCollection.find({ $and: [{ age: { $gt: 20 } }, { age: { $lt: 40 } }] })// Finds documents where age is between 20 (exclusive) and 40 (inclusive)











