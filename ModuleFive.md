# `Module 5 - Storage and Databases`

## `5.1 Instance Stores and Amazon Elastic Block Store (Amazon EBS)`

- ### `Instance Stores`
  - Provides temporary `block-level` storage for an Amazon EC2 instance.
  - Block-level storage volumes behave like physical hard drives.
  - When the instance is `terminated`, you `lose` any data in the instance store.
- ### `Amazon Elastic Block Stores (Amazon EBS)`
  - Physically attached to the host computer of an EC2 instance.
  - Provides `block-level` storage volumes that you can use with Amazon EC2 instances.
  - To create an EBS volume, you define the configuration (volume size and type) and provision it.
  - After creating an EBS volume, it can attach to an Amazon EC2 instance.
  - You can take incremental backups of EBS volumes by creating Amazon EBS snapshots.
- ### `Amazon EBS Snapshots`
  - An `incremental` backup.
  - First backup taken of a volume copies all the data.
  - For subsequent backups, only the blocks of data that have changed since the most recent snapshot are saved.

## `5.2 Amazon Simple Storage Service (Amazon S3)`

- ### `Object Storage`
  - Each object consists of `data`, `metadata`, and a `key`.
  - `Data` - can be an image, video, text document, or any other type of file.
  - `Metadata` - contains information about what the data is, how it is used, the object size, etc.
  - `Key` - unique identifier.
- ### `Amazon Simple Storage Service (Amazon S3)`
  - Service that provides `object-level` storage. Amazon S3 stores data as objects in `buckets`.
  - `Unlimited` storage space.
  - Any type of file can be uploaded.
  - The maximum file size for an object in Amazon S3 is `5TB`.
  - Set permissions to control `visibility` and access to it.
  - Use the Amazon S3 versioning feature to `track changes` to your objects over time.
- ### `Amazon S3 Storage Classes`
  - Pay only for what you use.
  - When selecting an Amazon S3 storage class, consider these two factors:
    ```
      1. How often you plan to retrieve your data.
      2. How available you need your data to be.
    ```
  - #### `S3 Standard`
    - Designed for `frequently` accessed data.
    - Stores data in a `minimum of three` Availability Zones.
    - Higher cost compared to other storage classes.
    - `Use cases`: websites, content distribution, and data analytics.
  - #### `S3 Standard-Infrequent Access (S3 Standard-IA)`
    - Ideal for `infrequently` accessed data.
    - Stores data in a `minimum of three` Availability Zones.
    - Lower storage price and higher retrieval price.
  - #### `S3 One Zone-Infrequent Access (S3 One Zone-IA)`
    - Stores data in a `single` Availability Zone.
    - Has a lower storage price than Amazon S3 Standard-IA.
    - `Use cases`: You can easily reproduce your data in the event of an Availability Zone failure.
  - #### `S3 Intelligent-Tiering`
    - Monitors objects’ access patterns.
    - Ideal for data with `unknown` or `changing` access patterns.
    - Requires a small monthly monitoring and automation fee per object.
    - `Use cases`: If you haven’t accessed an object for 30 consecutive days, Amazon S3 automatically moves it to the infrequent access tier, S3 Standard-IA. If you access an object in the infrequent access tier, Amazon S3 automatically moves it to the frequent access tier, S3 Standard.
  - #### `S3 Glacier Instant Retrieval`
    - Works well for archived data that requires `immediate` access.
    - Can retrieve objects within a few milliseconds, same performance as S3 Standard.
  - #### `S3 Glacier Flexible Retrieval`
    - Low-cost storage designed for data archiving.
    - Retrieve objects within `1 minute to 12 hours`.
    - `Use cases`: store archived customer records or older photos and video files.
  - #### `S3 Glacier Deep Archive`
    - long-term retention and digital preservation for data that might be accessed once or twice in a year.
    - Lowest-cost object storage class ideal for archiving.
    - Able to retrieve objects from `12 to 48 hours`.
    - All objects from this storage class are replicated and stored across at least `three` geographically dispersed Availability Zones.
  - #### `S3 Outposts`
    - Creates S3 buckets on Amazon S3 Outposts.
    - Makes it easier to retrieve, store, and access data on AWS Outposts.
    - Delivers object storage to your on-premises AWS Outposts environment.
    - Stores data durably and redundantly across multiple devices and servers on your Outposts.

## `5.3 Amazon Elastic File System (Amazon EFS)`

- ### `Amazon EFS`
  - Scalable file system used with `AWS Cloud services` and `on-premises resources`.
  - As files are added or removed, Amazon EFS grows and shrinks `automatically`.
  - Can `scale on-demand` to petabytes without disrupting applications.
- ### `Comparison between Amazon EBS and Amazon EFS`

  |                         `Amazon EBS`                          |                                    `Amazon EFS`                                    |
  | :-----------------------------------------------------------: | :--------------------------------------------------------------------------------: |
  |                  `Single` availability zone.                  |                           `Multiple` availability zones.                           |
  | EBS and EC2 instances must be in the `same` availability zone | Access data from `all` availability zones within a region where a file is located. |
  |                                                               |         On-premise servers can access Amazon EFS using AWS Direct Connect.         |

