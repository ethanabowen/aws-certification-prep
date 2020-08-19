#### Domains of the test
Domain 1: Cloud Concepts
  * Define the AWS Cloud and its value proposition
  * Identify aspects of AWS Cloud economics
  * List the different cloud architecture design principles
  
Domain 2: Security and Compliance
  * Define the AWS shared responsibility model
  * Define AWS Cloud security and compliance concepts
  * Identify AWS access management capabilities
  * Identify resources for security support
  
Domain 3: Technology
  * Define methods of deploying and operating in the AWS Cloud
  * Define the AWS global infrastructure
  * Identify the core AWS services
  * Identify resources for technology support
  
Domain 4: Billing and Pricing
  * Compare and contrast the various pricing models for AWS
  * Recognize the various account structures in relation to AWS billing and pricing
  * Identify resources available for billing support

On exam day:
We recommend logging into your account 30 minutes early to start the check-in process and to allow for any troubleshooting. If you are more than 15 minutes late after your scheduled exam time you will be unable to begin your exam and are unlikely to receive a refund.
To log into your account:

Log in to your AWS Certification Account
On the homepage, click ‘Manage Pearson VUE Exams’, you are taken to the Pearson VUE dashboard
Click on your scheduled exam under 'Purchased Online Exams'
Click “Begin Exam” and follow the on-screen prompts to complete the check-in process
Once you have completed the check-in process you will be contacted by a Proctor to begin your exam

# <u>Cloud Foundations</u>
##### As A Service
* **IaaS** - Managed Physical Hardware and Hypervisor (software that runs the OS).  etc EC2
* **PaaS** - Managed Physical Hardware, Hypervisor, and  OS/Runtime.  etc Elastic Beanstalk
* **SaaS** - Everything is managed by the provider, only consuming software

##### Cloud Deployment Models
* Private Cloud - dedicated infrastructure and data center.  Ex.) VMware, Microsoft, Redhat, OpenStack
* Public Cloud - Hosted and delivered from a 3rd-party (typically over the internet).  Ex.) AWS, Microsoft Azure, Google Cloud Platform
    * Variable expense, instead of capital expense
    * Economies of scale - savings on large scale projects
    * Massive elasticity - grow to any size
* Hybrid Cloud - A mix of public and private clouds
  * Keeps critical sensitive applications/data in house while non-critical applications/data can be put in the public cloud
* Multicloud - Two or more clouds 

##### Legacy IT
* Large upfront cost for infrastrucure
* Operations within the organization is an big expensive
* Operations costs don't go down as the company scales down

##### Size advantages of cloud computing
| # | Name | Description
|---|---|---|
| 1 | Trade **capital expense** for **variable expense** | Instead of investing in data centers before you know how you're going to user them, pay only when, and for how much, you consume 
| 2 | Benefit from massive **economies of scale** | Achieve a **lower variable cost** due to AWS' **scale** |
| 3 | Stop guessing about capacity |Eliminate guessing, **scale as demand dictates** |
| 4 | Increate speed and agility | Easily and **quickly scale** your usage |
| 5 | **Stop spending money** running and maintaining data centers | **Focus on business growth** and innovation instead! |
| 6 | Go global in minutes | Easily **deploy applications in multiple regions **around the world |

### Amazon Web Services (History)
* 2002 - Launched internally
* 2003 - Vision casted for public offering
* 2004 - SQS public launch
* 2006 - Re-launch with S3, SQS, EC2
* 2010 - All amazon.com retail sites miratred to AWS
* 2015 - Sales $1.57 billion!
* 2018 - Revenue of $25 billion
* Today - Over 165+ services in Computing, Storage, Networking, Database, Analytics, Media services, ,chine Learning, Management, Mobile, IoT all in **22 Geographical regions** of presense

### AWS Global Infrastructure
|Name|Description|
|---|---|
|Region| A geographical area with **2 or AZs**, isolated from other AWS regions |
|Availability Zone (AZ)| One or more data centers that are **physically separate and isolated from other AZs**.  Each AZ is designed as an independary failure zone and use discrete power sources on seperate grids |
|Edge Location| A location with **cache of content that can be delivered at low latency** to users - used by CloudFront |
|Regional Edge Cache| Also part of the CloudFront network. These are **larger caches that sit between AWS services and Edge Locations** |
|Global Network| **Highly available, low-latency** private global network **interconnecting every data center, AZ, and AWS region** |


### AWS Services in Scope (for exam)
##### Legend: <span style="color:red">Red - Global Service </span> | White - Regional Service
  
