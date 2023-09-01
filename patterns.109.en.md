# patterns (109)

## Creational Patterns (16)

1. **Singleton:** Ensures that a class has only one instance and provides a global point of access to that instance.
2. **Factory Method:** Defines an interface for creating an object but allows subclasses to alter the type of objects that will be created.
3. **Abstract Factory:** Provides an interface for creating families of related or dependent objects without specifying their concrete classes.
4. **Builder:** Separates the construction of a complex object from its representation, allowing the same construction process to create different representations.
5. **Prototype:** Allows the creation of new objects by copying an existing object, known as the prototype.
6. **Object Pool:** Maintains a pool of objects that are ready for use instead of creating and destroying them repeatedly.
7. **Dependency Injection:** Supplies dependencies that a class requires from the outside rather than creating them internally.
8. **Simple Factory:** Allows the creation of objects of different types without exposing the object creation logic to the client.
9. **Lazy Initialization:** Delays the creation of an object until it is needed.
10. **Factory Kit:** Defines an interface for creating families of related objects but uses static methods instead of classes.
11. **Multiton:** Similar to Singleton but manages multiple instances with names or keys.
12. **Singleton Registry:** Provides access to Singleton instances through a central registry.
13. **Singleton Per Thread:** Offers a Singleton instance per thread of execution.
14. **Singleton Per Request:** Provides a Singleton instance per request in a web application.
15. **Static Factory:** Uses static methods to create objects instead of constructors.
16. **Multiton Registry:** A central registry that manages multiple instances of Multiton.

## Structural Patterns (29)

1. **Adapter:** Allows incompatible interfaces to work together by converting the interface of one class into another expected by the client.
2. **Bridge:** Separates an object's abstraction from its implementation, allowing both to vary independently.
3. **Composite:** Allows you to compose objects into tree structures to represent part-whole hierarchies.
4. **Decorator:** Dynamically adds additional behaviors to objects without affecting other objects of the same class.
5. **Facade:** Provides a simplified interface to a larger set of classes and functionalities.
6. **Flyweight:** Efficiently shares objects commonly used to conserve resources.
7. **Proxy:** Controls access to an object by providing a surrogate or placeholder.
8. **Module:** Groups related components into a single module or unit.
9. **Private Class Data:** Hides implementation details by separating public interface and private data.
10. **Faceted:** Divides an interface into multiple smaller interfaces called facets.
11. **Pluggable Selector:** Allows an object to select its behavior from several algorithms.
12. **Aggregate:** Groups objects into a single entity to treat them as a unit.
13. **Role Object:** Represents a role or set of behaviors that an object can take on.
14. **Tree Structure:** Organizes objects into a hierarchical tree structure.
15. **Hierarchical:** Organizes objects into a nested hierarchy.
16. **Event-Based Composition:** Object composition based on events.
17. **Layers:** Divides an application into layers, each with a specific responsibility.
18. **Component Configurator:** Configures objects using separate components.
19. **Double Buffer:** Stores two copies of a dataset to improve performance.
20. **Service Locator:** Provides a centralized location to look up services.
21. **Resource Acquisition Is Initialization (RAII):** Manages the acquisition and release of resources automatically.
22. **Handle-Body Idiom:** Hides the implementation of an object behind a pointer or handle.
23. **Metadata Mapping:** Associates metadata with objects.
24. **Half-Object + Protocol:** Splits an object into two parts, local and remote, to reduce network communication.
25. **Type Object:** Uses an object to represent and manage data types.
26. **Role Object:** Represents a role or set of behaviors that an object can take on.
27. **Super Type:** Groups related types into a common hierarchy.
28. **Sub Type:** Defines a new type that inherits from an existing type.
29. **Mixin:** Combines behaviors from multiple classes into one.

## Behavioral Patterns (45)

