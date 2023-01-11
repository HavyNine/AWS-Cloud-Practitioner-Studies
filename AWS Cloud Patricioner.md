# AWS Cloud Patricioner GIT


# IAM Section

- **Summary**
    - Users: mapped to a physical user, has a password for AWS Console
    - Groups: contains users only
    - Policies: json document that outlines permissions for users or groups
    - Roles: for EC@ instances or AWS services
    - Security: MFA + password policy
    - AWS CLI: manage your AWS services using the command-line
    - AWS-SDK: manage your AWS services using a programming language
    - Access Keys: access AWS using the CLI or SDK
    - Audit: IAM Credentials Reports & IAM Access Advisor

# EC2 (Elastic Compute Cloud)

- **Section - Summary**
    - EC2 Instance: AMI (OS) + Instance Size (CPU + RAM) + Storage  + security groups + EC2 User Data
    - Security Groups: Firewall attached to the EC2 instance
    - EC2 User Data: Script launched at the first of an instance
    - SSH: start a terminal into our EC2 Instances (port 22)
    - EC2 Instance Role: link to IAM roles
    - Purchasing Options: On-Demand, Spot, Reserved (Standard + Convertible + Scheduled), Dedicated Host, Dedicated Instance

# EC2 Instance Storage Section

- **EC2 Instance Storage - Summary**
    - **EBS volumes:**
        
        • network drives attached to one EC2 instance at a time 
        
        • Mapped to an Availability Zones 
        
        • Can use EBS Snapshots for backups / transferring EBS volumes across AZ 
        
    - **AMI**: create ready-to-use EC2 instances with our customizations
    - **EC2 Image Builder:** automatically build, test and distribute AMIs
    - **EC2 Instance Store**:
        - High performance hardware disk attached to our EC2 instance
        - Lost if our instance is stopped / terminated
    - **EFS**: network file system, can be attached to 100s of instances in a region
    - **EFS-IA**: cost-optimized storage class for infrequent accessed files
    - **FSx for Windows:** Network File System for Windows servers
    - **FSx for Lustre**: High Performance Computing Linux file system

# Elastic Load Balancing & Auto Scaling Groups Section

- **ELB & ASG – Summary**
    - **High Availability** vs **Scalability** (vertical and horizontal) vs **Elasticity** vs
    **Agility** in the Cloud
    - **Elastic Load Balancers (ELB)**
        - Distribute traffic across backend EC2 instances, can be Multi-AZ
        - Supports health checks
        - 3 types: Application LB (HTTP – L7), Network LB (TCP – L4), Classic LB (old)
    - Auto Scaling Groups (ASG)
        - Implement Elasticity for your application, across multiple AZ
        - Scale EC2 instances based on the demand on your system, replace unhealthy
        - Integrated with the ELB

# **Amazon S3 Section**

- **Amazon S3 – Summary**
    - **Buckets vs Objects**: global unique name, tied to a region
    - **S3 security**: IAM policy, S3 Bucket Policy (public access), S3 Encryption
    - **S3 Websites**: host a static website on Amazon S3
    - **S3 Versioning**: multiple versions for files, prevent accidental deletes
    - **S3 Replication**: same-region or cross-region, must enable versioning
    - **S3 Storage Classes**: Standard, IA, 1Z-IA, Intelligent, Glacier (Instant, Flexible, Deep)
    - **Snow Family**: import data onto S3 through a physical device, edge computing
    - **OpsHub**: desktop application to manage Snow Family devices
    - **Storage Gateway**: hybrid solution to extend on-premises storage to S3

# **Databases Section**

- **Databases & Analytics Summary in AWS**
    - **Relational Databases - OLTP**: RDS & Aurora (SQL)
    - **Differences between Multi-AZ, Read Replicas, Multi-Region**
    - **In-memory Database**: ElastiCache
    - **Key/Value Database**: DynamoDB (serverless) & DAX (cache for DynamoDB)
    - **Warehouse** - OLAP: Redshift (SQL)
    - **Hadoop Cluster**: EMR
    - **Athena**: query data on Amazon S3 (serverless & SQL)
    - **QuickSight**: dashboards on your data (serverless)
    - **DocumentDB**: “Aurora for MongoDB” (JSON – NoSQL database)
    - **Amazon QLDB**: Financial Transactions Ledger (immutable journal, cryptographically verifiable)
    - **Amazon Managed Blockchain**: managed Hyperledger Fabric & Ethereum blockchains
    - **Glue**: Managed ETL (Extract Transform Load) and Data Catalog service
    - **Database Migration**: DMS
    - **Neptune**: graph database
