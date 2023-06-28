<h1 align="center">Lab Diagram</h1>

_This repository is a test infrastructure in AWS cloud._
---
![Image diagram](https://github.com/ethansjc/AWS-Projects/blob/79e8672aacaf0ddecd5f701e4b6b78245c656e7d/src/Lab-VPC.drawio.png)
## Objective:
* Create VPC 
* Create subnets
* Configure a security group
* Launch an Amazon Elastic Compute Cloud (Amazon EC2) instance into a VPC

# Create a VPC
We will create VPC, 4 Subnets and place the EC-2 instance inside the subnet.

We will also install a webserver on the EC-2 instance and access it using a web browser.

<details>
<summary>Rundown Check</summary>
  1.Create the VPC with the CIDR Block Range 10.0.0.0/16 (65000 Hosts)
  

  2.Create an Internet Gateway and attach it to the newly created VPC

  3.Create Public Subnet-1 in Availability Zone-1 with the CIDR 10.0.0.0/24

  4.Create Private Subnet-1 in Availability Zone-1 with CIDR of 10.0.1.0/24

  5.Create an Elastic IP.

  6.Create a NAT Gateway using the Elastic IP and Public Subnet -1 as base

  7.Create Public Subnet-2 in Availability Zone-2 with the CIDR 10.0.2.0/24

  8.Create Private Subnet-2 in Availability Zone-2 with the CIDR 10.0.3.0/24

  9.Update Route Configurations for present Route Table and name it Private Route Table

  10.Create Public Route Table and update Route Configurations

  11.Create VPC Security Group to allow inbound HTTP,HTTPS and SSH

  12.Create EC-2 Instances using the VPC Created as base and the Public Subnet-1 as EC-2 Location.

  13.Enable Public IP for the EC-2 

  14.Associate the VPC Security Group for the EC-2

  15.Update User Data for the EC-2

  16.Launch EC-2

  17.Test Webserver running on EC-2 using a browser.
</details>