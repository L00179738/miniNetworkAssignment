# Mini network assignment

A company wants to have a network supporting management of customized HITT training routes for 
user location conaining running routes.

- company is growing rapidly
- solution have to be extensible from the start
- company requires best practices implemented
- requires services and documentation

### how to address the requirements
- we need a website server for customers to log in and access resources
- we need a website server for employees to log in and manage resources
- we need admin access to modify whatever / add users blah blah
- we need ssh access for jumpbox to manage application server
- we needa a database to store user / tracks / trainings information
- we need to create documentation document describing landscape

### how to implement the requirements

- create VPC
- create 2 AZ which can be easily expanded
- create jump box - Bastion - in load balancer group to ensure availability if one instance is down (public) (nested)
- create web server in scalable and balanced group(privet) (nested)
- create DB server (private) (nested ?)
- create application server (private) (nested)
- configure CIDR
- configure routing table
- configuring NATed gateway

## to consider
- consider using load balancer
- consider using auto-scaling (ensure it is easy to enable when needed) (consider using nested stack)

## methods
- github
- aws

## where we lacking (temporary)
- how the nesting really works
- how to manage AWS instances (cheat sheet)
- how to test the changes
- how to set up the network addressess
- how to connect component using the subnet
- how to communicate between subnets with the ip addressess
- is there a need to communicate between AZ?
- How to tidy up the code (best practices)
- How to use parameters and mapping
- how to ensure security
- how to ensure reliability and high availability
- how to create internal/external archiving mechanism

## steps to take:
- create template to make VPC
- add private and public zones
- decide on the networking mask
- create resources as above

## implementation goals


## to documentation

- If template requires parameters, they can be provided in cloudFormation -> create stack. This can be a key name, instance type and any(?) other parameter defined in yaml.
- AMI images are region dependant.
