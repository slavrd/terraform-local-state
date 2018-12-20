# Terraform local state

A project to demonstrate how terraform is used with local state.

When terraform applies a configuration it stores the resulting infrastructure state. The state can be stored in a local file (default) or remotely.

The state file contains the mappings between the resources described in the terraform configuration and the resources that were created in reality. Before applying configuration, terraform makes a plan for the needed changes by checking the state file for resources that should exist and verifying it against reality.

## Prerequisites

* Install Terraform - [instructions](https://www.terraform.io/intro/getting-started/install.html#installing-terraform)

## Apply the Terraform configuration

* Initialize terraform in the current directory - run `terraform init`

Terraform will check the configuration it will work with and download any providers and modules that will be needed to apply it to a `.terraform/` folder.

* Apply the terraform configuration  - run `terraform apply`

Terraform will make a plan that will show the resources which will be created and then create them after a user confirmation. After that it will store information about the created resources in a state file named `terraform.tfstate`.

If `terraform apply` is run again terraform will again make a plan. Since the `terraform.tfstate` file is present terraform will check it for resources that were already created, confirm that these resources still exist in reality and so plan to create only resources that do not.

In case that no changes were made to the configuration or the reality terraform's plan will say that no changes are needed.