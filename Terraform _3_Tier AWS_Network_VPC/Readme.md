AWS VPC with Terraform

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
 
Step 3: Write Terraform Configuration
To write our code, we will create two directories. One directory will be for instance vpc called modules/vpc and the other one I named Jupiter-website-ecs which will contain the vpc that we want to create referring to module/vpc. So in the future if we want to create a different vpc with different cidr blocks we can just refer to modules\vpc.
In modules\vpc will contain 
main.tf(creation of vpc, internet gateway, subnest and AZs),
![Screenshot 2024-02-16 135611](https://github.com/ChannickE/AWS_Projects/assets/148730724/1c1638bd-1920-4f00-a12d-c81e1390309b)




variables.tf(variables that will be used to create our vpc) and outputs.tf(deployed the ID of the created vpc).
In the jupter-website-ecs directory, we will have:
Backend.tf, which would store the terraform state file in S3
Terraform.tfvars ,which would initiate the variables to the value we want like the region, the vpc cidr and subnets.
Main.tf, which would create our vpc according to the variable entered in terrafoem.tfvars and it willconfigure our provider which is AWS in our case.
Variables.tf to define our variable in that directory 


Step 4 Inintialize terraform with the command “terraform init”:
This command initializes the working directory and downloads the necessary provider plugins.


Step 5: Apply Terraform Configuration
Run the following command:
terraform apply 
Terraform will prompt you to confirm the actions it will take based on the configuration provided. 
Also, if you are not sure about what will be launched, you can type terraform plan. It will give a list of services and configurations that will be deployed.



Step 6: Verify Resources
Once Terraform completes applying the configuration, you can verify the created resources in the AWS Management Console or by running the following command:
terraform output vpc_id 
This command will output the ID of the created VPC.

Conclusion:
You've now successfully created a VPC with public and private subnets using Terraform on AWS. You can further extend this configuration to include additional resources like security groups, NAT gateways, etc., based on your requirements.






