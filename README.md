CD12352 - Infrastructure as Code Project Solution
 Automation script for CloudFormation Stacks
 [FRANS MSIZA]

# Parameters
   $1: Execution mode. Valid values: deploy, delete, preview.
   $2: Name of the cloudformation stack.
   $3: Name of the template file.
   $4: Name of the parameters file.
   $5: Target region.

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








