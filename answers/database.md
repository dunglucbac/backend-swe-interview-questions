# Topic: DATABASE

## Compare Relational DB (SQL) vs NoSQL. It's also really nice to know about newSQL (a kind of auto sharding DB which support SQL stuff but scale like NoSQL)

Relational DB (SQL) and NoSQL are two types of database systems that have different characteristics and use cases. Here is a brief comparison of them:

- Relational DB (SQL) uses structured data that is organized in tables with predefined schemas. SQL (Structured Query Language) is the standard language for querying and manipulating data in relational databases. Relational DB (SQL) supports ACID (Atomicity, Consistency, Isolation, Durability) guarantees, which ensure data integrity and consistency in transactions. Relational DB (SQL) is suitable for applications that require complex queries, joins, transactions, and data consistency. Some examples of relational DB (SQL) are MySQL, PostgreSQL, Oracle, and SQL Server¹².
- NoSQL uses unstructured or semi-structured data that is stored in various formats, such as key-value pairs, documents, columns, or graphs. NoSQL does not have a standard query language, but rather uses different APIs or languages for accessing and manipulating data. NoSQL does not support ACID guarantees, but rather offers BASE (Basically Available, Soft state, Eventual consistency) properties, which allow for high availability, scalability, and performance in distributed systems. NoSQL is suitable for applications that require flexible data models, fast writes, horizontal scaling, and real-time processing. Some examples of NoSQL are MongoDB, Redis, Cassandra, and Neo4j¹².

NewSQL is a term that describes a new group of databases that combine the features of relational DB (SQL) and NoSQL. NewSQL databases use relational data models and SQL query language, but also provide scalability, flexibility, and performance of NoSQL databases. NewSQL databases use various techniques to achieve this, such as sharding, replication, caching, concurrency control, and distributed transactions. NewSQL databases aim to address the limitations of both relational DB (SQL) and NoSQL databases in handling large-scale and complex data workloads. Some examples of NewSQL are VoltDB, MemSQL, CockroachDB, and TiDB³⁴.

Source: Conversation with Bing, 9/21/2023
(1) Relational vs. NoSQL data - .NET | Microsoft Learn. https://learn.microsoft.com/en-us/dotnet/architecture/cloud-native/relational-vs-nosql-data.
(2) NoSQL, NewSQL, or RDBMS: How To Choose - InformationWeek. https://www.informationweek.com/big-data-analytics/nosql-newsql-or-rdbms-how-to-choose.
(3) NewSQL: The Bridge between SQL and NoSQL - Analytics Vidhya. https://www.analyticsvidhya.com/blog/2022/06/newsql-the-bridge-between-sql-and-nosql/.
(4) NoSQL vs. NewSQL: What's the difference? - Volt Active Data. https://www.voltactivedata.com/blog/2016/09/nosql-vs-newsql-whats-difference/.
(5) undefined. https://eu-images.contentstack.com/v3/assets/blt66983808af36a8ef/blt3fe57d095790034a/61011a86da22395e2cc8acf6/NWC-stack-logo_3.png.
(6) undefined. https://eu-images.contentstack.com/v3/assets/blt66983808af36a8ef/blt0816c01687333878/610119936c1bfa5e2d66efb6/DR_Logo_Stacked_Black.png.
(7) undefined. https://eu-images.contentstack.com/v3/assets/blt66983808af36a8ef/blt18e31896ac4268a1/61017aa2bc767c65981b3bb0/tech-library-logo_1.png.
(8) undefined. https://eu-images.contentstack.com/v3/assets/blt66983808af36a8ef/blt70477ef3b3642d3b/610119938bb8dc5cf2523667/OMDIA_LOGO_BLACK_2_with_extra_height.png.

## How these 2 things can scale up?

Scaling up is the process of increasing the capacity and performance of a system to handle more load or traffic. Different database systems have different ways of scaling up, depending on their data models, architectures, and features. Here is a brief summary of how relational DB (SQL) and NoSQL can scale up:

- Relational DB (SQL) uses structured data that is organized in tables with predefined schemas. SQL (Structured Query Language) is the standard language for querying and manipulating data in relational databases. Relational DB (SQL) supports ACID (Atomicity, Consistency, Isolation, Durability) guarantees, which ensure data integrity and consistency in transactions. Relational DB (SQL) is suitable for applications that require complex queries, joins, transactions, and data consistency. However, relational DB (SQL) has some challenges in scaling up, such as:
    - Most relational DB (SQL) are vertically scalable, which means that you can increase the load on a single server by increasing components like RAM, SSD, or CPU. However, this approach has some limitations, such as high cost, hardware constraints, and single point of failure¹².
    - Some relational DB (SQL) are horizontally scalable, which means that they can handle increased traffic by adding more servers to the database. However, this approach requires more complexity and coordination, such as sharding, replication, caching, concurrency control, and distributed transactions²³.