- **Databases & Shared Responsibility on AWS**
    - AWS offers use to manage different databases
    - Benefits include:
        - Quick Provisioning, High Availability, Vertical and Horizontal Scaling
        - Automated Backup & Restore, Operations, Upgrades
        - Operating System Patching is handled by AWS
        - Monitoring, alerting
    - Note: many databases technologies could be run on EC2, but you must handle yourself the resiliency, backup, patching, high vailability, fault tolerance, scaling…

# Other Compute Section

- **Other Compute - Summary**
    - **Docker**: container technology to run applications
    - **ECS**: run Docker containers on EC2 instances
    - **Fargate**:
        - Run Docker containers without provisioning the infrastructure
        - Serverless offering (no EC2 instances)
    - **ECR**: Private Docker Images Repository
    - **Batch**: run batch jobs on AWS across managed EC2 instances
    - **Lightsail**: predictable & low pricing for simple application & DB stacks
- **Lambda Summary**
    - Lambda is Serverless, Function as a Service, seamless scaling, reactive
    - **Lambda Billing**:
        - By the time run x by the RAM provisioned
        - By the number of invocations
    - **Language Support**: many programming languages except (arbitrary) Docker
    - **Invocation time**: up to 15 minutes
    - **Use cases**:
        - Create Thumbnails for images uploaded onto S3
        - Run a Serverless cron job
    - **API Gateway**: expose Lambda functions as HTTP API

# Deploying and Managing Infrastructure at Scale Section

- **Deployment - Summary**
    - CloudFormation: (AWS only)
        - Infrastructure as Code, works with almost all of AWS resources
        - Repeat across Regions & Accounts
    - Beanstalk: (AWS only)
        - Platform as a Service (PaaS), limited to certain programming languages or Docker
        - Deploy code consistently with a known architecture: ex, ALB + EC2 + RDS
    - CodeDeploy (hybrid): deploy & upgrade any application onto servers
    - Systems Manager (hybrid): patch, configure and run commands at scale
    - OpsWorks (hybrid): managed Chef and Puppet in AWS
- **Developer Services - Summary**
    - CodeCommit: Store code in private git repository (version controlled)
    - CodeBuild: Build & test code in AWS
    - CodeDeploy: Deploy code onto servers
    - CodePipeline: Orchestration of pipeline (from code to build to deploy)
    - CodeArtifact: Store software packages / dependencies on AWS
    - CodeStar: Unified view for allowing developers to do CICD and code
    - Cloud9: Cloud IDE (Integrated Development Environment) with collab
    - AWS CDK: Define your cloud infrastructure using a programming language

# Global Infrastructure Section

- **Global Applications in AWS - Summary**
    - **Global DNS: Route 53**
    • Great to route users to the closest deployment with least latency
    • Great for disaster recovery strategies
    - **Global Content Delivery Network (CDN): CloudFront**
    • Replicate part of your application to AWS Edge Locations – decrease latency
    • Cache common requests – improved user experience and decreased latency
    - **S3 Transfer Acceleration**
    • Accelerate global uploads & downloads into Amazon S3
    - **AWS Global Accelerator:**
    • Improve global application availability and performance using the AWS global network
- **Global Applications in AWS - Summary**
    - **AWS Outposts**
        - Deploy Outposts Racks in your own Data Centers to extend AWS services
    - **AWS WaveLength**
        - Brings AWS services to the edge of the 5G networks
        - Ultra-low latency applications
    - **AWS Local Zones**
        - Bring AWS resources (compute, database, storage, …) closer to your users
        - Good for latency-sensitive applications

# Cloud Integration Section

- **Integration Section – Summary**
    - **SQS**:
    • Queue service in AWS
    • Multiple Producers, messages are kept up to 14 days
    • Multiple Consumers share the read and delete messages when done
    • Used to **decouple** applications in AWS
    
    - **SNS**:
    • Notification service in AWS
    • Subscribers: Email, Lambda, SQS, HTTP, Mobile…
    • Multiple Subscribers, send all messages to all of them
    • No message retention
    
    - **Kinesis**: real-time data streaming, persistence and analysis
    
    - **Amazon MQ**: managed message broker for ActiveMQ and RabbitMQ in the cloud (MQTT, AMQP.. protocols)

