# Advantages of Cloud

* Trade capital expense for variable expense
* Benefit from massive economies of scale
* Stop guessing about capacity
* Increase speed and agility
* Stop spending money running and maintaining data centers
* Go global in minutes

# The AWS Well-Architected Framework 5 Pillars 

* Operational Excellence
* Security
* Reliability
* Performance Efficiency
* Cost Optimization.

# Characteristics of AWS Cloud

* Agility: refers to the ability to rapidly develop, test and launch software applications that drive business growth Another way to explain "Agility" - AWS provides a massive global cloud infrastructure that allows you to quickly innovate, experiment and iterate. Instead of waiting weeks or months for hardware, you can instantly deploy new applications. This ability is called Agility.

* Elasticity: refers to the ability to acquire resources as you need and release when they are no longer needed is termed as Elasticity of the Cloud.

* Reliability: refers to the ability of a system to recover from infrastructure or service disruptions, by dynamically acquiring computing resources to meet demand, and mitigate disruptions.

* Scalability: it is the measurement of a system's ability to grow to accommodate an increase in demand, or shrink down to a diminishing demand.

* Resiliency - Describes the ability of a system to recover from a failure induced by the load (data or network), attacks, and failures (hardware, software, or network failures).

-------

# Types of Cloud Computing

* Infrastructure as a Service (IaaS)

Amazon EC2 (on AWS), Digital Ocean, GCP, Azure,

* Platform as a Service (PaaS)

Elastic Beanstalk (on AWS), Heroku

AWS Elastic Beanstalk is an easy-to-use service for deploying and scaling web applications and services. 

* Software as a Service (SaaS)

 Examples - Amazon Rekognition, Google Apps (Gmail), Dropbox,

 Note:  Amazon Rekognition, you can identify objects, people, text, scenes, and activities in images and videos as well as detect any inappropriate content. Rekognition is an example of Software as a Service model.

 # Types of Cloud Computing Deployments

* Public - AWS, Azure, GCP
* Hybrid - mixture of public and private
* Private - your own datacenter with Openstack or Vmware

# Types of Scaling

* Vertical Scaling: is constrained to be running its processes on only one computer. In such systems, the only way to increase performance is to add more resources into one computer in the form of faster (or more) CPUs, memory or storage.

* Horizontal Scaling: the ne that can increase capacity by adding more computers to the system. Horizontally scalable systems are oftentimes able to outperform vertically scalable systems by enabling parallel execution of workloads and distributing those across many different computers.

# AWS Pricing

Data transfer between AWS services within the same region is not charged, so there would be no data transfer charge for moving 500 GB of data from an EC2 instance to an S3 bucket in the same region

--------

# Region x Availabiliy Zone (AZ) x Edge Location