- NoSQL uses unstructured or semi-structured data that is stored in various formats, such as key-value pairs, documents, columns, or graphs. NoSQL does not have a standard query language, but rather uses different APIs or languages for accessing and manipulating data. NoSQL does not support ACID guarantees, but rather offers BASE (Basically Available, Soft state, Eventual consistency) properties, which allow for high availability, scalability, and performance in distributed systems. NoSQL is suitable for applications that require flexible data models, fast writes, horizontal scaling, and real-time processing. However, NoSQL also has some challenges in scaling up, such as:
    - Most NoSQL databases are horizontally scalable, which means that they can handle increased traffic by adding more servers to the database. However, this approach requires more tradeoffs between availability and consistency¹². For example, some NoSQL databases use eventual consistency, which means that the data may not be the same across all servers at any given time⁴. This can cause problems such as inconsistency, concurrency anomalies, or data loss⁵.
    - Some NoSQL databases are vertically scalable, which means that they can increase the load on a single server by increasing components like RAM, SSD, or CPU. However, this approach has some limitations as well¹². For example, some NoSQL databases use in-memory storage or caching techniques to improve performance⁶, but this can also increase the risk of data loss or corruption in case of power failure or system crash⁷.

In summary, both relational DB (SQL) and NoSQL have different ways of scaling up to handle more load or traffic. However, both types of databases also have some challenges and tradeoffs in doing so. Therefore, choosing the right database for your application depends on your requirements and preferences.

Source: Conversation with Bing, 9/21/2023
(1) Why do NoSql databases scale better than relational databases? How .... https://stackoverflow.com/questions/68368190/why-do-nosql-databases-scale-better-than-relational-databases-how-should-i-choo.
(2) SQL, NoSQL, and Scale: How DynamoDB scales where relational databases .... https://www.alexdebrie.com/posts/dynamodb-no-bad-queries/.
(3) SQL vs NoSQL Databases: What’s The Difference? - BMC Software. https://www.bmc.com/blogs/sql-vs-nosql/.
(4) NoSQL Vs SQL Databases | MongoDB. https://www.mongodb.com/nosql-explained/nosql-vs-sql.
(5) Is SqlServer or NoSql more cost efficient when scaling horizontally. https://dba.stackexchange.com/questions/310105/is-sqlserver-or-nosql-more-cost-efficient-when-scaling-horizontally.
(6) undefined. https://softwareengineering.stackexchange.com/questions/194340/why-are-nosql-databases-more-scalable-than-sql.
(7) undefined. https://neo4j.com/blog/acid-vs-base-consistency-models-explained/.

## 3 normal forms in DBMS

The three normal forms in DBMS are:

- First Normal Form (1NF): This is the most basic level of normalization. In 1NF, each table cell should contain only a single value, and each column should have a unique name. The first normal form helps to eliminate duplicate data and simplify queries¹.
- Second Normal Form (2NF): 2NF eliminates redundant data by requiring that each non-key attribute be dependent on the primary key. This means that each column should be directly related to the primary key, and not to other columns¹.
- Third Normal Form (3NF): 3NF builds on 2NF by requiring that all non-key attributes are independent of each other. This means that each column should be directly related to the primary key, and not to any other columns in the same table¹.

Normal forms help to reduce data redundancy, increase data consistency, and improve database performance. However, higher levels of normalization can lead to more complex database designs and queries. It is important to strike a balance between normalization and practicality when designing a database¹.

If you want to learn more about the three normal forms in DBMS, you can check out these resources:

- [Normal Forms in DBMS - Database Normalization](^1^) is an article that explains the concept of normalization and the first three normal forms with examples.
- [Third Normal Form (3NF)](^2^) is an article that discusses the third normal form in detail and how to convert a relation to 3NF.
- [Normal Forms 1nf 2nf 3nf Table Examples](^3^) is an article that provides some examples of tables in different normal forms and how to normalize them.
- [3NF in DBMS | Third Normal Form](^4^) is an article that defines the third normal form and its advantages and disadvantages.

Source: Conversation with Bing, 9/21/2023
(1) Normal Forms in DBMS - Database Normalization - GeeksforGeeks. https://www.geeksforgeeks.org/normal-forms-in-dbms/.
(2) Normal Forms in DBMS - Database Normalization - GeeksforGeeks. https://www.geeksforgeeks.org/normal-forms-in-dbms/.
(3) Third Normal Form (3NF) - GeeksforGeeks. https://www.geeksforgeeks.org/third-normal-form-3nf/.
(4) Normal Forms 1nf 2nf 3nf Table Examples - freeCodeCamp.org. https://www.freecodecamp.org/news/database-normalization-1nf-2nf-3nf-table-examples/.
(5) 3NF in DBMS | Third Normal Form - javatpoint. https://www.javatpoint.com/dbms-third-normal-form.

## ACID of SQL and BASE of NoSQL? Why NoSQL is eventual consistency?

ACID and BASE are two acronyms that describe the properties of database transactions. ACID stands for Atomicity, Consistency, Isolation, and Durability. BASE stands for Basically Available, Soft state, and Eventual consistency. They represent two different approaches to ensuring data integrity and availability in distributed systems.

