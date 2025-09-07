# HLD

### 1. Clarify Requirements
- Functional Requirements
- Non Functional Requirements

---

### 2. Flow and Actors
- Explain flow for clarity
- List actors

---

### 3. Actions and APIs
- Write down actions done by actors
- Make them as APIs

---

### 4. Identify Microservices
- Based on APIs identify Services

---

### 5. Capacity Estimation

- `Users and Traffic` : DAU/MAU, Peak QPS, Traffic patterns
- `Data Size Estimations` : Request average payload size (in KB/MB), Database storage, Logs & metadata (add 10–20% overhead), Growth rate (per day/month/year), Index size overhead (~20–30%)
- `Read/Write Ratio` : Helps decide DB sharding, caching, and indexing
- `Latency` : Time taken for a request (e.g., <200ms)
- `Throughput` : Number of requests served per second
- `Bandwidth` : Request payload size × QPS
- `Cache Estimation` : Hit ratio, Cache size = Working set of hot data
- `Database Scaling` : Vertical, Horizontal, Partition key selection
- `Storage and Replication` : Replication factor, Effective storage = Raw storage × Replication factor, Cold vs hot storage

---

### 6. Cost Estimation

- **Compute (Servers/VMs/Containers)**:  
  `No. of instances × Cost per instance`

- **Storage**:  
  `(Database storage + Blob storage) × Replication factor`

- **Network / Bandwidth**:  
  - Ingress traffic: `Usually free`  
  - Egress traffic: `X TB × $Y/TB`

- **Cache / CDN**:  
  - Redis/Memcached cluster: `$X/month`  
  - CDN traffic: `X GB × $Y/GB`

- **Queue / Streaming**:  
  - Kafka / PubSub cluster: `$X/month`

- **Monitoring & Logging**:  
  - Monitoring tools: `$X per host × Y hosts`

- **Backups & Disaster Recovery**:  
  - Backup storage: `X TB × $Y/TB (e.g., Glacier)`

- **Third Party Integrations**:  
  - SMS (Twilio): `X messages × $Y/message`  
  - Emails (SendGrid): `X emails × $Y/1000 emails`

---

### 7. Data Model and Database

- `Entities` : Attributes (with type, size, constraints)  
- `Relationships` : One-to-One, One-to-Many, Many-to-Many
- `Database Choice` : **SQL** (strong consistency, transactions, joins needed), **NoSQL** (high scale, flexible schema, eventual consistency)
- `Access Patterns` : Read heavy or write heavy, Frequent queries, Indexing, Query optimization (denormalization, caching)
- `Scaling Strategy` : **Vertical** (bigger DB machine), **Horizontal** (sharding, partitioning), Replication (read replicas, master-slave), CAP theorem (Strong Consistency vs Availability) 
- `Backup and Recovery` : Point-in-time recovery, Replication across regions, Cold storage for historical data.  

---

### 8. High Level Architecture

- `Client Applications` : Web App, Mobile App, Desktop App, API Clients, SDKs
- `API Gateway` : Entry point for all clients, Authentication, throttling, routing
- `Application Servers` : Backend services (monolith or microservices), Business logic layer
- `Microservices` : Core services, Communicate via REST/gRPC
- `Databases` : Relational (PostgreSQL, MySQL), NoSQL (MongoDB, DynamoDB, Cassandra)
- `File/Object Storage` : AWS S3, GCS, Azure Blob Storage (For images, videos, logs, backups)
- `Message Queue` : Kafka, RabbitMQ, ActiveMQ, SQS, Pub/Sub
- `Cache Layer` : Redis, Memcached
- `Search Engine` : Elasticsearch, Solr
- `Big Data / Analytics` : Data Lake (S3, HDFS), Data Warehouse (Snowflake, BigQuery, Redshift), Stream Processing (Flink, Spark Streaming, Kinesis)
- `Third Party APIs` : Payment Gateways (Stripe, PayPal, Razorpay), SMS/Email Providers (Twilio, SendGrid), Maps/Geo APIs (Google Maps, Mapbox)
- `Load Balancer` : Nginx, HAProxy, AWS ELB/ALB 
- `Service Discovery` : Consul, Eureka, etcd
- `CDN (Content Delivery Network)` : Cloudflare, Akamai, AWS CloudFront
- `Container Orchestration` : Kubernetes, Docker Swarm, ECS
- `CI/CD Pipeline` : Jenkins, GitHub Actions, GitLab CI 
- `Monitoring and Logging` : Prometheus + Grafana (metrics),
ELK Stack (logs), Jaeger / Zipkin (tracing)
- `Identity and Access Management` : OAuth, OpenID Connect, JWT, SSO (Okta, Auth0, Cognito)
- `WAF (Web Application Firewall)` : Cloudflare WAF, AWS WAF
- `Secrets Manager` : Vault, AWS Secrets Manager 
- `TLS/SSL Certificates` : Digital certificate to establish a secure, encrypted connection
- `Scheduler/Job Queue` : CronJobs, Celery, Sidekiq
- `Feature Flag System` : LaunchDarkly, Unleash
- `Configuration Management` : Consul, Spring Config Server

