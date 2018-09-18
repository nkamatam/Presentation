## AWS Introduction/Demo

### What is AWS?

Amazon Web Services (AWS) is a secure cloud services platform, offering **compute power, database storage, content delivery and other functionality** to help businesses scale and grow.

### What are important AWS Services that we need to know 

#### Route53

Route53  is a highly available, scalable, and feature rich domain name service (DNS) web service. Route53 can even register your domain name.

#### Identity and Access Management

[Identity and access management (IAM)](http://aws.amazon.com/iam/)  provides enhanced security and identity management for your AWS account. In addition, it allows you to enable “multi factor” authentication to enhance the security of your AWS account.

**Should you use it?**  Definitely. If you have more than 1 person accessing your AWS account using IAM will allow everyone to get a separate account with fine grained permissions. Multi factor authentication is also critically important since a compromise at the infrastructure level would be catastrophic for most businesses. Read more about IAM  [here](http://shout.setfive.com/2013/03/14/amazon-aws-you-should-enable-iam/).

### Simple Storage Service

**What is it?**  [Simple storage service (S3)](http://aws.amazon.com/s3/)  is a flexible, scalable, and highly available storage web service. Think of S3 like having an infinitely large hard drive where you can store files which are then accessible via a unique URL. S3 also supports access control, expiration times, and several other useful features. Additionally, the payment model for S3 is “pay as you go” so you’ll only be billed for the amount of data you store and how much bandwidth you use to transfer it in and out.

**Should you use it?**  Definitely. S3 is probably the most widely used AWS service because of its attractive pricing and ease of use. If you’re running a site with lots of static assets (images, CSS assets, etc.), you’ll probably get a “free” performance boost by hosting those assets on S3. Additionally, S3 is an ideal solution for incremental backups, both data and code. We use S3 extensively, usually for hosting static files, frequently backing up MySQL databases, and backing up git repositories. The new AWS S3 Console also makes administering S3 and using it non-programmatically much easier.

### Elastic Compute Cloud

**What is it?**  [Elastic Compute Cloud (EC2)](http://aws.amazon.com/ec2/)  is the central piece of the AWS ecosystem. EC2 provides flexible, on-demand computing resources with a “pay as you go” pricing model. Concretely, what this means is that you can “rent” computing resources for as long as you need them and process any workload on the machines you’ve provisioned. Because of its flexibility, EC2 is an attractive alternative to buying traditional servers for unpredictable workloads.

**Should you use it?**  Maybe. Whether or not to use EC2 is always a controversial discussion because the complexity it introduces doesn’t always justify its benefits. As a rule of thumb, if you have unpredictable workloads like sporadic traffic using EC2 to run your infrastructure is probably a worthwhile investment. However, if you’re confident that you can predict the resources you’ll need you might be better served by a “normal” VPS solution like  [Linode](http://www.linode.com/).

### Elastic Block Store

**What is it?**  [Elastic block store (EBS)](http://aws.amazon.com/ebs/)  provides persist storage volumes that attach to EC2 instances to allow you to persist data past the lifespan of a single EC2. Due to the architecture of elastic compute cloud, all the storage systems on an instance are ephemeral. This means that when an instance is terminated all the data stored on that instance is lost. EBS addresses this issue by providing persistent storage that appears on instances as a regular hard drive.

**Should you use it?**  Maybe. If you’re using EC2, you’ll have to weigh the choice between using only ephemeral instance storage or using EBS to persist data. Beyond that, EBS has well documented performance issues so you’ll have to be cognizant of that while designing your infrastructure.

### CloudWatch

**What is it?**  [CloudWatch](http://aws.amazon.com/cloudwatch/)  provides monitoring for AWS resources including EC2 and EBS. CloudWatch enables administrators to view and collect key metrics and also set a series of alarms to be notified in case of trouble. In addition, CloudWatch can aggregate metrics across EC2 instances which provides useful insight into how your entire stack is operating.

**Should you use it?**  Probably. CloudWatch is significantly easier to setup and use than tools like  [Nagios](http://www.nagios.org/)  but its also less feature rich. We’ve had some success coupling CloudWatch with  [PagerDuty](http://www.pagerduty.com/)  to provide alerts in case of critical service interruptions. You’ll probably need additional monitoring on top of CloudWatch but its certainly a good baseline to start with.

Anyway, the AWS ecosystem includes several additional services but these are the ones that I felt are key to getting started on AWS. We haven’t had a chance to use it yet but  [Redshift](http://aws.amazon.com/redshift/)  looks like it’s an exciting addition which will probably make this list soon. As always, comments and feedback welcome.

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM0NzU1MTE1MywxNTQ5NzIzNzc1LDk3MT
E3NzQwNF19
-->