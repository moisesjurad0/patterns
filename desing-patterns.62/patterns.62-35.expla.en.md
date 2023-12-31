# Design Patterns (62)

## Creational Patterns (7)

1. **Singleton:** Ensures a class has only one instance and provides a global point of access to that instance.
2. **Factory Method:** Defines an interface for creating an object, but allows subclasses to alter the type of objects that will be created.
3. **Abstract Factory:** Provides an interface for creating families of related or dependent objects without specifying their concrete classes.
4. **Builder:** Separates the construction of a complex object from its representation, allowing the creation of different representations.
5. **Prototype:** Allows the creation of new objects by copying an existing object, known as the prototype.
6. **Object Pool:** Maintains a set of objects in a pool for reuse, improving performance and efficiency.
7. **Dependency Injection:** Supplies dependencies from the outside rather than creating them internally, promoting flexibility and testability.

## Structural Patterns (11)

1. **Adapter:** Allows incompatible interfaces to work together by providing a wrapper that conforms to the expected interface.
2. **Bridge:** Separates an object's abstraction from its implementation so that the two can vary independently.
3. **Composite:** Composes objects into tree structures to represent part-whole hierarchies.
4. **Decorator:** Dynamically adds behavior to objects without altering their structure.
5. **Facade:** Provides a simplified interface to a larger body of code or a complex subsystem.
6. **Flyweight:** Efficiently shares objects that are frequently used to conserve resources.
7. **Proxy:** Controls access to an object by providing a surrogate or placeholder.
8. **Module:** Organizes code into modules that can be loaded and unloaded dynamically at runtime.
9. **Private Class Data:** Hides the implementation details of a class by restricting access to its internal data.
10. **Faceted:** Provides a simple interface to a complex subsystem by defining multiple entry points.
11. **Pluggable Selector:** Allows clients to choose from several implementations of a component through a common interface.

## Behavioral Patterns (17)

1. **Chain of Responsibility:** Passes a request along a chain of handlers. Each handler decides whether to process the request or pass it to the next handler.
2. **Command:** Encapsulates a request as an object, allowing for parameterization of clients with queues, requests, and operations.
3. **Interpreter:** Defines a grammar for a language and provides an interpreter to evaluate sentences in that language.
4. **Iterator:** Provides a way to access elements of a collection sequentially without exposing its underlying representation.
5. **Mediator:** Defines an object that centralizes communication between objects instead of allowing them to communicate directly.
6. **Memento:** Captures and externalizes an object's internal state, allowing the object to be restored to that state in the future.
7. **Observer:** Defines a one-to-many dependency between objects, so that when one object changes state, all its dependents are notified and updated automatically.
8. **State:** Allows an object to alter its behavior when its internal state changes. The object will appear to change its class.
9. **Strategy:** Defines a family of algorithms, encapsulates each one, and makes them interchangeable. It allows the algorithm to vary independently from clients that use it.
10. **Template Method:** Defines the skeleton of an algorithm in an operation, allowing subclasses to modify certain steps of the algorithm.
11. **Visitor:** Lets you add further operations to objects without having to modify them.
12. **Null Object:** Provides an object as a surrogate for the lack of an object of a given type.
13. **Servant:** Offers some of its functionality to a set of objects without knowing which objects it is serving.
14. **Specification:** Defines a set of business rules that can be combined to form a complex specification.
15. **Command Processor:** Efficiently manages commands and their execution in a concurrent environment.
16. **Event Aggregator:** Allows objects to subscribe to and receive event notifications from multiple sources.
17. **Publish-Subscribe:** Lets objects subscribe to and receive event notifications generated by other objects.

## Architectural Patterns (15)

1. **Model-View-Controller (MVC):** Separates an application into three interconnected components: Model (data and business logic), View (user interface), and Controller (manages user input and communication).
2. **Model-View-Presenter (MVP):** Separates an application into Model (business logic and data), View (user interface), and Presenter (handles user input and communicates between Model and View).
3. **Model-View-ViewModel (MVVM):** Separates an application into Model (data and logic), View (user interface), and ViewModel (manages the presentation logic and communication between Model and View).
4. **Layered Architecture:** Organizes an application into distinct layers (e.g., presentation, business logic, data) to enhance modularity and maintainability.
5. **Microservices:** Decomposes an application into small, independently deployable services that communicate through APIs, enabling scalability and flexibility.
6. **Service-Oriented Architecture (SOA):** Structures an application as a collection of loosely coupled services that interact via well-defined interfaces.
7. **Repository Pattern:** Separates the logic that retrieves data from the underlying storage, providing a unified interface to access data.
8. **Unit of Work:** Manages changes to data in a transactional manner, typically used with the Repository pattern.
9. **CQRS (Command Query Responsibility Segregation):** Separates read and write operations for data storage, enabling optimization for each type of operation.
10. **Event Sourcing:** Stores the state of an application as a sequence of events, allowing reconstruction of the application's state at any point in time.
11. **Hexagonal Architecture:** Focuses on the interaction between an application and external systems, isolating the core business logic.
12. **Clean Architecture:** Emphasizes separation of concerns, with distinct layers for business rules, interfaces, and external dependencies.
13. **Domain-Driven Design (DDD):** Centers development on a shared understanding of the problem domain, promoting a rich domain model.
14. **Pipes and Filters:** Divides a processing task into a series of sequential, independent stages (filters) connected by pipes.
15. **Blackboard Pattern:** Integrates diverse knowledge sources to solve complex problems through collaboration.

## Concurrency Patterns (8)

1. **Active Object:** Allows objects to run asynchronously without worrying about concurrency details.
2. **Monitor Object:** Provides a mechanism for multiple threads of execution to synchronize and block as needed.
3. **Half-Sync/Half-Async:** Divides a system's logic into two parts: one handling synchronous tasks and the other handling asynchronous tasks.
4. **Thread Pool:** Manages a set of reusable threads for executing tasks in parallel.
5. **Double-Checked Locking:** Optimizes concurrent access to shared data by adding an additional check before acquiring a full lock.
6. **Thread-Specific Storage:** Allows each thread of execution to have its own copy of data, avoiding concurrency conflicts.
7. **Balking Pattern:** Prevents an object from performing an action if certain conditions are not met.
8. **Barrier Pattern:** Synchronizes a group of threads at a control point until all threads are ready to proceed.

## Anti-Patterns (4)

1. **Big Ball of Mud:** Represents an unstructured and disorganized software design.
2. **Spaghetti Code:** Refers to messy, convoluted, and difficult-to-maintain source code.
3. **God Object:** Describes a class or component that performs too many functions and contains excessive logic.
4. **Singletonitis:** The excessive use of Singleton patterns, which can lead to maintenance and coupling issues.
