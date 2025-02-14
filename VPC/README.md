# Building a VPC and Launching a Web Server
## Objectives
- Create a virtual private cloud(VPC)
- Create subnets
- Configure a security group
- Launch an Amazon Elastic Compute Cloud(EC2)instance into a VPC


## Scenario
- In this AWS lab,you use Amazon Virtual Private Cloud to create your own VPC and add additional components to produce a customized network for an organization,you also create security groups for the EC2 instance and then configure and customize the EC2 instance to run a web server and launch it into the VPC 


## Architecture













## Steps
1. Log into your AWS Management Console and search for VPC in the search bar 
2. Select Create VPC and configure 
   - Resources to create:Choose VPC and more,IPv4 CIDR enter 10.0.0.0/16, IPv6 choose No IPv6 CIDR block,tenancy select Default
   - Number of AZs should be 1, public subnets 1,number of private subnets 1 
3. Expand Customize subnets CIDR blocks,public subnet block in us-west-2a:10.0.0.0/24,private subnet block in us-west-2a:10.0.1.0/24,NAT gateways choose in 1AZ,VPC endpoints:choose None
4. On the preview pane name your resources and Create VPC whose details are displayed as per configuration