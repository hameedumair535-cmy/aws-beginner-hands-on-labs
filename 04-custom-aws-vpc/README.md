Project 4: Build a Custom AWS VPC with Public and Private Subnets

 Project Overview

Designed and configured a custom Amazon Virtual Private Cloud (VPC) with separate public and private subnets. Configured an Internet Gateway and route tables, then launched an EC2 instance in the public subnet to test network connectivity.

 AWS Services Used

  Amazon VPC
  Amazon EC2
  Internet Gateway
  Route Tables
  Subnets
  Security Groups

 Network Configuration

 Resource  Configuration 

 VPC Name  My-Custom-VPC 
  Region | Europe (Stockholm) 
  Region Code | eu-north-1 
  VPC IPv4 CIDR | 10.0.0.0/16 
  Public Subnet | 10.0.1.0/24 
  Private Subnet | 10.0.2.0/24 
  Internet Gateway | My-Internet-Gateway 
  Public Route Table | My-Public-Route-Table 
 Private Route Table | My-Private-Route-Table 

 Implementation Steps

1. Created a custom VPC with IPv4 CIDR block 10.0.0.0/16.
2. Created a public subnet using 10.0.1.0/24.
3. Created a private subnet using 10.0.2.0/24.
4. Created and attached an Internet Gateway to the VPC.
5. Created a public route table and associated it with the public subnet.
6. Added a default route (0.0.0.0/0) pointing to the Internet Gateway.
7. Created a separate private route table and associated it with the private subnet.
8. Kept the private subnet without a direct Internet Gateway route.
9. Enabled automatic public IPv4 assignment for the public subnet.
10. Launched an Amazon Linux 2023 EC2 instance in the public subnet.
11. Connected to the instance using EC2 Instance Connect.
12. Tested internet connectivity, DNS resolution, and HTTPS access.

 Network Connectivity Testing

Executed the following Linux commands on the EC2 instance:

 Check Network Interface

```bash
ip addr
```

Private IP address observed: `10.0.1.204`

 Test Internet Connectivity

```bash
ping -c 4 8.8.8.8
```

Result: 4 packets received, 0% packet loss.

 Test DNS Resolution

```bash
ping -c 4 google.com
```

Result: Domain name successfully resolved and responded.

 Test HTTPS Connectivity

```bash
curl -I https://www.google.com
```

Result: HTTP/2 200 — successful HTTPS response.

  Key Learnings

  Understanding VPC architecture and IPv4 CIDR blocks.
  Creating and configuring public and private subnets.
  Understanding Internet Gateways and route tables.
  Configuring subnet associations and routing.
  Connecting EC2 instances to a custom VPC.
  Troubleshooting subnet and connectivity configuration.
  Testing network connectivity using Linux commands.

 Project Outcome

Successfully built and tested a custom AWS VPC with separate public and private subnets. Verified that an EC2 instance in the public subnet could connect to the internet and resolve domain names.

Cost Management

The EC2 instances were used for hands-on testing. The original test instance was stopped after troubleshooting. Resource cleanup is pending.

Screenshots

 VPC Created

 Public and Private Subnets

 Public Route Table

 Private Route Table

 EC2 Instance in Public Subnet

 Network Connectivity Tests
