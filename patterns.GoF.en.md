# patterns GoF | 23

## Creational Patterns | 5

1. **Singleton:** Ensures a class has only one instance and provides a global point of access to that instance.
2. **Factory Method:** Defines an interface for creating an object but allows subclasses to alter the type of objects that will be created.
3. **Abstract Factory:** Provides an interface for creating families of related or dependent objects without specifying their concrete classes.
4. **Builder:** Separates the construction of a complex object from its representation, allowing the same construction process to create various representations.
5. **Prototype:** Allows the creation of new objects by copying an existing object, known as the prototype.

## Structural Patterns | 7

1. **Adapter:** Allows incompatible interfaces to work together by converting the interface of one class into one expected by the client.
2. **Bridge:** Separates an object's abstraction from its implementation so that the two can vary independently.
3. **Composite:** Composes objects into tree structures to represent part-whole hierarchies.
4. **Decorator:** Dynamically adds behavior to objects without affecting their class.
5. **Facade:** Provides a simplified interface to a set of interfaces in a subsystem, making it easier to use.
6. **Flyweight:** Shares a common set of objects efficiently to conserve resources when many instances with the same data are needed.
7. **Proxy:** Controls access to an object by providing a surrogate or placeholder for another object.

## Behavioral Patterns | 11

1. **Chain of Responsibility:** Passes a request along a chain of handlers. Each handler decides either to process the request or to pass it to the next handler.
2. **Command:** Encapsulates a request as an object, thereby allowing for parameterization of clients with queuable requests, requests that can be undone, and support for logging.
3. **Interpreter:** Defines a grammar for a language and provides an interpreter to evaluate sentences in that language.
4. **Iterator:** Provides a way to access the elements of an aggregate object sequentially without exposing its underlying representation.
5. **Mediator:** Defines an object that coordinates communication between objects, reducing the coupling between them.
6. **Memento:** Captures and externalizes an object's internal state so that the object can be restored to this state later.
7. **Observer:** Defines a one-to-many dependency between objects, so when one object changes state, all its dependents are notified and updated automatically.
8. **State:** Allows an object to alter its behavior when its internal state changes. The object will appear to change its class.
9. **Strategy:** Defines a family of algorithms, encapsulates each one, and makes them interchangeable. Strategy lets the algorithm vary independently from clients that use it.
10. **Template Method:** Defines the skeleton of an algorithm in the superclass but lets subclasses override specific steps of the algorithm without changing its structure.
11. **Visitor:** Lets you add additional operations to objects without having to modify them.
