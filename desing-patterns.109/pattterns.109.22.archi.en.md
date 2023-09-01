# pattterns.22.archi.en

## Architectural Patterns (22)

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
16. **Client-Server:** Separates an application into client and server components, allowing distributed processing and communication.
17. **Master-Slave:** Distributes tasks among multiple worker nodes, with one node (master) coordinating the others (slaves).
18. **Peer-to-Peer:** Allows interconnected nodes to share resources and information directly, without a central server.
19. **Broker:** Introduces an intermediary (broker) to handle communication between distributed components or services.
20. **Component-Based Architecture:** Structures an application as a composition of reusable, self-contained components.
21. **Event-Driven Architecture (EDA):** Emphasizes the production, detection, consumption, and reaction to events in a system.
22. **N-Tier Architecture:** Divides an application into multiple tiers, each responsible for specific functionality or services.
