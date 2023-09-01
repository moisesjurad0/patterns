# SOLID | en

The SOLID principles are a set of software design guidelines that help create cleaner, maintainable, and extensible code. Each letter in "SOLID" represents one of these principles:

## SOLID Principles

### 1. Single Responsibility Principle (SRP)

- **Explanation:** A class should have a single reason to change. This means a class should have only one responsibility and should not have more than one reason to change. If a class has multiple responsibilities, it's more likely to change due to different reasons, making the code fragile and hard to maintain.

**Python Example:**

```python
# Bad example: A class with multiple responsibilities
class Customer:
    def __init__(self, name):
        self.name = name

    def calculate_discount(self, order):
        # Discount calculation
        pass

    def send_email_confirmation(self, order):
        # Sending confirmation email
        pass
```

### 2. Open/Closed Principle (OCP)

- **Explanation:** Software entities (classes, modules, etc.) should be open for extension but closed for modification. This means it should be possible to add new functionalities to a system without modifying existing code. Extension is achieved through inheritance, composition, and interface implementation.

**Python Example:**

```python
# Good example: Extension through inheritance
class Shape:
    def area(self):
        pass

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * self.radius * self.radius

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height
```

### 3. Liskov Substitution Principle (LSP)

- **Explanation:** Subclasses should be substitutable for their base classes without affecting the program's correctness. This means if a class A is a subclass of class B, any instance of B should be replaceable by an instance of A without the program behaving incorrectly.

**Python Example:**

```python
# Good example: Liskov Substitution
class Bird:
    def fly(self):
        pass

class Sparrow(Bird):
    def fly(self):
        print("Sparrow can fly")

class Ostrich(Bird):
    def fly(self):
        print("Ostrich can't fly")
```

### 4. Interface Segregation Principle (ISP)

- **Explanation:** Clients should not be forced to depend on interfaces they do not use. Instead of having a single large interface, it's preferable to have several smaller, specific interfaces that clients can implement as needed. This prevents clients from depending on methods they don't use.

**Python Example:**

```python
# Good example: Segregated interfaces
class Worker:
    def work(self):
        pass

class Eater:
    def eat(self):
        pass

class Robot(Worker):
    def work(self):
        print("Robot working")

class Human(Worker, Eater):
    def work(self):
        print("Human working")

    def eat(self):
        print("Human eating")
```

### 5. Dependency Inversion Principle (DIP)

- **Explanation:** High-level modules should not depend on low-level modules. Both should depend on abstractions. Furthermore, abstractions should not depend on details, but details should depend on abstractions. This principle promotes dependency on interfaces and abstractions rather than concrete classes, making code more flexible and extensible.

**Python Example:**

```python
# Good example: Dependency Inversion
class Switchable:
    def turn_on(self):
        pass

    def turn_off(self):
        pass

class LightBulb(Switchable):
    def turn_on(self):
        print("LightBulb turned on")

    def turn_off(self):
        print("LightBulb turned off")

class Fan(Switchable):
    def turn_on(self):
        print("Fan turned on")

    def turn_off(self):
        print("Fan turned off")

class Switch:
    def __init__(self, device):
        self.device = device

    def operate(self):
        if isinstance(self.device, Switchable):
            self.device.turn_on()
        else:
            self.device.turn_off()

# High-level code depends on abstraction (Switchable) rather than concrete implementations (LightBulb, Fan).
```

These examples illustrate how to apply the SOLID principles in Python to write more modular, extensible, and maintainable code.
