# 1. SQL vs NoSQL

SQL databases - are relational (structured tables with fixed rows and columns), while NoSQL databases are non-relational (flexible document-based storage).

`-- SQL Table Structure (Rigid)
CREATE TABLE users (id INT, name VARCHAR(50), age INT);`

`// NoSQL Document Structure (Flexible)
{ "_id": 1, "name": "Sumit", "age": 22, "skills": ["Node.js", "MongoDB"] }`

# 2. What is MongoDB?

A popular open-source, NoSQL document-oriented database designed to store data in flexible, JSON-like documents called BSON.

`db.users.insertOne({
  name: "Sumit",
  role: "Software Engineer",
  active: true
});`

# 3. When to use MongoDB?

Best used when dealing with rapidly changing data structures, large volumes of unstructured or semi-structured data, real-time analytics, and hierarchical data.

`db.products.find({ "specs.ram": "16GB" });`

# 4. What is MongoDB Atlas?

A fully-managed cloud database service hosted by MongoDB that handles deployment, scaling, and backups across AWS, Azure, or GCP.

`const mongoose = require('mongoose');
mongoose.connect('mongodb+srv://<username>:<password>@cluster.mongodb.net/myDatabase');`

# 5. MongoDB Terminology

The mapping of traditional relational database terms to MongoDB terms (Database stays Database, Table becomes Collection, Row becomes Document, Column becomes Field).

`// In MongoDB, inserting into a non-existent collection automatically creates it
db.createCollection("students");
db.getCollectionNames();`
