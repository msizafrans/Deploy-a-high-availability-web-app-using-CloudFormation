# Deploy a high-availability web app using CloudFormation
In this project, you’ll deploy web servers for a highly available web app using CloudFormation. You will write the code that creates and deploys the infrastructure and application for an Instagram-like app from the ground up. You will begin with deploying the networking components, followed by servers, security roles and software. 

# Dependencies
AWS CLI installed and configured in your workspace using an AWS IAM role with Administrator permissions.

Access to a diagram creator software of your choice.

Your favorite IDE or text editor ready to work.

# Working files Context
- The "network.yml" file is a template file to deploy networking infrastructure which is managed by the networking team. Resources in the file includes VPC, Internet Gateway, Subnets, EC2 instances and NAT Gateways.
- The network-parameters.json file contains parameters for the network.yml values.
- The "udagram.yml" file is a template file to deploy the Udagram High Availability Application EC2 resources which includes Launch Template, Load Balancer, Security Groups, IAM Role, Instance Profile, AutoScaling Group, Listener, ListenerRule, and TargetGroup.
- The "udagram-parameters.json" file contains parameters for the udagram.yml values.
   
# Project Instructions

1. Design a visual diagram depicting the infrastructure layout and resources involved, which will be deployed when executing the CloudFormation scripts, (see "Diagram.JPG" file).

2. You'll need to manually create an S3 bucket and it should have public-read access. Your servers IAM Role should provide read and write permissions to this bucket. 

3. Firstly, deploy network.yml and network-parameters.json scripts, follow the instructions in the "runscript.sh" file.

4. Secondly, deploy udagram.yml and udagram-parameters.json scripts, follow the instructions in the "runscript.sh" file.

5. To avoid errors when tearing down resources, delete the application stack first followed by the network stack.

6. Thereafter, empty and delete the bucket manually.


# To Spin up Resoucers
./runscript.sh deploy network network.yml network-parameters.json us-east-1
./runscript.sh deploy udagram udagram.yml udagram-parameters.json us-east-1

# Tear down Resources
./runscript.sh delete udagram udagram.yml udagram-parameters.json us-east-1
./runscript.sh delete network network.yml network-parameters.json us-east-1

## Useful Information
To access the deployed application, check out the outputs tab of the udagram stack and open the Load balancer URL provided in that section.