* **AWS IAM -** <span style="color:red">Identity and Access Management</span>
* **AWS Compute** - EC2, EC2, Lambda, LightSail
* **AWS Storage** - <span style="color:red">S3</span>, EBS, EFS, Storage Gateway
* **AWS Networking** - VPC, <span style="color:red">Direct Connect</span>
* **Databases** - RDS, DynamoDB, Redshift, ElastiCache
* **Elastic Load Balancing and Auto Scaling** - Elastic Load Balancing, Auto Scaling
* **Content Delivery and DNS Services** - <span style="color:red">Route 53, CloudFront</span>
* **Monitoring and Logging Services** - CloudWatch, CloudTrail
* **Notification Services** - SNS
* **Migration and Transfer** - Database Migration Service, Server Migration Service, Snowball
* **Cloud Governance and Security** - GuardDuty, KMS, <span style="color:red">WAF & Shield</span>, CloudHSM, <span style="color:red">Artifact</span>, Inspector, <span style="color:red">Trusted Advisor</span>, AWS Config, AWS Service Catalog, <span style="color:red">Personal Health Dashboard</span>


## Three Fundamentals of AWS Pricing
* Compute - pay for virtual server + CPU cycles
* Storage - pay for the amount of data you have stored
* Outbound data - pay for the amount of data you pull out (charged at the outbound data transfer rate)

* On-demand
  * Used for Compute and Database capacity
  * No long-term commitments or upfront payments
* Dedicated Instances
  * Available for Amazon Ec2
  * Hardware is dedicated to a single customer
* Spot instances
  * Purchase spare capacity with no commitments
  * **Great discounts for hourly rates**
* Reservations
  * Up to 75% discounts (with 1 or 3 year term), No/Partial/All upfront cost options
  * Availabe for these services: EC2, DynamoDB, ElastiCache, RDS, RedShift

```code
AWS Acceptable User Policy - study it.
```


## <u>IAM</u>
**Authentication**
* Access key and Secret key combined provide programatic Access (CLI, SDK, etc)
  * MFA can be added on
  * These keys can be rotated, but the secret key is only available at the time of creation
  * Users CAN change their own keys **through IAM policy (not from the console)**
  * These keys can be disabled at any time by administrative means
* Tradiational sign in with user/pass in AWS Console
  * MFA can be added on.
  * Users can change their own passwords
  * The ability to give only selected users password changing abilities exists.  
    * First disable the password changing ability for all users via an IAM Policy.
    * Then grant the password changing ability to the selected users you wish to have it.
* Signing Certificate (not very often)
  * SSL/TLS certificate that can be used to authenticate with some AWS services.
  * AWS Certificate Manager (ACM) is recommended for provisioning, managing and deploying your server certificates
  * Use IAM when you must support HTTPS connections in a region that is not supported by ACM (less and less common)
  * 
**MFA (Multi-Factor Authentication)** - A combination of something you know (password, secret), have (phone, usb), or ARE (biometrics)

### Best Practices
* Lock away the AWS root user access keys
* Create individual IAM users, do not share amongst multiple persons
* Use AWS defined policies to assign permissions whenever possible
* User groups to assign permissions to IAM users, will help relieve the clutter of user -> policy assignments
* Least Privilege approach
* User access level to **review** IAM permissions
* Configure strong password policy for users
* Enable MFA for **ALL privileged** users
* **Use roles for applications that run on AWS EC2 instances**
  * Never put User/Pass/Keys into code [on EC2 instances]
* Use Roles over sharing credentials
* Rotate credentials regularly (this is hard to do in practice)
* Remove unnecessary credentials
* Use policy conditions for extra security (ex. certain computer coming from certain ip address)
* Monitor activity in your AWS account (tools to use later in the course)

## <u>STS (Security Token Service)</u>
* Allows for the abilit to request temporary, limit-privilege credentials for IAM users or for users that you authenticate (federated users)
* Global service https://sts.amazonaws.com
* All regions are eabled by default, but can be disabled
* The region in which temporary credentials are requested muist be enabled
* Credentials will **always work globally**

# AWS Compute

## <u>EC2 (Elastic Compute Cloud)</u>
Web Service providing secure, resizable compute capacity in the cloud

* IaaS (Infrastructure)
* Composed of CPU, RAM, Disk, NIC and OS (**Linux**/Windows/etc)
* Instance - Individual Virtual Server
  * AMI (Amazon Machine Image) - an **EBS (Elastic Blockstore Volume) Snapshot** (which has an OS installed on it)
  * Type - scale of resources (small, medium, large, xlarge, etc)
