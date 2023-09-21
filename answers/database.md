# Topic: DATABASE

## Compare Relational DB (SQL) vs NoSQL. It's also really nice to know about newSQL (a kind of auto sharding DB which support SQL stuff but scale like NoSQL)

Relational DB is organized by schema, table. All records in a table must be in the same structure, follow some constraints. Relational DB guarantees ACID characteristics so it is safe and stable.

NoSQL is something that is not relational DB. Currently, it contains 4 main kinds:

- The first kind is Document. In this kind, each piece of data is a JSON document.
- The second is Key-Value DB. Simply, it is like a hash map that maps one key to one value.
- The third is Wide Column DB. Records in a table can have a different number of columns.
- The last one is Graph which is suitable for some graph-like data, for example, connections of people on a social network.

## How these 2 things can scale up?

Usually, people scale up Relational DB vertically. Add more CPU, more RAM, more storage. An additional thing we can do is sharding, that device data into different clusters, different nodes. Due to ACID characteristics, relational DB needs to do more work when writing and reading data to ensure those characteristics.
Cause NoSQL sacrifices one or some ACID characteristics, it can be easily scaled horizontally just by simply adding nodes.

## 3 normal forms in DBMS

The first normal form is about making everything atomic. It means a column stores a single value, not multiple values.

The second normal form is about removing partial dependencies. It means no column depends only on a subset of the candidate key of the relation.

The third normal form is about removing transitive dependencies. It means there is no relationship that column A depends on column B, and column B depends on column C.

## ACID of SQL and BASE of NoSQL? Why NoSQL is eventual consistency?

BASE:

- Basically Availability
- Soft state
- Eventually consistency

## CAP theorem in this case. [This is a so nice graph](http://blog.nahurst.com/visual-guide-to-nosql-systems)

In CAP theorem:

- C stands for Consistency
- A stands for Availability
- P stands for Network Partition

It's kinda confused when people say we can only choose 2 out of three things because network partition is not something we can choose in a distributed system.
In the good condition, when there is no network partition, a system can guarantee both consistency and availability. But when the network fault comes, we have to choose one thing between Consistency and Availability to sacrifice.

## What is parameterized statement (in Java it's prepared statement)? How does it work **internally**?

A parameterized statement is a statement that we can customize, like changing filter conditions.

## What is SQL injection? How to avoid it?

SQL injection is when the attacker sends a parameter that contains SQL queries and hopes this query will be executed in the system's database.
SQL injection can be avoided by escaping special characters in the params that users submit to the system.

## How many "requests" you have to send to Database in a single prepared statement query? // one for compile and one for execute

It includes 2 steps, compile and execute.

First, the database management system will compile the statement template then store the result without executing it.

Next, the necessary values will be bound into the compiled statement template, then the statement will be executed.

## Can you reuse the compiled query multiple times? (does it help to speed up your application?)

Yes, we can reuse the compiled query multiple times with different bound values. And yes it speeds up the application.

## How indexing works internally?

Indexing adds a data structure with columns for the search conditions and a pointer. The pointer is the address on the memory disk of the row with the rest of the information. The query looks for the specific row in the index; the index refers to the pointer which will find the rest of the information.

## What algorithm and data structure indexing used? And why?

