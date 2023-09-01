# Patterns (62) | Python Examples

## Creational Patterns (7)

### 1. Singleton

```python
class Singleton:
    _instance = None

    def __new__(cls):
        if cls._instance is None:
            cls._instance = super(Singleton, cls).__new__(cls)
            cls._instance.value = None
        return cls._instance

singleton1 = Singleton()
singleton1.value = "First Instance Value"

singleton2 = Singleton()
print(singleton2.value)  # Output: "First Instance Value"
```

### 2. Factory Method

```python
from abc import ABC, abstractmethod

class Creator(ABC):
    @abstractmethod
    def factory_method(self):
        pass

class ConcreteCreatorA(Creator):
    def factory_method(self):
        return ConcreteProductA()

class ConcreteCreatorB(Creator):
    def factory_method(self):
        return ConcreteProductB()

class Product(ABC):
    @abstractmethod
    def operation(self):
        pass

class ConcreteProductA(Product):
    def operation(self):
        return "Product A Operation"

class ConcreteProductB(Product):
    def operation(self):
        return "Product B Operation"

creator_a = ConcreteCreatorA()
product_a = creator_a.factory_method()
print(product_a.operation())  # Output: "Product A Operation"

creator_b = ConcreteCreatorB()
product_b = creator_b.factory_method()
print(product_b.operation())  # Output: "Product B Operation"
```

### 3. Abstract Factory

```python
from abc import ABC, abstractmethod

class AbstractFactory(ABC):
    @abstractmethod
    def create_product_a(self):
        pass

    @abstractmethod
    def create_product_b(self):
        pass

class ConcreteFactory1(AbstractFactory):
    def create_product_a(self):
        return ConcreteProductA1()

    def create_product_b(self):
        return ConcreteProductB1()

class ConcreteFactory2(AbstractFactory):
    def create_product_a(self):
        return ConcreteProductA2()

    def create_product_b(self):
        return ConcreteProductB2()

class AbstractProductA(ABC):
    @abstractmethod
    def operation_a(self):
        pass

class ConcreteProductA1(AbstractProductA):
    def operation_a(self):
        return "Product A1 Operation A"

class ConcreteProductA2(AbstractProductA):
    def operation_a(self):
        return "Product A2 Operation A"

class AbstractProductB(ABC):
    @abstractmethod
    def operation_b(self):
        pass

class ConcreteProductB1(AbstractProductB):
    def operation_b(self):
        return "Product B1 Operation B"

class ConcreteProductB2(AbstractProductB):
    def operation_b(self):
        return "Product B2 Operation B"

factory1 = ConcreteFactory1()
productA1 = factory1.create_product_a()
productB1 = factory1.create_product_b()

print(productA1.operation_a())  # Output: "Product A1 Operation A"
print(productB1.operation_b())  # Output: "Product B1 Operation B"
```

### 4. Builder

```python
class Director:
    def construct(self, builder):
        builder.build_part_a()
        builder.build_part_b()

class Builder:
    def __init__(self):
        self.product = Product()

    def build_part_a(self):
        pass

    def build_part_b(self):
        pass

class ConcreteBuilder(Builder):
    def build_part_a(self):
        self.product.add("Part A")

    def build_part_b(self):
        self.product.add("Part B")

class Product:
    def __init__(self):
        self.parts = []

    def add(self, part):
        self.parts.append(part)

    def show(self):
        print("Product Parts: ", ", ".join(self.parts))

builder = ConcreteBuilder()
director = Director()
director.construct(builder)
product = builder.product
product.show()  # Output: "Product Parts: Part A, Part B"
```

### 5. Prototype

```python
import copy

class Prototype:
    def clone(self):
        return copy.deepcopy(self)

class ConcretePrototype(Prototype):
    def __init__(self, data):
        self.data = data

    def show(self):
        print("Data:", self.data)

prototype = ConcretePrototype("Original Data")
clone = prototype.clone()
clone.show()  # Output: "Data: Original Data"
```

### 6. Object Pool

```python
class ObjectPool:
    def __init__(self):
        self._objects = set()

    def acquire(self):
        if not self._objects:
            return Object()
        return self._objects.pop()

    def release(self, obj):
        self._objects.add(obj)

class Object:
    def operation(self):
        return "Object Operation"

# Usage
pool = ObjectPool()
obj1 = pool.acquire()
print(obj1.operation())  # Output: "Object Operation"
pool.release(obj1)

obj2 = pool.acquire()
print(obj2.operation())  # Output: "Object Operation"
```

### 7. Dependency Injection

```python
class DatabaseConnection:
    def connect(self):
        return "Connected to Database"

class Logger:
    def log(self, message):
        return f"Logged: {message}"

class UserService:
    def __init__(self, database, logger):
        self.database = database
        self.logger = logger

    def user_data(self, username):
        self.logger.log(f"Getting data for {username}")
        return self.database.connect()

# Usage with Dependency Injection
db_connection = DatabaseConnection()
logger = Logger()
user_service = UserService(db_connection, logger)
print(user_service.user_data("John"))
# Output:
# Logged: Getting data for John
# Connected to Database
```

## Structural Patterns (11)

### 1. Adapter

```python
class OldSystem:
    def legacy_operation(self):
        return "Legacy System Operation"

class Adapter:
    def __init__(self, old_system):
        self.old_system = old_system

    def new_operation(self):
        return f"Adapter: {self.old_system.legacy_operation()}"

old_system = OldSystem()
adapter = Adapter(old_system)
print(adapter.new_operation())  # Output: "Adapter: Legacy System Operation"
```

### 2. Bridge

