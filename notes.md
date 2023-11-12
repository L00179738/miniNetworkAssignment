creating initially 2 availability zones.

First AZ is hidden from external network and contains company data, 
configuration etc.
DB is located in first AZ
customer data is stored in this AZ
Data Processing App server is stored in this instance (compressing files, data processing,
etc)


second AZ is accessible from interest and contains company website, 
allows users and customers to log in and access the data
Web page is stored in second AZ
Jumpbox is stored in 2nd AZ
Data here is routed from AZ1 based on user (customers have standard view, employees can access
CMS to add/modify tracks, excercises, manage users)

HOW TO DECIDE ON IPs... 
Have to be depending on the physical resources
have to accommodate possible scaling
how to define AZ IP's to ensure scalability

VPC

Internet Gateway

Internet Gateway Attachment

az1 (public and private subnets)

az2 (public and private subnets)

bastion 

auto scaling group for Bastion, EC2?

load balancer (?)

NAT Gateway

Router + default routes

Security Group (no ingres?) (developers, testers, admins, viewers (for log analysis))

RDS

subnet addresses

ElasticIP (?)

Each availability zone contains 2 subnets

