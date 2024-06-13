# Deploy a High-Availability Web App Using CloudFormation (IaC)
In this project, I deployed web servers for a highly available web app using CloudFormation. Wrote the code to create and deploy the infrastructure and application for an Instagram-like app from scratch. The process begins with deploying the networking components, followed by servers, security roles, and software.


# Dependencies
- AWS CLI installed and configured in your workspace using an AWS IAM role with Administrator permissions.
- Access to a diagram creation software of your choice.
- Your favorite IDE or text editor ready to work.


# Topics Covered
- High Availability
- Infrastructure as Code (IaC)
- Security
- Automation and Scripting
- Scalability
- AWS Services


# Context of Working Files

- **network.yml**: A template file to deploy networking infrastructure managed by the networking team. Resources include VPC, Internet Gateway, Subnets, EC2 instances, and NAT Gateways.

- **network-parameters.json**: Contains parameters for the values/placeholders in the network.yml file.

- **udagram.yml**: A template file to deploy the Udagram Application EC2 resources, including Launch Template, Load Balancer, Security Groups, IAM Role, Instance Profile, AutoScaling Group, Listener, ListenerRule, and TargetGroup.

- **udagram-parameters.json**: Contains parameters for the values/placeholders in the udagram.yml file.

- **runscript.sh**: A script detailing how to deploy and tear down resources automatically.


# Project Instructions

1. Plan and design a visual diagram that depicts the infrastructure layout of resources (see "Diagram.JPG" file).

2. Firstly, deploy the network.yml and network-parameters.json scripts. Refer to "How to Spin Up Resources" section below.

3. Next, deploy the udagram.yml and udagram-parameters.json scripts.

4. To avoid errors when tearing down resources, delete the udagram/application stack first, followed by the network stack.


# How to Spin Up Resources

From your IDE terminal, ensure you have permission to execute files in your working directory. For example, if you are using Visual Studio Code, you might need to run chmod +x runscript.sh to grant execute permission.

- ./runscript.sh deploy network network.yml network-parameters.json us-east-1
- ./runscript.sh deploy udagram udagram.yml udagram-parameters.json us-east-1


# How to Tear Down Resources

- ./runscript.sh delete udagram udagram.yml udagram-parameters.json us-east-1
- ./runscript.sh delete network network.yml network-parameters.json us-east-1


# Useful Information
To access the deployed application, check the outputs tab of the udagram stack and open the Load Balancer URL provided in that section.