* Elasticity - increase or decrease capacity within minutes, commission 1-1000+ instacnes simultaneously
* Complete control (including root access) to each instance
  * No loss of data on start/stop
  * Ability to communicate to via API
* Flexible Hosting Services - preconfigued images based on configurable options (OS, hardware, storage, etc)
* Scale Vertically (CPU/Mem/HDD)
* Scale Horizontally (automatically) with Auto Scaling
* Used for Traditional Applications that from for long periods of time (month/years)
* Pay for instance run time based on family/type (resources allocated)
  
Instance data - Configuration data about your instances can be found and queried at http://169.254.169.254/latest/meta-data
User data - 16kb max of non-encrpyted user supplied data, commands run when the instances launchs

## <u>AMI (Amazon Machine Image)</u>
Provides the information required to launch an instance
* One or more EBS snapshots (a copy of an EBS volume)
* Permission settings associated with the launching the AMI
* A device mapping that specifies the volumes to attach to the instance when launched
  
Type:
* Community AMIs - free to use, typically just select the OS you want
* Marketplace AMIs - pay to use, usually somes with additional licensed software
* My AMIs - AMIs that you create yourself

[Instance Types](https://aws.amazon.com/ec2/instance-types/)


## <u>ECS (Elastic Container Service)</u>
* CaaS (Container)
* Provides a **highly scalable, high performance container management service** that **supports Docker container**
* Container - a virtual instance, OS is not apart of it
  * Contains Code, runtime, system tools/libraryies/settings
* Eliminates the need for own implementation of cluster management
* There are 2 launch types:
  |EC2|Fargate|
  |---|---|
  |Explicitly Provisioned Instances|(Control plane) **Resources are automatically provisioned**|
  |Responsible for upgrading and patching|Provisions compute as needed|
  |**Manually** handle cluster optimization|**Automatically** handles cluster   optimization|
  |**More granular control over infreatructure**|**Limited control, as infrastructure is automated**|
  |Best for microservice and batch use cases where you need containers and have the need to maintain the underlying platform|Same, but best is there is no need for maintaining an underlying platform|
  |Pay for instance run time based on family/type|Pay for container run time based on allocated resources|

## <u>Lambda</u>
* FaaS (Function)
* Serverless, allowing you to run code without provisioning or managing servers
* Typically executed off of a trigger.  Ex. API call, scheduled run, another lambda?, etc
* Pay only for compute time, this is the big payoff of serverless
* Benefits of Lambda:
  * No servers to manage
  * Continuous scaling
  * Subsecond metering
  * Integrates with almost all other AWS services
* Primary user cases:
  * Data processing
  * Real-time file/stream processing
  * Building a serverless backend for web, mobile, IOT, and 3rd party API requests
* Auto Scaling up to 1000 (default limit) concurrent executions
* Best use cases - ETL, infrastructure automation, data validation, mobile backends
* Pay only for execution time based on memory allocation

## <u> LightSail </u>
* Best for users who do not have deep AWS technical expertise
* Makes it very easy to provision computer services
* Basically it bundles compute into simple use-cases for a 'low barrier to entry'


# AWS Storage

### Storage System types
* Object Storage (S3)
  * Manage data as individual objcts, rather than as blocks and sectors (block-based) or a file hierarchy (file-based)
  * Accessed via REST API (GET, PUT, POST, DELETE, etc)
  * Each object contains the data itself, metadata, and a **globally unique identifier** (this is a constraint of S3)
  * Virtually unlimited scalability to due flat file structure
* Block Storage (EBS - Elastic Block Storage)
  * Manage data in blocks within sectors and tracks and is controller by a server-based operating system
  * Appears as local disks to the OS and can be partitioned and formatted
  * **You can use block storage devices as a boot volume**
  * Use Cases - Structured information such as a file system, databases, transactional logs, SQL databases and virtual machines (VMs)
  * EC2 attached to EBS which has the OS that it runs and it's connected over a network
* File Storage
  * Manage data in file structures (hierarchy)
  * Mounted via the network to a client computer where it then becomes accessible for reading and writing data
  * Protocols used for accessing file systems include NFS or (Microsoft) CIFS/SMB


# <u>S3 (Simple Storage Service)</u>
* Object storage system built to store and retrieve any amount of data from anywhere
* Public service - everyone connects to it over the public internet
  * Edge case - S3 Gateway Endpoint can allow for an EC2 instance to connect to S3 without going to through Public Internet 
* Any type of file supported
* S3 is designed to deliver 99.99999999999 (11) durability
* Use Cases
  * Backup and Storage
  * Application Hosting - deploy, install, and manage web applications
  * Media Hosting - upload/download style service of any type of media
  * Software Delivery - customer download portal for your applications
  * Static Website - run static page straight from an S3 bucket!
* Buckets are root level folders
* Files are stored in buckets with a 5TB limit per file
* Unlimited storage - charged for storage
* **S3 is a universal namespace** so bucket names must be unique globally
* However, you **create your buckets within a REGION**
* It is a best practice to create buckets in regions that are physically closest to your user's to reduce latency
* Objects consist of:
  * Key - name of the object
  * Value - data made up of a sequence of bytes)
  * Version ID - changes on each upload?
  * Metadata - information relating to the data that is stored
