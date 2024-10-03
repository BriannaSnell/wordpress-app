# Terraform code to Launch a WordPress application with RDS

data.tf: This file defines a Terraform data block that retrieves the latest Amazon Machine Image (AMI) for Linux 2 from AWS. It specifies that the AMI should be owned by Amazon and filters the search based on the AMI name pattern and virtualization type.

keypair.tf: This code creates an AWS key pair and saves the private key to a local file. The key pair will be used for SSH authentication purposes in AWS EC2 instances.

main.tf: It contains the resource block to create a VPC, private subnets for our RDS, public subnet for EC2, security groups; provisions an RDS database instance, and deploys an EC2 instance for hosting a WordPress application.

outputs.tf: This file contains outputs that provide convenient access to important information about the provisioned AWS resources, such as the public IP address of the EC2 instance and the endpoint URL of the RDS database. They also provide a message with a URL for accessing the WordPress application.

userdata.tpl: This file contains the user data needed to install the necessary software, download and extract the WordPress files, modify the configuration file to use the provided database information, set up the appropriate file permissions, and start the Apache web server.

variable.tf: This file contains all our variables to allow you to customize various aspects of the infrastructure deployment, such as the database configuration, AWS region, availability zones, VPC and subnet CIDR blocks, EC2 instance and RDS instance types, and root volume size.

version.tf: This code ensures the Terraform project has the required providers (AWS, Null, and Template) at the specified versions and sets the minimum required version of Terraform.
