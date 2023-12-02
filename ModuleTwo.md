## `Module Two - Compute in the Cloud`

### `Amazon Elastic Compute Cloud (Amazon EC2)`

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

### `Amazon EC2 Instance Types`

- [`Amazon EC2 Instance Types`](https://aws.amazon.com/ec2/instance-types/) - Optimized for different tasks. When selecting an instance type, consider the specific needs of your workloads and applications. This might include requirements for `compute`, `memory`, or `storage` capabilities.

  |   `Instances Types`   |                                                                                                              `Description`                                                                                                              |
  | :-------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
  |    General Purpose    |                            Provides a balance of compute, memory, and networking resources. ( application servers, gaming servers, backend servers for enterprise applications, small and medium databases )                            |
  |   Compute Optimized   |                                                                           Ideal for compute-bound applications that benefit from high-performance processors.                                                                           |
  |   Memory Optimized    |                                                                              Deliver fast performance for workloads that process large datasets in memory.                                                                              |
  | Accelerated Computing |        Uses hardware accelerators, or coprocessors, to perform some functions more efficiently than is possible in software running on CPUs. ( floating-point number calculations, graphics processing, data pattern matching )         |
  |   Storage Optimized   | Designed for workloads that require high, sequential read and write access to large datasets on local storage. ( distributed file systems, data warehousing applications, high-frequency online transaction processing (OLTP) systems ) |

### `Amazon EC2 Pricing`

- Pay only for the compute time that you use.
- `On-Demand`
  - Ideal for short-term, irregular workloads that cannot be interrupted.
  - No upfront costs or minimum contracts apply.
  - The instances run continuously until you stop them, and you pay for only the compute time you use.
- `Reserved Instances (1 year / 3 year terms)`

  1. `Standard Reserved Instances`

  - Good fit if you know the EC2 instance type and size you need for your steady-state applications and in which AWS Region you plan to run them.
  - Requires you to state the instance type and size, platform description ( operating system ) and tenancy ( default or dedicated tenancy ).

  2. `Convertible Reserved Instances`

  - For those who needs to run their EC2 instances in different Availability Zones or different instance types. Note: You trade in a deeper discount when you require flexibility to run your EC2 instances.
  - At the end of a Reserved Instance term, you can continue using the Amazon EC2 instance without interruption. However, you are charged `On-Demand rates` until you do one of the following:
    - Terminate the instance.
    - Purchase a new Reserved Instance that matches the instance attributes (instance family and size, Region, platform, and tenancy).

- `EC2 Instance Savings Plans`
  - For flexibility in your Amazon EC2 usage over the duration of the commitment term.
  - Benefit of saving costs on running any EC2 instance within an EC2 instance family in a chosen Region (for example, M5 usage in N. Virginia) regardless of Availability Zone, instance size, OS, or tenancy.
  - The savings with EC2 Instance Savings Plans are similar to the savings provided by Standard Reserved Instances but does not need any specifications.
- `Spot Instances`
  - Ideal for workloads with flexible start and end times, or that can withstand interruptions.
  - Uses unused Amazon EC2 computing capacity and offer you cost savings at up to 90% off of On-Demand prices.
- `Dedicated Hosts`
  - physical servers with Amazon EC2 instance capacity that is fully dedicated to use.
  - You can use your existing per-socket, per-core, or per-VM software licenses to help maintain license compliance.
  - You can purchase On-Demand Dedicated Hosts and Dedicated Hosts Reservations. Of all the Amazon EC2 options that were covered, Dedicated Hosts are the most expensive.

### `Scaling Amazon EC2`

- `Amazon EC2 Auto Scalling`
  - Automatically add or remove Amazon EC2 instances in response to changing application demand.
  - Maintains a greater sense of application availability.
  - `Dynamic Scalling` - responds to changing demand.
  - `Predictive scaling` - automatically schedules the right number of Amazon EC2 instances based on predicted demand.