# Cloud Monitoring Section

- **Monitoring Summary**
    - **CloudWatch**:
    • **Metrics**: monitor the performance of AWS services and billing metrics
    • **Alarms**: automate notification, perform EC2 action, notify to SNS based on metric
    • **Logs**: collect log files from EC2 instances, servers, Lambda functions…
    • **Events (or EventBridge)**: react to events in AWS, or trigger a rule on a schedule
    - **CloudTrail**: audit API calls made within your AWS account
    - **CloudTrail** **Insights**: automated analysis of your CloudTrail Events
    - **X-Ray**: trace requests made through your distributed applications
    - **Service Health Dashboard**: status of all AWS services across all regions
    - **Personal Health Dashboard**: AWS events that impact your infrastructure
    - **Amazon CodeGuru**: automated code reviews and application performance recommendations

# VPC Section

- **VPC - Summary**
    - VPC Endpoints: Provide private access to AWS Services within VPC
    - PrivateLink: Privately connect to a service in a 3rd party VPC
    - VPC Flow Logs: network traffic logs
    - Site to Site VPN: VPN over public internet between on-premises DC and AWS
    - Client VPN: OpenVPN connection from your computer into your VPC
    - Direct Connect: direct private connection to AWS
    - Transit Gateway: Connect thousands of VPC and on-premises networks together

# Security & Compliance Section

- **Section Summary: Security & Compliance**
    - **Shared Responsibility on AWS**
    - **Shield**: Automatic DDoS Protection + 24/7 support for advanced
    - **WAF**: Firewall to filter incoming requests based on rules
    - **KMS**: Encryption keys managed by AWS
    - **CloudHSM**: Hardware encryption, we manage encryption keys
    - **AWS Certificate Manager**: provision, manage, and deploy SSL/TLS Certificates
    - **Artifact**: Get access to compliance reports such as PCI, ISO, etc…
    - **GuardDuty**: Find malicious behavior with VPC, DNS & CloudTrail Logs
    - **Inspector**: For EC2 only, install agent and find vulnerabilities
    - **Config**: Track config changes and compliance against rules
    - **Macie**: Find sensitive data (ex: PII data) in Amazon S3 buckets
    - **CloudTrail**: Track API calls made by users within account
    - **AWS Security Hub**: gather security findings from multiple AWS accounts
    - **Amazon Detective**: find the root cause of security issues or suspicious activities
    - **AWS Abuse**: Report AWS resources used for abusive or illegal purposes
    - **Root user privileges**:
        - Change account settings
        - Close your AWS account
        - Change or cancel your AWS Support plan
        - Register as a seller in the Reserved Instance Marketplace

# Machine Learning Section

- **AWS Machine Learning - Summary**
    - Rekognition: face detection, labeling, celebrity recognition
    - Transcribe: audio to text (ex: subtitles)
    - Polly: text to audio
    - Translate: translations
    - Lex: build conversational bots – chatbots
    - Connect: cloud contact center
    - Comprehend: natural language processing
    - SageMaker: machine learning for every developer and data scientist
    - Forecast: build highly accurate forecasts
    - Kendra: ML-powered search engine
    - Personalize: real-time personalized recommendations
    - Textract: detect text and data in documents

# Account Management, Billing & Support Section

- **Account Best Practices – Summary**
    - Account Best Practices – Summary
    - Operate multiple accounts using Organizations
    - Use SCP (service control policies) to restrict account power
    - Easily setup multiple accounts with best-practices with AWS Control Tower
    - Use Tags & Cost Allocation Tags for easy management & billing
    - IAM guidelines: MFA, least-privilege, password policy, password rotation
    - Config to record all resources configurations & compliance over time
    - CloudFormation to deploy stacks across accounts and regions
    - Trusted Advisor to get insights, Support Plan adapted to your needs
    - Send Service Logs and Access Logs to S3 or CloudWatch Logs
    - CloudTrail to record API calls made within your account
    - If your Account is compromised: change the root password, delete and rotate all passwords / keys, contact the AWS support