* Region - physical location in the world (EU, US West, South America, etc.)
* AZ - one or more data center, each with redundant power, networking and connectivity, housed in separate facilities
* Edge Location - where end users access services located at AWS; endpoints for AWS used for caching content (tipically CloudFront or Amazon's Content Delivery Network - CDN)

Each Region consists of at least two Availability Zones which are physically separated, fault tolerant, and connected among themselves by high throughput, low latency, and highly redundant network

# Things to consider when choosing your AWS region

* Regional laws about data
* Latency to end users
* AWS services availability

# Retrieving files

* Edge Location: location where content will be cached. This is separate to an AWS Region or AZ
* Origin: the origin of all the files that the CDN will distribute. This can be either an S3 Bucket, an EC2 Instance, an Elastic Load Balancer or Route53.
* Distribution: a CDN that's a collection of Edge Locations
* Web Distribution: Distributions used for websites
* RTMP: Distribution used for media streaming

Note: CDN stands for Content Delivery Network

-----

# Support packages

* Basic - free
* Developer - $29/mo (scales based on usage)
* Business - $100/mo (scales based on usage)
* Enterprise - $15.000/mo (scales based on usage) + Technical Account Manager (TAM)

AWS has billing allerts that will allert you automatically when a certain level of AWS spend has been reached, so you should really turn it on

# Response Time

* Basic - 
* Developer - General (24h) + System impaired (12h)
* Business - General (24h) + System impaired (12h) + Producting system impaired (4h) + Production system down (1h)
* Enterprise - General (24h) + System impaired (12h) + Producting system impaired (4h) + Production system down (1h) + Businness-critical system down (15min)

# APN Consulting Partner

APN Consulting Partners are professional services firms that help customers of all types and sizes design, architect, build, migrate, and manage their workloads and applications on AWS, accelerating their migration to AWS cloud.

# Concierge Support Team

The Concierge Support Team are AWS billing and account experts that specialize in working with enterprise accounts. They will quickly and efficiently assist you with your billing and account inquiries. The Concierge Support Team is only available for the Enterprise Support plan. 

# APN Technology Partner 

APN Technology Partners provide software solutions that are either hosted on, or integrated with, the AWS platform. Technology Partners include Independent Software Vendors (ISVs), SaaS, PaaS, Developer Tools, Management and Security Vendors.

-----

# Identity Access Management (IAM)

In AWS, privilege management is primarily supported by the AWS Identity and Access Management (IAM) service, which allows you to control user and programmatic access to AWS services and resources. You should apply granular policies, which assign permissions to a user, group, role, or resource. 

You also can require strong password practices, such as complexity level, avoiding re-use, and enforcing multi-factor authentication (MFA).

IAM stands for Identity Access Management and it is Global, which means when you create a user or group this is created **globally** because you don't specify a region when dealing with IAM.

# Root account

Your root account is the email address used to set up your AWS account. It has full admin access and it should not be shared. It's also a good pratice to secure this root account using MFA.

# Group

A group is simply a place to store your users. Your users will inherit all permisions their groups have.  
To set the permissions of a group you need to apply a policy to that group. A policy is a JSON configuration.

# AWS Organizations

OU stands for Organizational Units.

AWS Organizations helps you to centrally manage billing; control access, compliance, and security; and share resources across your AWS accounts. Using AWS Organizations, you can automate account creation, create groups of accounts to reflect your business needs, and apply policies for these groups for governance. 

AWS Organizations is available to all AWS customers at no additional charge.

You have your root account, you then have your different organizational units (finance, developer, marketing, etc). Then you have AWS accounts
that will sit behind those organizational units. You can apply policies either directly to organizational units or to AWS accounts themselves.

# AWS Organizations Best Practices

* Make sure you always enable multi-factor authentication on your root account.
* Make sure you use a strong and complex password on the root account.
* Make sure that the paying account should be used for billing purposes only. Do not deploy resources into the paying account

# AWS Access

You can access AWS in three ways:

* Via the console
* Programatically with command line
* Using the SDK

-----

# Amazon Simple Storage Service (S3) 

Amazon Simple Storage Service (Amazon S3) is an object storage service that offers industry-leading scalability, data availability, security, and performance.

* Object-based (allows you to upload files)
* Files can be from 0B to 5TB
* There is unlimited storage
* Files are stored in Buckets
* S3 name is a universal namespace, which means it must be unique globally
* Example S3 URL: https://s3-[location]-amazonaws.com/[bucket name]
* Can't be installed on operating systems
* Successful Object uploads will return HTTP status code 200
* Key and Value pairs are the fundamentals of S3
* It's okay to read an Object after it's been written, but it may take a while to read an object after it's been updated or deleted.
* You can have buckets in different regions
* It's possible to replicate data between Buckets automatically and it's called cross region replication
* You can use S3 to host static websites, but you can't host websites that require database connections
* S3 scales automatically to meet your demand. It's a common pratice for companies to put static websites when they think there's going to be a large number of requests (such as static websites for movie previews for example).

Note: An Amazon S3 bucket is a public cloud storage resource available in Amazon Web Services' (AWS) Simple Storage Service (S3), an object storage offering. Amazon S3 buckets, which are similar to file folders, store objects, which consist of data and its descriptive metadata.

# Storage classes

* S3 Standard: 99.99% availability, 99.9999999% durability, and it's stored redundantly across multiple devices in multiple facilities. It's also designed to sustain t he loss of 2 facilities concurrently.
* S3 Infrequently Accessed (IA): for data that's accessed less frequently but still needs rapid access when needed. Lower fee than S3 Standard, but they charge a retrieval fee.
* S3 One Zone IA: lower cost option when you need infrequently accessed data, but you don't need the multiple Availability Zone resilience
* S3 Intelligent Tiering: designed to optimize cost by automatically moving data to the most cost-effective access tier without performance impact or operational overhead.
* S3 Glacier: secure, durable and low-cost storage class for data archiving. Retrieval times are configurable from minutes to hours.
* S3 Glacier Deep Archive: lowest-cost storage you can use when a retrieval time of 12 hours is acceptable.

# Athena
an interactive query service and it allows you to query data located in S3 using standard SQL. Athena is serverless, so there is no infrastructure to manage, and you pay only for the queries that you run.

-----

# Databases

* Amazon Relational Database Service  (RDS) (SQL/OLTP): SQL, MySQL, PostgreSQL, Oracle, Aurora and MariaDB  
* DynamoDB (NoSQL)
* Redshift OLAP (Big Data, Data warehousing)
* ElastiCache: caches frequent identical database queries
    * Two types: memory cached or Redis
* Amazon Neptune: fully managed graph database
    * Useful for Scalability and High availability

# Multi-AZ deployments, multi-region deployments, and read replicas

* Multi-AZ deployments: Main purpose is high availability
* Multi-region deployments: Main purpose is disaster recovery and local performance
* Read replicas: Main purpose is scalability

------

# EC2

Amazon Elastic Compute Cloud (Amazon EC2) is a web service that provides resizable compute capacity in the cloud. It's got scale capacity, both up and down, as your computing requirements change. It can boot new servers instances in minutes, so scaling is really quick.

It's possible to provide multiple EC2 instances behind a load balancer automatically depending on your demand.

# S3 x EC2

An EC2 instance is like a remote computer running Windows or Linux and on which you can install whatever software you want, including a Web server running PHP code and a database server.

Amazon S3 is just a storage service, typically used to store large binary files. Amazon also has other storage and database services, like RDS for relational databases and DynamoDB for NoSQL.

# Load Balancers

3 types: 

* Application Load Balancers: routes traffic to targets within Amazon VPC based on the content of the HTTP/HTTPS request.
* Network Load Balancers: is best suited for load balancing of Transmission Control Protocol (TCP), User Datagram Protocol (UDP), and Transport Layer Security (TLS) traffic where extreme performance is required.
* Gateway Load Balancer: easy to deploy, scale, and run third-party virtual networking appliances.

# Instance Store

An instance store provides temporary block-level storage for your instance. This storage is located on disks that are physically attached to the host computer. This is a good option when you need storage with very low latency, but you don't need the data to persist when the instance terminates or you can take advantage of fault-tolerant architectures. 

# EC2 Instance Types

* On-Demand Instances - an instance that you use on-demand. You have full control over its lifecycle — you decide when to launch, stop, hibernate, start, reboot, or terminate it. On-demand instances cannot be interrupted.

* Reserved Instances - not physical instances, but rather a billing discount applied to the use of On-Demand Instances in your account. You can purchase a Reserved Instance for a one-year or three-year commitment, with the three-year commitment offering a bigger discount. You will be charged for the entire duration, irrespective of your usage.

* Spot Instances - an unused EC2 instance that is available for less than the On-Demand price. Because Spot Instances enable you to request unused EC2 instances at steep discounts, you can lower your Amazon EC2 costs significantly. Spot Instances are well-suited for data analysis, batch jobs, background processing, and optional tasks. These can be terminated at short notice, so these are not suitable for critical workloads that need to run at a specific point in time. 

* Dedicated Hosts - allow you to use your eligible software licenses from vendors such as Microsoft and Oracle on Amazon EC2 so that you get the flexibility and cost-effectiveness of using your licenses, but with the resiliency, simplicity, and elasticity of AWS. An Amazon EC2 Dedicated Host is a physical server fully dedicated for your use, so you can help address corporate compliance requirement. They're not cost-efficient compared to On-Demand instances.

# EC2 Instances Pricing Models

* On Demand Instances: allows you to pay a fixed rate by the hour (or by the second) with no commitment
* Reserved Instances: provides you with a capacity reservation and offer a significant discount on the hourly charge for an instance. Contract Terms are 1 Year or 3 Year Terms
* Spot Instances: enables you to bid whatever price you want for instance capacity, providing even greater savings if your application have flexible start and end times.
* Dedicated Hosts: physical server dedicated for your use. Dedicated Hosts can help you reduce costs by allowing you to use your existing server-bound software licenses.

# Reasons for instance interruption

The following are the possible reasons that Amazon EC2 might interrupt your Spot Instances:

Price – The Spot price is greater than your maximum price.

Capacity – If there are not enough unused EC2 instances to meet the demand for On-Demand Instances, Amazon EC2 interrupts Spot Instances. The order in which the instances are interrupted is determined by Amazon EC2.

Constraints – If your request includes a constraint such as a launch group or an Availability Zone group, these Spot Instances are terminated as a group when the constraint can no longer be met.

# EBS

Amazon Elastic Block Store (EBS) is an easy to use, high-performance block storage service designed for use with Amazon Elastic Compute Cloud (EC2) instances for both throughput and transaction-intensive workloads at any scale.

SSD

* General Purpose SSD (GP2): balances price and performance for a wide variety of workloads
* Provisioned IPOS SSD (IO1): highest-performance SSD volume for mission-critical low-latency or high-throughput workloads

Magnetic

* Throughput Optimized HDD (ST1): low cost HDD volume designed for frequently accessed throughput-intensive workloads
* Cold HDD (SC1): lowest cost HDD volume designed for less frequently accessed workloads (like File Servers)
* Magnetic: previous generation and may be discontinued

# EFS 

Amazon Elastic File System (Amazon EFS) provides a simple, scalable, fully managed, elastic NFS file system.

Can be accessed simultaneously by multiple EC2 instances.

# Storages Comparison

Amazon S3 provides simple object storage, useful for hosting website images and videos, data analytics, and both mobile and web applications. Object storage manages data as objects, meaning all data types are stored in their native formats. There is no hierarchy of relations between files with object storage — data objects can be distributed across several machines. You can access the S3 service from anywhere on the internet. Learn more about Amazon S3 common operations on objects and buckets. 

AWS EBS provides persistent block-level data storage. Block storage stores files in multiple volumes called blocks, which act as separate hard drives; block storage devices are more flexible and offer higher performance than regular file storage. You need to mount EBS onto an Amazon EC2 instance. Use cases include business continuity, software testing, and database management. Learn more about EBS volume types and common operations.

AWS EFS is a shared, elastic file storage system that grows and shrinks as you add and remove files. It offers a traditional file storage paradigm, with data organized into directories and subdirectories. EFS is useful for SaaS applications and content management systems. You can mount EFS onto several EC2 instances at the same time.  Learn how to create an EFS file system and mount it on an EC2 instance.

# Design for failure

Always design for failure, which means you should have one EC2 instance in each Availability Zone.

---------

# AWS Storage Gateway

AWS Storage Gateway is a hybrid cloud storage service that connects your existing on-premises environments with the AWS Cloud.

AWS Storage Gateway service provides three different types of gateways – Tape Gateway, File Gateway, and Volume Gateway – that seamlessly connect on-premises applications to cloud storage, caching data locally for low-latency access.

AWS Snowball, a part of the AWS Snow Family, is a data migration and edge computing device. If you have large quantities of data you need to migrate into AWS, offline data transfer with AWS Snowball can overcome the challenge of limited bandwidth, and avoid the need to lease additional bandwidth. Snowball moves terabytes of data in about a week. You can use it to move things like databases, backups, archives, healthcare records, analytics datasets, etc.

# API Gateway

Amazon API Gateway is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale. APIs act as the "front door" for applications to access data, business logic, or functionality from your backend services.

# Amazon VPC (Virtual Private Cloud)

Amazon Virtual Private Cloud (Amazon VPC) is a service that lets you launch AWS resources in a logically isolated virtual network that you define.

# Internet Gateway

An Internet Gateway is a horizontally scaled, redundant, and highly available VPC component that allows communication between your VPC and the internet.

# AWS Transit Gateway

AWS Transit Gateway connects VPCs and on-premises networks through a central hub. This simplifies your network and puts an end to complex peering relationships. It acts as a cloud router.

# AWS Direct Connect

AWS Direct Connect is a cloud service solution that makes it easy to establish a dedicated network connection from your premises to AWS. You can use AWS Direct Connect to establish a private virtual interface from your on-premise network directly to your Amazon VPC.

-----

# Consolidated Billings

Allows you to get volume discounts on all your accounts

# AWS Simple Monthly Calculator

It's used to calculate your running costs on AWS on a per month basis,

It is not a comparison tool. If you're being asked to do a comparison, you should use AWS's Total Cost of Ownership calculator, which is used to compare the costs of running your infrastructure on premise in the AWS cloud and then you can use it to generate reports you can give to your C-level executives.

# Budgets vs Cost Explorer

* Budgets: used to budget (or predict) costs before they are incurred.
* Cost Explorer is used to explore costs after they have been incurred.

AWS Budgets gives you the ability to set custom budgets that alert you when your costs or usage exceed (or are forecasted to exceed) your budgeted amount.

----

# AWS Service Health Dashboard 

AWS Service Health Dashboard publishes most up-to-the-minute information on the status and availability of all AWS services in tabular form for all Regions that AWS is present in.

# AWS Personal Health Dashboard

AWS Personal Health Dashboard provides alerts and remediation guidance when AWS is experiencing events that may impact you. With Personal Health Dashboard, alerts are triggered by changes in the health of your AWS resources, giving you event visibility, and guidance to help quickly diagnose and resolve issues.

-----

# Free Services

* Amazon VPC
* Elastic Beanstalk
* CloudFormation
* Identity Access Management (IAM)
* Auto Scaling 
* Opsworks
* Consolidated Billing

But do remember that the services like Elastic Beanstalk, CloudFormation and Opsworks are provisioning resources for you like EC2 and you will have to pay for those resources.

# AWS Global Services

Most of the services that AWS offers are Region specific. But few services, by definition, need to be in a global scope because of the underlying service they offer. AWS IAM, Amazon CloudFront, Route 53 and WAF are some of the global services.

* IAM
* Route53
* CloudFront
* SNS
* SES

# Services that can be used on-premise (physically located)

* Snowball
* Snowball Edge
* Storage Gateway
* CodeDeploy
* Opsworks
* IoT Greengrass


-----

# AWS Service Catalog 

AWS Service Catalog allows organizations to create and manage catalogs of IT services that are approved for use on AWS. These IT services can include everything from virtual machine images, servers, software, and databases to complete multi-tier application architectures.

## SNS - Amazon Simple Notification Service
used to fan out notifications to end users using mobile push, SMS, and email.

## SQS - Amazon Simple Queue Service
send, store, and receive messages between software components at any volume, without losing messages or requiring other services to be available.

## Lambda 
run code without provisioning or managing servers. You pay only for the compute time you consume.

## Glue
batch ETL data processing. Fully managed extract, transform, and load (ETL) service that makes it easy for customers to prepare and load their data for analytics.

## EMR - Elastic MapReduce
big data platform for processing vast amounts of data using open source tools such as Hadoop, Apache Spark, Apache Hive, Apache HBase, Apache Flink, Apache Hudi, and Presto. 

## Fargate
serverless compute engine for containers. It works with both Amazon Elastic Container Service (ECS) and Amazon Elastic Kubernetes Service (EKS). You only pay for the resources required to run your containers.

## Route53 - Amazon DNS
DNS is the process of resolving names to IP addresses

## Elastic Beanstalk
an easy-to-use service for deploying and scaling web applications in the AWS Cloud without worrying about infrastructure that runs those applications. You pay only for the AWS resources needed to store and run your applications.

## Secrets Manager
this service enables you to easily rotate, manage, and retrieve database credentials, API keys, and other secrets throughout their lifecycle.

## Systems Manager
gives you visibility and control of your infrastructure on AWS with a unified user interface so you can view operational data from multiple AWS services and also automate operational tasks across your AWS resources. 

## CloudFront
improve the performance of your website by making your website files (such as HTML, images, and video) available from data centers around the world (called edge locations). When a visitor requests a file from your website, CloudFront automatically redirects the request to a copy of the file at the nearest edge location.

## Global Accelerator
a service that improves the availability and performance of your applications with local or global users.

## CodeDeploy
a service that automates code deployments to any instance, including Amazon EC2 instances and instances running on-premises.

## X-Ray
analyze and debug serverless and distributed applications

## Amazon Polly (TTS)
turn text into lifelike speech thereby allowing you to create applications that talk.

## Amazon Transcribe (STT)
add speech-to-text capability to your applications.

## Amazon Translate
used for language translation.

## AWS Organizations
helps you to centrally manage billing and also controls access, compliance, security and share resources across your AWS accounts. 
Using AWS Organizations, you can automate account creation, create groups of accounts to reflect your business needs, and apply policies for these groups for governance. 

You have your root account, you then have your different organizational units (finance, developer, marketing, etc). Then you have AWS accounts
that will sit behind those organizational units. You can apply policies either directly to organizational units or to AWS accounts themselves.

## CloudFormation
helps you model and set up your AWS resources so you can spend less time managing and more time focusing on your applications that run in AWS

## CloudWatch
used for monitoring performance and it can monitor most of AWS as well as your apps that run on AWS.

## CloudTrail
 a service that enables governance, compliance, operational auditing, and risk auditing of your AWS account. With CloudTrail, you can log, continuously monitor, and retain account activity related to actions across your AWS infrastructure. CloudTrail provides an event history of your AWS account activity, including actions taken through the AWS Management.

## Config 
a service that enables you to assess, audit, and evaluate the configurations of your AWS resources. It can also continuously monitors and records your AWS resource configurations.

## Quick Start
a way of deploying environments quickly using CloudFormation templates built by AWS Solutions Architects who are experts in that particular technology. Quick Start is always on a per account basis.

## Landing Zone
a solution that helps customers set up a multi AWS account based on AWS best practices. Currently it will set you up with four different AWS accounts: organizations account, shared services account, log archive account, and security account.

---------

## WAF (Web Application Firewall)
designed to stop hackers. It operates at layer 7 (application layer).

## Shield 
designed to stop DDOS attacks. Shield is turned on by default, but if you want the Shild Advanced protection (intelligent DDoS attack detection and mitigation for not only for network layer (layer 3) and transport layer (layer 4) attacks, but also for application layer (layer 7) attacks) it's going to cost you $3,000 a month.

## GuardDuty 
a threat detection service that monitors malicious activity and unauthorized behavior to protect your AWS account. It's for account level access.

## Trusted Advisor 
an online tool that provides you real-time guidance to help you provision your resources following AWS best practices. 
Whether establishing new workflows, developing applications, or as part of ongoing improvement, recommendations provided by Trusted Advisor regularly help keep your solutions provisioned optimally.

## CloudHSM - Hardware Security Module
a cloud-based hardware security module (HSM) that enables you to easily generate and use your encryption keys on the AWS Cloud.
It's not just a security service, it actually inspects your whole AWS account, so not just EC2. And it does more than security checks, it also does Cost Optimization, Performance, and Fault Tolerance.

## Macie
a fully managed data security and data privacy service that uses machine learning and pattern matching to discover and protect your sensitive data in AWS. Macie helps identify and alert you to sensitive data, such as personally identifiable information (PII). This service is for securing data and has nothing to do with an EC2 security assessment.

## NACL vs Sercurity Group

A Security Group acts as a virtual firewall for your instance to control inbound and outbound traffic.

A Network Access Control List (NACL) is an optional layer of security for your VPC that acts as a firewall for controlling traffic in and out of one or more subnets (i.e. it works at subnet level).

## Shared Responsibility Model

![](shared-responsibility-model.png)

# Tags and Resource Groups

Tags consist of a bunch of different things, but essentially, they are key value pairs that are attached to AWS resources.
Resource groups make it easy to group your resources using the tags that are assigned to them. You can group resources which share one or more tags.
You can apply automation to resources tagged with specific tags, like stopping all EC2 instances in Stockholm Region.
When you combine Resource Groups with AWS Systems Manager you're allowed to control and execute automation against entire fleets of EC2 instances at the push of a button.
Tag Editor is a global service which allows us to discover resources and to add additional tags to them, and newer regions may take some time
to be compatible with the tag editor.

-----
Author Diogo Autilio - [Github](https://github.com/dogo)