* Pricing:
  * Storage - pay for what you put in
  * Requests - Retrieve data
  * Storage Management
  * Data transfer
  * Transfer acceleration - way to accelerate the upload of data to S3

Storage Class
* **Standard** - durable, immediately available, **frequency accessed**
* **Intelligent-Tiering** - automatically moves data to the most cost-effective tier
* **Standard-IA** - durable, immediately available, **infrequency accessed**
* **One Zone-IA** - lower cost for infrequently accessed data with LESS resilience (99.5%, due to non-replicated data accross multiple availability zones)
* **Glacier** - archieve data, retrieval times in minutes or hours
* **Glacier Deep Archive** - lowest cost storage class for long term retention

|S3 Capability|How it works|
|---|---|
|Transfer Acceleration| Speed up data uploads using CloudFront in reverse|
|Requester Pays|The requester rather than the bucket owner pays for requests and data transfer|
|Tags|Assign taghs to objects to use in costing, billing, security, etc|
|Events|Trigger notifications to SNS, SQS, or Lanbda when certain events happen in your bucket|
|Static Web Hosting|Simple and massively scalable static website hosting|
|BitTorrent|Use the BitTorrent protocol to retrieve any publicly available object by automatically generating a .torrent file|

Versioning - sounds like what it is, if Versioning is suspended, it prevents NEW VERSIONS from being uploaded, all uploads will be under the latest version.  Deleting the object creates a new version.

CRR - Cross-Region Replication
  * Source and destinations must have versioning enabled
  * Can be the same or different account
SRR - Same-Region Replications
  * same as CRR, just in the same region

Why replication?
  * Compliance requirements
  * Backups into another region
  * Copy to another region for closer access for users
  * Copy into a new storage tier


# <u>EBS (Elastic Block Store)</u>
* Provides persistence block storage, even if associated (EC2) instance is detacted and terminated
* Replicated within its AZ
* No need for an EBS to be attached an instance, can be zombied with no problem
* 1:M -> EC2 Instance:EBS Volumes
* * Multiple EBS volumes can be attached to the same instance
  * Can not attach EBS volum to multiple instances (use EFlastic File Store instead)
* EBS is AZ contrained, meaning the instance has to be in the same AZ
* **Termination protection is OFF by default** and must be manually enabled (keeps the volume/data when teh instance is terminated)
  * Root EBS volumes are deleted on termination by default
  * Extra non-boot volumes are not deleted on termination by default
* **SSD is the default boot type for EC2 instances**

### EBS Volume Info:
|Type|Description|Use Cases|Size|MAX IOPS/ Volume|Max Throughout/ Volume|
|---|---|---|---|---|---|
|EBS Provisioned IOPS SSD (io1)|**Highest Performance** designed for latency-sensitive transactional workloads|I/O-Intensive NoSQL and relational databases|4GB-16TB|64,000|1,000MB/s|
|EBS General Purpose SSD (gp2)|General Purpose, balances price performance for a wide variety of transactional worklaods|Boot volumes, low-latency, interactive apps, dev & test|1GB-16TB|16,000|250MB/s|
|Throughput Optimized HDD (st1)|Low cost, designed for frequently accessed, throughput intensive workloads|Big data, data warehouses, log processing|500GB-16TB|500|500MB/s|
|Cold HDD (sc1)|**Lowest Cost** designed for less frequently accessed workloads|Colder data requiring fewer scans per day|500GB-16TB|250|250MB/s

### EBS Snapshot
* Point-In-Time state backup of EBS Volume
* Stored as object in S3
* **Each new snapshot is a delta (incremental) of the previous**
  * Only the latest is needed to restore the volume, which is CRAZY COOL!
* Snapshots can only be access through the EC2 APIs
* EBS volumes are AZ specific, but snapshots are region specific
  * An EBS Snapshot is a way to migrate your EBS Volume to another AZ in the created region.  The flow for that is Existing Volume -> Snapshot (S3) -> Create AMI from Snapshot -> Launch new EC2 Instance pointing to new AMI

