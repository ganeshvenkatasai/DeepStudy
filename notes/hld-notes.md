# HLD


### 1. Clarify Requirements
- Functional Requirements
- Non Functional Requirements

### 2. Understand System Flow and Actors
- Explain flow for clarity
- List actors

### 3. Define User Actions and APIs
- Write down actions done by actors
- Make them as APIs

### 4. Identify Microservices
- Based on APIs identify Services

### 5. Capacity and Scale Estimation

- `Users and Traffic` : DAU/MAU, Peak QPS, Traffic patterns
- `Data Size Estimations` : Request average payload size (in KB/MB), Database storage, Logs & metadata (add 10–20% overhead), Growth rate (per day/month/year)
- `Read/Write Ratio` : Helps decide DB sharding, caching, and indexing
- `Latency` : Time taken for a request (e.g., <200ms)
- `Throughput` : Number of requests served per second
- `Bandwidth` : Request payload size × QPS
- `Cache Estimation` : Hit ratio, Cache size = Working set of hot data
- `Database Scaling` : Vertical, Horizontal, Partition key selection
- `Storage and Replication` : Replication factor, Effective storage = Raw storage × Replication factor, Cold vs hot storage

### 6. Cost Estimation

#### 1. Compute (Servers/VMs/Containers)
- Number of instances: X  
- Cost per instance: $Y/month  
- **Total: $X × Y = $Z/month**


#### 2. Storage
- Database storage: X TB × $Y/TB  
- Blob storage (images/videos): X TB × $Y/TB  
- Replication factor: R  
- **Total: (DB + Blob) × R**


#### 3. Network / Bandwidth
- Ingress traffic: Usually free  
- Egress traffic: X TB × $Y/TB  
- **Total: $Z/month**

#### 4. Cache / CDN
- Redis/Memcached cluster: $X/month  
- CDN traffic: X GB × $Y/GB  
- **Total: $Z/month**

#### 5. Queue / Streaming
- Kafka / PubSub cluster: $X/month  
- **Total: $Z/month**

#### 6. Monitoring & Logging
- Monitoring tools: $X per host × Y hosts  
- **Total: $Z/month**

#### 7. Backups & Disaster Recovery
- Backup storage: X TB × $Y/TB (e.g., Glacier)  
- **Total: $Z/month**

#### 8. Third-Party Integrations
- SMS (Twilio): X messages × $Y/message  
- Emails (SendGrid): X emails × $Y/1000 emails  
- **Total: $Z/month**


### 7. Design Data Model and Database

#### 1. Entities (Tables/Collections)
- **Entity 1**: Attributes (with type, size, constraints)  
- **Entity 2**: Attributes  
- **Entity 3**: Attributes  
- ...


## 2. Relationships
- **One-to-One**: e.g., User ↔ Profile  
- **One-to-Many**: e.g., User → Orders  
- **Many-to-Many**: e.g., Students ↔ Courses  

---

## 3. Database Choice
- **SQL (Relational)** → If strong consistency, transactions, joins needed.  
- **NoSQL (Document/Key-Value/Column/Graph)** → If high scale, flexible schema, eventual consistency.  
- Hybrid approach if required.

---

## 4. Schema Design Example (Relational)
**Users**  
- user_id (PK)  
- name  
- email (unique)  
- created_at  

**Orders**  
- order_id (PK)  
- user_id (FK → Users.user_id)  
- amount  
- status  
- created_at  

**Payments**  
- payment_id (PK)  
- order_id (FK → Orders.order_id)  
- amount  
- mode  
- status  

---

## 5. Access Patterns (Queries)
- Read-heavy or write-heavy?  
- Frequent queries (e.g., "Get all orders by user").  
- Indexing strategy.  
- Query optimization (denormalization, caching if needed).  

---

## 6. Scaling Strategy
- **Vertical scaling** → bigger DB machine.  
- **Horizontal scaling** → sharding, partitioning.  
- Replication (read replicas, master-slave).  
- CAP theorem consideration: Strong Consistency vs Availability.  

---

## 7. Storage Estimation
- Avg row size × number of rows = total DB size.  
- Growth rate (daily/monthly/yearly).  
- Index size overhead (~20–30%).  

---

## 8. Backup & Recovery
- Point-in-time recovery.  
- Replication across regions.  
- Cold storage for historical data.  



### 8. High Level Architecture Diagram

### 9. Address Scalability and Reliability
 - Cover all non functional requirements

**Kafka** 
Retention period

### 10. Identify Tradeoffs 

### 11. Handling Failures and Bottlenecks

### 12. Security and Compliance

### 13. Take Feedback and Iterate

### 14. Summarize the Design





---

## My Learnings

- `Snowflake ID` : Unique identifiers across a distributed system.