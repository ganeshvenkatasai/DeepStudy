# HLD Micro Notes

## Core Concepts
- Scalability (Vertical/Horizontal)
- Availability (SLA, SLO, SLI)
- Reliability vs Fault Tolerance
- Latency vs Throughput
- Consistency (Strong, Eventual, CAP Theorem)
- Partition Tolerance
- Load Balancing (Round Robin, Least Connections)
- Caching (CDN, Redis, Memcached)
- Proxies (Forward/Reverse)
- Redundancy & Replication

## Databases
- ACID vs BASE
- SQL (MySQL, PostgreSQL) vs NoSQL (MongoDB, Cassandra)
- Database Sharding (Hash, Range, Directory-Based)
- Indexing (B-Tree, LSM Tree)
- Read Replicas
- Database Partitioning
- ORM vs Raw Queries
- Connection Pooling

## System Architecture
- Monolithic vs Microservices
- SOA (Service-Oriented Architecture)
- Event-Driven Architecture
- Pub-Sub Model
- REST vs GraphQL vs gRPC
- API Gateway
- Service Discovery (Consul, Zookeeper)
- Circuit Breaker Pattern
- Saga Pattern

## Performance
- Latency Numbers (CPU Cache, SSD, Network)
- Throughput Optimization
- Queues (Kafka, RabbitMQ)
- Batch Processing vs Stream Processing
- Backpressure Handling
- Rate Limiting (Token Bucket, Leaky Bucket)
- Idempotency

## Storage
- Block vs File vs Object Storage
- Blob Storage (S3, GCS)
- In-Memory Databases
- Time-Series Databases
- Data Warehousing (BigQuery, Redshift)

## Security
- OAuth 2.0 / JWT
- HTTPS/TLS
- DDoS Protection
- SQL Injection / XSS
- Rate Limiting
- CORS
- Data Encryption (At Rest/Transit)

## Distributed Systems
- Consensus Algorithms (Paxos, Raft)
- Leader Election
- Distributed Locking
- MapReduce
- Vector Clocks
- Consistent Hashing
- Gossip Protocol
- Quorum

## Observability
- Logging (ELK Stack)
- Metrics (Prometheus, Grafana)
- Tracing (Jaeger, Zipkin)
- Health Checks
- Alerting (PagerDuty)

## Deployment
- Blue-Green Deployment
- Canary Releases
- Rolling Updates
- Feature Flags
- Infrastructure as Code (Terraform)
- Containerization (Docker, Kubernetes)
- Serverless (AWS Lambda)

## Core Principles
- CAP Theorem (Consistency, Availability, Partition Tolerance)
- PACELC Theorem
- ACID Properties
- BASE Properties
- Fallacies of Distributed Computing
- Back-of-the-Envelope Estimation
- Non-Functional Requirements (NFRs)

## Scalability Patterns
- Horizontal Scaling
- Vertical Scaling
- Stateless Architecture
- Stateful Services
- Sharding (Hash, Range, Directory)
- Partitioning (Vertical, Horizontal)
- Denormalization
- Materialized Views

## Load Management
- Load Balancers (ALB, NLB)
- Round Robin
- Least Connections
- IP Hashing
- Weighted Distribution
- Circuit Breaker Pattern
- Bulkhead Pattern
- Throttling

## Database Systems
### SQL/RDBMS
- Indexing (B-Tree, LSM Tree)
- Transactions (ACID)
- Isolation Levels
- Locking (Optimistic, Pessimistic)
- Connection Pooling
- Read Replicas
- Database Federation

### NoSQL
- Key-Value (Redis, DynamoDB)
- Document (MongoDB)
- Columnar (Cassandra)
- Graph (Neo4j)
- Time-Series (InfluxDB)
- Search (Elasticsearch)

## Distributed Systems
- Consensus (Paxos, Raft)
- Leader Election
- Quorum
- Vector Clocks
- Gossip Protocol
- Consistent Hashing
- Distributed Locking
- MapReduce
- CRDTs (Conflict-Free Replicated Data Types)

## Networking
- REST
- GraphQL
- gRPC
- WebSockets
- Long Polling
- SSE (Server-Sent Events)
- API Gateway
- Service Mesh

## Security
- OAuth 2.0
- JWT
- SAML
- TLS/SSL
- Rate Limiting
- CORS
- WAF (Web Application Firewall)
- DDoS Protection

## Observability
- Logging (ELK)
- Metrics (Prometheus)
- Tracing (Jaeger)
- SLOs/SLIs
- Error Budgets
- Health Checks
- Alerting

## Deployment
- Blue-Green
- Canary
- Rolling Updates
- Feature Flags
- IaC (Terraform)
- Containers (Docker)
- Orchestration (Kubernetes)
- Serverless

## Design Patterns
- CQRS
- Event Sourcing
- Saga Pattern
- Sidecar
- Strangler Fig
- Ambassador
- Retry Pattern
- Backpressure

## Storage Systems
- Block Storage
- File Storage
- Object Storage
- Distributed FS
- RAID Configurations
- Data Lakes
- Data Warehouses

## Messaging
- Pub-Sub
- Message Queues
- Kafka Topics
- Consumer Groups
- Dead Letter Queues
- Exactly-Once Semantics
- Ordered Delivery

## Real-World Systems
- URL Shortener
- Chat System
- Payment Gateway
- Rate Limiter
- Recommendation Engine
- Search Autocomplete
- Stock Exchange
- Ride-Sharing

## Optimization
- Caching (LRU, LFU)
- CDN
- Compression
- Connection Pooling
- Batching
- Pre-computation
- Geohashing
- Bloom Filters

## Tools & Tech
- Redis
- Kafka
- PostgreSQL
- Cassandra
- Kubernetes
- Envoy
- Istio
- Terraform