ACID is a traditional model that guarantees that transactions are reliable and consistent. It ensures that each transaction is either fully completed or aborted, and that the database remains in a valid state at all times. ACID is suitable for applications that require complex queries, joins, transactions, and data consistency. Relational databases, such as MySQL, PostgreSQL, Oracle, and SQL Server, are examples of ACID-compliant databases¹².

BASE is a relaxed model that allows for more flexibility and scalability. It sacrifices some consistency for higher availability and performance. It allows for some data to be temporarily inconsistent or outdated across different nodes, as long as it eventually converges to a consistent state. BASE is suitable for applications that require flexible data models, fast writes, horizontal scaling, and real-time processing. NoSQL databases, such as MongoDB, Cassandra, Redis, and DynamoDB, are examples of BASE-compliant databases¹².

NoSQL databases use eventual consistency because they are designed to handle large-scale and distributed data. Maintaining strict consistency in fully distributed systems has a high overhead and can slow down the system or cause failures. Eventual consistency enables high availability by spreading and replicating data across multiple nodes. It also improves performance by reducing locking and blocking. However, eventual consistency also introduces some trade-offs and challenges, such as inconsistency, concurrency anomalies, data loss, or conflict resolution³⁴.

Source: Conversation with Bing, 9/21/2023
(1) ACID Model vs BASE Model For Database - GeeksforGeeks. https://www.geeksforgeeks.org/acid-model-vs-base-model-for-database/.
(2) ACID vs. BASE: Comparison of Database Transaction Models - phoenixNAP. https://phoenixnap.com/kb/acid-vs-base.
(3) Difference between SQL and NoSQL - GeeksforGeeks. https://www.geeksforgeeks.org/difference-between-sql-and-nosql/.
(4) Eventual Consistency in NoSQL Databases: Theory and Practice. https://dzone.com/articles/eventual-consistency-nosql.
(5) NoSQL and eventual consistency - real world examples. https://stackoverflow.com/questions/5466012/nosql-and-eventual-consistency-real-world-examples.
(6) Eventual Consistency - Great Learning. https://www.mygreatlearning.com/no-sql/tutorials/eventual-consistency.
(7) Meaning of eventual consistency in Cassandra? - Stack Overflow. https://stackoverflow.com/questions/4584353/meaning-of-eventual-consistency-in-cassandra.
(8) What is Eventual Consistency? - Volt Active Data. https://www.voltactivedata.com/blog/2022/09/what-is-eventual-consistency/.

## CAP theorem in this case. [This is a so nice graph](http://blog.nahurst.com/visual-guide-to-nosql-systems)

In CAP theorem:

- C stands for Consistency
- A stands for Availability
- P stands for Network Partition

It's kinda confused when people say we can only choose 2 out of three things because network partition is not something we can choose in a distributed system.
In the good condition, when there is no network partition, a system can guarantee both consistency and availability. But when the network fault comes, we have to choose one thing between Consistency and Availability to sacrifice.

## What is parameterized statement (in Java it's prepared statement)? How does it work **internally**?

A parameterized statement (also known as a prepared statement) is a way of writing SQL queries that use placeholders for parameters instead of embedding them directly in the query. This has several advantages, such as:

- It prevents SQL injection attacks, which are malicious attempts to execute unauthorized commands or access sensitive data by injecting malicious input into the query. By using placeholders, the input is treated as data, not as part of the query syntax¹².
- It improves performance, as the query can be compiled and cached by the database system once, and then executed multiple times with different parameter values. This reduces the overhead of parsing and optimizing the query for each execution¹³.
- It simplifies the code, as it avoids the need to concatenate strings or escape special characters to construct the query. It also makes the code more readable and maintainable¹⁴.

To use a parameterized statement, you need to follow these steps:

- Create a SQL query with placeholders for parameters, usually denoted by question marks (?) or named variables (such as @name or :email). For example:

```sql
INSERT INTO CustomerTable (Name, Email) VALUES (?, ?)
```

- Create a parameterized statement object using a database connection and the SQL query. For example, in Java, you can use the `prepareStatement` method of the `Connection` interface to create a `PreparedStatement` object⁵:

```java
PreparedStatement pstmt = conn.prepareStatement(sql);
```

- Set the values for the parameters using the appropriate methods of the parameterized statement object. For example, in Java, you can use methods such as `setString`, `setInt`, or `setDate` of the `PreparedStatement` interface to set the values for each placeholder by index or name⁵:

```java
pstmt.setString(1, name); // set the first placeholder to name
pstmt.setString(2, email); // set the second placeholder to email
```

- Execute the parameterized statement using the appropriate methods of the parameterized statement object. For example, in Java, you can use methods such as `executeQuery` or `executeUpdate` of the `PreparedStatement` interface to execute the query and return a result set or an update count⁵:

```java
int rows = pstmt.executeUpdate(); // execute the query and get the number of affected rows
```

- Close the parameterized statement object and release any resources associated with it. For example, in Java, you can use the `close` method of the `PreparedStatement` interface to close the object⁵:

```java
pstmt.close(); // close the prepared statement
```

