# Terraform_project
what is terraform?
Terraform is an open-source infrastructure as code tool developed by HashiCorp, that allows users to define provision and manage infrastructure using a simple declarative language called hashicorp configuration language(HCL)

Lets look into terraform life cycle!

There are four step of terraform life cycle

step 1: write(configuration)
In this initial step we define the infrastructure in configure file with .tf

Here is a Example file:

terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 4.16"
    }
  }

  required_version = ">= 1.2.0"
}

provider "aws" {
  region  = "us-west-2"
}

resource "aws_instance" "app_server" {
  ami           = "ami-830c94e3"
  instance_type = "t2.micro"

  tags = {
    Name = "Terraform_Demo"
  }
}
step 2: Initilize
This step sets up the working directory for Terraform.

Downloads the required providers (e.g., AWS, Azure)
Prepares the backend (for storing state, if configured)
terraform init
step 3: Plan
Here, in this third step we will do a dry run to check the error and for the output

terraform plan
step 4: Apply
In the last step the plan will execute and reflect in the AWS

terraform apply
