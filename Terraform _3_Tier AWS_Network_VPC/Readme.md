
AWS VPC (with 2 availability Zones, 2 public subnets, 2 private subnets and a NAT gateway) deployed as IaC with Terraform

Terraform is an open-source Infrastructure as Code (IaC) software tool created by HashiCorp. It allows users to define and provision data center infrastructure using a high-level configuration language known as HashiCorp Configuration Language (HCL), or optionally, JSON. Terraform enables users to manage various cloud services (such as AWS, Azure, Google Cloud Platform, etc.), as well as on-premises infrastructure and services.
With Terraform, infrastructure is defined in configuration files, which describe the desired state of the infrastructure. These files declare the resources needed (e.g., virtual machines, networks, databases) and their configurations. Terraform then automates the process of provisioning and managing these resources, ensuring that the current state matches the desired state defined in the configuration files. This terraforms module allows u to create as many vpc as you want. In this project, I am going to demonstrate the creation of a VPC on AWS with Public and Private subnets.



Step 1: Set up Terraform and VsCode

Install Terraform on your local machine. You can download Terraform from the official website: https://www.terraform.io/downloads.html
Once installed, ensure that the Terraform binary is added to your system's PATH.
Connect Terraform to your AWS Account. In this website https://registry.terraform.io/providers/hashicorp/aws/latest/docs, there are all steps necessary to set up terraform and AWS.

Step 2: Configure AWS Credentials

Obtain your AWS Access Key ID and Secret Access Key from the AWS Management Console.
Configure your AWS credentials using one of the following methods:
AWS CLI: Run aws configure and input your AWS Access Key ID and Secret Access Key.
Environment Variables: Set AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY environment variables.
Your credentials will allow you to connect to your ass account once your run your terraform code.
You may create new credentials in your account settings.

Step 2:Creating a Provider for AWS!

![image](https://github.com/ChannickE/AWS_Projects/assets/148730724/d4aed9bd-69ee-49e3-9fca-b3b3a540fe73)

 
Step 3: Create a VPC (Virtual Private Cloud in AWS)!

![image](https://github.com/ChannickE/AWS_Projects/assets/148730724/38c057a7-0a38-49a8-91aa-4540ed4e3c03)


Step 4: Create a Public Subnet with auto public IP Assignment enabled in custom VPC!

![image](https://github.com/ChannickE/AWS_Projects/assets/148730724/915892f0-9863-4efa-b0c6-67cc90280272)

Step 5: Create a Private Subnet in customer VPC!

![image](https://github.com/ChannickE/AWS_Projects/assets/148730724/3fbd118a-bfd1-4bf3-ad28-b751d0e1b3d9)

Step 6: Creating an Internet Gateway!

![image](https://github.com/ChannickE/AWS_Projects/assets/148730724/96844f93-bfd1-45e8-819e-1f7698ec2b5c)

Step 7: Create a routing table for Internet Gateway!

![image](https://github.com/ChannickE/AWS_Projects/assets/148730724/9e7575f4-6e09-4fa7-a1b7-99c5060a168e)

Step 8: Associate the routing table to the Public Subnet!

![image](https://github.com/ChannickE/AWS_Projects/assets/148730724/3e3560a0-741e-448e-a170-a6643fc1f8d2)

Step 9: Creating an Elastic IP for the NAT Gateway!

![image](https://github.com/ChannickE/AWS_Projects/assets/148730724/62cd1399-889b-4c70-a497-ae2ef28b8eed)

Step 10: Creating a NAT Gateway!

![image](https://github.com/ChannickE/AWS_Projects/assets/148730724/de1ab63d-0284-4890-9964-42ff678de0f5)

Step 11: Creating a Route Table for the NAT Gateway!

![image](https://github.com/ChannickE/AWS_Projects/assets/148730724/ea5d47eb-b395-4fab-98b9-4478c3efc694)

Step 12: Associating the Route table for NAT Gateway to Public Subnet!

![image](https://github.com/ChannickE/AWS_Projects/assets/148730724/111c2ac7-819f-484f-a948-2a7b4d4821bc)

Step 13: Inintialize terraform with the command “terraform init”:
This command initializes the working directory and downloads the necessary provider plugins.

Step 14: Apply Terraform Configuration
Run the following command:
terraform apply 
Terraform will prompt you to confirm the actions it will take based on the configuration provided. 
Also, if you are not sure about what will be launched, you can type terraform plan. It will give a list of services and configurations that will be deployed.

Step 15: Verify Resources on aws account 

![image](https://github.com/ChannickE/AWS_Projects/assets/148730724/5bfa5b09-baed-43a7-802d-1507f05f3bf5)







