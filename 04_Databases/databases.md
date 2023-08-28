# AWS Database Differences

## Aurora
Relational Database.
### Pro
- Aurora comes with Postgres and MySQL compatibility.
- Fully managed serverless database.
- Automated failover, failover priority. Less than 30 seconds failover.
- Automated AutoScaling.
- Master + up to 15 READ replicas. 
- Automated encrypted backups which are stored in a S3.
- Multi-Master WRITE is possible, but only within availability zones, not regional.
- Aurora Global up to 16 READ replicas in each region.
- Aurora Machine Learning, machine learning model using SageMaker

## Contra
- Costs 20% more than RDS databases.
- Multiple master replication only within a region, multiple region write data not possible.

## Use Cases
- High performance, scalable, high available, managed relational database, compatible with Postgres and MySQL.
- WebApps, fast read and write.
- CMS platforms.
- Microservice architecture.

---
<br>

## DynamoDB
NoSQL database.<br>
DynamoDB is the only one global database in AWS which offers global tables.

### Pro
- Automatically replicate READ/Write data across multiple AWS regions.
- Fully managed serverless database.
- Low latency access due to regional replicas.
- Each regional replica is asynchronously updated. Maintain consistency.
- TTL, time to live functionality. Meaning, automatically delete items after expiry timestamp.
- Steaming processing, react in real time.
- Ability to trigger Lambda functions.
- Fully automated on-demand backup, restore, and point-in-time recovery for data protection and archiving.
- DynamoDB DAX for read cache, low latency like ElastiCache.
- Export, import to S3.
- AutoScaling
- Integrated IAM for security.
- Free VPC endpoint (Gateway endpoint), you can connect DynamoDb from a VPC via VPC Endpoint for free.

### Use Cases:
- Serverless architectures.
- Millions of requests per seconds.
- Multi regional architecture.  

---
<br>

## DocumentDB
NoSQL Database.<br>
Aurora is an AWS implementation of Postgres/MySQL and DocumentDB is the same for MongoDB.

### Pro
- AutoScaling.
- MongoDB compatibility.
- Replication across three AZ.
- Fully managed serverless database.
- Continuous backups into an S3, automated snapshots.

### Contra 
- Multi region READ/Write replications not possible.

### Use Cases
- Million requests per second. 

___
<br>

## RSD
Relational databases.<br>
Managed Postgres, MySQL, Oracle, SQL Server, MariaDB databases.

### Pro
- AutoScaling capability.
- Multi AZ read replicas.
- Automated backups.
- Manual DB snapshots possible.
- RDS Custom to customize the underlying EC2 Instance only for Oracle & SQL Server.

### Contra
- Multi region READ/Write replications not possible.

___
<br>

## S3
The core service of AWS, a key/value store for objects.

### S3 Types
- S3 Standard: General-purpose storage for various data types like static websites, videos, pictures, and more.
- S3 Standard-IA (Infrequent Access): Cost-effective storage for infrequently accessed data, suitable for backups and disaster recovery.
- S3 One Zone-IA (Infrequent Access): Cost-effective infrequent access storage with data stored in a single availability zone for reduced redundancy.
- S3 Glacier (Instant Retrieval): Low-cost archival storage with quick retrieval times for data that may be needed more frequently.
- S3 Glacier Deep Archive: Extremely low-cost archival storage with longer retrieval times, suitable for data that is accessed very infrequently. Also called cold data.
- S3 Intelligent-Tiering: Automatically moves objects between frequent and infrequent access tiers based on changing usage patterns, optimizing costs.

### Pro
- Different tiers for data backups.
- Cheap data store of any kind of data.
- Able to trigger Lambda functions.
- Accessible by Lambda.
- Versioning of data in S3 possible.
- Ability to create different path, for example /photos, /private, /secure and grant specific or different policies to each path.
- Lifecycle rules: Manage things on S3 for example move data from S3 Standard to S3 Glacier or delete data which are older than 7 years. 
- Sync between S3 buckets in different regions possible via CLI.
- Batch operations: Encrypt un-encrypt objects etc.
- Event Notifications: Send events via EventBridge to over 18 AWS services like SNS, SQS, Lambda.
- S3 is accessible via roles, can also have policies and you can create an secret link to grant access via this links to other AWS users.
- Requester pays model. You can configure that the requester pay the network costs.
- Possible to set MFA to delete something in S3.
- Ability to set data encryption.
- S3 Glacier Vault Lock. A vaulted object can no longer be deleted.
- Possibility to create pre-signed URL´s. Send other users or friends the link, then he has temporary access over the link (download something for example GET).