- **Billing and Costing Tools – Summary**
    - **Compute Optimizer:** recommends resources’ configurations to reduce cost
    - **Pricing Calculator**: cost of services on AWS
    - **Billing Dashboard**: high level overview + free tier dashboard
    - **Cost Allocation Tags**: tag resources to create detailed reports
    - **Cost and Usage Reports**: most comprehensive billing dataset
    - **Cost Explorer**:View current usage (detailed) and forecast usage
    - **Billing Alarms**: in us-east-1 – track overall and per-service billing
    - **Budgets**: more advanced – track usage, costs, RI, and get alerts
    - **Savings Plans**: easy way to save based on long-term usage of AWS

# Advanced Identity Section

- Advanced Identity - Summary
    - **IAM**
        - Identity and Access Management inside your AWS account
        - For users that you trust and belong to your company
    - **Organizations** – manage multiple AWS accounts
    - **Security Token Service (STS)** – temporary, limited-privileges credentials to
    access AWS resources
    - **Cognito** – create a database of users for your mobile & web applications
    - **Directory Services** – integrate Microsoft Active Directory in AWS
    - **IAM Identity Center** – one login for multiple AWS accounts & applications

# Other AWS Services

- Amazon WorkSpaces
    - Managed Desktop as a Service (DaaS) solution to easily provision Windows or Linux desktops
    - Great to eliminate management of on-premise VDI (Virtual Desktop Infrastructure)
    - Fast and quickly scalable to thousands of users
    - Secured data – integrates with KMS
    - Pay-as-you-go service with monthly or hourly rates
- Amazon AppStream 2.0
    - Desktop Application Streaming Service
    - Deliver to any computer, without acquiring, provisioning infrastructure
    - The application is delivered from within a web browser
- Amazon AppStream 2.0 vs WorkSpaces
    - **Workspaces**
    • Fully managed VDI and desktop available
    • The users connect to the VDI and open native or WAM applications
    • Workspaces are on-demand or always on
    - **AppStream 2.0**
    • Stream a desktop application to web browsers (no need to connect to a VDI)
    • Works with any device (that has a web browser)
    • Allow to configure an instance type per application type (CPU, RAM, GPU)
- Amazon Sumerian
    - Create and run virtual reality (VR), augmented reality (AR), and 3D applications
    - Can be used to quickly create 3D models with animations
    - Ready-to-use templates and assets - no programming or 3D expertise required
    - Accessible via a web-browser URLs or on popular hardware for AR/VR
- AWS IoT Core
    - IoT stands for “Internet of Things”
    – the network of internet-connected devices that are able to collect and transfer data
    - AWS IoT Core allows you to easily connect IoT devices to the AWS Cloud • Serverless, secure & scalable to billions of devices and trillions of messages
    - Your applications can communicate with your devices even when they aren’t connected
    - Integrates with a lot of AWS services
    (Lambda, S3, SageMaker, etc.)
    - Build IoT applications that gather, process, analyze, and act on data
- Amazon Elastic Transcoder
    - Elastic Transcoder is used to convert media files stored in S3 into media
    files in the formats required by consumer playback devices (phones etc..)
    - Benefits:
    • Easy to use
    • Highly scalable – can handle large volumes of media files and large file sizes
    • Cost effective – duration-based pricing model
    • Fully managed & secure, pay for what you use
- AWS AppSync
    - Store and sync data across mobile and web apps in real-time
    - Makes use of GraphQL (mobile technology from Facebook)
    - Client Code can be generated automatically
    - Integrations with DynamoDB / Lambda
    - Real-time subscriptions
    - Offline data synchronization (replaces Cognito Sync)
    - Fine Grained Security
    - AWS Amplify can leverage AWS AppSync in the background!
- AWS Amplify
    - A set of tools and services that helps you develop and deploy scalable full stack web and mobile applications
    - Authentication, Storage, API (REST, GraphQL), CI/CD, PubSub, Analytics,
    AI/ML Predictions, Monitoring, Source Code from AWS, GitHub, etc…
- AWS Device Farm
    - Fully-managed service that tests your web and mobile apps against desktop browsers, real mobile devices, and tablets
    - Run tests concurrently on multiple devices (speed up execution)
    - Ability to configure device settings (GPS, language, Wi-Fi, Bluetooth, …)
- AWS Backup
    - Fully-managed service to centrally manage and automate backups across AWS services
    - On-demand and scheduled backups
    - Supports PITR (Point-in-time Recovery)
    - Retention Periods, Lifecycle Management, Backup Policies, …
    - Cross-Region Backup
    - Cross-Account Backup (using AWS Organizations)
