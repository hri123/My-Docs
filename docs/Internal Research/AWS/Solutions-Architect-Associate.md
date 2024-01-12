Design High Performing Architectures: Question 3

## IAM

- Use **permissions boundary** to control the maximum permissions employees can grant to the IAM principals (Users and Roles)

- **Amazon Cognito**
    - **Amazon Cognito User Pools**: provide a user directory that manages user profiles and authentication. They handle sign-up and sign-in, multi-factor authentication, account recovery, and user profile management.
    - **Amazon Cognito Identity Pools**: enable your users to obtain temporary AWS credentials, which are then used to access other AWS services. Identity Pools integrate with Amazon Cognito User Pools for user authentication, but they can also integrate with other identity providers (IdPs) to allow users to sign in with their existing credentials.

- **API Gateway Lambda authorizer**: is a feature in Amazon API Gateway, before allowing a request to reach your API's backend, API Gateway can trigger a Lambda function to perform custom authorization logic.

- **Amazon GuardDuty**: Amazon GuardDuty is a threat detection service that continuously monitors for malicious activity and unauthorized behavior to protect your AWS accounts, workloads, and data stored in Amazon S3. The service uses machine learning, anomaly detection, and integrated threat intelligence to identify and prioritize potential threats. GuardDuty analyzes tens of billions of events across multiple AWS data sources, such as AWS CloudTrail events, Amazon VPC Flow Logs, and DNS logs.

- **Amazon Macie**:
    - data security and data privacy service that uses machine learning and pattern matching to discover and protect your sensitive data on Amazon S3

- **Miscellaneous**:
    - You can use IAM roles to access cross-account resources.

    - If the IAM role that you create for the Lambda function is in the same AWS account as the bucket, then you don't need to grant Amazon S3 permissions on both the IAM role and the bucket policy. Instead, you can grant the permissions on the IAM role and then verify that the bucket policy doesn't explicitly deny access to the Lambda function role. If the IAM role and the bucket are in different accounts, then you need to grant Amazon S3 permissions on both the IAM role and the bucket policy.

    - With ACLs, you can only grant other AWS accounts (not specific users) access to your Amazon S3 resources. 

## Security

- **AWS Certificate Manager**:
    - provision, manage, and deploy public and private Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificates for use with AWS services and your internal connected resources
    - ACM does not attempt to renew third-party certificates that are imported
    - Any SSL/TLS certificates created via ACM do not need any monitoring/intervention for expiration. ACM automatically renews such certificates
    - Amazon CloudWatch metrics and Amazon EventBridge events are enabled for all certificates that are managed by ACM.

- **AWS Config**:
    - creates configuration items for every supported resource in the region, and generates configuration items when the configuration of a resource changes
    - AWS Config rules
        - When AWS Config evaluates your resources (on change or periodically), it invokes the rule's AWS Lambda function. If a resource violates the conditions of a rule, AWS Config flags the resource and the rule as noncompliant. AWS Config sends a notification to your Amazon SNS topic.



## S3


## Storage

- **EBS**
    - Encrypted: Data at rest, in transit to / from instance, snapshot

- **ElastiCache for Redis / Memcached**
    - HIPAA compliant
    - in-memory database
    - supports SQL query caching
    - Sub-millisecond latency, Data partitioning, Support for a broad set of programming languages
    - Choosing between Redis and Memcached: Memcached is designed for simplicity while Redis offers a rich set of features that make it effective for a wide range of use cases

    - **ElastiCache for Redis**
        - real-time transactional and analytical processing use cases such as caching, chat/messaging, gaming leaderboards, geospatial, machine learning, media streaming, queues, real-time analytics, and session store
        - IAM Auth is not supported
        - Redis authentication tokens enable Redis to require a token (password) before allowing clients to execute commands
        - Advanced data structures, Snapshots, Replication, Transactions, Pub/Sub, Lua scripting, Geospatial support
        - enhanced engine which improves on the reliability and efficiency of open source Redis while remaining Redis-compatible
        - Online Cluster Resizing, supports encryption, and is HIPAA eligible and PCI DSS compliant
        - sub-millisecond latency to power internet-scale real-time applications
        - supports replication, high availability, and cluster sharding right out of the box.

    - **ElastiCache for Memcached**
        - Multithreaded architecture
        - Auto Discovery which helps developers save time and effort by simplifying the way an application connects to a cluster
        - is a great choice for implementing an in-memory cache to decrease access latency, increase throughput, and ease the load off your relational or NoSQL database
        - Session stores are easy to create


- **DynamoDB**
    - key-value and document database
    - delivers single-digit millisecond performance at any scale
    - fully managed, multi-region, multi-master, durable database with built-in security, backup and restore
    - in-memory caching (via DAX) for internet-scale applications
    - NOT an in-memory database

    - **DynamoDB Accelerator (DAX)**
        -  DynamoDB-compatible caching service that enables you to benefit from fast in-memory performance for demanding applications
        -  DAX does not support SQL query caching


- **DocumentDB**
    - fast, scalable, highly available, and fully managed document database service that supports MongoDB workloads
    - easy to store, query, and index JSON data
    - NOT an in-memory database




## VPC

- **VPC endpoints** are powered by **AWS PrivateLink**, connect your VPC to supported AWS services.
    - Two types of VPC endpoints:
        - **Interface Endpoints**
            - Supported Services
                - SQS
        - **Gateway Endpoints**
            - Supported Services
                - S3
                - DynamoDB


- **IPsec VPN connection** / **site-to-site VPN** (customer n/w to VPC over internet)
    - **VPN Gateway** on AWS Side
    - **Customer Gateway** on on-premises side

- **AWS Direct Connect**

- **Internet Gateway** vs **NAT gateway**
    - instances in VPC to and from internet vs prevent the instances from receiving inbound traffic initiated by someone on the Internet

- **NAT Gateway** vs **NAT instance**
  - NAT instance can be used as a bastion server
  - Security Groups can be associated with a NAT instance
  - NAT instance supports port forwarding

- **NACL** vs **Security Group**

- **VPC sharing** (part of **Resource Access Manager**)
    - the account that owns the VPC (owner) shares one or more subnets with other accounts that belong to the same organization from AWS Organizations

- **VPN CloudHub** operates on a simple hub-and-spoke model that you can use with or without a VPC

- **transit gateway**
    - A transit gateway is a network transit hub that you can use to interconnect VPCs and on-premises networks, **VPC peering** between all VPCs is an inelegant and clumsy way
    - MTU is 8500 bytes (VPN is 1500)
    - transit gateway route table

## Networking

- **Application Load Balancer**
    - If a target group contains only unhealthy registered targets, the load balancer nodes route requests across its unhealthy targets

- **Security Group**
    - acts as a virtual firewall for EC2 instances to control incoming and outgoing traffic


## Miscellaneous

- **CloudFront**: 


## Monitoring

- **CloudWatch**:


## Notification

- **SNS**


- **Amazon EventBridge**: 