1. **Chain of Responsibility:** Allows passing a request along a chain of handlers. Each handler decides whether to process the request or pass it to the next.
2. **Command:** Encapsulates a request as an object, allowing parameterization of objects with operations and queuing of requests.
3. **Interpreter:** Defines a grammar for a language and provides an interpreter to evaluate statements in that language.
4. **Iterator:** Provides a way to access elements of a collection sequentially without exposing its underlying representation.
5. **Mediator:** Defines an object that coordinates communication between objects instead of allowing them to communicate directly.
6. **Memento:** Captures and externalizes the internal state of an object so it can be restored later.
7. **Observer:** Defines a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically.
8. **State:** Allows an object to alter its behavior when its internal state changes. The object will appear to change its class.
9. **Strategy:** Defines a family of algorithms, encapsulates each one, and makes them interchangeable. Allows the algorithm to vary independently from clients that use it.
10. **Template Method:** Defines the skeleton of an algorithm in an operation, allowing subclasses to modify certain steps of that algorithm.
11. **Visitor:** Lets you add further operations to objects without having to modify them.
12. **Null Object:** Provides an object as a surrogate for the lack of an object of a given type.
13. **Servant:** Groups methods that can be applied to multiple classes into a single object.
14. **Specification:** Defines a business rule as an object and allows checking if an object meets that specification.
15. **Command Processor:** Executes commands in a queue asynchronously.
16. **Event Aggregator:** Combines events from multiple sources into a single event.
17. **Publish-Subscribe:** Allows objects to subscribe and receive notifications of events from other objects.
18. **Scheduler:** Schedules tasks for execution at specific times.
19. **Scheduler (Threaded):** Schedules tasks for execution in separate threads.
20. **Two-Step View:** Divides the view into two parts, one for logic and one for presentation.
21. **Delegation:** Delegates responsibilities among objects to avoid code duplication.
22. **Chain of Command:** Chains command objects to perform actions in sequence.
23. **Priority Queue:** Organizes elements by priority.
24. **Bytecode:** Uses a set of instructions instead of direct source code.
25. **Reflection:** Allows examining and modifying an object's structure and behavior at runtime.
26. **Event Queue:** Stores and manages events for later processing.
27. **Asynchronous Method Invocation:** Invokes methods asynchronously.
28. **Futures and Promises:** Provides a mechanism to obtain a future value from an asynchronous operation.
29. **Active Object:** Provides an intermediate object for asynchronous method calls.
30. **Monitor Object:** Synchronizes access to shared objects.
31. **Half-Sync/Half-Async:** Divides an application into two parts, one asynchronous and one synchronous.
32. **Thread Pool:** Manages a pool of threads for parallel task execution.
33. **Double-Checked Locking:** Improves Singleton initialization performance by locking only when necessary.
34. **Thread-Specific Storage:** Provides thread-local storage for data.
35. **Balking Pattern:** Prevents an object from taking action if certain conditions are not met.
36. **Barrier Pattern:** Synchronizes multiple threads at a specific point.
37. **Worker Thread:** Uses worker threads to perform background tasks.
38. **Leaders/Followers:** Efficiently manages a group of threads.
39. **Proactor:** Initiates actions asynchronously and associates event handlers for processing.
40. **Reactor:** Manages events and associated operations.
41. **Read-Write Lock:** Allows simultaneous read and write access to shared resources.
42. **Lock:** Provides mutual exclusion for shared resources.
43. **Thread-Local Storage:** Stores data locally for each thread.
44. **Thread-Specific Storage:** Stores thread-specific data.
45. **Thread-Safe Interface:** Ensures thread-safe operations on an interface.

## Architectural Patterns (22)

1. **Model-View-Controller (MVC):** Separates an application into three interconnected components: Model (data and logic), View (user interface), and Controller (manages user input).
2. **Model-View-Presenter (MVP):** Separates an application into three components similar to MVC but with a more passive View.
3. **Model-View-ViewModel (MVVM):** Separates an application into three components: Model (data and logic), View (user interface), and ViewModel (exposes data and commands to the View).
4. **Layered Architecture:** Divides an application into different layers, each responsible for a specific aspect of functionality.
5. **Microservices:** Architectural style that structures an application as a collection of small, loosely coupled services.
6. **Service-Oriented Architecture (SOA):** Organizes software as a collection of services that can be discovered and invoked independently.
7. **Repository Pattern:** Separates the logic that retrieves data from the underlying data source.
8. **Unit of Work:** Manages changes to a set of data by tracking the modifications and coordinating their storage.
9. **CQRS (Command Query Responsibility Segregation):** Separates read and write operations for data storage.
10. **Event Sourcing:** Stores the state of an application as a sequence of events.
11. **Hexagonal Architecture:** Organizes an application into inner and outer layers with a clear boundary and separation of concerns.
12. **Clean Architecture:** Separates an application into concentric circles, each with a specific level of abstraction.
13. **Domain-Driven Design (DDD):** Focuses on the core domain and domain logic in an application.
14. **Pipes and Filters:** Composes data processing components in a pipeline.
15. **Blackboard Pattern:** Solves problems by breaking them down into sub-problems, each processed by different knowledge sources.
16. **Client-Server:** Divides an application into client and server components that communicate over a network.
17. **Master-Slave:** Splits the processing responsibilities between a master and one or more slaves.
18. **Peer-to-Peer:** Distributes tasks or workloads across peers or nodes.
19. **Broker:** Acts as an intermediary that coordinates communication between distributed components.
20. **Object-Relational Mapping (ORM):** Maps between an object-oriented domain model and a relational database.
21. **Publish-Subscribe:** Allows objects to subscribe and receive notifications of events from other objects.
22. **Event-Driven Architecture (EDA):** Models the flow of events to trigger actions in a system.
