# Chris Iregbu - Udacity/BIT Cloud DevOps Engineer Program - Project 2: Deploy a High-Availability Web App using CloudFormation

## Solution

### Diagram

network-architecture-diagram.PNG

### Description

The solution consists of a number of two stack template files for manageability for example, to avoid ovewriting code.

### Template Stack Files
1. network-infrastructure.yml and network-infrastructure-params.json are used for deploying the network infrastructure including
   LoadBalancer, Launch Configuration, AutoScaling group a health check, security groups and a Listener and Target Group
   network-infrastructure-params.json template file contains the default parameters which are substituted dynamically 
   with values that are provided at runtime via network-infrastructure.yml 

2. The template stack files named application-server.yml and application-server-params are used to deploy the application server resources

### Shell Scripts
1. create.sh is used to create required network and server resources. It invokes the aws cloudformation create-stack api
2. update.sh is used to update existing stacks. It invokes the aws cloudformation update-stack api	
3. delete.sh is used to delete to discard existing infrastructure after the testing team have finished their test and gathered their results. It
   calls the aws cloudformation delete-stack api - it accepts the stack name as parameter

### Deployment Instructions

To deploy the networking resources and servers, please run the following template stack files in a terminal

    > ./create.sh networkinfra network-infrastructure.yml network-infrastructure-params.json

    > ./create.sh appserver application-server.yml application-server-params.json

The Udagram website can be accessed using the LoadBalancer URL: http://appli-webap-uw1gotil898z-1153458155.us-west-2.elb.amazonaws.com/

### Screenshots
screenshots.docx