### Instance Store Volume
* Physically attached to the Server the EC2 instance is running on
* When the EC2 instance is shutdown/terminated, the Instance Store Volume is not persisted (Ephemeral)
* High Performance local disks
* Good for temp dat - buffer, cache, sratch data, etc.
* ISV root devices are created from AMI templates stored on S3
* ISV cannot be detached/reattached

# <u>EFS (Elastic File System)</u>
* **Network based**, scalable file storage system, mounted as a file system
* NFS Format - Network File System Format (v4.1 protocol)
* **Multiple EC2 Instances can connect to the same File System**
* On-prem solution compliant
* **Linux ONLY**
* Use Cases
  * Big Data and Analytics
  * Media processing Workflows
  * Content Management
  * Web Serving
  * Home Directories
* **Data is stored across multiple AZ's within a region**
* Read after write consistency (Opposite of Eventual Consistency)
* Pay for what you user
* On-premises access can be enabled via Direct Connect or AWS VPN
* After a EFS is attached to an instance, the EFS needs to be mounted via CLI (or attached through console at creation, maybe can be updated in console as well)

# <u>Storage Gateway</u>
* Hybrid cloud storage service that gives you **on-premises access to virtually unlimited cloud storage**
* Seamlessly connects on-premises applications to cloud storage, **caching data locally for low-latency access**
* Types of Gateway:
  * Tape - virtual tape library
  * File Gateway - accessed using SMB (Microsoft), NFS or S3 API protocols
  * Volume Gateway - block device access using iSCSI (look into)


# AWS VPC (Virtual Private Cloud)
A VPC is a logically isolated (your AWS account only) portion of the AWS cloud within a region.
* A VPC spans all the AZs in the region and exist by default (Subnets as well)
  * 5 per region max
* A VPC has a different address block called a **different CIDR (Classless InterDomain Routing) block**, a list of addresses that VPC can use
* A Subnet is a subset of those VPC addresses
  * Has a block of IP addresses from the VPC CIDR block
  * Subnets are created within AZs
  * Each 
* All traffic in and out of the VPC goes through the Internet Gateway, which uses a Router (that references the 'Main Route Table')
* A VPC provides complete control over the virtual networking environment including selection of IP ranges, creation of subnets, and configuration of route tables and gateways
* When you create a VPC, you must specify a range of IPv4 addresses for the VPC in the form of a CIDR block, for examples 10.0.0.0/16
 * You have full control over who has access to the AWS resources inside your VPC

How to securely connect?
* AWS Managed VPN - fast to setup
  * Encrypted VPN connection between external customer gateway to owned VPN gateway
  * Not guaranteed on performance
* AWS Direct Connect - high bandwidth, low-latency but takes weeks to months to setup
  * On-prem and Cloud connection, typically creates a hybrid cloud
  * Network service that provides an alternative to useing the internet to connect a customer's on premise sites to AWS
  * The connection is private
  * Charged by port hours and data transfer, Available in 1Gbps and 10Gbps or through AWS Direct Connect Partners
  * Guaranteed performance
* VPN Cloud Hub - used for connection multile sites to AWS
* Software VPN - use  3rd party software
  
## ACL (Access Control Lists)
* Subnet level firewall that controls inbound and outbound traffic
* Allow and deny rule (White and Black lists)
* Stateless, checks rules sequencially until all pass or single fail 
  
## Security Group
* Instance level firewall that controls inbound and outbound internet traffic permissions on a GROUP of resources
* Can be used in multiple subnets, because it's just traffic rules
* Allow rules only (White list)
* Stateful, checkes all rules on each request

## NAT Gateway  (Network Address Translation)
* Translations public ips to private ips
* VPC associated
* Used by uUpdating route table so that private subnet route table goes to NAT Gateway id
* Managed by AWS

## Nat Instance
* EC2 Instance from a specific AMI
* Same functionality of a NAT Gateway
* Managed by you
* Can use as a bastion host, a way to get to the private subnet via this ec2 instance.  Typically for 'management/devops reasons'

## Transit Gateway
* Connects VPCs and on-premises networks through a central hub
* Simplifies networks and puts an end to complex peering relationships
  * Peering relationships are not transitive between VPCs
* Acts as a CLOUD ROUTER
* Inter-Region peering connects AWS Transit Gateways together using the AWS global network (AWS's private internet)
* Data is automatically encrypted and never tranels over a public network