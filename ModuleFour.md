# `Module 4 - Networking`

## `4.1 Connectivity to AWS`

- ### `Amazon Virtual Private Cloud (`[`Amazon VPC`](https://aws.amazon.com/vpc/)`)`
  - A networking service that you can use to establish boundaries around your AWS resources.
  - Launch resources in a virtual network that you define.
  - Organize your resources into `subnets`.
  - A `subnet` is a section of a VPC that can contain resources such as Amazon EC2 instances.
- ### `Internet Gateway`
  - Connection between a VPC and the internet.
  - Allows public traffic from the internet to access your VPC.
- ### `Virtual Private Gateway`
  - Component that allows protected internet traffic to enter into the VPC.
  - Allows traffic into the VPC only if it is coming from an approved network.
  - `Establish a virtual private network (VPN) connection between your VPC and a private network` - such as an on-premises data center or internal corporate network.
- ### `AWS Direct Connect`
  - Reduce network costs and increase the amount of bandwidth that can travel through your network.
  - `Establish a dedicated private connection between the on-premise data center and a VPC.`

## `4.2 Subnets and Network Access Control List`

- ### `Subnets`
  - A section of VPC that can group resources based on `security` or `operational` needs.
  - Subnets can be `public` or `private`.
  - In a VPC, subnets can communicate with each other.
  - #### `Public Subnets`
    - Contain resources that need to be accessible by the public, such as an online store’s website.
    - `Supports the customer-facing websites.`
  - #### `Private Subnets`
    - Contain resources that should be accessible only through your private network, such as a database that contains customers’ personal information and order histories.
    - `Isolates databases containing customers' personal information.`
- ### `Network Traffic in a VPC`
  - Requested data from an application hosted in the AWS Cloud, is sent as a `packet`.
  - A `packet` is a unit of data sent over the internet or a network.
  - The packet enters into a VPC through an `internet gateway`.
  - Before a packet can enter into a `subnet` or exit from a subnet, it checks for `permissions`.
  - These permissions indicate who sent the packet and how the packet is trying to communicate with the resources in a subnet.

#

- ### `Network Access Control List (Network ACL)`
  - VPC component that checks packet permissions for `subnets`.
  - Virtual firewall that controls inbound and outbound traffic at the `subnet` level.
  - `All` network ACLs have an `explicit deny rule`. This rule ensures that if a packet doesn’t match any of the other rules on the list, the packet is denied.
  - #### `Default Network ACL`
    - `Allows` all inbound and outbound traffic.
    - Can be modified by adding your own rules.
  - #### `Custom Network ACL`
    - `Denies` all inbound and outbound traffic.
    - You add rules to specify which traffic are allowed.
- ### `Security Group`
  - Virtual firewall that controls inbound and outbound traffic for an Amazon EC2 instance.
  - By default, `denies all inbound traffic` and `allows all outbound traffic`.
  - Custom rules can be added to configure which traffic should be allowed.

#

- ### `Stateless Packet Filtering`
  - Remembers `nothing` and check packets that cross the subnet border, `inbound` and `outbound`.
  - `Network ACLs` perform stateless packet filtering.
- ### `Statefull Packet Filtering`
  - Remembers previous decisions made for `incoming` packets.
  - `Security groups` perform stateful packet filtering.

## `4.3 Global Networking`

- ### `Domain Name System (DNS)`
  - DNS resolution is the process of translating a domain name to an IP address.
- ### `Amazon Route 53`
  - DNS web service.
  - Connects user requests to infrastructure running in AWS. (Amazon RC2 Instances / Load Balancers)
  - Also route users to infrastructure outside of AWS.
  - Manages the DNS record for domain names.
  - Register new domain names.
  - Transfer DNS records for existing domain names managed by other domain registrars.
- ### `How Amazon Route 53 and Amazon CloudFront deliver content`

  Suppose that AnyCompany’s application is running on `several Amazon EC2 instances`. These instances are in an `Auto Scaling group` that attaches to an `Application Load Balancer`.

  ```
  1. A customer requests data from the application by going to AnyCompany’s website.
  2. Amazon Route 53 uses DNS resolution to identify AnyCompany.com’s corresponding IP address, 192.0.2.0. This information is sent back to the customer.
  3. The customer’s request is sent to the nearest edge location through Amazon CloudFront.
  4. Amazon CloudFront connects to the Application Load Balancer, which sends the incoming packet to an Amazon EC2 instance.
  ```

## `Additional Resources`

- [`Network and Content Deliveryon AWS`](https://aws.amazon.com/products/networking)
- [`AWS Networking & Content Delivery Blog`](https://aws.amazon.com/blogs/networking-and-content-delivery/)
- [`Amazon Virtual Private Cloud`](https://aws.amazon.com/vpc)
- [`What is Amazon VPC?`](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)
- [`How Amazon VPC works`](https://docs.aws.amazon.com/vpc/latest/userguide/how-it-works.html)