- AWS Elastic Disaster Recovery (DRS)
    - Used to be named “CloudEndure Disaster Recovery”
    - Quickly and easily recover your physical, virtual, and cloud-based servers into AWS
    - Example: protect your most critical databases (including Oracle, MySQL, and SQL Server),enterprise apps (SAP), protect your data from ransomware attacks, …
    - Continuous block-level replication for your servers
- AWS DataSync
    - Move large amount of data from on-premises to AWS
    - Can synchronize to: Amazon S3 (any storage classes – including Glacier), Amazon EFS, Amazon FSx for Windows
    - Replication tasks can be scheduled hourly, daily, weekly
    - The replication tasks are incremental after the first full load
- AWS Application Discovery Service
    - Plan migration projects by gathering information about on-premises data centers
    - Server utilization data and dependency mapping are important for migrations
    - Agentless Discovery (AWS Agentless Discovery Connector)
    - VM inventory, configuration, and performance history such as CPU, memory, and disk usage
    - Agent-based Discovery (AWS Application Discovery Agent)
    - System configuration, system performance, running processes, and details of the network connections between systems
    - Resulting data can be viewed within AWS Migration Hub
- AWS Application Migration Service (MGN)
    - The “AWS evolution” of CloudEndure Migration, replacing AWS Server Migration Service (SMS)
    - Lift-and-shift (rehost) solution which simplify migrating applications to AWS
    - Converts your physical, virtual, and cloud-based servers to run natively on AWS
    - Supports wide range of platforms, Operating Systems, and databases
    - Minimal downtime, reduced costs
- AWS Fault Injection Simulator (FIS)
    - A fully managed service for running fault injection experiments on AWS workloads
    - Based on Chaos Engineering – stressing an application by creating disruptive events (e.g., sudden increase in CPU or memory), observing how the system responds, and
    implementing improvements
    - Helps you uncover hidden bugs and performance bottlenecks
    - Supports the following AWS services: EC2, ECS, EKS, RDS…
    - Use pre-built templates that generate the desired disruptions
- AWS Step Functions
    - Build serverless visual workflow to
    orchestrate your Lambda functions
    - Features: sequence, parallel, conditions,
    timeouts, error handling, …
    - Can integrate with EC2, ECS, On-premises
    servers, API Gateway, SQS queues, etc…
    - Possibility of implementing human approval
    feature
    - Use cases: order fulfillment, data processing,web applications, any workflow
- AWS Ground Station
    - Fully managed service that lets you control sattelite communications, process data, and scale your satellite operations
    - Provides a global network of satellite
    ground stations near AWS regions
    - Allows you to download satellite data to
    your AWS VPC within seconds
    - Send satellite data to S3 or EC2 instance
    - Use cases: weather forecasting, surface
    imaging, communications, video broadcasts
- Amazon Pinpoint
    - Scalable 2-way (outbound/inbound) marketing communications service
    - Supports email, SMS, push, voice, and in-app messaging
    - Ability to segment and personalize messages with the right content to customers
    - Possibility to receive replies
    - Scales to billions of messages per day
    - Use cases: run campaigns by sending marketing, bulk, transactional SMS messages
    - Versus Amazon SNS or Amazon SES
    • In SNS & SES you managed each message's audience,
    content, and delivery schedule
    • In Amazon Pinpoint, you create message templates,
    delivery sched

# AWS Architecting & Ecosystem Section

- Well Architected Framework General Guiding Principles
    - Stop guessing your capacity needs
    - Test systems at production scale
    - Automate to make architectural experimentation easier
    - Allow for evolutionary architectures
    - Design based on changing requirements
    - Drive architectures using data
    - Improve through game days
        - Simulate applications for flash sale days
- AWS Cloud Best Practices – Design Principles
    - **Scalability**: vertical & horizontal
    - **Disposable** Resources: servers should be disposable & easily configured
    - **Automation**: Serverless, Infrastructure as a Service, Auto Scaling…
    - **Loose Coupling**:
        - Monolith are applications that do more and more over time, become bigger
        - Break it down into smaller, loosely coupled components
        - A change or a failure in one component should not cascade to other components
    - **Services, not Servers**:
        - Don’t use just EC2
        - Use managed services, databases, serverless, etc !
