# Using Secure Shell (SSH) to access an Amazon Linux Machine Image(AMI)
- This guide will walk you through the steps to launch a single EC2 instance on a public subnet, accessible over the internet via SSH.

## Architecture diagram
![Architecture diagram](Assets/lab%20001.png)


## Prerequisites

- An AWS account
- AWS CLI installed and configured
- SSH key pair

## steps
1. Log in to the AWS console and search for EC2 
2. Select the Amazon Machine Image(AMI) and also define the virtual hardware confuguration by selecting
an Instance type
4. Create the AWS key pair and choose the appropriate format(.pem for Open SSH/Linux/macOS and .ppk for Windows/PuTTY)
3. Review both the storage and network settings

![Instance](Assets/Screenshot%20from%202025-01-23%2017-56-27.png)

