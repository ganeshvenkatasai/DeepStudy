# LLD

### 1. Requirements Clarification
- Requirements are God Listen carefully
- Think about possible entities and actors
- Write down responsibilities and core features
- Ask minimal but impactful questions
- Keep requirements minimalistic don't solve everything
- Note down requirements as you discuss
- Think like the user

#### Key Questions to Ask:
- What are the core features to prioritize?
- Who are the primary users?
- Any specific constraints or limitations?
- Need to handle concurrency?
- Any additional actions to include?

### 2. Define Flow and Key Components
- Explain the flow for more clarity
- List all important entities based on requirements
- Identify main actors and their responsibilities
- Break down system into core modules

### 3. Class Diagram Design
- Draw class diagram with entities
- Define relationships, enumerations, multiplicity
- Add attributes and methods
- Use DSA concepts in UML
- Show inheritance, composition, associations

### 4. Design Patterns Consideration
- **Keep it simple** - use patterns you can build quickly
- Use **SOLID Principles**
- Focus on **Factory, Singleton, Observer, Strategy**

#### Essential Patterns:
- **Creational**: Singleton, Factory Method, Abstract Factory, Builder
- **Structural**: Adapter, Decorator, Facade, Composite  
- **Behavioral**: Observer, Strategy, Command, Iterator, State

### 5. Interface Definitions
- **Interface is God**
- Use SOLID principles
- Create clean abstractions based on patterns

### 6. Core Logic Implementation
- Add methods for endpoints (CRUD + additional)
- Write pseudocode for helper functions
- Handle exceptions gracefully
- Focus on core functionality first

### 7. Database Considerations
- Normalization and indexing
- Schema design if required

### 8. Concurrency Handling
- Thread safety considerations
- Synchronization mechanisms

### 9. Scalability Discussion
- **Discuss tradeoffs**
- Performance considerations
- Future extensibility

### 10. Testing Approach
- Handle edge cases, errors and exceptions

---

## Time Management Strategy

### Problem Type Adaptation
- **Narrow problems** (Chess, Tic-tac-toe): Less requirements, more coding
- **Broad problems** (Uber, Swiggy): More requirements gathering
- **Don't follow standard templates** - adapt based on problem

### Time Allocation Tips:
- Plan time for each stage
- Don't rush, better to do core features well
- Take 10-15 seconds to explain approach choices

---

## Key Patterns

### Common Use Cases:
- **Payment**: Strategy Design Pattern
- **Vehicle/ParkingSpot**: Abstract Factory  
- **ParkingLot**: Singleton
- **Notifications**: Observer (Pull/Push)

### Important Concepts:
- Use **Enums** for status/types
- **Soft Delete** for data integrity
- **Lost ticket handling** scenarios
- **Payment processing failure** scenarios

---

## Relationships

#### 1. Association (uses/works with):
- When one class needs another
- ClassA  -------->  ClassB

#### 2. Aggregation (weak has-a):
- Weak relationship, child can exist without parent
- Library ◇------ Book

#### 3. Composition (strong has-a):
- Strong relationship, child cannot exist without parent
- House ◆------ Room

#### 4. Generaliation / Inheritance (is-a):
- Child class inherits from parent

#### 5. Realization (interface):
- Class implements an interface

#### 6. Dependency (depends on):
- One class temporarily uses another


---

## Design Patterns

#### 1. Creational Patterns (object creation mechanisms)
1. **Singleton** : Ensure a class has only one instance.  
2. **Factory Method** : Define an interface for creating objects, but let subclasses decide the class.  
3. **Abstract Factory** : Provide an interface to create families of related objects.  
4. **Builder** : Construct complex objects step by step.  
5. **Prototype** : Create new objects by copying existing ones.  

---

#### 2. Structural Patterns (object composition)
6. **Adapter** : Convert one interface into another expected by clients.  
7. **Bridge** : Decouple abstraction from implementation.  
8. **Composite** : Treat individual objects and groups uniformly (tree structures).  
9. **Decorator** : Add responsibilities dynamically without modifying code.  
10. **Facade** : Provide a simplified interface to a subsystem.  
11. **Flyweight** : Use sharing to support large numbers of fine-grained objects efficiently.  
12. **Proxy** : Provide a placeholder/surrogate to control access.  

