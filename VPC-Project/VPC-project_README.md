<h1 align="center">Lab Diagram</h1>

_This repository is a test infrastructure in AWS cloud._
---
![Image diagram](https://github.com/ethansjc/AWS-Projects/blob/79e8672aacaf0ddecd5f701e4b6b78245c656e7d/src/LabVPC/Lab-VPC.drawio.png)
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

  1. Create the VPC with the CIDR Block Range 10.0.0.0/16 (65000 Hosts)

  2. Create an Internet Gateway and attach it to the newly created VPC

  3. Create Public Subnet-1 in Availability Zone-1 with the CIDR 10.0.0.0/24

  4. Create Private Subnet-1 in Availability Zone-1 with CIDR of 10.0.1.0/24

  5. Create an Elastic IP.

  6. Create a NAT Gateway using the Elastic IP and Public Subnet -1 as base

  7. Create Public Subnet-2 in Availability Zone-2 with the CIDR 10.0.2.0/24

  8. Create Private Subnet-2 in Availability Zone-2 with the CIDR 10.0.3.0/24

  9. Update Route Configurations for present Route Table and name it Private Route Table

  10. Create Public Route Table and update Route Configurations

  11. Create VPC Security Group to allow inbound HTTP,HTTPS and SSH

  12. Create EC-2 Instances using the VPC Created as base and the Public Subnet-1 as EC-2 Location.

  13. Enable Public IP for the EC-2 

  14. Associate the VPC Security Group for the EC-2

  15. Update User Data for the EC-2

  16. Launch EC-2

  17. Test Webserver running on EC-2 using a browser.
</details>

### Tutorial (Step-By-Step)

1. Create the VPC with the CIDR Block Range 10.0.0.0/16 (65000 Hosts).

![VPC-Project-photo](https://github.com/ethansjc/AWS-Projects/blob/main/src/LabVPC/LabVPC-IMG-1.png)

2. Create an Internet Gateway and attach it to the newly created VPC.

![VPC-Project-photo](https://github.com/ethansjc/AWS-Projects/blob/main/src/LabVPC/LabVPC-IMG-2.png)

3. Create Public Subnet-1 in Availability Zone-1 with the CIDR 10.0.0.0/24.

![VPC-Project-photo](https://github.com/ethansjc/AWS-Projects/blob/main/src/LabVPC/LabVPC-IMG-3.png)

4. Create Private Subnet-1 in Availability Zone-1 with CIDR of 10.0.1.0/24

![VPC-Project-photo](https://github.com/ethansjc/AWS-Projects/blob/main/src/LabVPC/LabVPC-IMG-4.png)

5. Create an Elastic IP.

6. Create a NAT Gateway using the Elastic IP and Public Subnet -1 as base

![VPC-Project-photo](https://github.com/ethansjc/AWS-Projects/blob/main/src/LabVPC/LabVPC-IMG-6.png)

7. Create Public Subnet-2 in Availability Zone-2 with the CIDR 10.0.2.0/24

8. Create Private Subnet-2 in Availability Zone-2 with the CIDR 10.0.3.0/24

![VPC-Project-photo](https://github.com/ethansjc/AWS-Projects/blob/main/src/LabVPC/LabVPC-IMG-5.png)

9. Update Route Configurations for present Route Table and name it Private Route Table

Update Private Route Table Route’s as follows

| Destination |   Target    |
| ----------- | ----------- |
| 10.0.0.0/16 |    Local    |
| 0.0.0.0/0   | NAT Gateway |


10. Create Public Route Table and update Route Configurations

![VPC-Project-photo](https://github.com/ethansjc/AWS-Projects/blob/main/src/LabVPC/LabVPC-IMG-7.png)

11. Create VPC Security Group to allow inbound HTTP,HTTPS and SSH

12. Create EC-2 Instances using the VPC Created as base and the Public Subnet-1 as EC-2 Location.

![VPC-Project-photo](https://github.com/ethansjc/AWS-Projects/blob/main/src/LabVPC/LabVPC-IMG-8.png)

12. Create EC-2 Instances using the VPC Created as base and the Public Subnet-1 as EC-2 Location.

13. Enable Public IP for the EC-2 

14. Associate the VPC Security Group for the EC-2

15. Update User Data for the EC-2

![VPC-Project-photo](https://github.com/ethansjc/AWS-Projects/blob/main/src/LabVPC/LabVPC-IMG-9.png)

![VPC-Project-photo](https://github.com/ethansjc/AWS-Projects/blob/main/src/LabVPC/LabVPC-IMG-10.png)

Double Check Both Public and Private Routes

![VPC-Project-photo](https://github.com/ethansjc/AWS-Projects/blob/main/src/LabVPC/LabVPC-IMG-11.png)

![VPC-Project-photo](https://github.com/ethansjc/AWS-Projects/blob/main/src/LabVPC/LabVPC-IMG-12.png)

16. Launch EC-2

![VPC-Project-photo](https://github.com/ethansjc/AWS-Projects/blob/main/src/LabVPC/LabVPC-IMG-13.png)

17. Test Webserver running on EC-2 using a browser.

![VPC-Project-photo](https://github.com/ethansjc/AWS-Projects/blob/main/src/LabVPC/LabVPC-IMG-15.png)

Use Putty to add in the following commands after successful connection:

```bash
#!/bin/bash

sudo su

yum update

# Install Apache Web Server and PHP

yum install -y httpd

yum install -y mysql

yum install -y php

# Download Lab files

wget https://github.com/ethansjc/AWS-Projects/main/src/lab-app-ethan.zip

unzip lab-app-ethan.zip -d /var/www/html/

# Turn on web server

chkconfig httpd on

service httpd start

```

  Enter to our WEB page:

``` http://<our_instance_ip>```

![VPC-Project-photo](https://github.com/ethansjc/AWS-Projects/blob/main/src/LabVPC/LabVPC-IMG-14.png)

<h1 align="center">Congratulations!!!</h1>