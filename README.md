# Launching a Single EC2 Instance on a Public Subnet

- This guide will walk you through the steps to launch a single EC2 instance on a public subnet, accessible over the internet via SSH.

## Architecture diagram
![Architecture diagram](Assets/lab%20001.png)


## Prerequisites

- An AWS account
- AWS CLI installed and configured
- SSH key pair

## Steps

### 1. Create a VPC

```sh
aws ec2 create-vpc --cidr-block 10.0.0.0/16
```

### 2. Create a Public Subnet

```sh
aws ec2 create-subnet --vpc-id <vpc-id> --cidr-block 10.0.1.0/24
```

### 3. Create an Internet Gateway

```sh
aws ec2 create-internet-gateway
aws ec2 attach-internet-gateway --vpc-id <vpc-id> --internet-gateway-id <igw-id>
```

### 4. Create a Route Table and Associate it with the Subnet

```sh
aws ec2 create-route-table --vpc-id <vpc-id>
aws ec2 create-route --route-table-id <route-table-id> --destination-cidr-block 0.0.0.0/0 --gateway-id <igw-id>
aws ec2 associate-route-table --subnet-id <subnet-id> --route-table-id <route-table-id>
```

### 5. Launch an EC2 Instance

```sh
aws ec2 run-instances --image-id <ami-id> --count 1 --instance-type t2.micro --key-name <key-pair-name> --subnet-id <subnet-id> --associate-public-ip-address
```

### 6. Configure Security Group to Allow SSH Access

```sh
aws ec2 create-security-group --group-name my-sg --description "Security group for SSH access" --vpc-id <vpc-id>
aws ec2 authorize-security-group-ingress --group-id <sg-id> --protocol tcp --port 22 --cidr 0.0.0.0/0
```

### 7. Connect to Your Instance

```sh
ssh -i <path-to-key-pair> ec2-user@<public-ip-address>
```

## Conclusion

You have successfully launched an EC2 instance on a public subnet and connected to it via SSH.