Index can use a hash table or B-Tree. [The index is decided to use depending on the data type and how you query the data](https://dev.mysql.com/doc/refman/8.0/en/index-btree-hash.html).

## How composite indexing works?

It's like a single index but the key is a compound key, which is the combined values of these columns that are indexed.

Let’s say we have an index defined on 4 columns — col1, col2, col3, col4. With a composite index, we have search capability on col1, (col1, col2) , (col1, col2, col3) , (col1, col2, col3, col4). So we can use any left side prefix of the indexed columns, but we can’t omit a column from the middle & use that like — (col1, col3) or (col1, col2, col4) or col3 or col4 etc. These are invalid combinations.

## How to know your query is using index?

By adding "explain" in front of the query, we will get how the query ran and if it uses index or not.

The query optimizer will use index automatically if possible and chose the index that it thinks is the best. And we can force our query to use an index by specifying it in the query.

## How index work in this case: `WHERE age = 5` and `Where age > 5`? The complexity to go to the next record?

It depends on the index type is hashing or B-Tree. If the index type is B-Tree, there is no difference between these two cases. The complexity to go to the next record is O(1) because all the leaves are linked together as a doubly linked list.

## Indexing with char?

For text fields, index on that column only is used when filter condition filters a prefix of this column.

## The complexity of SQL query? How to measure it? How SQL optimize a query?

To be defined.

## Compare `WHERE id = 'a' AND id = 'b' AND id = 'c'` vs `WHERE id in (a, b, c)`?

In MySQL, the values in the IN list will be sorted and MySQL will use binary search to check if the current value is in the list. So the check operator will cost O(log N) complexity, with N being the number of elements that need to be compared.

Some links to read more:

- https://www.postgresql.org/message-id/12553.1135634231@sss.pgh.pa.us

- https://www.cybertec-postgresql.com/en/postgresql-indexing-index-scan-vs-bitmap-scan-vs-sequential-scan-basics/

- https://subscription.packtpub.com/book/big_data_and_business_intelligence/9781785284335/11/ch11lvl1sec104/running-bitmap-heap-and-index-scan

- https://www.oreilly.com/library/view/high-performance-mysql/9780596101718/ch04.html"

## Complexity of this query `SELECT * FROM abc ORDER BY name LIMIT 10 OFFSET 1000000` // SELECT 10 record from offset 10^6 after sort by name (which is a char)? How to optimize it?

O(N log N) with N being the total number of records.

We can optimize the query by indexing the column name.

## What is the complexity of COUNT(\*) query?

In MySQL, it depends on the storage engine that the table uses. For MyISAM, the total number of rows is stored with each table so the complexity is O(1), but for InnoDB, it is O(N).

## How to write query to avoid full table scan?

We need to write a query that takes advantage of index if any.

## Complexity of JOIN, INNER JOIN, OUTER JOIN?

The complexity of JOIN, INNER JOIN, OUTER JOIN depends on the size of the tables, the number of columns, the join conditions, and the indexes available. Generally, the complexity of a join operation is O(M*N), where M and N are the number of rows in the two tables. However, this can be reduced by using indexes, which can speed up the search for matching rows. For example, if one table has an index on the join column, the complexity can be O(M*log N) or O(N*log M), depending on which table is smaller. Some database systems also use hash join or merge join algorithms, which can further improve the performance of join operations. ¹²³

Source: Conversation with Bing, 9/21/2023
(1) What is the difference between "INNER JOIN" and "OUTER JOIN"?. https://stackoverflow.com/questions/38549/what-is-the-difference-between-inner-join-and-outer-join.
(2) SQL Query: Complex Inner Joins and Outer Joins - Stack Overflow. https://stackoverflow.com/questions/13831145/sql-query-complex-inner-joins-and-outer-joins.
(3) Difference Between Inner Join, Cross Join, and Full Outer Join. https://vaishaligoilkar3322.medium.com/difference-between-inner-join-cross-join-and-full-outer-join-3c279a5eeac1.
(4) SQL | Join (Inner, Left, Right and Full Joins) - GeeksforGeeks. https://www.geeksforgeeks.org/sql-join-set-1-inner-left-right-and-full-joins/.

## What is Database Replicating? When do we need it?

Database replicating is the act of making one or many copies of a database to increase the availability of data.

## What is bin log? How Master DB sync with Slave DB?

When data is written into DB, first it will be stored in Write Ahead Logs (bin logs). Master DB send these log to Slave DB so Slave DB can also have those changes.

## Can a Slave DB be a slave of another Slave DB (we do not need to sync from Master DB directly)?

Yes it can.

## What is Database Sharding? When we need it?

Sharding happens when a database is too big so the query time increases. We shard database to improve query time and also increase the availability of the system. If one shard is down, there is only a portion failure.

## Which rule we can apply to DB Sharding?

- Ensure unique key for the whole system.

- Distribute load.

## How to ensure primary key is globally unique when sharding?

We can have a key generating system that generates keys for all servers. But this server can be a central point of failure. To improve that, we can have multiple servers to generate keys, each server is in charge of some range of keys.

## How we can shard a table to multiple tables (same server) and multiple DB (multiple servers)?

Sharding a table to multiple tables and multiple databases is a way of scaling a database horizontally to improve its performance and availability. There are different methods and strategies for sharding, but the basic idea is to split the data into smaller chunks, called shards, and distribute them across different servers or nodes. Each shard contains a subset of the data that is independent from the other shards, and each node can handle queries for one or more shards.

One of the challenges of sharding is how to partition the data in a way that balances the load across the nodes, minimizes the cross-shard queries, and preserves the consistency and integrity of the data. There are two main types of partitioning: range partitioning and hash partitioning. Range partitioning divides the data based on a range of values in a key column, such as date, ID, or name. Hash partitioning applies a hash function to a key column and assigns the data to a shard based on the hash value. Both methods have their advantages and disadvantages, depending on the distribution and access patterns of the data.

Another challenge of sharding is how to query the data across multiple shards and nodes. This requires a mechanism to route the queries to the appropriate shards and nodes, and to combine the results from different sources. One way to do this is to use a middleware layer or an application-level logic that can handle the sharding logic and communicate with the nodes. Another way is to use a distributed SQL engine that can abstract away the sharding details and provide a unified interface for querying the data.

There are many resources and tutorials that can help you learn more about sharding and how to implement it in different database systems. Here are some examples:

- [Understanding Database Sharding](^1^) is an article that explains the concept of sharding, its benefits and drawbacks, and some common sharding methods.
- [How sharding a database can make it faster](^2^) is an article that discusses how sharding can improve the performance of a database by reducing contention, increasing parallelism, and enabling horizontal scaling.
- [Query sharded databases](^3^) is a tutorial that shows how to use Azure SQL Database Elastic Database tools to query data across multiple shards using T-SQL commands.
- [How do I split a table into multiple tables](^4^) is a question on Stack Overflow that provides some answers on how to use partitioning in MySQL to split a table into smaller tables.

Source: Conversation with Bing, 9/21/2023
(1) Understanding Database Sharding | DigitalOcean. https://www.digitalocean.com/community/tutorials/understanding-database-sharding.
(2) How sharding a database can make it faster - Stack Overflow. https://stackoverflow.blog/2022/03/14/how-sharding-a-database-can-make-it-faster/.
(3) Query sharded databases - Azure SQL Database | Microsoft Learn. https://learn.microsoft.com/en-us/azure/azure-sql/database/elastic-scale-multishard-querying?view=azuresql.
(4) How do I split a table into multiple tables - Stack Overflow. https://stackoverflow.com/questions/41635651/how-do-i-split-a-table-into-multiple-tables.

## How query can work when we sharding (the data might be in the same or different tables/dbs)?

For a query that we might know exactly where data is using its key, we can detect which shard is holding necessary data and query on this shard.

For a query that data might be on a lot of shards, we can execute the query on all possible shards then aggregate data later.

## What is database transaction?

Relational DB ensures Atomicity by Transaction. A transaction is a collection of operations. Either all of those operations are executed, or non of them is executed. It ensures there is no time when something is failed in the middle and we have no idea when or how to roll back.

## How rollback works internally?

A rollback is a process of undoing the changes made by a transaction that has not been committed to the database. A rollback can be triggered by an explicit command, an error, or a system failure. Different database systems implement rollback operations in different ways, but the general idea is to use some form of logging or backup to restore the original state of the data before the transaction started.

One common method of implementing rollback is to use a write-ahead logging (WAL) technique, which records all the changes made by a transaction in a log file before applying them to the database. The log file contains enough information to undo or redo any change made by the transaction. If a transaction needs to be rolled back, the database system can use the log file to reverse the changes in reverse order, restoring the data to its previous state. This method ensures that the database is always in a consistent state, even in the event of a system crash or power failure.

Another common method of implementing rollback is to use a rollback segment, which is a special area of the database that stores the original data before it is modified by a transaction. The rollback segment acts as a backup copy of the data, which can be used to restore the data if a transaction is rolled back. The rollback segment also allows other transactions to read the original data without being affected by the uncommitted changes. This method improves the concurrency and performance of the database, as it reduces locking and blocking.

Both methods have their advantages and disadvantages, depending on the size and frequency of transactions, the availability of disk space and memory, and the performance requirements of the database. For more information on how rollback works internally in different database systems, you can refer to these sources:

- [MySQL Transactions and how does Rollback work?](^1^) explains how MySQL uses rollback segments and write-ahead logging to implement rollback operations for InnoDB tables.
- [How commit and rollback operations work](^2^) describes how IBM DB2 uses write-ahead logging and commit and rollback operations to ensure data integrity and consistency.
- [Difference between COMMIT and ROLLBACK in SQL](^3^) compares the effects of commit and rollback operations in SQL databases.

Source: Conversation with Bing, 9/21/2023
(1) MySQL Transactions and how does Rollback work?. https://stackoverflow.com/questions/21057314/mysql-transactions-and-how-does-rollback-work.
(2) How commit and rollback operations work - IBM. https://www.ibm.com/docs/en/i/7.3?topic=concepts-how-commit-rollback-operations-work.
(3) Difference between COMMIT and ROLLBACK in SQL - GeeksforGeeks. https://www.geeksforgeeks.org/difference-between-commit-and-rollback-in-sql/.

## What is dirty read, dirty write, read skew, phantom read, write skew, lost update?

Dirty read is when transaction A is allowed to read a value that has been modified by transaction B but has yet been committed. This may cause a problem when transaction B fails and rollback happens, so the value that A reads is not the value in database.

Dirty write is when transaction A is allowed to write a value that has been modified by transaction B but has yet been committed.

Read skew is when someone needs to read one value multiple times in a transaction. But the result each time is different.

Phantom read is when a transaction needs to get a collection of records multiple times in a transaction. But the number of records each time is different.

Write skew is when someone needs to read some object then update some object based on the result of the read value.

Lost update is a special case of write skew when read and update happen with the same object.

Read committed is a weak isolation level that is used to guarantee no dirty read and no dirty write. It assures that all object that can be read is already committed and no write can happen to an uncommitted object.

2 stronger isolation levels are snapshot isolation and serializable snapshot isolation. For snapshot isolation, a transaction can read the old version of a value while other transactions are writing. For serializable snapshot isolation, a transaction cannot read while other transactions are writing. It is called 2PL - two-phase locking.

## How transaction work when there are many concurrent requests?

A transaction is a logical unit of work that consists of one or more operations on a database, such as reading, writing, updating, or deleting data. A transaction must follow the ACID properties, which are Atomicity, Consistency, Isolation, and Durability. These properties ensure that the database remains in a valid state even when there are many concurrent requests from different users or applications.

One of the challenges of handling concurrent requests is to maintain the isolation level of transactions, which means that each transaction should not interfere with or be affected by other transactions. Different database systems use different techniques and algorithms to achieve isolation, such as locking, versioning, timestamping, or serialization. These techniques aim to prevent or resolve conflicts that may arise when multiple transactions access or modify the same data at the same time.

For example, one common technique is locking, which means that a transaction acquires exclusive access to the data it needs before performing any operation on it. Locking can prevent other transactions from reading or writing the same data until the first transaction releases the lock. However, locking can also cause problems such as deadlock, livelock, or starvation, which may affect the performance and availability of the database.

Another common technique is versioning, which means that a transaction works with a snapshot of the data at a certain point in time, rather than the current state of the data. Versioning can allow other transactions to read or write the same data without blocking each other, as long as they do not conflict with each other. However, versioning can also cause problems such as inconsistency, concurrency anomalies, or wasted resources, which may affect the correctness and efficiency of the database.

There are many resources and tutorials that can help you learn more about how transactions work when there are many concurrent requests and how different database systems handle them. Here are some examples:

- [How does a database server handle thousands of concurrent requests?](^1^) is an article that explains the concept of isolation levels and some common techniques for achieving them.
- [Handling Concurrent Requests in a RESTful API](^2^) is an article that discusses how to use optimistic locking to prevent overwriting changes made by other users in a RESTful API.
- [How transaction work when there are many concurrent requests?](^3^) is a question on The Quick Advisor that provides a brief answer on how locking works in a transaction.

Source: Conversation with Bing, 9/21/2023
(1) How does a database server handle thousands of concurrent requests?. https://medium.com/how-the-web-works/how-does-a-database-server-handle-thousands-of-concurrent-requests-d54352310183.
(2) Handling Concurrent Requests in a RESTful API - Medium. https://medium.com/swlh/handling-concurrent-requests-in-a-restful-api-5a25a4b81a1.
(3) How transaction work when there are many concurrent requests?. https://thequickadvisor.com/how-transaction-work-when-there-are-many-concurrent-requests/.

## How to avoid race condition in DB? Read/Write lock?

A race condition is a situation where the outcome of a database operation depends on the timing or order of execution of concurrent requests. For example, if two users try to update the same record at the same time, one of them may overwrite the other's changes without knowing it. This can lead to data inconsistency and corruption.

To avoid race conditions in a database, you need to ensure that concurrent requests are executed in a safe and controlled manner, so that they do not interfere with each other or cause conflicts. There are different techniques and strategies for doing this, depending on the database system and the application logic. Some of the common ones are:

- Read/write lock: This is a mechanism that allows multiple readers to access the same data simultaneously, but only one writer can modify it at a time. A read lock prevents other writers from modifying the data, while a write lock prevents other readers and writers from accessing the data. Read/write locks can be implemented at different levels, such as table, row, or column level. They can also be explicit or implicit, depending on whether the application or the database system manages them. Read/write locks can prevent race conditions by ensuring that only one transaction can update the data at a time, and that other transactions can read the latest version of the data. However, they can also cause problems such as deadlock, livelock, or starvation, which may affect the performance and availability of the database.
- Optimistic locking: This is a strategy that assumes that race conditions are rare and unlikely to happen, and therefore does not use any locking mechanism to prevent them. Instead, it uses a version number or a timestamp to detect if the data has changed since it was read by a transaction. If the data has changed, the transaction fails and needs to be retried. Optimistic locking can improve the concurrency and performance of the database, as it reduces locking and blocking. However, it can also cause problems such as inconsistency, concurrency anomalies, or wasted resources, which may affect the correctness and efficiency of the database.
- Transactions: This is a logical unit of work that consists of one or more operations on a database, such as reading, writing, updating, or deleting data. A transaction must follow the ACID properties, which are Atomicity, Consistency, Isolation, and Durability. These properties ensure that the database remains in a valid state even when there are many concurrent requests from different users or applications. Transactions can prevent race conditions by providing different levels of isolation, which means that each transaction should not interfere with or be affected by other transactions. Different database systems use different techniques and algorithms to achieve isolation, such as locking, versioning, timestamping, or serialization. These techniques aim to prevent or resolve conflicts that may arise when multiple transactions access or modify the same data at the same time.

There are many resources and tutorials that can help you learn more about how to avoid race conditions in a database and how to use read/write locks or other techniques. Here are some examples:

- [Do database transactions prevent race conditions?](^1^) is an article that explains the concept of isolation levels and some common techniques for achieving them.
- [Database race conditions](^2^) is an article that discusses how to use optimistic locking to prevent overwriting changes made by other users.
- [Race Conditions](^3^) is an article that describes how to use read/write locks in MySQL.

Source: Conversation with Bing, 9/21/2023
(1) Do database transactions prevent race conditions?. https://stackoverflow.com/questions/6477574/do-database-transactions-prevent-race-conditions.
(2) Database race conditions - Stack Overflow. https://stackoverflow.com/questions/9850336/database-race-conditions.
(3) Race Conditions, Locks, Semaphores, and Deadlocks - Medium. https://bing.com/search?q=How+to+avoid+race+condition+in+DB%3f+Read%2fWrite+lock%3f.
(4) Race Conditions, Locks, Semaphores, and Deadlocks - Medium. https://medium.com/swlh/race-conditions-locks-semaphores-and-deadlocks-a4f783876529.
(5) sql - How to avoid race condition in MySQL - Stack Overflow. https://stackoverflow.com/questions/22561241/how-to-avoid-race-condition-in-mysql.
(6) Race conditions. When 2 thread try to update in same entity in table. https://dba.stackexchange.com/questions/308654/race-conditions-when-2-thread-try-to-update-in-same-entity-in-table.

## Distributed transaction? How to make a transaction when a query needs to access multiple DB?

A distributed transaction is needed when data that suppose to be in a transaction is stored in different databases. There is a technique called 2 phase commit (2PC) that helps to resolve this situation.

There will be a coordinator which orchestrates the whole transaction. When the transaction begins, the coordinator generates a global transaction ID for all participants of this transaction. Each participant will execute their own transaction that attaches to the global transaction. When all local transactions are done, the coordinator sends the prepare request for all participants. This is the first phase - the prepare phase in 2PC. Participants can respond yes or no, indicate if they can commit this transaction or not. And the "yes" answer is the promise that it will be able to commit this transaction no matter what. If all participants respond "yes", the coordinator can decide to commit this transaction and send the commit request to all participants. This is the second phase of 2PC, the commit phase. Once the commit decision is made by the coordinator, it is irreversible. It will keep resending commit requests to participants no matter what. If the coordinator fails, the participant must keep the status of being able to commit this global transaction no matter what.

## What is Try-Confirm Cancel?

Try-Confirm-Cancel (TCC) is a protocol for implementing distributed transactions in microservices. It is based on the idea of reserving resources or placing them in escrow before committing them. The protocol consists of three phases:

- Try: This phase checks the availability of the resources and reserves them for the transaction. For example, a try request in a flight booking service will reserve a seat for the customer and insert a customer reservation record with reserved state into the database⁵.
- Confirm: This phase commits the transaction and releases the resources. For example, a confirm request in a flight booking service will change the customer reservation record from reserved to confirmed and deduct the payment from the customer's account⁵.
- Cancel: This phase aborts the transaction and rolls back the changes. For example, a cancel request in a flight booking service will delete the customer reservation record and release the seat⁵.

The TCC protocol ensures that each transaction is either completed or cancelled, and that no resources are left in an inconsistent state. The TCC protocol can handle scenarios where two-phase commit (2PC) is not feasible or desirable, such as long-running transactions, high concurrency, or network failures¹. However, the TCC protocol also has some challenges, such as designing idempotent and compensating operations, handling concurrent requests, and coordinating multiple services²³⁴.

Source: Conversation with Bing, 9/21/2023
(1) Eventual Data Consistency Solution in ServiceComb - part 3. https://servicecomb.apache.org/docs/distributed_saga_3/.
(2) Making Try-Confirm/Cancel Easy with MicroTx - Oracle Blogs. https://blogs.oracle.com/database/post/making-try-confirmcancel-easy-with-microtx.
(3) AgileDev - Try-Cancel/Confirm. - GitHub Pages. http://uniknow.github.io/AgileDev/site/0.1.15-SNAPSHOT/tcc.html.
(4) 深度剖析 Seata TCC 模式（一）. https://seata.io/zh-cn/blog/seata-tcc.html.
(5) transaction - Try Confirm Cancel (TCC) Protocol - Database .... https://dba.stackexchange.com/questions/313761/try-confirm-cancel-tcc-protocol.