For more information on how to use parameterized statements in different languages and database systems, you can refer to these sources:

- [How and Why to Use Parameterized Queries](^1^) is an article that explains the concept and benefits of parameterized queries and how to use them with PHP and SQL Server.
- [How PreparedStatement Works Internally in Java: How compilation & caching of SQL works](^2^) is an article that discusses how parameterized statements work internally in Java and how they prevent SQL injection attacks.
- [Parameterized Queries](^3^) is a tutorial that shows how to use parameterized queries with Python and SQLite.
- [Parameterized Queries in PostgreSQL](^4^) is a tutorial that shows how to use parameterized queries with Node.js and PostgreSQL.
- [Using Prepared Statements](^5^) is a tutorial that shows how to use parameterized statements with Java and JDBC.

Source: Conversation with Bing, 9/21/2023
(1) How and Why to Use Parameterized Queries - Microsoft Community Hub. https://techcommunity.microsoft.com/t5/sql-server-blog/how-and-why-to-use-parameterized-queries/ba-p/383483.
(2) How PreparedStatement Works Internally in Java: How compilation .... https://stackoverflow.com/questions/41758436/how-preparedstatement-works-internally-in-java-how-compilation-caching-of-sql.
(3) php - What is parameterized query? - Stack Overflow. https://stackoverflow.com/questions/4712037/what-is-parameterized-query.
(4) What is the difference between prepared statement and parameterized .... https://stackoverflow.com/questions/76317435/what-is-the-difference-between-prepared-statement-and-parameterized-query-in-npg.
(5) What is Parameterized Query? - Definition from Techopedia. https://www.techopedia.com/definition/24414/parameterized-query.
(6) How and Why to Use Parameterized Queries - Microsoft Community Hub. https://techcommunity.microsoft.com/t5/sql-server-blog/how-and-why-to-use-parameterized-queries/ba-p/383483.
(7) How PreparedStatement Works Internally in Java: How compilation .... https://stackoverflow.com/questions/41758436/how-preparedstatement-works-internally-in-java-how-compilation-caching-of-sql.
(8) php - What is parameterized query? - Stack Overflow. https://stackoverflow.com/questions/4712037/what-is-parameterized-query.
(9) What is the difference between prepared statement and parameterized .... https://stackoverflow.com/questions/76317435/what-is-the-difference-between-prepared-statement-and-parameterized-query-in-npg.
(10) What is Parameterized Query? - Definition from Techopedia. https://www.techopedia.com/definition/24414/parameterized-query.

## What is SQL injection? How to avoid it?

SQL injection is a type of attack that exploits a vulnerability in a web application or database that uses SQL (Structured Query Language) to manipulate data. An attacker can inject malicious SQL code into the input fields of a web form or a URL parameter, and trick the application or database into executing it. This can result in data theft, data corruption, unauthorized access, or other damages¹.

To avoid SQL injection attacks, developers should use parameterized queries or prepared statements, which separate the SQL code from the user input. This way, the input is treated as data, not as part of the query syntax. Parameterized queries or prepared statements can be implemented in various programming languages, such as Java, PHP, Python, and more²³. Additionally, developers should also validate and sanitize the user input before using it in a query, and use secure coding practices and frameworks⁴.

Source: Conversation with Bing, 9/21/2023
(1) SQL Injection & How To Prevent It - Kaspersky. https://www.kaspersky.com/resource-center/definitions/sql-injection.
(2) SQL Injection and How to Prevent It? | Baeldung. https://www.baeldung.com/sql-injection.
(3) What is SQL Injection (SQLi) and How to Prevent It - GuardRails. https://www.guardrails.io/blog/what-is-sql-injection-sqli-and-how-to-prevent-it/.
(4) How to Protect Against SQL Injection Attacks. https://security.berkeley.edu/education-awareness/how-protect-against-sql-injection-attacks.

## How many "requests" you have to send to Database in a single prepared statement query? // one for compile and one for execute

The number of requests you have to send to the database in a single prepared statement query depends on the database system and the implementation of the prepared statement. Generally, there are two types of prepared statements: server-side and client-side¹.

- Server-side prepared statements are executed by the database server, which means that you have to send at least two requests to the database: one to prepare the statement and one to execute it with the parameter values. The advantage of this method is that the database server can cache and optimize the statement for future executions, which can improve performance and security. However, the disadvantage is that it requires more network round trips and consumes more server resources¹².
- Client-side prepared statements are executed by the database client, which means that you only have to send one request to the database: one to execute the statement with the parameter values. The advantage of this method is that it reduces network overhead and server load. However, the disadvantage is that it does not benefit from the caching and optimization of the database server, and it may be vulnerable to SQL injection attacks if not implemented properly¹³.

Some database systems, such as MySQL, support both types of prepared statements and allow you to choose which one to use. Other database systems, such as PostgreSQL, only support server-side prepared statements. Therefore, the number of requests you have to send to the database in a single prepared statement query may vary depending on your choice or availability of the prepared statement type¹⁴.

