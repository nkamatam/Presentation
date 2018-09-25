## AWS Introduction/Demo

### What is AWS?

Amazon Web Services (AWS) is a secure cloud services platform, offering **compute power, database storage, content delivery and other functionality** to help businesses scale and grow.


### What are important AWS Services that we need to know 

![Image result for number of cloud services aws](http://www.cyberphoton.com/wp-content/uploads/2016/02/aws-cloud-computing.jpg)

#### Route53

[**Route53**](http://aws.amazon.com/route53)  is a highly available, scalable, and feature rich domain name service (DNS) web service. Route53 can even register your domain name.

#### Identity and Access Management

[**IAM**](http://aws.amazon.com/iam/)  provides enhanced security and identity management for your AWS account. In addition, it allows you to enable “multi factor” authentication to enhance the security of your AWS account.

#### Simple Storage Service

[**S3**](http://aws.amazon.com/s3/)  is a flexible, scalable, and highly available storage web service. Payment model for S3 is “pay as you go” so you’ll only be billed for the amount of data you store and how much bandwidth you use to transfer it in and out.

#### Elastic Compute Cloud

[**EC2**](http://aws.amazon.com/ec2/)   provides flexible, on-demand computing resources with a “pay as you go” pricing model. 

#### Elastic Block Store

[**EBS**](http://aws.amazon.com/ebs/)  provides persist storage volumes that attach to EC2 instances to allow you to persist data past the lifespan of a single EC2. 

#### CloudWatch

[**CloudWatch**](http://aws.amazon.com/cloudwatch/)  provides monitoring for AWS resources including EC2 and EBS. CloudWatch enables administrators to view and collect key metrics and also set a series of alarms to be notified in case of trouble.

#### Why Cloud? Why AWS? 
Ability to Experiment with little upfront cost<br>
Scalability<br>
Operational Ease<br>
Security<br>
Competitiveness<br>
Cap Ex vs Op Ex<br>

#### Why AWS?
![Image result for cloud magic quadrant 2018](https://regmedia.co.uk/2018/05/29/gartner_iaas_mq_2018_supplied.jpg)

## Simple Website with AWS
Let us try to build a simple Website using AWS

### Architecture Diagram
![Architecture](https://s3.ap-south-1.amazonaws.com/nkamatam/WebServer.jpg)

### Steps involved
* Create a SG1 to allow port 443, 80 and 22
* Create a SG2 to allow port 3306
* Create a server and choose SG1
* Create a database and choose SG2
* 

### Basics before we start
* VPC - Virtual Private Cloud
* Subnet - A private/public section of VPC that has a Subnet mask
*  Availability Zone - Can be thought of as  a _Data Center_ in a region
* Port and IP Address -  IP Address is a unique way to identify a networked entity (Port is a standard/non-standard number assigned to a service)
* Webserver - A demon that is running on a server operating on a port (usually port 80) and servicing HTTP requests 

### Steps Involved 
* Create Virtual Private Cloud - VPC (10.0.0.0/16)
* Create an Internet Gateway
* Assign it to the new VPC that we created
* Create a Subnet in that VPC (10.0.1.0/24) - For the webserver
* Create a Subnet in that VPC (10.0.2.0/24) - For the DB AZ1
* Create a Subnet in that VPC (10.0.3.0/24) - For the DB AZ2
* Create a Security Group that Allows only Port 22, 80 and 443 (outbound all)
* Create second Security Group that allows only Port 3306 (mysql) (outbound all)
* Create a RDS instance (MySQL)
* Create a EC2 instance  (use the user data to install the software needed)
* Create the sample HTML files 
	* Index.html (something that connects to the database table)
	* health.html
* Move them to the Apache directory
* Create a Sample database table
	* Student 
		* StudentId
		* StudentName
* Load some sample table data
*  Connect to the webserver
* 



<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg3NDcxNjAxMCwtMTA3MjIyOTQ5LDE2MD
I0OTEwNDcsLTM0NDU3OTY0OSwtNTc0MTkxMTYxLC0yMTAzMjk4
MTczLC0yOTM0MjAyMzksNzk5NDE5MDE4LDI0NzA0MzEzNCwxOT
kwOTU0Mzk5LC0xMDU3MjUwMDQsLTEzMTY1MDEzOF19
-->