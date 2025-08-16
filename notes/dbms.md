# DBMS Interview

## Database Fundamentals
### Basic Concepts
- `Database` → Organized collection of structured data  
- `DBMS` → Software to manage databases (MySQL, Oracle, etc.)  
- `Schema` → Blueprint of database structure  
- `Instance` → Current state of database at runtime  

## Database Models
- `Relational` → Tables with rows/columns (SQL)  
- `NoSQL` → Non-tabular formats (document, key-value, etc.)  
- `Hierarchical` → Tree-like structure  
- `Network` → Graph-like many-to-many relationships  

## RDBMS Concepts
### Core Components
- `Table` → Data organized in rows and columns  
- `Tuple` → Single row in a table  
- `Attribute` → Column in a table  
- `Relation` → Connection between tables  

### Keys
- `Primary Key` → Unique identifier for records  
- `Foreign Key` → Reference to primary key in another table  
- `Candidate Key` → Potential primary key options  
- `Composite Key` → Multiple columns as primary key  

## SQL Operations
### DDL (Data Definition)
- `CREATE` → Makes new database objects  
- `ALTER` → Modifies existing structures  
- `DROP` → Removes database objects  
- `TRUNCATE` → Deletes all table data (faster than DELETE)  

### DML (Data Manipulation)
- `SELECT` → Retrieves data from tables  
- `INSERT` → Adds new records  
- `UPDATE` → Modifies existing records  
- `DELETE` → Removes records  

### DCL (Data Control)
- `GRANT` → Gives user privileges  
- `REVOKE` → Takes back privileges  

## SQL Advanced
### Joins
- `INNER JOIN` → Matching rows from both tables  
- `LEFT JOIN` → All left table rows + matched right rows  
- `RIGHT JOIN` → All right table rows + matched left rows  
- `FULL JOIN` → All rows when match in either table  
- `CROSS JOIN` → Cartesian product of tables  

### Functions
- `Aggregate` → SUM(), AVG(), COUNT(), MAX(), MIN()  
- `Scalar` → UPPER(), LOWER(), ROUND(), LEN()  
- `Date` → NOW(), DATE(), YEAR(), MONTH()  

### Clauses
- `WHERE` → Filters records  
- `GROUP BY` → Groups identical data  
- `HAVING` → Filters groups  
- `ORDER BY` → Sorts results  
- `LIMIT` → Restricts number of rows  

## Normalization
- `1NF` → Atomic values, no repeating groups  
- `2NF` → 1NF + no partial dependencies  
- `3NF` → 2NF + no transitive dependencies  
- `BCNF` → Stronger 3NF variant  
- `Denormalization` → Intentional redundancy for performance  

## Indexes
- `B-tree` → Balanced tree structure (default)  
- `Hash` → Exact match lookups  
- `Clustered` → Physically orders data (1 per table)  
- `Non-clustered` → Logical ordering (multiple allowed)  

## Transactions
- `ACID Properties` → Atomicity, Consistency, Isolation, Durability  
- `COMMIT` → Saves transaction permanently  
- `ROLLBACK` → Undoes transaction changes  
- `SAVEPOINT` → Intermediate rollback points  

## Concurrency Control
- `Dirty Read` → Reading uncommitted data  
- `Lost Update` → Overwritten changes  
- `Non-repeatable Read` → Different values in same transaction  
- `Phantom Read` → New rows appear in repeated reads  

### Isolation Levels
- `Read Uncommitted` → Lowest isolation  
- `Read Committed` → Default in most DBs  
- `Repeatable Read` → Consistent reads within transaction  
- `Serializable` → Highest isolation (no concurrency)  

## Database Objects
- `Views` → Virtual tables from queries  
- `Stored Procedures` → Precompiled SQL routines  
- `Triggers` → Automatic actions on events  
- `Cursors` → Row-by-row result set processing  

## NoSQL Databases
- `Document` → JSON-like documents (MongoDB)  
- `Key-Value` → Simple pairs (Redis)  
- `Column-family` → Column-oriented (Cassandra)  
- `Graph` → Nodes/edges (Neo4j)  

## Distributed Databases
- `Sharding` → Horizontal partitioning across servers  
- `Replication` → Copies data across nodes  
- `CAP Theorem` → Consistency, Availability, Partition tolerance  
- `BASE` → Basically Available, Soft state, Eventually consistent  

## Performance Tuning
- `Query Optimization` → EXPLAIN plans, indexing  
- `Normalization` → Reduces redundancy  
- `Denormalization` → Improves read performance  
- `Connection Pooling` → Reuses database connections  

## Backup & Recovery
- `Full Backup` → Complete database copy  
- `Incremental` → Only changed data since last backup  
- `Point-in-Time Recovery` → Restore to specific moment  
- `Log Shipping` → Continuous transaction log backups  

## Security
- `Authentication` → Verifying user identity  
- `Authorization` → Granting access rights  
- `Encryption` → Data protection at rest/in transit  
- `SQL Injection` → Code injection attack prevention  

## Cloud Databases
- `RDS` → Managed relational databases  
- `DynamoDB` → Managed NoSQL (AWS)  
- `Cosmos DB` → Multi-model database (Azure)  
- `Firestore` → NoSQL (Google Cloud)  