Source: Conversation with Bing, 9/21/2023
(1) Do prepared statements persist between requests?. https://stackoverflow.com/questions/18138804/do-prepared-statements-persist-between-requests.
(2) Execute multiple queries using a single JDBC Statement object. https://stackoverflow.com/questions/21327012/execute-multiple-queries-using-a-single-jdbc-statement-object.
(3) mysqli: can it prepare multiple queries in one statement?. https://stackoverflow.com/questions/11632902/mysqli-can-it-prepare-multiple-queries-in-one-statement.
(4) Submitting Multiple SQL Statements in a Single Request. https://docs.snowflake.com/en/developer-guide/sql-api/submitting-multiple-statements.
(5) Is there a more efficient way of executing multiple SQL prepared .... https://codereview.stackexchange.com/questions/67220/is-there-a-more-efficient-way-of-executing-multiple-sql-prepared-statements-at-o.
(6) undefined. http://www.postgresql.org/docs/9.2/static/sql-prepare.html.

## Can you reuse the compiled query multiple times? (does it help to speed up your application?)

Yes, you can reuse the compiled query multiple times with different parameter values, and it can help to speed up your application. A compiled query is a query that has been parsed and optimized by the database system once, and then stored in memory for future executions. By reusing the compiled query, you can avoid the overhead of parsing and optimizing the query for each execution, which can improve performance and security. However, the number of requests you have to send to the database in a single prepared statement query depends on the database system and the implementation of the prepared statement. Generally, there are two types of prepared statements: server-side and client-side¹. Server-side prepared statements require at least two requests to the database: one to prepare the statement and one to execute it with the parameter values. Client-side prepared statements require only one request to the database: one to execute the statement with the parameter values. Therefore, the number of requests you have to send to the database in a single prepared statement query may vary depending on your choice or availability of the prepared statement type¹. For more information on how to use compiled queries in different languages and database systems, you can refer to these sources:

- [How to: Store and Reuse Queries - ADO.NET](^2^) is an article that explains how to use compiled queries with C# and ADO.NET.
- [How PreparedStatement Works Internally in Java: How compilation & caching of SQL works](^3^) is an article that discusses how compiled queries work internally in Java and how they prevent SQL injection attacks.
- [Parameterized Queries](^4^) is a tutorial that shows how to use compiled queries with Python and SQLite.
- [Parameterized Queries in PostgreSQL](^5^) is a tutorial that shows how to use compiled queries with Node.js and PostgreSQL.

Source: Conversation with Bing, 9/21/2023
(1) How to reuse a large query without repeating it? - Stack Overflow. https://stackoverflow.com/questions/9119465/how-to-reuse-a-large-query-without-repeating-it.
(2) How to: Store and Reuse Queries - ADO.NET | Microsoft Learn. https://learn.microsoft.com/en-us/dotnet/framework/data/adonet/sql/linq/how-to-store-and-reuse-queries.
(3) Call a SQL Server CTE multiple times and reuse the data. https://expert-only.com/en/t-sql/call-a-sql-server-cte-multiple-times/.
(4) Unleash EF Core Performance With Compiled Queries - Milan Jovanovic. https://www.milanjovanovic.tech/blog/unleash-ef-core-performance-with-compiled-queries.
(5) Why does my query run multiple times - Power Query. https://learn.microsoft.com/en-us/power-query/multiple-queries.

## How indexing works internally?

Indexing is a technique that improves the performance of database queries by creating a data structure that allows faster access to the data. Indexing works by storing a copy of one or more columns of a table in a sorted order, along with a pointer to the corresponding row in the original table. The index data structure is usually a B-tree, which is a balanced tree that can efficiently search, insert, and delete values. When a query is executed, the database system can use the index to quickly find the matching rows, instead of scanning the entire table. This reduces the number of disk I/O operations and the query execution time¹².

However, indexing also has some drawbacks, such as:

- Indexing consumes extra disk space, as it creates a separate data structure for each index.
- Indexing increases the overhead of insert, update, and delete operations, as it requires updating the index data structure as well as the table.
- Indexing may not be effective for some types of queries, such as those that use complex conditions, range searches, or full-text searches¹³.

Therefore, indexing requires careful design and optimization, depending on the data characteristics and query patterns. Some of the factors that affect indexing are:

- The cardinality of the column, which is the number of distinct values in the column. A high-cardinality column has many unique values, while a low-cardinality column has few unique values. Generally, indexing is more beneficial for high-cardinality columns, as they can narrow down the search results more effectively¹ .
- The selectivity of the query, which is the percentage of rows that match the query condition. A high-selectivity query returns few rows, while a low-selectivity query returns many rows. Generally, indexing is more beneficial for high-selectivity queries, as they can avoid scanning unnecessary rows¹ .
- The size and type of the column, which affect the storage and comparison cost of the index. Generally, indexing is more beneficial for smaller and simpler data types, such as integers or dates, than for larger and complex data types, such as strings or blobs¹ .

If you want to learn more about how indexing works internally in different database systems, you can check out these resources:

