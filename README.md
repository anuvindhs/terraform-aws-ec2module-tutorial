# Terraform Module tutorial

![cover](https://res.cloudinary.com/practicaldev/image/fetch/s--gfIMaQ_T--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ni1ut3598m6a6gif80mq.png)


Terraform module to create and EC2 instance which is running an Apache.

 This module is for learning  purpose only donot use it for **PRODUCTION**
  
## Tutorial

Read on [iCTPro.co.nz](https://ictpro.co.nz/all-about-terraform-modules-create-publish-your-own-modules-100-days-of-cloud-day-21/)
</br>
Read on [dev.to](https://dev.to/aws-builders/all-about-terraform-modules-create-publish-your-own-modules-502b)

## Code

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