---

### 9. Scalability and Reliability
 - `Scalability` : Microservices Architecture, Event-Driven Architecture, CQRS
 - `Low Latency` : Cache-Aside Pattern, Read-Through/Write-Through Caching, Lazy Loading / Proxy Pattern
 - `Availability` : Redundant servers, Multi Region deployment, Leader Election Pattern, Failover Pattern, Circuit Breaker Pattern
 - `Reliability & Fault Tolerance` : Retry Pattern, Idempotent APIs, Bulkhead Pattern (isolate failures)
 - `Consistency` : ACID, Eventual consistency, Saga Pattern, Event Sourcing 
 - `Security` : Authentication/Authorization (OAuth2, JWT, SSO), Encrypt sensitive data at rest and in transit, Use WAF, API Gateway, rate limiting, Proxy Pattern (for request filtering), Policy Enforcement Point, Facade Pattern (via API Gateway). 
 - `Maintainability` : Layered Architecture, Dependency Injection, Factory Pattern
 - `Observability` : Centralized logging (ELK stack), Metrics collection (Prometheus/Grafana), Tracing (Jaeger, Zipkin), Observer Pattern
 - `Extensibility` : Modular microservices, API-first approach, Use feature flags, Strategy Pattern, Plugin Pattern, Adapter Pattern
 - `Cost Efficiency` : Auto-scaling, Use serverless, Optimize queries & storage, Queue-based Load Leveling, Lazy Initialization

---

### 10. Tradeoffs 

- **Scalability**:  
  - `SQL` : best when strong consistency and ACID needed
  - `NoSQL` : best when scale out and flexible schema needed

- **Low Latency**:  
  - `Inmemory cache` : best for hot data, leaderboards, sessions
  - `CDN` : best for static content delivery near users

- **Availability**:  
  - `Load Balancer` : distribute traffic
  - `Multi Region Deployment` : survive region failures

- **Reliability**:  
  - `Message Queue` : reliable task processing
  - `Event Streaming` : large scale event driven reliability

- **Consistency**:  
  - `Strong consistency` : ensures correctness for financial apps, inventory etc.
  - `Eventual consistency` : gives speed & scale at cost of eventual sync for social media, analytics etc.

- **Security**:  
  - `Auth0/Okta/Firebase` : SaaS-based and quick setup
  - `Custom OAuth2/JWT` : gives flexibility and lower cost at scale

- **Maintainability**:  
  - `Monolith` : best for small teams and MVPs
  - `Microservices` : best for large teams and complex domains

- **Observability**:  
  - `Prometheus` : how is system performing
  - `ELK` : what happened when it failed
  - `Jaeger` : where is the bottleneck in a request

- **Extensibility**:  
  - `Plugin based system` : easy feature extension
  - `API-first design` : external integrations easy (REST/gRPC, GraphQL)

- **Cost Efficiency**:  
  - `Kubernetes/ECS/GKE` : best for predictable workloads, steady traffic, better control
  - `AWS Lambda, GCP Cloud Functions` : best for bursty workloads, unpredictable, event driven workloads, cheaper at small scale



---

### 11. Failures and Bottlenecks

#### `Single Point of Failure (SPOF)`
- **Failure:** One component (DB, load balancer, server) goes down → whole system fails.  
- **Recovery:**  
  - Replication & clustering  
  - Multiple load balancers  
  - Health checks + automatic failover  


#### `Database Bottlenecks`
- **Failure:** DB too slow under heavy reads/writes.  
- **Recovery:**  
  - Add caching layer (Redis, Memcached)  
  - Sharding/Partitioning  
  - Read replicas  
  - Use NoSQL if workload fits  