- [How database indexing actually works internally? - Pankaj Tanwar](^1^) is an article that explains the concept and benefits of indexing and some common indexing methods.
- [sql - How does database indexing work? - Stack Overflow](^2^) is an article that provides a detailed answer on how indexing works and why it is needed.
- [How Does Indexing Work | Tutorial by Chartio](^3^) is a tutorial that shows how indexing works with examples and diagrams.

Source: Conversation with Bing, 9/21/2023
(1) How database indexing actually works internally? - Pankaj Tanwar. https://www.pankajtanwar.in/blog/how-database-indexing-actually-works-internally.
(2) sql - How does database indexing work? - Stack Overflow. https://stackoverflow.com/questions/1108/how-does-database-indexing-work.
(3) How Does Indexing Work | Tutorial by Chartio. https://chartio.com/learn/databases/how-does-indexing-work/.
(4) How database indexing actually works internally? - Pankaj Tanwar. https://www.pankajtanwar.in/blog/how-database-indexing-actually-works-internally.
(5) sql - How does database indexing work? - Stack Overflow. https://stackoverflow.com/questions/1108/how-does-database-indexing-work.
(6) How Does Indexing Work | Tutorial by Chartio. https://chartio.com/learn/databases/how-does-indexing-work/.

## What algorithm and data structure indexing used? And why?

