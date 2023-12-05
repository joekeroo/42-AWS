# `Module 6 - Security`

## `6.1 AWS Shared Responsibility Model`

![Shared Responsibility Model](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1701774000/b2p5De1Hgool6MU0I0WDMw/tincan/5215426675a09eb3c237d30a006d261309b59486/assets/JmwK4j7IqVDfToXi_ssiWI6HiRWe-b_r6.png)

- ### `Customers: Security in the Cloud`
  - Customers are responsible for the security of everything that they create and put `in the AWS Cloud`.
  - Customers are `responsible` for managing security requirements for their content, including content they store and which AWS services they use.
  - Customers also control how access rights are granted, managed, and revoked.
- ### `AWS: Security of the Cloud`
  - AWS is responsible for security `of the cloud`.
  - AWS `operates`, `manages`, and `controls` the components at `all layers of infrastructure`. (host OS virtualization layer, physical security of the data centers)
  - AWS is responsible for `protecting the global infrastructure` that runs all of the services offered in the AWS Cloud. ( AWS Regions, Availability Zones, and edge locations )
  - AWS manages the security of the cloud, specifically the `physical infrastructure` that hosts your resources, which include:
    ```
    - Physical security of data centers
    - Hardware and software infrastructure
    - Network infrastructure
    - Virtualization infrastructure
    ```

## `6.2 User Permissions and Access`

- ### `AWS Identity and Access Management (IAM)`
  - Manage access to AWS services and resources securely.
  - Flexibility to configure access based on your company’s operational and security needs.
  - `IAM features includes`:
    - `IAM users, groups, and roles.`
    - `IAM policies.`
    - `Multi-factor authentication.`
- ### `AWS account root user`
  ![Root Access](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1701774000/b2p5De1Hgool6MU0I0WDMw/tincan/5215426675a09eb3c237d30a006d261309b59486/assets/aFbFxxsEERDhh-MF_G6mCtOEHNBDNNKV4.png)
  - #### `Best Practices`
    - Do not use the root user for everyday tasks.
    - Create your first IAM user and assign it permissions to create other users.
    - Create other IAM users, and access those identities for performing regular tasks throughout AWS.
    - Only use the root user when you need to perform tasks that are only available to the root user. For example, changing root user email address and changing your AWS support plan.
    - [`AWS Account Management Reference Guide`](https://docs.aws.amazon.com/IAM/latest/UserGuide/root-user-tasks.html)
- ### `IAM Users`
  - Identity that root user creates in AWS.
  - Represents a person or application that interacts with AWS services and resources.
  - Consists of a name and credentials.
  - By default, IAM users has no permissions associated with it.
  - #### `Best Practices`
    - Create individual IAM users for each person who needs to access AWS.
    - Provides additional security by allowing each IAM user to have a unique set of security credentials.
- ### `IAM Policies`

  - Document that allows or denies permissions to AWS services and resources.
  - Customize users’ levels of access to resources.
  - #### `Best Practices`
    - Follow the security principle of least privilege when granting permissions.
    - Prevent users or roles from having more permissions than needed to perform their tasks.
  - #### `Example`

    ![IAM Policy](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1701774000/b2p5De1Hgool6MU0I0WDMw/tincan/5215426675a09eb3c237d30a006d261309b59486/assets/mpl6qiqDH6ciUAKe_vKf8uGbqJDqmoCNE.png)

    - Allows a specific action within Amazon `S3:ListObject`.
    - Mentions a specific bucket ID: `AWSDOC-EXAMPLE-BUCKET`.
    - Allow the cashier to view all of the objects in the `AWSDOC-EXAMPLE-BUCKET` bucket.

- ### `IAM Groups`

  - Collection of IAM users.
  - All users in the group are granted permissions specified by the policy.

    ![IAM Groups](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1701774000/b2p5De1Hgool6MU0I0WDMw/tincan/5215426675a09eb3c237d30a006d261309b59486/assets/qeo00K6Rwaa2hCRP_dJWwAFus-2ObBezE.png)

- ### `IAM Roles`

  - An identity that you can assume to gain temporary access to permissions.
  - Before an IAM user, application, or service can assume an IAM role, they must be granted permissions to switch to the role.
  - Abandons all previous permissions that they had under a previous role and assume the permissions of the new role.
  - #### `Best Practices`
    - IAM roles are ideal for situations in which access to services or resources needs to be granted temporarily, instead of long-term.

- ### `Multi-factor authentication`
  - Provides an extra layer of security for your AWS account.

## `4.3 AWS Organizations`
