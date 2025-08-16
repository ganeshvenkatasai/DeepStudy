# HLD Short Notes

## Core Concepts
- `Scalability (Vertical)` → Increase capacity of existing servers  
- `Scalability (Horizontal)` → Add more servers to the system  
- `Availability (SLA)` → Service Level Agreement (uptime guarantee)  
- `Availability (SLO)` → Service Level Objective (performance target)  
- `Availability (SLI)` → Service Level Indicator (measured metric)  
- `Reliability` → System performs correctly over time  
- `Fault Tolerance` → System continues working during failures  
- `Latency` → Time taken for a single operation  
- `Throughput` → Operations completed per time unit  
- `Consistency (Strong)` → All reads get latest write  
- `Consistency (Eventual)` → Reads eventually get latest write  
- `CAP Theorem` → Can only guarantee 2 of 3: Consistency, Availability, Partition Tolerance  
- `Partition Tolerance` → System works despite network partitions  
- `Load Balancing (Round Robin)` → Distribute requests sequentially  
- `Load Balancing (Least Connections)` → Send to server with fewest active connections  
- `Caching (CDN)` → Geographic content distribution network  
- `Caching (Redis)` → In-memory key-value store  
- `Caching (Memcached)` → Simple distributed memory cache  
- `Proxies (Forward)` → Client-side proxy (e.g., VPN)  
- `Proxies (Reverse)` → Server-side proxy (e.g., Nginx)  
- `Redundancy` → Duplicate critical components  
- `Replication` → Copy data across multiple nodes  

## Databases
- `ACID` → Atomicity, Consistency, Isolation, Durability  
- `BASE` → Basically Available, Soft state, Eventually consistent  
- `SQL` → Structured Query Language (tabular data)  
- `NoSQL` → Non-relational databases (flexible schemas)  
- `Sharding (Hash)` → Distribute data using hash function  
- `Sharding (Range)` → Partition by value ranges  
- `Sharding (Directory)` → Lookup service for data location  
- `Indexing (B-Tree)` → Balanced tree structure for fast lookups  
- `Indexing (LSM Tree)` → Log-structured merge tree for write-heavy workloads  
- `Read Replicas` → Copy of data for read scaling  
- `Database Partitioning` → Split tables for performance  
- `ORM` → Object-Relational Mapping (database abstraction)  
- `Raw Queries` → Direct SQL for complex operations  
- `Connection Pooling` → Reuse database connections  

## System Architecture
- `Monolithic` → Single unified codebase  
- `Microservices` → Independent, loosely-coupled services  
- `SOA` → Services communicate via protocols  
- `Event-Driven` → Systems react to events  
- `Pub-Sub` → Publishers send events to subscribers  
- `REST` → Representational State Transfer (HTTP API)  
- `GraphQL` → Query language for APIs  
- `gRPC` → High-performance RPC framework  
- `API Gateway` → Single entry point for microservices  
- `Service Discovery` → Locate services in a network  
- `Circuit Breaker` → Fail fast when downstream fails  
- `Saga Pattern` → Manage distributed transactions  

## Performance
- `Latency Numbers` → Know orders of magnitude (CPU ns → network ms)  
- `Throughput Optimization` → Maximize requests processed  
- `Queues (Kafka)` → Distributed event streaming  
- `Queues (RabbitMQ)` → Message broker with queues  
- `Batch Processing` → Process data in large chunks  
- `Stream Processing` → Process data in real-time  
- `Backpressure` → Control flow to prevent overload  
- `Rate Limiting` → Control request frequency  
- `Idempotency` → Repeated calls have same effect  

## Storage
- `Block Storage` → Raw storage volumes (e.g., EBS)  
- `File Storage` → Hierarchical file systems  
- `Object Storage` → Flat namespace (e.g., S3)  
- `Blob Storage` → Binary large object storage  
- `In-Memory DBs` → Ultra-fast volatile storage  
- `Time-Series DBs` → Optimized for timestamped data  
- `Data Warehousing` → Analytics-optimized storage  

## Security
- `OAuth 2.0` → Authorization framework  
- `JWT` → JSON Web Tokens for authentication  
- `HTTPS/TLS` → Encrypted communication  
- `DDoS Protection` → Mitigate flood attacks  
- `SQL Injection` → Malicious SQL code injection  
- `XSS` → Cross-site scripting attacks  
- `CORS` → Cross-Origin Resource Sharing  
- `Data Encryption` → Protect data at rest/transit  

## Distributed Systems
- `Consensus (Paxos)` → Agreement protocol  
- `Consensus (Raft)` → Easier-to-understand consensus  
- `Leader Election` → Choose coordinator node  
- `Distributed Locking` → Coordinate resource access  
- `MapReduce` → Distributed processing framework  
- `Vector Clocks` → Track event ordering  
- `Consistent Hashing` → Distribute keys evenly  
- `Gossip Protocol` → Epidemic information spread  
- `Quorum` → Minimum votes for agreement  

## Observability
- `Logging` → Record system events  
- `Metrics` → Quantitative measurements  
- `Tracing` → Follow requests across services  
- `Health Checks` → Verify service status  
- `Alerting` → Notify about issues  

## Deployment
- `Blue-Green` → Two identical production environments  
- `Canary` → Gradual rollout to users  
- `Rolling Updates` → Incremental service updates  
- `Feature Flags` → Toggle features without deploy  
- `IaC` → Manage infrastructure as code  
- `Containerization` → Package apps with dependencies  
- `Serverless` → Run code without managing servers  

## Design Patterns
- `CQRS` → Separate read/write models  
- `Event Sourcing` → Store state changes as events  
- `Sidecar` → Helper container for main service  
- `Strangler Fig` → Incrementally replace legacy  
- `Ambassador` → Proxy network requests  
- `Retry Pattern` → Automatically retry failed ops  

## Messaging
- `Pub-Sub` → Publish events to topics  
- `Message Queues` → Store-and-forward messages  
- `Kafka Topics` → Categories for event streams  
- `Consumer Groups` → Parallel message processing  
- `DLQ` → Store failed messages  
- `Exactly-Once` → Process messages exactly once  

## Real-World Systems
- `URL Shortener` → Map short URLs to long  
- `Chat System` → Real-time messaging  
- `Payment Gateway` → Process transactions  
- `Rate Limiter` → Control request flow  
- `Recommendation Engine` → Suggest relevant items  

## Optimization
- `Caching (LRU)` → Evict least recently used  
- `Caching (LFU)` → Evict least frequently used  
- `CDN` → Cache content geographically  
- `Compression` → Reduce data size  
- `Batching` → Group operations together  
- `Bloom Filters` → Probabilistic set membership  

## Tools & Tech
- `Redis` → In-memory data store  
- `Kafka` → Distributed event streaming  
- `PostgreSQL` → Advanced SQL database  
- `Cassandra` → Wide-column NoSQL DB  
- `Kubernetes` → Container orchestration  
