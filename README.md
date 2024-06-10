# Project Introduction and Implementation

Creating this project will give you the hands-on experience you need to talk about infrastructure as code confidently. I have chosen a realistic scenario where you will deploy a dummy application (a sample JavaScript or HTML file) to an NGINX server running on an EC2 instance.

# There will be two parts to this project:

Diagram: Designed a visual diagram depicting the infrastructure layout and resources involved, which will be deployed when executing the CloudFormation scripts. (see "Diagram.JPG" file)
Scripts (Template and Parameters): Download matching CloudFormation scripts files from the main repository.

# Deploy a high-availability web app using CloudFormation
In this project, you’ll deploy web servers for a highly available web app using CloudFormation. You will write the code that creates and deploys the infrastructure and application for an Instagram-like app from the ground up. You will begin with deploying the networking components, followed by servers, security roles and software. 

# Getting Started
# Dependencies
AWS CLI installed and configured in your workspace using an AWS IAM role with Administrator permissions 

Access to a diagram creator software of your choice.

Your favorite IDE or text editor ready to work.

# Project Instructions

1. I designed a visual diagram depicting the infrastructure layout and resources involved, which will be deployed when executing the CloudFormation scripts, (see "Diagram.JPG" file)

2. Firstly, deploy network.yml and network-parameters.json CloudFormation scripts files from the main repository, follow the instructions in the "runscript.sh" file.

3. Secondly, deploy udagram.yml and udagram-parameters.json CloudFormation scripts files from the main repository, follow the instructions in the "runscript.sh" file.

4. To auto spin up and tear down of the CloudFormation stacks, follow the instructions in the "runscript.sh" 



## 2x Script Usage examples:


# To Spin up Resoucers
./runscript.sh deploy network network.yml network-parameters.json us-east-1
./runscript.sh deploy udagram udagram.yml udagram-parameters.json us-east-1

# Tear down Resources
./runscript.sh delete udagram udagram.yml udagram-parameters.json us-east-1
./runscript.sh delete network network.yml network-parameters.json us-east-1

# To preview Resources 
./runscript.sh deploy network network.yml network-parameters.json us-east-1
./runscript.sh deploy udagram udagram.yml udagram-parameters.json us-east-1
# then confirm the changes by executing-change-set given command

## Useful Information
To access the deployed application, check out the outputs tab of the udagram stack and open the Load balancer URL provided in that section.
Additionally, here is a working url of the deployed app http://udagr-myloa-nhq1py8j8iwv-1970531655.us-east-1.elb.amazonaws.com/ after deploying the network and udagram stacks.
To avoid errors when tearing down resources, delete the application stack first followed by the network stack.








