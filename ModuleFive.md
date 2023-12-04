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
    - Designed for frequently accessed data.
    - Stores data in a minimum of three Availability Zones.
    - Use cases: `websites`, `content distribution`, and `data analytics`.
    - `Higher cost` compared to other storage classes.
  - #### `S3 Standard-Infrequent Access (S3 Standard-IA)`
    - Ideal for infrequently accessed data.
    - Lower storage price and higher retrieval price.
    - Stores data in a minimum of three Availability Zones.
