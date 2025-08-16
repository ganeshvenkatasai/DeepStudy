# Object Oriented Programming

## Core Principles
- `Encapsulation` → Bundling data with methods that operate on that data  
- `Abstraction` → Hiding complex implementation details  
- `Inheritance` → Creating new classes from existing ones  
- `Polymorphism` → Ability to present the same interface for different forms  

## Class Relationships
- `Association` → Objects know about each other (weak relationship)  
- `Aggregation` → "Has-a" relationship (whole-part, independent lifecycle)  
- `Composition` → Strong "owns-a" relationship (dependent lifecycle)  
- `Dependency` → One class depends on another (temporary relationship)  

## Advanced Concepts
- `Interface` → Contract defining what a class can do  
- `Abstract Class` → Cannot be instantiated, contains abstract methods  
- `Method Overloading` → Same name, different parameters  
- `Method Overriding` → Subclass provides specific implementation  
- `Coupling` → Degree of interdependence between classes  
- `Cohesion` → How closely responsibilities of a class are related  

## Design Principles
- `SOLID Principles` → 
  - SRP: Single Responsibility Principle  
  - OCP: Open/Closed Principle  
  - LSP: Liskov Substitution Principle  
  - ISP: Interface Segregation Principle  
  - DIP: Dependency Inversion Principle  
- `DRY` → Don't Repeat Yourself  
- `KISS` → Keep It Simple, Stupid  
- `YAGNI` → You Aren't Gonna Need It  

# Unified Modeling Language (UML) Concepts

## Structural Diagrams
### Class Diagram
- `Class` → Blueprint for objects (name, attributes, methods)  
- `Visibility` → + (public), - (private), # (protected)  
- `Relationships` → Inheritance, association, dependency  

### Object Diagram
- `Object` → Instance of a class at runtime  
- `Links` → Connections between objects  

### Component Diagram
- `Component` → Modular part of system  
- `Interfaces` → Required/provided interfaces  

### Deployment Diagram
- `Node` → Hardware/software execution environment  
- `Artifact` → Physical entity (executable, library)  

## Behavioral Diagrams
### Use Case Diagram
- `Actor` → External entity interacting with system  
- `Use Case` → System functionality/action  
- `Relationships` → Include, extend, generalization  

### Sequence Diagram
- `Lifeline` → Participant in interaction  
- `Message` → Communication between objects  
- `Activation Bar` → Time period when participant is active  

### Activity Diagram
- `Action` → Task/operation  
- `Decision Node` → Branching point  
- `Fork/Join` → Parallel activities  

### State Diagram
- `State` → Condition of object at specific time  
- `Transition` → Movement between states  
- `Event` → Trigger for transition  

## Interaction Diagrams
- `Communication Diagram` → Focuses on object relationships  
- `Timing Diagram` → State changes over time  
- `Interaction Overview` → High-level workflow  

## UML Relationships
- `Generalization` → Inheritance (is-a)  
- `Realization` → Interface implementation  
- `Dependency` → Temporary "uses" relationship  
- `Association` → Structural relationship  
- `Aggregation` → Shared ownership  
- `Composition` → Strong ownership  

## UML Notations
- `Stereotypes` << >> → Extend UML vocabulary  
- `Constraints` { } → Rules for elements  
- `Notes` → Additional explanations  