- Well Architected Framework 6 Pillars
    
    OPSRPCS
    
    - 1) Operational Excellence
    - 2) Security
    - 3) Reliability
    - 4) Performance Efficiency
    - 5) Cost Optimization
    - 6) Sustainability
    - They are not something to balance, or trade-offs, they’re a synergy
- 1) Operational Excellence
    - Includes the ability to run and monitor systems to deliver business value and to continually improve supporting processes and procedures
    - Design Principles
    • Perform operations as code - Infrastructure as code
    • Annotate documentation - Automate the creation of annotated documentation
    after every build
    • Make frequent, small, reversible changes - So that in case of any failure, you can
    reverse it
    • Refine operations procedures frequently - And ensure that team members are
    familiar with it
    • Anticipate failure
    • Learn from all operational failures
- 2) Security
    - Includes the ability to protect information, systems, and assets while delivering business value through risk assessments and mitigation strategies
    - Design Principles
    • Implement a strong identity foundation - Centralize privilege management and reduce (or even eliminate) reliance on long-term credentials - Principle of least privilege - IAM
    • Enable traceability - Integrate logs and metrics with systems to automatically respond and take action
    • Apply security at all layers - Like edge network, VPC, subnet, load balancer, every instance, operating system, and application
    • Automate security best practices
    • Protect data in transit and at rest - Encryption, tokenization, and access control
    • Keep people away from data - Reduce or eliminate the need for direct access or manual
    processing of data
    • Prepare for security events - Run incident response simulations and use tools with automation to increase your speed for detection, investigation, and recovery
    • Shared Responsibility Model
- 3) Reliability
    - Ability of a system to recover from infrastructure or service disruptions,
    dynamically acquire computing resources to meet demand, and mitigate disruptions such as misconfigurations or transient network issues
    - Design Principles
    • Test recovery procedures - Use automation to simulate different failures or to recreate
    scenarios that led to failures before
    • Automatically recover from failure - Anticipate and remediate failures before they occur
    • Scale horizontally to increase aggregate system availability - Distribute requests across
    multiple, smaller resources to ensure that they don't share a common point of failure
    • Stop guessing capacity - Maintain the optimal level to satisfy demand without over or
    under provisioning - Use Auto Scaling
    • Manage change in automation - Use automation to make changes to infrastructure
- 4) Performance Efficiency
    - Includes the ability to use computing resources efficiently to meet
    system requirements, and to maintain that efficiency as demand changes
    and technologies evolve
    - Design Principles
    • Democratize advanced technologies - Advance technologies become services
    and hence you can focus more on product development
    • Go global in minutes - Easy deployment in multiple regions
    • Use serverless architectures - Avoid burden of managing servers
    • Experiment more often - Easy to carry out comparative testing
    • Mechanical sympathy - Be aware of all AWS services
- 5) Cost Optimization
    - Includes the ability to run systems to deliver business value at the lowest
    price point
    - Design Principles
    • Adopt a consumption mode - Pay only for what you use
    • Measure overall efficiency - Use CloudWatch
    • Stop spending money on data center operations - AWS does the infrastructure
    part and enables customer to focus on organization projects
    • Analyze and attribute expenditure - Accurate identification of system usage and
    costs, helps measure return on investment (ROI) - Make sure to use tags
    • Use managed and application level services to reduce cost of ownership - As
    managed services operate at cloud scale, they can offer a lower cost per
    transaction or service
- 6) Sustainability
    - The sustainability pillar focuses on minimizing the environmental impacts of running cloud workloads.
    - Design Principles
    • Understand your impact – establish performance indicators, evaluate improvements
    • Establish sustainability goals – Set long-term goals for each workload, model return on investment (ROI)
    • Maximize utilization – Right size each workload to maximize the energy efficiency of the underlying hardware and minimize idle resources.
    • Anticipate and adopt new, more efficient hardware and software offerings – and design for flexibility to adopt new technologies over time.
    • Use managed services – Shared services reduce the amount of infrastructure; Managed services help automate sustainability best practices as moving infrequent accessed data to cold storage
    and adjusting compute capacity.
    • Reduce the downstream impact of your cloud workloads – Reduce the amount of energy or resources required to use your services and reduce the need for your customers to upgrade
    their devices