```python
class Abstraction:
    def __init__(self, implementation):
        self.implementation = implementation

    def operation(self):
        return f"Abstraction: {self.implementation.operation_impl()}"

class Implementation:
    def operation_impl(self):
        pass

class ConcreteImplementationA(Implementation):
    def operation_impl(self):
        return "Concrete Implementation A Operation"

class ConcreteImplementationB(Implementation):
    def operation_impl(self):
        return "Concrete Implementation B Operation"

implementation_a = ConcreteImplementationA()
abstraction_a = Abstraction(implementation_a)
print(abstraction_a.operation())  # Output: "Abstraction: Concrete Implementation A Operation"

implementation_b = ConcreteImplementationB()
abstraction_b = Abstraction(implementation_b)
print(abstraction_b.operation())  # Output: "Abstraction: Concrete Implementation B Operation"
```

### 3. Composite

```python
class Component:
    def operation(self):
        pass

class Leaf(Component):
    def operation(self):
        return "Leaf Operation"

class Composite(Component):
    def __init__(self):
        self.children = []

    def add(self, child):
        self.children.append(child)

    def operation(self):
        results = []
        for child in self.children:
            results.append(child.operation())
        return f"Composite Operation: [{' + '.join(results)}']"

leaf1 = Leaf()
leaf2 = Leaf()
composite = Composite()
composite.add(leaf1)
composite.add(leaf2)

print(leaf1.operation())  # Output: "Leaf Operation"
print(composite.operation())  # Output: "Composite Operation: [Leaf Operation.Leaf Operation]"
```

### 4. Decorator

```python
class Component:
    def operation(self):
        pass

class ConcreteComponent(Component):
    def operation(self):
        return "Concrete Component Operation"

class Decorator(Component):
    def __init__(self, component):
        self.component = component

    def operation(self):
        return f"Decorator Operation: {self.component.operation()}"

component = ConcreteComponent()
decorator = Decorator(component)
print(decorator.operation())  # Output: "Decorator Operation: Concrete Component Operation"
```

### 5. Facade

```python
class SubsystemA:
    def operation_a(self):
        return "Subsystem A Operation"

class SubsystemB:
    def operation_b(self):
        return "Subsystem B Operation"

class Facade:
    def __init__(self):
        self.subsystem_a = SubsystemA()
        self.subsystem_b = SubsystemB()

    def operation(self):
        result_a = self.subsystem_a.operation_a()
        result_b = self.subsystem_b.operation_b()
        return f"Facade Operation: {result_a}, {result_b}"

facade = Facade()
print(facade.operation())  # Output: "Facade Operation: Subsystem A Operation, Subsystem B Operation"
```

### 6. Flyweight

```python
class Flyweight:
    def operation(self):
        pass

class ConcreteFlyweight(Flyweight):
    def operation(self):
        return "Concrete Flyweight Operation"

class FlyweightFactory:
    def __init__(self):
        self.flyweights = {}

    def get_flyweight(self, key):
        if key not in self.flyweights:
            self.flyweights[key] = ConcreteFlyweight()
        return self.flyweights[key]

factory = FlyweightFactory()
flyweight1 = factory.get_flyweight("key1")
flyweight2 = factory.get_flyweight("key2")

print(flyweight1.operation())  # Output: "Concrete Flyweight Operation"
print(flyweight2.operation())  # Output: "Concrete Flyweight Operation"
```

### 7. Proxy

```python
class Subject:
    def request(self):
        pass

class RealSubject(Subject):
    def request(self):
        return "Real Subject Request"

class Proxy(Subject):
    def __init__(self, real_subject):
        self.real_subject = real_subject

    def request(self):
        return f"Proxy Request: {self.real_subject.request()}"

real_subject = RealSubject()
proxy = Proxy(real_subject)
print(proxy.request())  # Output: "Proxy Request: Real Subject Request"
```

### 8. Module

```python
# Create a Python module named "my_module.py" with the following content:
# def greeting(name):
#     return f"Hello, {name}!"

# In another Python script, you can use this module as follows:
# import my_module
# message = my_module.greeting("John")
# print(message)  # Output: "Hello, John!"
```

### 9. Private Class Data

```python
class PrivateData:
    def __init__(self):
        self.__data = None

    def get_data(self):
        return self.__data

    def set_data(self, data):
        self.__data = data

private_data = PrivateData()
private_data.set_data("Sensitive Data")
print(private_data.get_data())  # Output: "Sensitive Data"
```

### 10. Faceted

```python
class PersonBuilder:
    def __init__(self):
        self.person = Person()

    def build(self):
        return self.person

    def name(self, name):
        self.person.name = name
        return self

    def age(self, age):
        self.person.age = age
        return self

    def address(self, address):
        self.person.address = address
        return self

class Person:
    def __init__(self):
        self.name = None
        self.age = None
        self.address = None

    def __str__(self):
        return f"Name: {self.name}, Age: {self.age}, Address: {self.address}"

builder = PersonBuilder()
person = builder.name("John").age

(30).address("123 Main St").build()
print(person)  # Output: "Name: John, Age: 30, Address: 123 Main St"
```

### 11. Pluggable Selector

```python
class Selector:
    def select(self, data):
        pass

class ConcreteSelectorA(Selector):
    def select(self, data):
        return [x for x in data if x % 2 == 0]

class ConcreteSelectorB(Selector):
    def select(self, data):
        return [x for x in data if x % 2 != 0]

data = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
selector_a = ConcreteSelectorA()
result_a = selector_a.select(data)
print(result_a)  # Output: [2, 4, 6, 8, 10]

selector_b = ConcreteSelectorB()
result_b = selector_b.select(data)
print(result_b)  # Output: [1, 3, 5, 7, 9]
```
