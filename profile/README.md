## Architecture Design
![image](https://github.com/Csye6225SumanthOrg/.github/assets/114118569/690c59e7-e139-4717-ac2d-5be1250ef0e9)




## Key Services and Features:

## Route 53:
Route 53 is a fully managed and scalable DNS service, providing 100% availability SLA and serving as a Domain Registrar. It translates human-readable hostnames to machine IP addresses.

## Virtual Private Cloud (VPC):
VPC forms the core of AWS infrastructure, offering resource isolation and a private network for applications. It can be segmented into public and private subnets.

## Internet Gateway (IGW):
IGW enables resources within a VPC, such as EC2 instances, to connect to the Internet. It scales horizontally and is tied to one VPC, requiring route table updates for Internet access.

## Application Load Balancer (ALB):
Launched in 2016, ALB operates at layer 7, supporting HTTP/s and Websocket protocols. It distributes traffic across resources in target groups and natively supports cross-zone load balancing.

## Elastic Compute Cloud (EC2):
EC2 provides virtual machines to host application logic and serve client requests.

## Auto Scaling Group (ASG):
ASG deploys EC2 instances with application code to ensure availability and scalability. It replaces unhealthy instances flagged by the Application Load Balancer's health checks.

## CloudWatch:
CloudWatch uses alarms to scale EC2 instances in ASG based on metrics like Average CPU Utilization. EC2 instances send logs to CloudWatch every 60 seconds via the CloudWatch Unified Agent.

## Simple Storage Service (S3):
S3 offers highly available and durable object storage. It uses buckets with globally unique names to store objects like product images.

## Relational Database Service (RDS):
RDS is a managed relational database service supporting various database engines. It enables Multi-AZ setups for disaster recovery and uses ACM for TLS certificates.

## Security Considerations:

## AWS Certificate Manager (ACM):
ACM manages TLS certificates for secure communication. It's integrated with services like ALB for HTTPS and supports both public and private certificates.

## Key Management Service (KMS):
KMS handles encryption keys, integrated with IAM for authorization and auditable via CloudTrail. It encrypts RDS databases and EC2 EBS volumes.

## Security Groups:
Security Groups act as firewalls, allowing specified traffic. EC2 instances only accept traffic from ALB, and RDS permits traffic solely from EC2 instances.

## IAM Role:
IAM roles grant EC2 instances in public subnets permissions to access S3 buckets.


## Continuous Integration (CI):
CI involves developers regularly integrating code changes into a shared repository, triggering automated tests (unit, integration) and code quality checks (linting, static analysis). GitHub Actions automates these processes, ensuring code integrity and identifying issues early.

## Continuous Deployment/Delivery (CD):
CD automates the deployment of code changes to production or staging environments after successful CI. GitHub Actions triggers deployment workflows, sets up deployment environments, executes deployment scripts/tools (e.g., AWS CLI), and validates deployments in staging before promoting to production.

## GitHub Actions Workflow:
Using YAML syntax, GitHub Actions workflows define trigger events (code pushes, pull requests), jobs (build, test, deploy), steps/actions (commands, tools), and manage environment variables/secrets securely. This automation streamlines software delivery, fostering collaboration, consistency, and faster release cycles.



