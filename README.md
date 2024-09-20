# EOM2-assessment-alanp
End of module 2 assessment challenges by instructors from NTU - Cloud Engineering course.


Overview
This document highlights the competencies and knowledge that learners are to be aware of at the end of module 2, prior to starting module 3.

Do take some time to brush up on these required skills during the 2 weeks break, and feel free to reach out to the instructors via Discord questions thread to clarify any information.

Topics & Competencies
Server Basics
Things To Know
Good understanding of basic server networking including protocols like TCP, UDP, SSH, HTTP etc.
Good understanding of basic server security including protocols like HTTPS and TLS/SSL, and also good grasp of blacklisting and whitelisting and its use cases
Good understanding of Linux and Windows server administration
Good understanding of virtualization on servers, particularly containerization technology
Good understanding of clustering servers e.g. using load balancing and how it helps infrastructure stability
Good understanding of High Availability and Disaster Recovery, and how it is set up in organizations.

Test Yourself:
Able to curl public API endpoints using powershell, terminal and Postman API. Use one or several of these publicly available endpoints here: https://github.com/public-apis/public-apis 
E.g. https://www.ipify.org/ to get public IP address
E.g. https://api.chucknorris.io/ to get fun Chuck Norris facts
E.g. https://uselessfacts.jsph.pl/ to get fun daily facts
Feel free to use more endpoints, especially those that require authentication, to test your understanding on creating API keys for accessing those endpoints
Able to work well with basic Linux commands found here: LINK
Able to work well with basic Windows powershell commands found here: LINK

AWS Cloud
Things to Know:
Good understanding of AWS networking basics which includes Regions, AZs, VPC, Subnets, Security Groups, Internet Gateway, NAT Gateway, Route Tables etc.
Good knowledge of EC2 compute resources which includes EBS and creating AMI.
Good understanding of load balancing in AWS, which includes Application Load Balancing, Launch Templates and Auto Scaling Groups. 
Good understanding of IAM - roles, permissions, groups and policies.
Familiarity with AWS Database offerings such as RDS and DynamoDB.
Good understanding of storage options in AWS including S3 and EFS
Good understanding of CDN, which includes CloudFront, WAF and Shield, to serve traffic to global users.

Test Yourself (from console):
Create a VPC with 3 public and 3 private subnets and 1 internet gateway for public subnets. Enable auto-assign public IPv4 address on your public subnets. 
Create an EC2 and place it in your public subnet. Install an Apache Web Server on your EC2 and test whether it is publicly accessible via port 80 on the public IP.
Further Test: Take an AMI snapshot of the EC2, copy it to another region, and start an EC2 from that AMI. Ensure that your EC2 is working as expected with Apache Web Server installed.
Further Test: Use ALB to direct traffic to it
Create a new IAM user to give the user only READ ACCESS to S3 buckets. Add extra permissions to give the user more privilege and test.
Create an RDS (MySQL) in Dev environment (Single instance)
Further Test: Connect to the RDS server using MySQL Workbench and test out: LINK > Connecting MySQL Workbench to RDS 
Further Test: Create an EFS and mount it to an EC2. Ensure you are able to view the EFS mount point on your EC2 and you are able to access the files on EFS. LINK
Create a CloudFront distribution that points to an S3 bucket containing your static website. Ensure you are able to view the static website from the CloudFront distribution. 
Further Test: Create an auto-scaling group for an EC2 with Apache Web Server installed on it via a Launch Template. Min EC2 = 1, Max EC2 = 3. Test whether you are able to scale up the number of EC2s from 1 to 3.
Further Test: Use the Launch Template earlier to create an application load balancer with auto-scaling enabled. Min EC2 = 1, Max EC2 = 3. Test whether you are able to scale up the number of EC2s from 1 to 3.
Further Test: Create a simple Lambda function that prints “Hello World” via Python. LINK


Docker
Things to Know:
Good understanding on containerization technology, particularly Docker, and how containerization can help with portability and scalability of your application.
Good understanding and experience building, packaging and publishing Docker images from Dockerfile to ECR.

Test Yourself: 
Using a simple python “Hello World” application, build an image locally and run the image as a container on your local machine. Ensure you are able to view the web page from your browser and you are able to curl the endpoint, showing “Hello World”. LINK
Publish your Docker image to an ECR container with the “latest” tag.
Further Test:
Update the app.py file to print “Hello Universe” instead of “Hello World”. Create an image from this code with the tag “v1-universe”. Publish the docker image to the same ECR container with the same “v1-universe” tag.
Update the same app.py file to print “Hello Galaxy” instead of “Hello Universe” or “Hello World”. Create an image from this code with the tag “v2-galaxy”. Publish the docker image to the same ECR container with the same “v2-galaxy” tag.
Balance the traffic between both instances using ALB and Route53


Terraform
Things to Know:
Good understanding of what infrastructure as code (Terraform) is and why it is preferred to manual provisioning of resources.
Good knowledge of terraform state files and how to securely store the state file with a backend code block.
Good knowledge of terraform providers and why it is needed for certain projects.
Good knowledge of the different terraform blocks including resources, data, outputs, variables etc. and when to use them.
Working knowledge of advanced terraform features like terraform functions (concat, joins, max, min etc.) and how to use them.
Working knowledge of how to handle multiple environments with the same terraform code using terraform workspaces/ terraform cloud.

Test Yourself:
Create AWS VPC and its networking components similar to AWS Cloud > Test Yourself > (1) using Terraform Resources. Ensure that the output is the same as that created via the cloud console.
Create AWS VPC and its networking components similar to AWS Cloud > Test Yourself > (1) using Terraform Module. Ensure that the output is the same as that created via the cloud console.
Create an EC2 using Terraform Resources and place it inside the public subnet of your previously created VPC. Ensure that you install Apache Web Server via User Data/ Bootstrap script. 
Further Test: Create an RDS with MySQL installed with Terraform, and ensure it works as expected as AWS Cloud > Test Yourself > (4). Test whether you are able to connect to the RDS via MySQL Workbench if you’d like to.
Further Test: Create a Lambda Function that prints a simple “Hello World” in Python using Terraform. Refer to AWS Cloud > Test Yourself > (9) as well as LINK on how to achieve this.
Utilize dev.tfvars, uat.tfvars, and prod.tfvars on the same Terraform codes to allow you to create multiple resources for different environments using Terraform workspaces. Run the code from this LINK locally (without Github Actions first)


Github Actions
Things to Know:
Good understanding of Github management console (Settings) including performing actions like adding/removing/updating secrets and environments.
Good knowledge of writing Github actions workflows - event triggers, jobs, steps etc.
Working ability on fixing and troubleshooting workflow runs seen from the console.

Test Yourself:
Create a workflow on a new Github Repository or an existing Repository that has 1 job which only prints “Hello World” on a workflow_dispatch and git push trigger.
Create a new Github Repository to create an EC2 from Terraform using Github Actions. EC2 should be created with Apache Web Server installed and deployed onto an existing public subnet and be publicly accessible. Create a yaml file in your .github/workflows to run the steps needed to create the EC2 via terraform plan and terraform apply -auto-approve. Test your workflow and ensure that your workflow allows an EC2 to be created on a workflow_dispatch.
Utilize dev.tfvars, uat.tfvars, and prod.tfvars on the same Terraform codes to allow you to create multiple resources for different environments using Terraform workspaces. Run the code from this LINK on Github Actions.
