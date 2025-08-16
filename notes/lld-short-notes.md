# LLD Short Notes

## Object-Oriented Design
### Core Principles
- `Encapsulation` → Bundling data with methods that operate on that data  
- `Abstraction` → Hiding complex implementation details  
- `Inheritance` → Creating new classes from existing ones  
- `Polymorphism` → Same interface for different underlying forms  

### SOLID Principles
- `SRP` → Single Responsibility Principle  
- `OCP` → Open/Closed Principle  
- `LSP` → Liskov Substitution Principle  
- `ISP` → Interface Segregation Principle  
- `DIP` → Dependency Inversion Principle  

## Design Patterns
### Creational
- `Singleton` → Single instance of a class  
- `Factory` → Creates objects without exposing logic  
- `Abstract Factory` → Factory of factories  
- `Builder` → Constructs complex objects step-by-step  
- `Prototype` → Clone existing objects  

### Structural
- `Adapter` → Bridges incompatible interfaces  
- `Decorator` → Adds responsibilities dynamically  
- `Facade` → Simplified interface to complex system  
- `Proxy` → Controls access to original object  
- `Composite` → Treat individual/group objects uniformly  

### Behavioral
- `Observer` → Publish-subscribe mechanism  
- `Strategy` → Encapsulates interchangeable algorithms  
- `Command` → Encapsulates request as object  
- `State` → Alter behavior when state changes  
- `Template` → Defines algorithm skeleton  

## UML Diagrams
### Structural
- `Class Diagram` → Shows system classes and relationships  
- `Object Diagram` → Snapshot of instances at runtime  
- `Component Diagram` → Modular parts of system  

### Behavioral
- `Sequence Diagram` → Interaction between objects over time  
- `State Diagram` → States and transitions of an object  
- `Activity Diagram` → Flow of activities/processes  

## Code Quality
### Principles
- `DRY` → Don't Repeat Yourself  
- `KISS` → Keep It Simple, Stupid  
- `YAGNI` → You Aren't Gonna Need It  
- `Law of Demeter` → Loosely coupled components  

### Metrics
- `Cohesion` → How closely responsibilities are related  
- `Coupling` → Degree of interdependence between classes  
- `Cyclomatic Complexity` → Measure of code complexity  

## Exception Handling
- `Checked Exceptions` → Must be declared or handled  
- `Unchecked Exceptions` → Runtime exceptions  
- `Custom Exceptions` → Domain-specific exceptions  
- `Error Handling Strategies` → Retry, Fallback, Log  

## Concurrency
### Basics
- `Process vs Thread` → Independent vs lightweight execution  
- `Race Condition` → Unpredictable behavior from concurrent access  
- `Deadlock` → Circular wait for resources  
- `Starvation` → Threads denied resources  

### Synchronization
- `Mutex` → Mutual exclusion lock  
- `Semaphore` → Limits access to resource pool  
- `Monitor` → Higher-level synchronization  
- `Atomic Operations` → Uninterruptible operations  

## Database Design
### ORM Concepts
- `Lazy Loading` → Load data on-demand  
- `Eager Loading` → Load all data upfront  
- `N+1 Problem` → Multiple queries for related data  
- `Transaction Management` → Commit/Rollback logic  

### Performance
- `Indexing Strategies` → When and what to index  
- `Query Optimization` → EXPLAIN plans, JOIN optimization  
- `Connection Pooling` → Reuse database connections  

## API Design
### REST
- `Resources` → Nouns not verbs  
- `HTTP Methods` → GET, POST, PUT, DELETE, PATCH  
- `Status Codes` → 200, 201, 400, 401, 404, 500  
- `HATEOAS` → Hypermedia as the Engine of Application State  

### gRPC
- `Protocol Buffers` → Interface definition language  
- `Streaming` → Server, Client, Bidirectional  
- `Deadlines` → Timeout handling  

## Testing
### Types
- `Unit Testing` → Individual components  
- `Integration Testing` → Component interactions  
- `Mocking` → Simulating external dependencies  

### Techniques
- `TDD` → Test-Driven Development  
- `BDD` → Behavior-Driven Development  
- `Fixtures` → Test data setup  

## Caching Strategies
- `Write-through` → Write to cache and DB simultaneously  
- `Write-behind` → Write to cache first, then async to DB  
- `Cache-aside` → Application manages cache  
- `Eviction Policies` → LRU, LFU, FIFO  

## Real-World Examples
### Design Problems
- `Parking Lot` → Space allocation, payment handling  
- `Elevator System` → Scheduling, capacity management  
- `Vending Machine` → Inventory, payment processing  
- `Chess Game` → Piece movement, game state  

### Implementation Patterns
- `Rate Limiter` → Token bucket, sliding window  
- `TinyURL` → Hash generation, redirection  
- `Leaderboard` → Real-time ranking system  

## Performance Optimization
- `Memory Management` → Object pooling, garbage collection  
- `Algorithm Selection` → Time/Space complexity tradeoffs  
- `Concurrency Patterns` → Thread pools, worker queues  

## Security Considerations
- `Input Validation` → Sanitize all inputs  
- `Authentication` → JWT, OAuth flows  
- `Data Protection` → Encryption at rest/transit  

## Microservices Patterns
- `Circuit Breaker` → Fail fast when downstream fails  
- `API Composition` → Aggregate data from multiple services  
- `Saga Pattern` → Manage distributed transactions  

## Code Organization
- `Package Structure` → Logical component grouping  
- `Layered Architecture` → Presentation, Business, Data  
- `Clean Architecture` → Independent of frameworks  

## Refactoring Techniques
- `Extract Method` → Break large methods  
- `Rename` → Meaningful names for variables/methods  
- `Replace Conditional with Polymorphism` → Eliminate switch cases  

## Version Control
- `Branching Strategies` → Git Flow, Trunk-based  
- `Merge vs Rebase` → Integrating changes  
- `Semantic Versioning` → MAJOR.MINOR.PATCH  

## Build & Deployment
- `CI/CD Pipelines` → Automated testing/deployment  
- `Artifact Management` → Versioned binary storage  
- `Feature Flags` → Enable/disable features without deploy  

## Documentation
- `Code Comments` → Why, not what  
- `API Docs` → Swagger/OpenAPI specifications  
- `Architecture Decision Records` → Document design choices  
