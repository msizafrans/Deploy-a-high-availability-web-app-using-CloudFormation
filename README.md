# Deploy-a-high-availability-web-app-using-CloudFormation

# ND9991 - Course 2 - Infrastructure as Code

This repository contains the starter code for the final project of course 2 Infrastructure as Code in the Cloud DevOps Engineer Nanodegree.

Please note that all supporting material for this course can be found in [this Github repository](https://github.com/udacity/cd12352-Deploy-Infrastructure-as-Code).

# Deploy a high-availability web app using CloudFormation

In this project, you’ll deploy web servers for a highly available web app using CloudFormation. You will write the code that creates and deploys the infrastructure and application for an Instagram-like app from the ground up. You will begin with deploying the networking components, followed by servers, security roles and software.  The procedure you follow here will become part of your portfolio of cloud projects. You’ll do it exactly as it’s done on the job - following best practices and scripting as much as possible. 

**Project Introduction**
Creating this project will give you the hands-on experience you need to talk about infrastructure as code confidently. We have chosen a realistic scenario where you will deploy a dummy application (a sample JavaScript or HTML file) to an NGINX server running on an EC2 instance.

**There will be two parts to this project:**

Diagram: You'll first develop a diagram that you can present as part of your portfolio and as a visual aid to understand the CloudFormation script.
Script (Template and Parameters): The second part is to interpret the instructions and create a matching CloudFormation script.

## Getting Started

### Dependencies

1. AWS CLI installed and configured in your workspace using an AWS IAM role with Administrator permissions (as reviewed in the course).

2. Access to a diagram creator software of your choice.

3. Your favorite IDE or text editor ready to work.

### Installation

You can get started by cloning this repo in your local workspace:

```
git clone git@github.com:udacity/-cd12352-Deploy-Infrastructure-as-Code-project.git
```

## Testing

No tests required for this project.

## Project Instructions

1. Design your solution diagram using a tool of your choice and export it into an image file.

2. Add all the CloudFormation networking resources and parameters to the `network.yml` and `network-parameters.json` files inside the `starter` folder of this repo.

3. Add all the CloudFormation application resources and parameters to the `udagram.yml` and `udagram-parameters.json` files inside the `starter` folder of this repo.

4. Create any required script files to automate spin up and tear down of the CloudFormation stacks.

5. Update the README.md file in the `starter` folder with creation and deletion instructions, as well as any useful information regarding your solution.
   
6.  Submit your solution as a GitHub link or a zipped file containing the diagram image, CloudFormation yml and json files, automation scripts and README file.

## License

[License](LICENSE.txt)
