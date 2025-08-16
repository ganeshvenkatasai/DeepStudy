# AWS Interview

## Cloud Fundamentals
### What is Cloud Computing?
- `On-demand IT resources` → Pay-as-you-go services over internet  
- `No upfront costs` → Only pay for what you use  

### AWS Global Infrastructure
- `Regions` → Geographical areas with multiple data centers  
- `Availability Zones` → Isolated locations within regions  
- `Edge Locations` → CloudFront CDN endpoints for faster delivery  

## AWS Architecture Principles
### Design Principles
- `Loose coupling` → Minimize dependencies between components  
- `Design for failure` → Assume components will fail  
- `Horizontal scaling` → Add more instances rather than larger ones  
- `Elasticity` → Automatically scale based on demand  
- `Parallel processing` → Divide tasks for faster execution  

### Well-Architected Framework
- `Operational Excellence` → Run/monitor systems effectively  
- `Security` → Protect data/systems  
- `Reliability` → Recover from failures  
- `Performance Efficiency` → Use resources efficiently  
- `Cost Optimization` → Eliminate unnecessary spending  

## Core AWS Services
### EC2 (Elastic Compute Cloud)
- `Virtual servers` → Configurable compute capacity  
- `Pricing models` → On-Demand, Spot, Reserved, Dedicated  
- `AMI` → Preconfigured server templates  
- `Security Groups` → Virtual firewalls for instances  

### S3 (Simple Storage Service)
- `Object storage` → Store/retrieve any data  
- `Storage classes` → Standard/IA/Glacier for different access needs  
- `11x9s durability` → Extremely reliable storage  

### VPC (Virtual Private Cloud)
- `Private network` → Isolated cloud environment  
- `Subnets` → Public/private network segments  
- `NACLs` → Stateless firewall rules for subnets  

### IAM (Identity Access Management)
- `Access control` → Manage who can do what  
- `Least privilege` → Grant minimum required permissions  
- `MFA` → Extra login security layer  

## Database Services
### RDS
- `Managed SQL` → Automated backups/patching  
- `Multi-engine` → MySQL/PostgreSQL/Oracle etc.  

### DynamoDB
- `Managed NoSQL` → Serverless key-value store  
- `Single-digit ms` → Consistent low latency  

## Pricing Models
### EC2 Pricing
- `On-Demand` → Flexible pay-as-you-go  
- `Reserved` → Discount for long-term commitment  
- `Spot` → Bid for unused capacity  

### S3 Pricing
- `Pay for` → Storage/requests/data transfer  

### Cost Optimization
- `Right-size` → Match instance to workload  
- `Auto-scale` → Adjust capacity automatically  

## Security Essentials
### Shared Responsibility Model
- `AWS secures` → Cloud infrastructure  
- `You secure` → Your data/applications  

### Key Services
- `KMS` → Encryption key management  
- `CloudTrail` → Audit API activity  
- `GuardDuty` → Threat detection  

## Monitoring & Management
- `CloudWatch` → Metrics/alarms  
- `Config` → Resource inventory/changes  
- `Systems Manager` → Operational management  

## Deployment Services
### CI/CD Tools
- `CodePipeline` → End-to-end workflow  
- `CodeBuild` → Build/test code  
- `CodeDeploy` → Automated deployments  

## Serverless Options
- `Lambda` → Run code without servers  
- `API Gateway` → Create/manage APIs  
- `Step Functions` → Coordinate workflows  

## Migration Strategies
- `Rehost` → Move as-is (lift-and-shift)  
- `Replatform` → Minor optimizations  
- `Refactor` → Redesign for cloud  

## Disaster Recovery
- `Backup/Restore` → Lowest cost option  
- `Pilot Light` → Minimal running services  
- `Multi-site` → Active-active redundancy  
