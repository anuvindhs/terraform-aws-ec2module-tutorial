# Terraform Module tutorial

Terraform module to create and EC2 instance which is running an Apache.

 This module is for learning  purpose only donot use it for **PRODUCTION**
  

```HCL
terraform {

}

provider "aws" {
  # Configuration options
  region = "us-east-1"
}

module "EC2-Apache" {
  source        = ".//terraform-aws-ec2module-tutorial"
  vpc_id        = "vpc-xxxxxx"
  public_key    = "ssh-rsa xxxxxxxxx"
  instance_type = "t2.micro"
  server_name   = "Apache Server terraform-ec2module-tutorial"

}

output "public_ip" {
  value = module.EC2-Apache.public_ip
}

```