Index can use a hash table or B-Tree. [The index is decided to use depending on the data type and how you query the data](https://dev.mysql.com/doc/refman/8.0/en/index-btree-hash.html).

## How composite indexing works?

Composite indexing is a technique that creates an index on multiple columns of a table, which can improve the performance of queries that use those columns in the WHERE clause, the JOIN condition, or the ORDER BY clause. A composite index works by sorting the data based on the order of the columns in the index, and storing a pointer to the corresponding row in the original table. For example, if you create a composite index on columns (a,b,c), the data will be sorted first by column a, then by column b, then by column c. A query that uses these columns can use the index to quickly find the matching rows, instead of scanning the entire table¹.

However, composite indexing also has some limitations and trade-offs, such as:

- Composite indexing consumes more disk space and memory than single-column indexing, as it stores more information in the index data structure.
- Composite indexing increases the overhead of insert, update, and delete operations on the table, as it requires updating the index data structure as well as the table.
- Composite indexing may not be effective for queries that do not use all or some of the columns in the index, or use them in a different order than the index. For example, a query that uses only column c or uses columns (c,b,a) will not benefit from a composite index on columns (a,b,c)².

Therefore, composite indexing requires careful design and optimization, depending on the data characteristics and query patterns. Some of the factors that affect composite indexing are:

- The cardinality of each column in the index, which is the number of distinct values in the column. Generally, higher cardinality columns should be placed first in the index, as they can narrow down the search results more effectively².
- The selectivity of each column in the index, which is the percentage of rows that match a given value in the column. Generally, higher selectivity columns should be placed first in the index, as they can reduce the number of rows to scan³.
- The size and type of each column in the index, which affect the storage and comparison cost of the index. Generally, smaller and simpler data types should be placed first in the index, as they can improve the performance and efficiency of the index⁴.

If you want to learn more about how composite indexing works internally in different database systems, you can check out these sources:

- [How do composite indexes work?](^1^) is an article that explains the concept and benefits of composite indexing with an example.
- [When should I use a composite index?](^2^) is an article that discusses some scenarios and trade-offs of using composite indexing.
- [MySQL Composite Indexes](^3^) is an article that shows how to create and use composite indexes in MySQL.
- [Composite Indexes: What Are They?](^4^) is an article that describes some best practices and tips for using composite indexes.

Source: Conversation with Bing, 9/21/2023
(1) sql - How do composite indexes work? - Stack Overflow. https://stackoverflow.com/questions/795031/how-do-composite-indexes-work.
(2) An in-depth look at Database Indexing - freeCodeCamp.org. https://www.freecodecamp.org/news/database-indexing-at-a-glance-bb50809d48bd/.
(3) Composite Index: Definition, Types, and Examples - Investopedia. https://www.investopedia.com/terms/c/compositeindex.asp.
(4) mysql - When should I use a composite index? - Stack Overflow. https://stackoverflow.com/questions/1823685/when-should-i-use-a-composite-index.
(5) sql - How do composite indexes work? - Stack Overflow. https://stackoverflow.com/questions/795031/how-do-composite-indexes-work.
(6) An in-depth look at Database Indexing - freeCodeCamp.org. https://www.freecodecamp.org/news/database-indexing-at-a-glance-bb50809d48bd/.
(7) Composite Index: Definition, Types, and Examples - Investopedia. https://www.investopedia.com/terms/c/compositeindex.asp.
(8) mysql - When should I use a composite index? - Stack Overflow. https://stackoverflow.com/questions/1823685/when-should-i-use-a-composite-index.

## How to know your query is using index?

By adding "explain" in front of the query, we will get how the query ran and if it uses index or not.

The query optimizer will use index automatically if possible and chose the index that it thinks is the best. And we can force our query to use an index by specifying it in the query.

## How index work in this case: `WHERE age = 5` and `Where age > 5`? The complexity to go to the next record?

The way index works in this case depends on the type and structure of the index. Assuming that the index is a B-tree index on the age column, which is a common type of index in many database systems, the following steps can be taken to answer the queries:

- For `WHERE age = 5`, the database system can use the index to perform a binary search on the sorted age values, and find the first entry that matches 5. Then, it can follow the pointer to the corresponding row in the table, and return it as a result. It can also scan the next entries in the index until it finds a different value than 5, and return all the matching rows. The complexity of this operation is O(log n), where n is the number of entries in the index¹.
- For `WHERE age > 5`, the database system can use the index to perform a binary search on the sorted age values, and find the first entry that is greater than 5. Then, it can follow the pointer to the corresponding row in the table, and return it as a result. It can also scan the next entries in the index until it reaches the end, and return all the matching rows. The complexity of this operation is O(log n + m), where n is the number of entries in the index, and m is the number of matching rows¹.

To go to the next record in both cases, the database system can simply move to the next entry in the index, and follow its pointer to the table. The complexity of this operation is O(1), which means constant time¹.

Source: Conversation with Bing, 9/21/2023
(1) python - How to use if and else statements to achieve Age Classifier .... https://stackoverflow.com/questions/32528468/how-to-use-if-and-else-statements-to-achieve-age-classifier-program.
(2) sql - How to calculate age (in years) based on Date of Birth and .... https://stackoverflow.com/questions/1572110/how-to-calculate-age-in-years-based-on-date-of-birth-and-getdate.
(3) Age Structure - Our World in Data. https://ourworldindata.org/age-structure.
(4) Child and youth mortality data ages 5-24 - UNICEF DATA. https://data.unicef.org/topic/child-survival/child-and-youth-mortality-age-5-24/.

## Indexing with char?

For text fields, index on that column only is used when filter condition filters a prefix of this column.

## The complexity of SQL query? How to measure it? How SQL optimize a query?

The complexity of a SQL query is a measure of how difficult it is to write, understand, and execute the query. There are different methods and metrics for measuring the complexity of a SQL query, such as:

- Cyclomatic complexity: This is a measure of how complicated the control flow is in a query. It is based on the number of conditions, branches, and loops in the query. A higher cyclomatic complexity means a more complex query¹.
- Halstead complexity: This is a measure of how complex the arithmetic is in a query. It is based on the number of operators, operands, and distinct elements in the query. A higher Halstead complexity means a more complex query¹.
- SQL Query Complexity: This is a model proposed by Gourav Sardana that considers the SQL query attributes, such as the number of tables, columns, joins, subqueries, aggregates, and functions in the query. A higher SQL Query Complexity means a more complex query².

SQL optimizes a query by transforming it into an efficient execution plan that minimizes the time and resources needed to retrieve the data. SQL uses various techniques and algorithms to optimize a query, such as:

- Parsing and validating the syntax and semantics of the query.
- Analyzing the statistics and metadata of the tables and indexes involved in the query.
- Generating multiple possible execution plans for the query, using different methods such as join order, join type, join algorithm, access method, filtering condition, sorting order, etc.
- Estimating the cost and benefit of each execution plan, based on factors such as CPU time, I/O operations, memory usage, network traffic, etc.
- Choosing the best execution plan for the query, based on the lowest cost or highest benefit criteria.
- Executing the chosen plan and returning the results to the user³⁴.

If you want to learn more about how to measure and optimize SQL queries, you can check out these resources:

- [Measuring the complexity of SQL statements - Stack Overflow](^1^) is an article that explains some common measures of software complexity and how they can be applied to SQL queries.
- [SQL Query Complexity - GeeksforGeeks](^2^) is an article that describes a new model for measuring the complexity of SQL queries based on their attributes.
- [How to Optimize SQL Queries: Helpful Tips and Techniques](^3^) is an article that explores how to analyze and improve the performance of SQL queries using various tools and techniques.
- [A new model for measuring the complexity of SQL commands](^4^) is an article that proposes a new model for measuring the complexity of SQL commands based on their syntax and semantics.

Source: Conversation with Bing, 9/21/2023
(1) Measuring the complexity of SQL statements - Stack Overflow. https://stackoverflow.com/questions/3353634/measuring-the-complexity-of-sql-statements.
(2) SQL Query Complexity - GeeksforGeeks. https://www.geeksforgeeks.org/sql-query-complexity/.
(3) How to Optimize SQL Queries: Helpful Tips and Techniques. https://www.apriorit.com/dev-blog/381-sql-query-optimization.
(4) A new model for measuring the complexity of SQL commands. https://ieeexplore.ieee.org/document/8534782.
(5) Measuring the complexity of SQL statements - Stack Overflow. https://stackoverflow.com/questions/3353634/measuring-the-complexity-of-sql-statements.
(6) SQL Query Complexity - GeeksforGeeks. https://www.geeksforgeeks.org/sql-query-complexity/.
(7) How to Optimize SQL Queries: Helpful Tips and Techniques. https://www.apriorit.com/dev-blog/381-sql-query-optimization.
(8) A new model for measuring the complexity of SQL commands. https://ieeexplore.ieee.org/document/8534782.
(9) Practical Ways to Improve the Performance of SQL Queries. https://learnsql.com/blog/practical-ways-to-improve-the-performance-of-sql-queries/.

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

A bin log, or binary log, is a file that records all the changes made to a MySQL database. It is used for replication, backup, and recovery purposes¹. A bin log contains events that describe the modifications to the database, such as queries, updates, inserts, deletes, and transactions².

Master DB syncs with Slave DB by using bin logs and two threads on the slave server. The master DB writes all the changes to its bin log files. The slave DB reads the bin log files from the master DB and writes them to its relay log files. The relay log files are similar to bin log files, but they store the changes received from the master DB³. The slave DB then executes the events in its relay log files and applies them to its own database. This way, the slave DB replicates the same changes as the master DB⁴.

If you want to learn more about how bin logs work and how to set up replication between master and slave DBs, you can check out these resources:

- [MySQL :: MySQL 8.0 Reference Manual :: 5.4.4 The Binary Log](^1^) is a reference manual that explains the concept and features of bin logs in MySQL.
- [MySQL :: MySQL 8.0 Reference Manual :: 23.2.1 Replication Formats](^2^) is a reference manual that describes the different types of events and formats in bin logs.
- [MySQL :: MySQL 8.0 Reference Manual :: 17.2.1 Replication Implementation Overview](^3^) is a reference manual that provides an overview of how replication works in MySQL using bin logs and relay logs.
- [MySQL :: MySQL 8.0 Reference Manual :: 17.2.2 Replication Channels](^4^) is a reference manual that explains how replication channels are used to communicate between master and slave DBs.

Source: Conversation with Bing, 9/21/2023
(1) replication - How do you re-sync the Master MySQL DB with Slave DB .... https://dba.stackexchange.com/questions/2733/how-do-you-re-sync-the-master-mysql-db-with-slave-db-changes-if-the-master-goes.
(2) database replication - what is the difference between master binary log .... https://stackoverflow.com/questions/52079372/what-is-the-difference-between-master-binary-log-and-slave-binary-log-in-mysql.
(3) MySQL replication and Master-Slave sync process - Medium. https://medium.com/@deelclasico/mysql-replication-and-master-slave-sync-process-fae9ec0d2630.
(4) What is the difference between binlog-do-db and replicate-do-db?. https://stackoverflow.com/questions/44431961/what-is-the-difference-between-binlog-do-db-and-replicate-do-db.
(5) replication - How do you re-sync the Master MySQL DB with Slave DB .... https://dba.stackexchange.com/questions/2733/how-do-you-re-sync-the-master-mysql-db-with-slave-db-changes-if-the-master-goes.
(6) database replication - what is the difference between master binary log .... https://stackoverflow.com/questions/52079372/what-is-the-difference-between-master-binary-log-and-slave-binary-log-in-mysql.
(7) MySQL replication and Master-Slave sync process - Medium. https://medium.com/@deelclasico/mysql-replication-and-master-slave-sync-process-fae9ec0d2630.
(8) What is the difference between binlog-do-db and replicate-do-db?. https://stackoverflow.com/questions/44431961/what-is-the-difference-between-binlog-do-db-and-replicate-do-db.
(9) Is binary logs required on the slave in order to do replication?. https://dba.stackexchange.com/questions/115247/is-binary-logs-required-on-the-slave-in-order-to-do-replication.

## Can a Slave DB be a slave of another Slave DB (we do not need to sync from Master DB directly)?

Yes it can.

## What is Database Sharding? When we need it?

Database sharding is a technique for horizontal scaling of databases, where the data is split across multiple database instances, or shards, to improve performance and reduce the impact of large amounts of data on a single database. A shard is a horizontal data partition that contains a subset of the total data set. It is responsible for serving a portion of the overall workload. Database sharding is also referred to as horizontal partitioning¹.

We need database sharding when we have a large and growing dataset that exceeds the capacity or performance of a single database server. By distributing the data across multiple servers, we can increase the storage space, reduce the query latency, and handle more concurrent requests. Database sharding also allows for horizontal scaling, which means that we can add or remove servers as needed to adjust to the changing demand. Database sharding is suitable for applications that have high write throughput, low data coupling, and predictable access patterns²³.

Source: Conversation with Bing, 9/21/2023
(1) Understanding Database Sharding | DigitalOcean. https://www.digitalocean.com/community/tutorials/understanding-database-sharding.
(2) Database Sharding: Concepts & Examples | MongoDB. https://www.mongodb.com/features/database-sharding-explained.
(3) What is Database Sharding or a Database Shard? - Yugabyte. https://www.yugabyte.com/tech/database-sharding/.
(4) Database Sharding – System Design Interview Concept. https://www.geeksforgeeks.org/database-sharding-a-system-design-concept/.
(5) What is database sharding? | Microsoft Azure. https://azure.microsoft.com/en-us/resources/cloud-computing-dictionary/what-is-database-sharding/.

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
