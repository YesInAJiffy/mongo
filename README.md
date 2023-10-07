## Command	Description
**help**	Displays help information.\
**show dbs**	Lists all available databases.\
**use <database>**	Switches to the specified database.\
**show collections**	Lists all collections in the current database.\
**db.collection.find(<query>)**	Retrieves documents from a collection based on a query.\
**db.collection.insertOne(<document>)**	Inserts a single document into a collection.\
**db.collection.insertMany([<documents>])**	Inserts multiple documents into a collection.\
**db.collection.updateOne(<filter>, <update>)**	Updates a single document that matches the filter.\
**db.collection.updateMany(<filter>, <update>)**	Updates multiple documents that match the filter.\
**db.collection.deleteOne(<filter>)**	Deletes a single document that matches the filter.\
**db.collection.deleteMany(<filter>)**	Deletes multiple documents that match the filter.\
**db.collection.aggregate([<pipeline>])**	Performs aggregation operations on documents in a collection.\
**db.collection.createIndex(<keys>, <options>)**	Creates an index on specified keys in a collection.\
**db.collection.getIndexes()**	Lists all indexes for a collection.\
**db.collection.dropIndex(<indexName>)**	Deletes an index from a collection.\
**exit**	Exits the mongosh shell.

Schema
Fixed schema
Flexible or dynamic schema
Query Language
SQL
Database-specific or custom query languages
Data Relationships
Established using foreign keys and joins
May use references or embedded data, optimized for denormalized structures
Scaling
Primarily vertical scaling
Horizontal scaling (sharding) for distribution across servers
Use Cases
Structured data, complex queries, data integrity is critical
Flexible and scalable for unstructured or semi-structured data, less emphasis on data integrity


| Characterstic    | Relational Data | Non Relational Data
| -------- | ------- | ------- |
| Data Structure  | Tables with rows and columns    | Various formats (JSON, key-value, wide-column, graph, etc.) | 

