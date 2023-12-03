# `Module 3 - Global Infrastructure and Reliability`

## `3.1 AWS Global Infrastructure`

- ### `Selecting a Region`
  1. Compliance with data governanceand legal requirements
  2. Proximity to customers
  3. Available services within a Region
  4. Pricing
- ### `Availability Zones`
  - Single data center or a group of data centers within a Region.
  - Availability Zones are located tens of miles apart from each other.
  - Reduce the chance that multiple Availability Zones are affected by natural disasters.

## `3.2 Edge Locations`

- A site that Amazon CloudFront uses to store cached copies of your content closer to your customers for faster delivery.

## `3.3 How to Provision AWS Resources`

- ### `Ways to interact with AWS services`
  - #### `AWS Management Console`
    - Web-based interface for accessing and managing AWS services.
    - Includes wizards and automated workflows that can simplify the process of completing tasks.
    - Quickly access recently used services and search for other services by `name`, `keyword`, or `acronym`.
    - You can also use the `AWS Console mobile application` to perform tasks such as monitoring resources, viewing alarms, and accessing billing information.
  - #### `AWS Command Line Interface (AWS CLI)`
    - Control multiple AWS services directly from the command line within one tool.
    - Available for users on `Windows`, `macOS`, and `Linux`.
    - Automate the actions that your services and applications perform through scripts.
  - #### `Software Development Kits (SDKs)`
    - Makes it easier for you to use AWS services through an API designed for your programming language or platform.
    - Enables you to use AWS services with your existing applications or create entirely new applications that will run on AWS.
- ### `Using Manage Tools to interact with AWS services`
  - #### `AWS Elastic Beanstalk`
    - Provide code and configuration settings, and Elastic Beanstalk deploys the resources necessary to perform the following tasks:
      - `Adjust capacity`
      - `Load balancing`
      - `Automatic scaling`
      - `Application health monitoring`
  - #### `AWS CloudFormation`
    - Build an environment by writing lines of code instead of using the AWS Management Console to individually provision resources.
    - Provisions your resources in a safe, repeatable manner, enabling you to frequently build your infrastructure and applications without having to perform manual actions.
    - Determines the right operations to perform when managing your stack and rolls back changes automatically if it detects errors.

## `Additional Resources`

- [`Global Infrastructure`](https://aws.amazon.com/about-aws/global-infrastructure/)
- [`Interactive map of the AWS Global Infrastructure`](https://www.infrastructure.aws/)
- [`Regions and Availability Zones`](https://aws.amazon.com/about-aws/global-infrastructure/regions_az)
- [`AWS Networking and Content Delivery Blog`](https://aws.amazon.com/blogs/networking-and-content-delivery/)
- [`Tools to Build on AWS`](https://aws.amazon.com/tools/)
- [`AWS Customer Stories: Content Delivery`](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc%7Cproduct%23api-gateway%7Cproduct%23cloudfront%7Cproduct%23route53%7Cproduct%23directconnect%7Cproduct%23elb&awsf.customer-references-category=category%23content-delivery)
