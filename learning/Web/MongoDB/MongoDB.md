- MongoDB is a NoSQL database
- It is document database
- It stores data in a type of JSON format called BSON

| JSON                             | BSON                                  |
| -------------------------------- | ------------------------------------- |
| JavaScript Object Notation       | Binary encoded JSON                   |
| Stores data in text-based format | stores data in  binary encoded format |
### Features of MongoDB 
- **Schema-less database**: A Schema-less database means one collection can hold different types of documents in it. Or in other words, in the MongoDB database, a single collection can hold multiple documents and these documents may consist of the different numbers of fields, content, and size.

- **Document Oriented**: all the data stored in the documents instead of tables. In these documents, the data is stored in fields(key-value pair) instead of rows and columns, which make the data much more flexible in comparison to RDBMS.

-  **Indexing**: every field in the documents is indexed with primary and secondary indices this makes easier and takes less time to get or search data from the pool of the data. If the data is not indexed, then database search each document with the specified query which takes lots of time and not so efficient.

- **Scalability**: provides horizontal scalability with the help of Sharding.

- **Replication**: provides high availability and redundancy with the help of replication, it creates multiple copies of the data and sends these copies toa a different server so that if one server fails, then the data is retrieved from another server.

 - **Aggregation**: It allows to perform operations on the grouped data and get a single result or computed result.

- **Special collection and index types**: It supports time-to-live (TTL) collections for data that should expire at a certain time

 - **Sharding**: Sharding is the process of splitting larger datasets across multiple distributed instances, or “shards.” When applied to particularly large datasets, sharding helps the database distribute and better execute what might otherwise be problematic and cumbersome queries.
### MongoDB Databases

- It is a container for collections.
- To view all databases using `mongosh` the following command is used:
```shell
show dbs
```

- To create a new database or use an existing one the command is:
```shell
use blogs
```

### MongoDB Collections

- A MongoDB collection is group of MongoDB documents.
- To create new collection in your database the following command in used in `mongosh`:
```shell
db.createCollection("users")
```
### MongoDB Document

- Records in MongoDB database are called documents 


[[CRUD operations]]



### Difference between SQL & NoSQL

| **SQL**                                    | **NoSQL**                            |
| ------------------------------------------ | ------------------------------------ |
| Relational Database Management System      | Non-Relational Management System     |
| fixed or predefined Schema                 | dynamic schema                       |
| not suitable for hierarchical data storage | best suited for hierarchical storage |
| best suited for complex queries            | not so good for complex queries      |
| Vertically scalable                        | Horizontally scalable                |
| Follows ACID properties                    | Follows [[CAP]] theorem              |
| Example - MySQL, PostgreSQL                | Example - MongoDB, Cassandra         |