---

#### 3. Behavioral Patterns (object interaction & responsibility)
13. **Chain of Responsibility** : Pass a request along a chain until handled.  
14. **Command** : Encapsulate a request as an object.  
15. **Interpreter** : Define a grammar and interpret sentences.  
16. **Iterator** : Sequentially access elements without exposing structure.  
17. **Mediator** : Define an object to control communication between objects.  
18. **Memento** : Capture and restore an object’s internal state.  
19. **Observer** : Define dependency so when one object changes, others are notified.  
20. **State** : Change behavior when internal state changes.  
21. **Strategy** : Define a family of algorithms, encapsulate each one, and make them interchangeable.  
22. **Template Method** : Define skeleton of an algorithm, let subclasses override steps.  
23. **Visitor** : Represent operations to perform on elements of an object structure.  


### Story to remember

I am **Single** (**Singleton**) working in a **Factory** (**Factory Method**). Recently, I moved to an **Abstract Factory** (**Abstract Factory**). There I met a **Builder** (**Builder**) he is very **Proactive** (**Prototype**). He told me he **Adapted** (**Adapter**) to the place. When he was coming from a **Bridge** (**Bridge**), he saw **Composite** (**Composite**) numbers written there. Then he also saw a **Decorated** (**Decorator**) **Falcon** (**Facade**) which was **Flying** (**Flyweight**) with a **Proxy** (**Proxy**) server. Later, he found a **Chain** (**Chain of Responsibility**) and a person **Commanded** (**Command**) that it was his chain. But he **Interpreted** (**Interpreter**) it was not true and he **Iterated** (**Iterator**) the person and gave the **Mediator** (**Mediator**) a **Memento** (**Memento**). Everyone was **Observing** (**Observer**) in that **State** (**State**). His **Strategy** (**Strategy**) was to give the **Template** (**Template Method**) to all **Visitors** (**Visitor**).  

---

## Common Mistakes to Avoid

### 1. Going Too Wide
- Don't list all possible features
- Focus on core functionality first
- Choose most important features only

### 2. Skipping Requirements
- Don't jump straight to design
- Ask clarifying questions first
- Document assumptions clearly

### 3. Manager Entity Anti Pattern
- Avoid just creating data classes + manager classes
- Think about proper object responsibilities
- Use meaningful object interactions

### 4. Poor Communication
- Explain your thought process
- Justify design decisions
- Be open to feedback and iterate

### 5. Not Considering Tradeoffs
- Discuss alternative approaches
- Explain why you chose specific solutions
- Consider scalability and maintainability

---

## Best Practices & Tips

### Communication:
- **Perfect communication** shows technical depth
- **Think aloud** - verbalize thought process
- **Stay structured** - follow actor's journey
- Take time to explain approach choices

### Problem Solving:
- **Practice on whiteboard**
- **Handle exceptions** and edge cases
- **Be open to feedback** and iterate
- Focus on **core features** rather than everything

### Code Quality:
- Use meaningful names for classes/methods
- Focus on simplicity and readability
- Apply design principles naturally
- Make code modular and maintainable

---

## What Interviewers Look For

### Technical Skills:
- Problem-solving approach and thought process
- **Clean, maintainable, extensible code**
- Understanding of OOP principles and design patterns
- Ability to handle changing requirements

### Communication Skills:
- Clear explanation of design choices
- Ability to collaborate and take feedback
- Structured thinking and organization

### Adaptability:
- Flexibility to modify design based on feedback
- Handling edge cases and exceptions
- Considering future extensibility

---

## Final Success Mantras

### Golden Rules:
1. **Requirements are God** - listen carefully and clarify
2. **Interface is God** - design good abstractions
3. **Communication is key** - show technical depth
4. **Practice regularly** on different problem types
5. **Stay calm and confident** throughout

### Remember:
- **Think like the user**
- **Keep it simple** but extensible
- **Focus on core functionality** first
- **Discuss tradeoffs** and alternatives
- **Practice whiteboard coding** regularly


---

## My Learnings

