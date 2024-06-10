# ND9991 - Course 2 - Infrastructure as Code
This repository contains the starter code for the final project of course 2 Infrastructure as Code in the Cloud DevOps Engineer Nanodegree.

Please note that all supporting material for this course can be found in this Github repository.

# Deploy a high-availability web app using CloudFormation
In this project, you’ll deploy web servers for a highly available web app using CloudFormation. You will write the code that creates and deploys the infrastructure and application for an Instagram-like app from the ground up. You will begin with deploying the networking components, followed by servers, security roles and software. The procedure you follow here will become part of your portfolio of cloud projects. You’ll do it exactly as it’s done on the job - following best practices and scripting as much as possible.

# Getting Started
# Dependencies
AWS CLI installed and configured in your workspace using an AWS IAM role with Administrator permissions (as reviewed in the course).

Access to a diagram creator software of your choice.

Your favorite IDE or text editor ready to work.

# Installation
You can get started by cloning this repo in your local workspace:

git clone git@github.com:udacity/-cd12352-Deploy-Infrastructure-as-Code-project.git

# Testing
No tests required for this project.

# Project Instructions
Design your solution diagram using a tool of your choice and export it into an image file.

Add all the CloudFormation networking resources and parameters to the network.yml and network-parameters.json files inside the starter folder of this repo.

Add all the CloudFormation application resources and parameters to the udagram.yml and udagram-parameters.json files inside the starter folder of this repo.

Create any required script files to automate spin up and tear down of the CloudFormation stacks.

Update the README.md file in the starter folder with creation and deletion instructions, as well as any useful information regarding your solution.

Submit your solution as a GitHub link or a zipped file containing the diagram image, CloudFormation yml and json files, automation scripts and README file.

License

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








