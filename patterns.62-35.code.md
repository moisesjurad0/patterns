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
