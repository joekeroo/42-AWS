# `Module 9 - Migration and Innovation`

## `9.1 AWS Cloud Adoption Framework (AWS CAF)`

- ### `Six Cloud Perspective of the Cloud Adoption Framework`

  - #### `Business Perspective`
    - Ensures that IT aligns with business needs and that IT investments link to key business results.
    - `Common roles in the Business Perspective include`:
      - `Business Manager`
      - `Finance Manager`
      - `Budget Owners`
      - `Strategy Stakeholders`
  - #### `People Perspective`
    - Supports development of an organization-wide change management strategy for successful cloud adoption.
    - `Common roles in the People Perspective include:`
      - `Human Resources`
      - `Staffing`
      - `People Manager`
  - #### `Governance Perspective`
    - Focuses on the skills and processes to align IT strategy with business strategy.
    - `Common roles in the Governance Perspective include`:
      - `Chief Information Officer (CIO)`
      - `Program Managers`
      - `Enterprise Architects`
      - `Business Analysts`
      - `Portfolio Managers`
  - #### `Platform Perspective`
    - Includes principles and patterns for implementing new solutions on the cloud, and migrating on-premises workloads to the cloud.
    - `Common roles in the Platform Perspective include`:
      - `Chief Technology Officer (CTO)`
      - `IT managers`
      - `Solutions architects`
  - #### `Security Perspective`
    - Ensures that the organization meets security objectives for visibility, auditability, control, and agility.
    - `Common roles in the Security Perspective include`:
      - `Chief Information Security Officer (CISO)`
      - `IT security managers`
      - `IT security analysts`
  - #### `Operations Perspective`
    - enable, run, use, operate, and recover IT workloads to the level agreed upon with your business stakeholders.
    - `Common roles in the Operations Perspective include`:
      - `IT operations managers`
      - `IT support managers`

## `9.2 Migration Strategies`

- ### `6 Strategies For Migration`
  - Six of the most common [`migration strategies`](https://aws.amazon.com/blogs/enterprise-strategy/6-strategies-for-migrating-applications-to-the-cloud/) that you can implement are:
    - #### `Rehosting`
      - Also known as “lift-and-shift” involves moving applications without changes.
    - #### `Replatforming`
      - Also known as “lift, tinker, and shift,” involves making a few cloud optimizations to realize a tangible benefit
    - #### `Refactoring/re-architecting`
      - Involves reimagining how an application is architected and developed by using cloud-native features.
      - Driven by a strong business need to add features, scale, or performance that would otherwise be difficult to achieve in the application’s existing environment.
    - #### `Repurchasing`
      - Involves moving from a traditional license to a software-as-a-service model.
    - #### `Retaining`
      - Consists of keeping applications that are critical for the business in the source environment.
    - #### `Retiring`
      - Process of removing applications that are no longer needed.

## `9.3 AWS Snow Family`

- ### `AWS Snow Family Members`

  - [`AWS Snow Family`](https://aws.amazon.com/snow) - a collection of physical devices that help to physically transport up to exabytes of data into and out of AWS.
    ![AWS Snow Family](assets/ModuleNine/aws-snow-family.jpg)
  - These devices offer different capacity points, and most include built-in computing capabilities.
  - AWS owns and manages the Snow Family devices and integrates with AWS security, monitoring, storage management, and computing capabilities.
  - #### `AWS Snowcone`
    - Small, rugged, and secure edge computing and data transfer device.
    - `2 CPUs`, `4GB` of memory, and up to `14 TB` of usable storage`.
  - #### `AWS Snowball`
    - `Snowball Edge Storage Optimized`
      - Large-scale data migrations and recurring transfer workflows, in addition to local computing with higher capacity needs.
      - `Storage`: 80 TB of hard disk drive (HDD) capacity for block volumes and Amazon S3 compatible object storage, and 1 TB of SATA solid state drive (SSD) for block volumes.
      - `Compute`: 40 vCPUs, and 80 GiB of memory to support Amazon EC2 sbe1 instances (equivalent to C5).
    - `Snowball Edge Compute Optimized`
      - Provides powerful computing resources for use cases such as machine learning, full motion video analysis, analytics, and local computing stacks.
      - `Storage`: 80-TB usable HDD capacity for Amazon S3 compatible object storage or Amazon EBS compatible block volumes and 28 TB of usable NVMe SSD capacity for Amazon EBS compatible block volumes.
      - `Compute`: 104 vCPUs, 416 GiB of memory, and an optional NVIDIA Tesla V100 GPU. Devices run Amazon EC2 sbe-c and sbe-g instances, which are equivalent to C5, M5a, G3, and P3 instances.
  - #### `AWS Snowmobile`
    - Exabyte-scale data transfer service used to move large amounts of data to AWS.
    - Transfer up to `100 petabytes` of data per Snowmobile, a 45-foot long ruggedized shipping container, pulled by a semi trailer truck.

## `9.4 Innovation with AWS`

- ### `Innovate with AWS Services`
  - #### `Serverless Applications`
    - Refers to applications that don’t require you to provision, maintain, or administer servers.
    - AWS Lambda is an example of a service that you can use to run serverless applications.
  - #### `Artificial Intelligence`
    - Convert speech to text with `Amazon Transcribe`.
    - Discover patterns in text with `Amazon Comprehend`.
    - Identify potentially fraudulent online activities with `Amazon Fraud Detector`.
    - Build voice and text chatbots with `Amazon Lex`.
  - #### `Machine Learning`
    - Analyze data, solve complex problems, and predict outcomes before they happen.
    - AWS offers `Amazon SageMaker` to remove the difficult work from that process and empower you to build, train, and deploy ML models quickly.

## `Additional Resources`

- [`Migration & Transfer on AWS`](https://aws.amazon.com/products/migration-and-transfer)
- [`A Process for Mass Migrations to the Cloud`](https://aws.amazon.com/blogs/enterprise-strategy/214-2/)
- [`6 Strategies for Migrating Applications to the Cloud`](https://aws.amazon.com/blogs/enterprise-strategy/6-strategies-for-migrating-applications-to-the-cloud/)
- [`AWS Cloud Adoption Framework`](https://aws.amazon.com/professional-services/CAF/)
- [`AWS Fundamentals: Core Concept`](https://aws.amazon.com/getting-started/fundamentals-core-concepts/)
- [`AWS Cloud Enterprise Strategy Blog`](https://aws.amazon.com/blogs/enterprise-strategy/)
- [`Mordenizing with AWS Blog`](https://aws.amazon.com/blogs/modernizing-with-aws/)
- [`AWS Customer Stories: Date Center Migration`](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc%7Cproduct%23api-gateway%7Cproduct%23cloudfront%7Cproduct%23route53%7Cproduct%23directconnect%7Cproduct%23elb&awsf.customer-references-category=category%23datacenter-migration)
