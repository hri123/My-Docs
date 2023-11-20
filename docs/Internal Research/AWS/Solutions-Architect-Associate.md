## IAM

- Use **permissions boundary** to control the maximum permissions employees can grant to the IAM principals (Users and Roles)

- **Amazon Cognito**
    - **Amazon Cognito User Pools**
    - **Amazon Cognito Identity Pools**

- **API Gateway Lambda authorizer**

## S3


## Storage

- **EBS**
    - Encrypted: Data at rest, in transit to / from instance, snapshot

- **ElastiCache for Redis**
    - blazing fast in-memory data store
    - real-time transactional and analytical processing use cases such as caching
    - IAM Auth is not supported
    - Redis authentication tokens enable Redis to require a token (password) before allowing clients to execute commands



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

- **NACL** vs **Security Group**

- **VPC sharing** (part of **Resource Access Manager**)
    - the account that owns the VPC (owner) shares one or more subnets with other accounts that belong to the same organization from AWS Organizations

