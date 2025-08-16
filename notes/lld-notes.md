# LLD Notes

## Object-Oriented Design
### Core Principles
- `Encapsulation` → Bundles data with methods that manipulate it. Prevents direct access to internal state. Example: Getters/setters for class fields.
- `Abstraction` → Hides complex implementation behind simple interfaces. Example: Database connection handling abstracted behind repository pattern.
- `Inheritance` → Creates hierarchical relationships between classes. Enables code reuse. Example: Vehicle → Car → ElectricCar hierarchy.

### SOLID Principles
- `SRP` → A class should have only one reason to change. Example: Separate OrderProcessor and OrderLogger classes.
- `OCP` → Open for extension but closed for modification. Example: Using interfaces for payment processors (CreditCard, PayPal).
- `LSP` → Subclasses should be substitutable for parent classes. Example: Square should extend Rectangle without breaking area calculations.

## Design Patterns
### Creational
- `Singleton` → Ensures only one instance exists globally. Used for logging, database connections. Thread-safety must be considered.
- `Factory` → Creates objects without specifying exact class. Example: DocumentCreator factory for Word/PDF documents.
- `Builder` → Constructs complex objects step-by-step. Useful when objects require many configuration parameters.

### Structural
- `Adapter` → Bridges incompatible interfaces. Example: Legacy payment system adapter for modern e-commerce platform.
- `Decorator` → Dynamically adds responsibilities to objects. Example: Adding encryption decorator to file storage.
- `Facade` → Provides simplified interface to complex subsystem. Example: Unified API for multiple microservices.

## UML Diagrams
### Structural
- `Class Diagram` → Shows classes, attributes, methods and relationships. Foundation for system design. Uses arrows for inheritance/association.
- `Sequence Diagram` → Illustrates object interactions over time. Shows lifelines and messages between components.
- `State Diagram` → Models object state transitions. Example: Order states (New → Paid → Shipped → Delivered).

## Code Quality
### Principles
- `DRY` → Avoid code duplication through abstraction. Violations lead to maintenance nightmares.
- `Law of Demeter` → Objects should only talk to immediate friends. Reduces coupling between classes.
- `Cyclomatic Complexity` → Measures decision points in code. Keep below 10 per method for maintainability.

## Concurrency
### Basics
- `Race Condition` → Occurs when threads access shared data unsafely. Solved using synchronization.
- `Deadlock` → Circular wait for resources (A waits for B, B waits for A). Prevention via lock ordering.
- `Thread Pool` → Reuses worker threads to avoid creation overhead. Size tuned to CPU cores.

## Database Design
### ORM Concepts
- `Lazy Loading` → Defers related object loading until needed. Can cause N+1 queries if misused.
- `Dirty Checking` → ORM tracks changes to persist only modified fields. Improves update performance.
- `Second-Level Cache` → Shared cache across sessions. Reduces database load for read-heavy apps.

## API Design
### REST
- `Resource Naming` → Use nouns (e.g., /orders not /createOrder). Plural form recommended.
- `HATEOAS` → Includes links for available actions in responses. Enables discoverable APIs.
- `Versioning` → Manage breaking changes via URL (/v1/orders) or headers. Never break clients.

## Testing
### Types
- `Unit Tests` → Isolate and test individual components. Fast execution, no dependencies.
- `Integration Tests` → Verify component interactions. Slower but catches interface issues.
- `Mocking` → Replace external services with test doubles. Enables predictable test environments.

## Caching Strategies
- `Write-through` → Writes to cache and DB simultaneously. Ensures consistency but slower writes.
- `Cache-aside` → App checks cache first, falls back to DB. Simple but can become inconsistent.
- `TTL` → Time-to-live expiration for cache entries. Balances freshness with performance.

## Real-World Examples
### Design Problems
- `Parking Lot` → Handle space allocation, payment, different vehicle types. Demonstrates state management.
- `Elevator System` → Manage multiple elevators, floor requests, capacity. Tests scheduling algorithms.
- `Vending Machine` → Track inventory, process payments, give change. Good for state pattern.

## Performance
- `Object Pool` → Reuses expensive-to-create objects. Common for database connections.
- `StringBuilder` → Mutable alternative to string concatenation. Reduces memory churn.
- `Batch Processing` → Groups operations to reduce I/O. Example: Bulk database inserts.

## Security
- `Input Validation` → Sanitize all external inputs. Prevent SQLi, XSS attacks.
- `Principle of Least Privilege` → Grant minimal required permissions. Limits breach impact.
- `Secure Defaults` → Systems should be secure out-of-the-box. Require explicit lowering of security.

## Microservices Patterns
- `Circuit Breaker` → Fails fast when downstream fails. Prevents cascading failures.
- `Bulkhead` → Isolates failures to single service. Like ship compartments preventing sinking.
- `Saga` → Manages distributed transactions using compensating actions. Alternative to 2PC.

## Code Organization
- `Package by Feature` → Group related classes together (e.g., order/, payment/). Better than layer-based.
- `Dependency Injection` → Externalize dependencies. Enables testing and configuration.
- `Clean Architecture` → Business logic independent of frameworks. Easy to change technologies.

## Refactoring
- `Extract Method` → Break long methods into smaller ones. Improves readability and reuse.
- `Replace Conditional with Polymorphism` → Eliminate switch statements using inheritance.
- `Introduce Parameter Object` → Group related parameters into single object. Reduces parameter lists.