- AWS Well-Architected Tool
    - Free tool to review your architectures against the 6 pillars Well-Architected
    Framework and adopt architectural best practices
    - How does it work?
    • Select your workload and answer questions
    • Review your answers against the 6 pillars
    • Obtain advice: get videos and documentations, generate a report, see the results in a dashboard
- AWS Right Sizing
    - EC2 has many instance types, but choosing the most powerful instance type
    isn’t the best choice, because the cloud is elastic
    - Right sizing is the process of matching instance types and sizes to your workload performance and capacity requirements at the lowest possible cost
    - Scaling up is easy so always start small
    - It’s also the process of looking at deployed instances and identifying
    opportunities to eliminate or downsize without compromising capacity or other requirements, which results in lower costs
    - It’s important to Right Size…
        - before a Cloud Migration
        - continuously after the cloud onboarding process (requirements change over time)
    - CloudWatch, Cost Explorer, Trusted Advisor, 3rd party tools can help
- AWS Ecosystem – Free resources
    - AWS Blogs:
    
    [https://aws.amazon.com/blogs/aws/](https://aws.amazon.com/blogs/aws/)
    
    • AWS Forums (community):
    
    [https://forums.aws.amazon.com/index.jspa](https://forums.aws.amazon.com/index.jspa)
    
    • AWS Whitepapers & Guides:
    
    [https://aws.amazon.com/whitepapers](https://aws.amazon.com/whitepapers)
    
    • AWS Quick Starts:
    
    [https://aws.amazon.com/quickstart/](https://aws.amazon.com/quickstart/)
    
    • Automated, gold-standard deployments in the AWS Cloud
    • Build your production environment quickly with templates
    • Example: WordPress on AWS
    
    [https://fwd.aws/P3yyv?did=qs_card&trk=qs_card](https://fwd.aws/P3yyv?did=qs_card&trk=qs_card)
    
    • Leverages CloudFormation
    • AWS Solutions:
    
    [https://aws.amazon.com/solutions/](https://aws.amazon.com/solutions/)
    
    • Vetted Technology Solutions for the AWS Cloud
    • Example - AWS Landing Zone: secure, multi-account AWS environment
    •
    
    [https://aws.amazon.com/solutions/implementations/aws-landing-zone/](https://aws.amazon.com/solutions/implementations/aws-landing-zone/)
    
    • “Replaced” by AWS Control Tower
    
- AWS Ecosystem - AWS Support
    
    DEVELOPER
    
    - Business hours email access to Cloud Support Associates
    - General guidance: < 24 business hours
    - System impaired: < 12 business hours
    
    BUSINESS
    
    - 24x7 phone, email, and chat access to Cloud Support Engineers
    - Production system impaired: < 4 hours
    - Production system down: < 1 hour
    
    ENTERPRISE
    
    - Access to a Technical Account Manager (TAM)
    - Concierge Support Team (for billing and account best practices)
    - Business-critical system down: < 15 minutes
- AWS Marketplace
    - Digital catalog with thousands of software listings from independent software vendors (3rd party)
    - Example:
    • Custom AMI (custom OS, firewalls, technical solutions…)
    • CloudFormation templates
    • Software as a Service
    • Containers
    - If you buy through the AWS Marketplace, it goes into your AWS bill
    - You can sell your own solutions on the AWS Marketplace
- AWS Training
    - AWS Digital (online) and Classroom Training (in-person or virtual)
    - AWS Private Training (for your organization)
    - Training and Certification for the U.S Government
    - Training and Certification for the Enterprise
    - AWS Academy: helps universities teach AWS
- AWS Professional Services & Partner Network
    - The AWS Professional Services organization is a global team of experts
    - Tey work alongside your team and a chosen member of the APN
    - APN = AWS Partner NetworK
    - APN Technology Partners: providing hardware, connectivity, and software
    - APN Consulting Partners: professional services firm to help build on AWS
    - APN Training Partners: find who can help you learn AWS
    - AWS Competency Program: AWS Competencies are granted to APN Partners who have demonstrated technical proficiency and proven customer success in specialized solution areas.
    - AWS Navigate Program: help Partners become better Partners
- AWS Knowledge Center
    - Contains the most frequent & common questions and requests
- AWS IQ
    - Quickly find professional help for your AWS projects
    - Engage and pay AWS Certified 3rd party experts for on-demand project work
    - Video-conferencing, contract management, secure collaboration, integrated billing
- AWS re:Post