# Deploy a High-Availability Web App Using CloudFormation (IaC)
In this project, I deployed web servers for a highly available web app using CloudFormation. Wrote the code to create and deploy the infrastructure and application for an Instagram-like app from scratch. The process begins with deploying the networking components, followed by servers, security roles, and software.


### Dependencies:
- AWS CLI installed and configured in your workspace using an AWS IAM role with Administrator permissions.
- Access to a diagram creation software of your choice.
- Your favorite IDE or text editor ready to work.


### Topics Covered:
- High Availability
- Infrastructure as Code (IaC)
- Security
- Automation
- Scripting
- Scalability
- AWS 
- Linux/Unix
- Observability


### Contents of templates in .yml and .json files:

- **network.yml**: A template file to deploy networking infrastructure managed by the networking team. Resources include VPC, Internet Gateway, Subnets, EC2 instances, and NAT Gateways.

- **network-parameters.json**: Contains parameters for the values/placeholders in the network.yml file.

- **udagram.yml**: A template file to deploy the Udagram Application EC2 resources, including Launch Template, Load Balancer, Security Groups, IAM Role, Instance Profile, AutoScaling Group, Listener, ListenerRule, and TargetGroup.

- **udagram-parameters.json**: Contains parameters for the values/placeholders in the udagram.yml file.

- **runscript.sh**: A script detailing how to deploy and tear down resources automatically.


### Project Instructions:

1. Plan and design a visual diagram that depicts the infrastructure layout of resources (see "Diagram.JPG" file).

2. Firstly, deploy the network.yml and network-parameters.json scripts. Refer to "How to Spin Up Resources" section below.

3. Next, deploy the udagram.yml and udagram-parameters.json scripts.

4. To avoid errors when tearing down resources, delete the udagram/application stack first, followed by the network stack.


### How to Spin Up Resources:

From your IDE terminal, ensure you have permission to execute files in your working directory. For example, if you are using Visual Studio Code, you might need to run chmod +x runscript.sh to grant execute permission.

- ./runscript.sh deploy network network.yml network-parameters.json us-east-1
- ./runscript.sh deploy udagram udagram.yml udagram-parameters.json us-east-1


### How to Tear Down Resources:

- ./runscript.sh delete udagram udagram.yml udagram-parameters.json us-east-1
- ./runscript.sh delete network network.yml network-parameters.json us-east-1


### Useful Information:
To access the deployed application, check the outputs tab of the udagram stack and open the Load Balancer URL provided in that section.

This CloudFormation template defines a highly available Udagram application infrastructure on AWS. Here's an overview of the key components and configurations:

### Parameters:
- **NetTeamInfra:** Specifies the environment name that will be prefixed to the resource names.
- **AppName:** Defines the name of the application-related resources.

### Resources:
**1. Security Groups:**
MyLoadBalancerSecGroup: Security Group allowing HTTP (port 80) and Prometheus (port 9090) access to the load balancer.
UdagramServerSecGroup: Security Group allowing HTTP (port 80), SSH (port 22), and Prometheus (port 9090) access to the application servers running on Ubuntu Linux Instances.

**2. IAM Roles and Instance Profiles:**
UdagramAppServerRole: IAM role for EC2 instances, granting permissions to interact with S3 buckets and describe EC2 instances.
UdagramAppInstanceProfile: Instance profile associated with the above IAM role.

**3. Launch Template:**
UdagramAppLaunchTemplate: Defines a launch template that includes the user data script for setting up the application servers, including the installation of Apache, Prometheus, Node Exporter, Apache Exporter, and Alertmanager.

**4. Auto Scaling Group:**
UdagramWebAppGroup: Auto Scaling Group with a desired capacity of 2 instances, utilizing the UdagramAppLaunchTemplate and connected to the load balancer's target groups.

**5. Load Balancer and Listeners:**
MyLoadBalancer: An Elastic Load Balancer with listeners on ports 80 (HTTP) and 9090 (Prometheus).
Listeners: Define listener rules for forwarding traffic to the appropriate target groups based on the path pattern.

**6. Target Groups:**
UdagramAppTargetGroup: Target group for the application servers, performing health checks on port 80.
UdagramAppTargetGroup9090: Target group for Prometheus metrics, performing health checks on port 9090.

**7. S3 Bucket:**
UdagramBucket: An S3 bucket for application storage, with public access enabled.

**8. Network ACLs:**
PublicSubnet1NACL & PublicSubnet2NACL: Network ACLs for the public subnets.
Inbound and Outbound Rules: Allow traffic on port 9090.

**User Data Script:**
The user data script in the launch template configures each Ubuntu Linux EC2 instance with the following:

- **Run System Updates**
- **Apache2:** Installed and started to serve web content.
- **Git:** Installed to clone the application repository.
- **Prometheus and Node Exporter:** Installed and configured for system monitoring.
- **Apache Exporter:** Installed and configured for monitoring Apache server metrics.
- **Alertmanager:** Installed to handle alert notifications.

**This template is designed for a highly available setup with load balancing, monitoring, and alerting integrated directly into the infrastructure. The template is modular and can be adapted to different environments by changing the parameter values.**