## `5.4 Amazon Relational Database Service (Amazon RDS)`

- ### `Relational Databases`
  - Data is stored in a way that relates it to other pieces of data.
  - Uses structured query language (SQL) to store and query data.
- ### `Amazon Relational Database Service (Amazon RDS)`
  - Enables you to run relational databases in the AWS Cloud.
  - Automates tasks such as hardware provisioning, database setup, patching, and backups.
  - Integratable with other services like AWS Lambda to query your database from a serverless application.
  - `Security options`: Encryption at rest (protecting data while it is stored) and encryption in transit (protecting data while it is being sent and received).
- ### `Amazon RDS Database Engines`
  - Supports `six database engines`, which optimize for memory, performance, or input/output (I/O):
    ```
    - Amazon Aurora
    - PostgreSQL
    - MySQL
    - MariaDB
    - Oracle Database
    - Microsoft SQL Server
    ```
- ### `Amazon Aurora`
  - Enterprise-class relational database.
  - Compatible with MySQL and PostgreSQL relational databases.
  - Up to `five times faster than standard MySQL databases` and up to `three times faster than standard PostgreSQL databases`.
  - Reduces database costs by reducing unnecessary input/output (I/O) operations, while ensuring that the database resources remain reliable and available.
  - Replicates `six copies of your data` across `three Availability Zones` and continuously backs up your data to Amazon S3.

## `5.5 Amazon DynamoDB`

- `Non-relational` database.
- `Key-value` database service.
- Delivers `single-digit millisecond` performance at any scale.
- `Serverless` and `automatic scaling`.

## `5.6 Amazon Redshift`

- Data warehousing service that you can use for `big data analytics`.
- Offers the ability to `collect data from many sources` and helps you to understand relationships and trends across your data.

## `5.7 AWS Database Migration Service (AWS DMS)`

- Migrate relational databases, nonrelational databases, and other types of data stores.
- The `source and target databases` can be of the `same type or different types`.
- During migration, your source database remains `operational`, reducing downtime for any applications that rely on the database.
- `Use Cases`:

  - `Development and test database migration`
    ```
    Enables developersto test application against production data without affecting production users.
    ```
  - `Database consolidation`

    ```
    Combining several databases into a single database.
    ```

  - `Continuous replication`

    ```
    Sending on-going copies of your data to other target sources instead of doing a one time-migration.
    ```

## `5.8 Additional Database Service`

- ### `Amazon DocumentDB`
  - Document database service that supports MongoDB workloads.
- ### `Amazon Neptune`
  - Graph database service.
  - Build and run applications that work with highly connected datasets, such as recommendation engines, fraud detection, and knowledge graphs.
  - `Use cases`: social networks.
- ### `Amazon Quatum Ledger Database (Amazon QLDB)`
  - Ledger database service.
  - Can be used to `review` a complete history of all the changes that have been made to your application data.
- ### `Amazon Managed Blockchain`
  - Service that you can use to create and manage `blockchain networks` with open-source frameworks.
  - Blockchain is a distributed ledger system that lets multiple parties run transactions and share data without a central authority.
- ### `Amazon Elasticache`
  - Service that adds caching layers on top of your databases to help improve the read times of common requests.
  - Supports `Redis` and `Memcached` data stores.
- ### `Amazon DynamoDB Accelerator (DAX)`
  - In-memory cache for DynamoDB.
  - Improves response times from single-digit milliseconds to microseconds.

## `Additional Resources`

- [`Cloud Storage on AWS`](https://aws.amazon.com/products/storage)
- [`AWS Storage Blog`](https://aws.amazon.com/blogs/storage/)
- [`Hands-on Tutorials: Storage`](https://aws.amazon.com/getting-started/hands-on/?awsf.getting-started-category=category%23storage&awsf.getting-started-content-type=content-type%23hands-on)
- [`AWS Customer Stories: Storage`](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc%7Cproduct%23api-gateway%7Cproduct%23cloudfront%7Cproduct%23route53%7Cproduct%23directconnect%7Cproduct%23elb&awsf.customer-references-category=category%23storage)
- [`AWS Database Migration Service`](https://aws.amazon.com/dms/)
- [`Databases on AWS`](https://aws.amazon.com/products/databases)
- [`Category Deep Dive: Databases`](https://aws.amazon.com/getting-started/deep-dive-databases/)
- [`AWS Database Blog`](https://aws.amazon.com/blogs/database/)
- [`AWS Customer Stories: Databases`](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc%7Cproduct%23api-gateway%7Cproduct%23cloudfront%7Cproduct%23route53%7Cproduct%23directconnect%7Cproduct%23elb&awsf.customer-references-category=category%23databases)