### Use Cases
- Deploy static websites, also possible to deploy React, Vuejs websites which have access to an API server.
- Use S3 as a backup database.
- Personal use to store pictures, videos or private backups.
- AWS using S3 for backup for other services like EBS snapshot, Aurora backups, DynamoDB backups, EFS backups etc.

___
<br>

## ElastiCache
ElastiCache is a database in RAM for high performance read.<br>
Redis- and Memcached-compatible service.

### Pro
- For frequently accessed data.
- Session management, store user session data.
- Attachable to multiple microservices.
- Speeds up database and application performance while caching database data etc.
- Compatible with RDS and Aurora.
- Redis for scaling, durability, automated backups to S3. You can also make a backup to the SSD.
- Memcached for multi-node partitioning, multi-threaded architecture.

### Contra
- No backup method for Memcached, but you can use Redis, just keep in mind.

### Use Cases
- In memory caching.
- Speeds up database and application performance.
- Data Analytics.

___
<br>

## Neptune
Graph database.

### Pro
- Fully managed.
- 3 AZ up to 15 read replicas.
- Fully managed.

### Use Cases
- Social Media apps.
- Knowledge graphs.
- Recommendation engines like e-commerce, streaming-provider.

___
<br>

## Keyspaces Apache Cassandra
NoSQL database. <br>
AWS Keyspaces.

### Pro
- Fully managed.
- AutoScaling.
- 3 AZ.
- Encrypted backups.

### Use Cases
- IoT devices info.
- Time series data

___
<br>

## QLDB
Quantum Ledger Database

### Pro
- Review history of all changes made from your application.
- Track all changes.
- Cryptographically verifiable.
- Deployed across multiple AZs with multiple copies per AZ.
- Possible to make backups to S3.
- All data in transit and at rest is encrypted.

### Contra
- Does not support cross-region replication.
- No default backup.

### Use Cases
- It is specifically designed for applications that require an immutable and verifiable transaction history.
- Financial Auditing and Compliance.
- Healthcare Records.
- Legal and Notary Services.

___
<br>

## Timestream
Time series database.

### Pro
- Each data point is associated with a specific timestamp.
- The Timestream database automatically organizes the data based on its timestamps and partitions it for efficient storage and querying.
- You can use the on-demand backup feature to create full backups of your Amazon Timestream tables.

### Use Cases
- Applications that deal with large volumes of time-stamped data points.
- Collect and analyze data directly in the database.
- Log and event analysis.
- Industrial machinery and equipment, helping monitor operational efficiency and predict maintenance needs.
- Digital Marketing Analytics.
- Timestream can automatically manage data retention policies, making it easy to manage and control the lifecycle of your time-series data.

___
<br>

## Solution Architect Summary 😍

- <b>Aurora: </b>Use Aurora for high-performance relational database needs with built-in replication, automatic failover, and compatibility with MySQL or PostgreSQL, ideal for applications requiring scalability and availability.

- <b>DynamoDB: </b>Use DynamoDB for managed NoSQL database needs, especially for high-speed, low-latency access to data with automatic scalability, making it suitable for dynamic and rapidly growing applications. Use it for multi regional architecture.

- <b>DocumentDB: </b>Use DocumentDB for MongoDB-compatible document database needs, offering scalability and security for applications with complex data models and rich querying.

- <b>RDS: </b>Use RDS for managed relational databases (MySQL, PostgreSQL, SQL Server, Oracle, etc.) when you need familiar database engines with automated backups, scaling, and patch management.

- <b>S3: </b>Use S3 for scalable and durable object storage, perfect for storing and retrieving large amounts of unstructured data like images, videos, backups, and static assets.

- <b>ElastiCache Redis: </b>Use ElastiCache with Redis for in-memory data caching and real-time use cases like caching frequently accessed data or session management, improving application performance.

- <b>ElastiCache Memchached: </b>Use ElastiCache with Memcached for simple, fast, in-memory caching to offload databases and reduce database load in applications with simple caching needs.

- <b>Quantum Ledger Database: </b>Use Quantum Ledger Database (QLDB) when you need history of all changes to your data, ensuring trust and data integrity. Perfect for financial institutions.

- <b>Timestream: </b>Use Timestream for time-series data storage and analysis, suitable for applications that need to ingest, store, and analyze large volumes of time-stamped data, such as IoT and monitoring.

- <b>RDS Proxy: </b>AWS RDS Proxy is a managed database proxy service that helps applications efficiently and securely connect to Amazon RDS (Relational Database Service) instances, enhancing scalability, performance, and security of database connections.