#### `Network Latency & Failures`
- **Failure:** High latency or dropped requests.  
- **Recovery:**  
  - Retries with exponential backoff  
  - Circuit breaker pattern  
  - Deploy closer to users (CDN, edge servers)  

#### `Traffic Spikes or Overload`
- **Failure:** Sudden surge in users → servers crash.  
- **Recovery:**  
  - Auto-scaling  
  - Rate limiting & throttling  
  - Queueing requests (Kafka, RabbitMQ)  

#### `Cache Failures`
- **Failure:** Cache node down → flood of DB queries.  
- **Recovery:**  
  - Multi-node cache clusters  
  - Graceful degradation (serve stale data)  
  - Cache warm-up  

#### `Storage Failures`
- **Failure:** Disk crash, corruption, or full storage.  
- **Recovery:**  
  - Backups & snapshots  
  - Replication across zones  
  - Disk usage monitoring

#### `Message Queue Overload`
- **Failure:** Consumers too slow → messages pile up.  
- **Recovery:**  
  - Add more consumers  
  - Dead-letter queues  
  - Prioritize critical messages

#### `Deployment Failures`
- **Failure:** New release breaks production.  
- **Recovery:**  
  - Blue-Green / Canary deployments  
  - Rollback mechanisms  
  - Feature flags

#### `Memory & CPU Bottlenecks`
- **Failure:** Service consumes too much memory/CPU → crash.  
- **Recovery:**  
  - Monitoring & alerts  
  - Resource limits per container (Kubernetes)  
  - Auto-restart unhealthy instances

#### `Security Failures`
- **Failure:** Unauthorized access, DDoS, data breach.  
- **Recovery:**  
  - Authentication & authorization (OAuth, JWT)  
  - Encrypt data (at rest & transit)  
  - WAF & rate limiting  
  - Continuous monitoring & alerts  

---

### 12. Security and Compliance

- **Data Breaches** : `Sensitive data (user info, passwords, credit cards) leaked.`
  - Encrypt data at rest (AES) & in transit (TLS/SSL)  
  - Use secure key management (KMS, Vault)  
  - Apply database access controls (least privilege)

- **Weak Authentication & Authorization** : `Unauthorized users gain access.`
  - Use strong authentication (OAuth2, JWT, MFA)  
  - Role-Based Access Control (RBAC) / Attribute-Based Access Control (ABAC)  
  - Regular token expiry & refresh

- **Injection Attacks (SQLi, XSS, Command Injection)** : `Malicious input alters queries or executes scripts.`
  - Input validation & sanitization  
  - Use prepared statements / parameterized queries  
  - Web Application Firewall (WAF)

- **Insecure APIs** : `APIs expose sensitive data or allow abuse.` 
  - API authentication & rate limiting  
  - Use HTTPS everywhere  
  - Schema validation & versioning

- **Insider Threats** : `Employees misuse access to steal data.`
  - Principle of least privilege  
  - Activity logging & monitoring  
  - Segregation of duties

- **Misconfigured Cloud Resources** : `Open S3 buckets, exposed DBs, wrong IAM policies.`
  - Automated config scanners (Cloud Security Posture Management)  
  - Infrastructure as Code (Terraform, OpenTofu) with policies  
  - Regular security audits

- **Denial of Service (DoS/DDoS)** : `Attackers overload servers, making system unavailable.`
  - Rate limiting & throttling  
  - CDN + WAF protection  
  - Auto-scaling under attack traffic

- **Lack of Compliance (GDPR, HIPAA, PCI-DSS)** : `System violates legal regulations → fines, legal action.` 
  - Data anonymization / masking  
  - Consent management & audit logs  
  - Regular compliance checks & certifications

- **Unpatched Vulnerabilities** : `Known software vulnerabilities exploited.`
  - Regular patching & upgrades  
  - Vulnerability scans & penetration testing  
  - Automated dependency monitoring

- **Poor Logging & Monitoring** : `Breach happens but goes unnoticed.` 
  - Centralized logging (ELK, Splunk)  
  - Intrusion detection & anomaly monitoring  
  - Alerts & incident response playbooks  

---

### 13. Feedback and Iterate


---

### 14. Summarize the Design



---

## My Learnings

- `Snowflake ID` : Unique identifiers across a distributed system.

### Papers to read :

- Facebook TAO
- Google File System
- Google Big Table
- Facebook MemCached
- Google Zanzibar