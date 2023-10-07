


# Relational vs Non-Relational DB

| Characterstic    | Relational Data | Non Relational Data
| -------- | ------- | ------- |
| Data Structure  | Tables with rows and columns    | Various formats (JSON, key-value, wide-column, graph, etc.) | 
| Schema  | Fixed schema    | Flexible or dynamic schema | 
|  Query Language |  SQL | Database-specific or custom query languages |
|  Data Relationships | Established using foreign keys and joins   |   May use references or embedded data, optimized for denormalized structures  |
|  Scaling |  Primarily vertical scaling  |   Horizontal scaling (sharding) for distribution across servers  |
| Use Cases  |  Structured data, complex queries, data integrity is critical  |   Flexible and scalable for unstructured or semi-structured data, less emphasis on data integrity  |

# Non Relational DB Types

| Type    | Examples | 
| -------- | ------- |
| Document Stores  | MongoDB, Couchbase, CouchDB   |
| Key-Value Stores  |   Redis, Amazon DynamoDB, Riak |
| Column-Family Stores  |  Apache Cassandra, HBase, ScyllaDB  |
| Graph Databases   |  Neo4j, Amazon Neptune, OrientDB  |
| Wide-Column Stores  | Apache HBase, Cassandra, Amazon Keyspaces   |
|  Time-Series Databases |  InfluxDB, TimescaleDB, OpenTSDB |
| Object Stores  |   Amazon S3, Google Cloud Storage, Azure Blob Storage |
|  XML Databases |  BaseX, eXist-db  |
| Multimodel Databases  | ArangoDB, Couchbase Server   |



## MongoSH commands
**help**	Displays help information.\
**show dbs**	Lists all available databases.\
**use <database>**	Switches to the specified database.\
**show collections**	Lists all collections in the current database.\
**db.collection.find(<query>)**	Retrieves documents from a collection based on a query.
```js
// Find all documents in the 'myCollection' collection
db.myCollection.find()

// Find documents matching specific criteria
db.myCollection.find({ age: { $gt: 25 } })

```
**db.collection.insertOne(<document>)**	Inserts a single document into a collection.
```js
db.myCollection.insertOne({
    name: "John",
    age: 30,
    email: "john@example.com"
})
```

**db.collection.insertMany([<documents>])**	Inserts multiple documents into a collection.\
**db.collection.updateOne(<filter>, <update>)**	Updates a single document that matches the filter.\
**db.collection.updateMany(<filter>, <update>)**	Updates multiple documents that match the filter.
```js
// Update a single document
db.myCollection.updateOne(
    { name: "John" },
    { $set: { age: 31 } }
)

// Update multiple documents
db.myCollection.updateMany(
    { age: { $lt: 30 } },
    { $set: { status: "young" } }
)

```
**db.collection.deleteOne(<filter>)**	Deletes a single document that matches the filter.\
**db.collection.deleteMany(<filter>)**	Deletes multiple documents that match the filter.
```js
// Delete a single document
db.myCollection.deleteOne({ name: "John" })

// Delete multiple documents
db.myCollection.deleteMany({ age: { $gt: 60 } })

```
**db.collection.aggregate([<pipeline>])**	Performs aggregation operations on documents in a collection.
```js
// Aggregation example: Calculate the average age of users
db.myCollection.aggregate([
    { $group: { _id: null, avgAge: { $avg: "$age" } } }
])

```
**db.collection.createIndex(<keys>, <options>)**	Creates an index on specified keys in a collection.\
**db.collection.getIndexes()**	Lists all indexes for a collection.\
**db.collection.dropIndex(<indexName>)**	Deletes an index from a collection.
```js
// Create a single-field index on the 'email' field
db.myCollection.createIndex({ email: 1 })

// Create a compound index on multiple fields
db.myCollection.createIndex({ name: 1, age: -1 })

```
**Schema of a Collection**
```js
var col=db.userAccount.findOne();
for (var c in col) { print (c) ; }
```

***load("myScript.js")*** Running JavaScript file
**exit**	Exits the mongosh shell.





## Query in Detail

In MongoDB using the mongosh shell, you can select specific fields or columns from documents returned by the find command by specifying a projection. A projection allows you to control which fields you want to include or exclude in the query results.

Here's how you can select specific fields using the find command with a projection in mongosh:
```js
db.collectionName.find(<query>, <projection>)

// collectionName: Replace this with the name of the collection you want to query.
// <query>: This is the query object that specifies your conditions, if any.
// <projection>: Use this to specify which fields you want to include or exclude from the results.

// Include 'name' and 'age', exclude 'email' and 'address'
db.myCollection.find({}, { name: 1, age: 1, email: 0, address: 0 })

```
```js

// Find documents where age is greater than 30
db.myCollection.find({ age: { $gt: 30 } })
// Find documents where age is lesser than 30
db.myCollection.find({ age: { $lt: 30 } })

// Find documents where age is 30 and name is "John"
db.myCollection.find({ $and: [{ age: 30 }, { name: "John" }] })

// Find documents where age is 30 or name is "Alice"
db.myCollection.find({ $or: [{ age: 30 }, { name: "Alice" }] })

// Find documents where age is not 30
db.myCollection.find({ age: { $not: { $eq: 30 } } })

```
```js

```
```js

```
```js

```
```js

```
```js

```
```js

```
```js

```



 




