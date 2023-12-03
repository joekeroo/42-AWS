# `Module Two - Compute in the Cloud`

## `Amazon Elastic Compute Cloud (Amazon EC2)`

- [`Amazon EC2`](https://aws.amazon.com/ec2/) - Provides `secure` and `resizable` compute capacity in the cloud as `Amazon EC2 instances`.

  |        `Traditional on-premise resources`         |                        `Amazon EC2 Instances`                        |
  | :-----------------------------------------------: | :------------------------------------------------------------------: |
  |     Spend money upfront to purchase hardware.     |     Provision and launch an Amazon EC2 instance within minutes.      |
  |   Wait for the servers to be delivered to you.    |       Stop using it when you have finished running a workload.       |
  | Install the servers in your physical data center. |  Pay only for the compute time you use when an instance is running.  |
  |      Make all the necessary configurations.       | Save costs by paying only for server capacity that you need or want. |

- How `Amazon EC2` works:
  - `Launch` - Select a template with basic configurations. ( oprating system, application server, application, instance type )
  - `Connect` - Connect to the instance. For example, connect to the instance by logging in and accessing the computer desktop.
  - `Use` - Run commands to install software, add storage, copy and organize files, etc.

## `Amazon EC2 Instance Types`

- [`Amazon EC2 Instance Types`](https://aws.amazon.com/ec2/instance-types/) - Optimized for different tasks. When selecting an instance type, consider the specific needs of your workloads and applications. This might include requirements for `compute`, `memory`, or `storage` capabilities.

  |   `Instances Types`   |                                                                                                              `Description`                                                                                                              |
  | :-------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
  |    General Purpose    |                            Provides a balance of compute, memory, and networking resources. ( application servers, gaming servers, backend servers for enterprise applications, small and medium databases )                            |
  |   Compute Optimized   |                                                                           Ideal for compute-bound applications that benefit from high-performance processors.                                                                           |
  |   Memory Optimized    |                                                                              Deliver fast performance for workloads that process large datasets in memory.                                                                              |
  | Accelerated Computing |        Uses hardware accelerators, or coprocessors, to perform some functions more efficiently than is possible in software running on CPUs. ( floating-point number calculations, graphics processing, data pattern matching )         |
  |   Storage Optimized   | Designed for workloads that require high, sequential read and write access to large datasets on local storage. ( distributed file systems, data warehousing applications, high-frequency online transaction processing (OLTP) systems ) |

## `Amazon EC2 Pricing`

- Pay only for the compute time that you use.
- ### `On-Demand`
  - Ideal for short-term, irregular workloads that cannot be interrupted.
  - No upfront costs or minimum contracts apply.
  - The instances run continuously until you stop them, and you pay for only the compute time you use.
- ### `Reserved Instances (1 year / 3 year terms)`

  1. #### `Standard Reserved Instances`

  - Good fit if you know the EC2 instance type and size you need for your steady-state applications and in which AWS Region you plan to run them.
  - Requires you to state the instance type and size, platform description ( operating system ) and tenancy ( default or dedicated tenancy ).

  2. #### `Convertible Reserved Instances`

  - For those who needs to run their EC2 instances in different Availability Zones or different instance types. Note: You trade in a deeper discount when you require flexibility to run your EC2 instances.
  - At the end of a Reserved Instance term, you can continue using the Amazon EC2 instance without interruption. However, you are charged `On-Demand rates` until you do one of the following:
    - Terminate the instance.
    - Purchase a new Reserved Instance that matches the instance attributes (instance family and size, Region, platform, and tenancy).

- ### `EC2 Instance Savings Plans`
  - For flexibility in your Amazon EC2 usage over the duration of the commitment term.
  - Benefit of saving costs on running any EC2 instance within an EC2 instance family in a chosen Region (for example, M5 usage in N. Virginia) regardless of Availability Zone, instance size, OS, or tenancy.
  - The savings with EC2 Instance Savings Plans are similar to the savings provided by Standard Reserved Instances but does not need any specifications.
- ### `Spot Instances`
  - Ideal for workloads with flexible start and end times, or that can withstand interruptions.
  - Uses unused Amazon EC2 computing capacity and offer you cost savings at up to 90% off of On-Demand prices.
- ### `Dedicated Hosts`
  - physical servers with Amazon EC2 instance capacity that is fully dedicated to use.
  - You can use your existing per-socket, per-core, or per-VM software licenses to help maintain license compliance.
  - You can purchase On-Demand Dedicated Hosts and Dedicated Hosts Reservations. Of all the Amazon EC2 options that were covered, Dedicated Hosts are the most expensive.

## `Scaling Amazon EC2`

- ### `Amazon EC2 Auto Scalling`
  - Automatically add or remove Amazon EC2 instances in response to changing application demand.
  - Maintains a greater sense of application availability.
  - `Dynamic Scalling` - responds to changing demand.
  - `Predictive scaling` - automatically schedules the right number of Amazon EC2 instances based on predicted demand.

## `Elastic Load Balancing`

- AWS service that automatically distributes incoming application traffic across multiple resources, such as Amazon EC2 instances.
- A load balancer acts as a single point of contact for all incoming web traffic to your Auto Scaling group.
- Requests route to the load balancer first. Then, the requests spread across multiple resources that will handle them.
- For example, if you have multiple Amazon EC2 instances, Elastic Load Balancing distributes the workload across the multiple instances so that no single instance has to carry the bulk of it.

## `Messaging and Queuing`

- ### `Monolithic Application (Legacy)`
  - Application with tightly coupled components.
  - If a single component fails, other components fail, and possibly the entire application fails.
- ### `Microservices Approach (Solution)`
  - Application with loosely coupled components.
  - if a single component fails, the other components continue to work because they are communicating with each other.
- ### `Amazon Solution`
  - `Amazon Simple Queue Service (Amazon SQS)`
    - `Send`, `store`, and `receive` messages between software components, without losing messages or requiring other services to be available.
    - Application sends messages into a queue. A user or service retrieves a message from the queue, processes it, and then deletes it from the queue.
  - `Amazon Simple Notification Service (Amazon SNS)`
    - `Publish` / `Subscribe` service.
    - Subscribers can be web servers, email addresses, AWS Lambda functions, etc.

## `Additional Compute Services`

- ### `Serverless Computing`

  - The term "`serverless`" means that your code runs on servers, but you do not need to provision or manage these servers.
  - `Flexibility` to scale serverless applications automatically.
  - Serverless computing can adjust the applications' capacity by modifying the units of consumptions, such as throughput and memory.
  - #### `AWS Lambda`
    - Service that lets you run code without needing to provision or manage servers.
    - Pay only for the compute time that you consume.
    - Runs code for virtually any type of application or backend service. `(zero administration)`
    - For example, a simple Lambda function might involve automatically resizing uploaded images to the AWS Cloud. In this case, the function triggers when uploading a new image.
      - `Upload code to Lambda`
      - `Set Code to trigger from event source`
      - `Code runs only when triggered`
      - `Pay only for the compute time you use`

- ### `Containers`

  - Standard way to package your application's code and dependencies into a single object.
  - Use containers for processes and workflows in which there are essential requirements for security, reliability, and scalability.
  - hard to manage when there are multiple people updating the container.
  - ### `Container Orchestration`
    - `Deploy`, `manage`, and `scale` your containerized applications.
    - `Amazon Elastic Container Service (Amazon ECS)`
      - Highly scalable, high-performance container management system that enables you to run and scale containerized applications on AWS.
      - Supports Docker Containers.
    - `Amazon Elastic Kubernetes Service (Amazon EKS)`
      - Fully managed service that you can use to run Kubernetes on AWS.
    - `AWS Fargate`
      - serverless compute engine for containers. It works with both `Amazon ECS` and `Amazon EKS`.
      - Do not need to provision or manage servers.
      - Manages your server infrastructure for you.
      - Pay only for the resources that are required to run your containers.
  - [`additional resources on "Compute on AWS"`](https://aws.amazon.com/products/compute/)

## `Additional Resources`

- [`Compute on AWS`](https://aws.amazon.com/products/compute)
- [`AWS Compute Blog`](https://aws.amazon.com/blogs/compute/)
- [`AWS Compute Services`](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/compute-services.html)
- [`Hands-on Tutorials: Compute`](https://aws.amazon.com/getting-started/hands-on/?awsf.getting-started-category=category%23compute&awsf.getting-started-content-type=content-type%23hands-on)
- [`Category Deep Dive: Serverless`](https://aws.amazon.com/getting-started/deep-dive-serverless/)
- [`AWS Customer Stories: Serverless`](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc%7Cproduct%23api-gateway%7Cproduct%23cloudfront%7Cproduct%23route53%7Cproduct%23directconnect%7Cproduct%23elb&awsf.customer-references-category=category%23serverless)
- [`Amazon EC2 Reserved Instances`](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-reserved-instances.html)
- [`How Savings Plans apply to usage`](https://docs.aws.amazon.com/savingsplans/latest/userguide/sp-applying.html)
