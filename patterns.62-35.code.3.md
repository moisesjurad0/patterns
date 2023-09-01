# Patterns (62) | Python Examples

## Behavioral Patterns (17)

### 1. Chain of Responsibility

```python
class Handler:
    def __init__(self, successor=None):
        self.successor = successor

    def handle_request(self, request):
        pass

class ConcreteHandlerA(Handler):
    def handle_request(self, request):
        if request == "A":
            return "ConcreteHandlerA: Handling request A"
        elif self.successor:
            return self.successor.handle_request(request)
        return "ConcreteHandlerA: Cannot handle the request"

class ConcreteHandlerB(Handler):
    def handle_request(self, request):
        if request == "B":
            return "ConcreteHandlerB: Handling request B"
        elif self.successor:
            return self.successor.handle_request(request)
        return "ConcreteHandlerB: Cannot handle the request"

handler_a = ConcreteHandlerA()
handler_b = ConcreteHandlerB(handler_a)
result_a = handler_b.handle_request("A")
result_b = handler_b.handle_request("B")
result_c = handler_b.handle_request("C")

print(result_a)  # Output: "ConcreteHandlerA: Handling request A"
print(result_b)  # Output: "ConcreteHandlerB: Handling request B"
print(result_c)  # Output: "ConcreteHandlerA: Cannot handle the request"
```

### 2. Command

```python
class Receiver:
    def action(self):
        pass

class ConcreteReceiver(Receiver):
    def action(self):
        return "Receiver: Performing an action"

class Command:
    def __init__(self, receiver):
        self.receiver = receiver

    def execute(self):
        pass

class ConcreteCommand(Command):
    def execute(self):
        return self.receiver.action()

class Invoker:
    def __init__(self, command):
        self.command = command

    def invoke(self):
        return self.command.execute()

receiver = ConcreteReceiver()
command = ConcreteCommand(receiver)
invoker = Invoker(command)
result = invoker.invoke()

print(result)  # Output: "Receiver: Performing an action"
```

### 3. Interpreter

```python
class Context:
    def __init__(self):
        self.input = ""
        self.output = ""

class AbstractExpression:
    def interpret(self, context):
        pass

class TerminalExpression(AbstractExpression):
    def interpret(self, context):
        context.output = f"Terminal: {context.input}"

class NonTerminalExpression(AbstractExpression):
    def interpret(self, context):
        context.output = f"Non-Terminal: {context.input}"

context = Context()
terminal_expression = TerminalExpression()
non_terminal_expression = NonTerminalExpression()

context.input = "Data for Terminal"
terminal_expression.interpret(context)
print(context.output)  # Output: "Terminal: Data for Terminal"

context.input = "Data for Non-Terminal"
non_terminal_expression.interpret(context)
print(context.output)  # Output: "Non-Terminal: Data for Non-Terminal"
```

### 4. Iterator

```python
class Iterator:
    def __init__(self):
        self.index = 0

    def has_next(self):
        pass

    def next(self):
        pass

class ConcreteIterator(Iterator):
    def __init__(self, collection):
        super().__init__()
        self.collection = collection

    def has_next(self):
        return self.index < len(self.collection)

    def next(self):
        if self.has_next():
            item = self.collection[self.index]
            self.index += 1
            return item
        return None

class Aggregate:
    def create_iterator(self):
        pass

class ConcreteAggregate(Aggregate):
    def __init__(self):
        self.items = []

    def create_iterator(self):
        return ConcreteIterator(self.items)

    def add_item(self, item):
        self.items.append(item)

aggregate = ConcreteAggregate()
aggregate.add_item("Item 1")
aggregate.add_item("Item 2")
iterator = aggregate.create_iterator()

while iterator.has_next():
    item = iterator.next()
    print(item)

# Output:
# "Item 1"
# "Item 2"
```

### 5. Mediator

```python
class Colleague:
    def __init__(self, mediator):
        self.mediator = mediator

    def send(self, message):
        pass

    def receive(self, message):
        pass

class ConcreteColleagueA(Colleague):
    def send(self, message):
        self.mediator.send_message(self, message)

    def receive(self, message):
        return f"Colleague A received: {message}"

class ConcreteColleagueB(Colleague):
    def send(self, message):
        self.mediator.send_message(self, message)

    def receive(self, message):
        return f"Colleague B received: {message}"

class Mediator:
    def send_message(self, colleague, message):
        pass

class ConcreteMediator(Mediator):
    def __init__(self):
        self.colleague_a = None
        self.colleague_b = None

    def set_colleague_a(self, colleague):
        self.colleague_a = colleague

    def set_colleague_b(self, colleague):
        self.colleague_b = colleague

    def send_message(self, colleague, message):
        if colleague == self.colleague_a:
            return self.colleague_b.receive(message)
        elif colleague == self.colleague_b:
            return self.colleague_a.receive(message)

mediator = ConcreteMediator()
colleague_a = ConcreteColleagueA(mediator)
colleague_b = ConcreteColleagueB(mediator)
mediator.set_colleague_a(colleague_a)
mediator.set_colleague_b(colleague_b)

result_a = colleague_a.send("Hello from A")
result_b = colleague_b.send("Hi from B")

print(result_a)  # Output: "Colleague B received: Hello from A"
print(result_b)  # Output: "Colleague A received: Hi from B"
```

### 6. Memento

```python
class Originator:
    def __init__(self):
        self.state = ""

    def create_memento(self):
        return Memento(self.state)

    def restore_memento(self, memento):
        self.state = memento.get_state()

    def set_state(self, state):
        self.state = state

    def show_state(self):
        return f"Originator State: {self.state}"

class Memento:
    def __init__(self, state):
        self.state = state

    def get_state(self):
        return self.state

caretaker = Caretaker()
originator = Originator()

originator.set_state("State 1")
caretaker.add_memento(originator.create_memento())
originator.set_state("State 2")
caretaker.add_memento(originator.create_memento())
originator.set_state("State 3")
caretaker.add_memento(originator.create_memento())

originator.restore_memento(caretaker.get_memento(1))
result = originator.show_state()

print(result)  # Output: "Originator State: State 2"
```

### 7. Observer

```python
class Observer:
    def update(self, data):
        pass

class ConcreteObserverA(Observer):
    def update(self, data):
        return f"ConcreteObserverA received data: {data}"

class ConcreteObserverB(Observer):
   

 def update(self, data):
        return f"ConcreteObserverB received data: {data}"

class Subject:
    def __init__(self):
        self.observers = []

    def add_observer(self, observer):
        self.observers.append(observer)

    def remove_observer(self, observer):
        self.observers.remove(observer)

    def notify_observers(self, data):
        for observer in self.observers:
            observer.update(data)

subject = Subject()
observer_a = ConcreteObserverA()
observer_b = ConcreteObserverB()
subject.add_observer(observer_a)
subject.add_observer(observer_b)

result = []
subject.notify_observers("Hello")

for observer in subject.observers:
    result.append(observer.update("Hello"))

print(result)
# Output:
# ["ConcreteObserverA received data: Hello", "ConcreteObserverB received data: Hello"]
```

### 8. State

```python
class State:
    def handle(self):
        pass

class ConcreteStateA(State):
    def handle(self):
        return "ConcreteStateA is handling the request"

class ConcreteStateB(State):
    def handle(self):
        return "ConcreteStateB is handling the request"

class Context:
    def __init__(self):
        self.state = None

    def set_state(self, state):
        self.state = state

    def request(self):
        if self.state:
            return self.state.handle()

context = Context()
state_a = ConcreteStateA()
state_b = ConcreteStateB()

context.set_state(state_a)
result_a = context.request()

context.set_state(state_b)
result_b = context.request()

print(result_a)  # Output: "ConcreteStateA is handling the request"
print(result_b)  # Output: "ConcreteStateB is handling the request"
```

### 9. Strategy

```python
class Strategy:
    def execute(self):
        pass

class ConcreteStrategyA(Strategy):
    def execute(self):
        return "ConcreteStrategyA is executing"

class ConcreteStrategyB(Strategy):
    def execute(self):
        return "ConcreteStrategyB is executing"

class Context:
    def __init__(self, strategy):
        self.strategy = strategy

    def execute_strategy(self):
        return self.strategy.execute()

strategy_a = ConcreteStrategyA()
strategy_b = ConcreteStrategyB()

context_a = Context(strategy_a)
result_a = context_a.execute_strategy()

context_b = Context(strategy_b)
result_b = context_b.execute_strategy()

print(result_a)  # Output: "ConcreteStrategyA is executing"
print(result_b)  # Output: "ConcreteStrategyB is executing"
```

### 10. Template Method

```python
class AbstractClass:
    def template_method(self):
        result = self.operation1()
        result += self.operation2()
        return result

    def operation1(self):
        pass

    def operation2(self):
        pass

class ConcreteClassA(AbstractClass):
    def operation1(self):
        return "ConcreteClassA: Operation 1"

    def operation2(self):
        return "ConcreteClassA: Operation 2"

class ConcreteClassB(AbstractClass):
    def operation1(self):
        return "ConcreteClassB: Operation 1"

    def operation2(self):
        return "ConcreteClassB: Operation 2"

client_a = ConcreteClassA()
result_a = client_a.template_method()

client_b = ConcreteClassB()
result_b = client_b.template_method()

print(result_a)  # Output: "ConcreteClassA: Operation 1ConcreteClassA: Operation 2"
print(result_b)  # Output: "ConcreteClassB: Operation 1ConcreteClassB: Operation 2"
```

### 11. Visitor

```python
class Element:
    def accept(self, visitor):
        pass

class ConcreteElementA(Element):
    def accept(self, visitor):
        return visitor.visit_element_a(self)

class ConcreteElementB(Element):
    def accept(self, visitor):
        return visitor.visit_element_b(self)

class Visitor:
    def visit_element_a(self, element):
        pass

    def visit_element_b(self, element):
        pass

class ConcreteVisitorA(Visitor):
    def visit_element_a(self, element):
        return f"ConcreteVisitorA visited {element.__class__.__name__}"

    def visit_element_b(self, element):
        return f"ConcreteVisitorA visited {element.__class__.__name__}"

class ConcreteVisitorB(Visitor):
    def visit_element_a(self, element):
        return f"ConcreteVisitorB visited {element.__class__.__name__}"

    def visit_element_b(self, element):
        return f"ConcreteVisitorB visited {element.__class__.__name__}"

elements = [ConcreteElementA(), ConcreteElementB()]
visitors = [ConcreteVisitorA(), ConcreteVisitorB()]

results = []

for visitor in visitors:
    for element in elements:
        result = element.accept(visitor)
        results.append(result)

print(results)
# Output:
# ["ConcreteVisitorA visited ConcreteElementA", "ConcreteVisitorA visited ConcreteElementB",
#  "ConcreteVisitorB visited ConcreteElementA", "ConcreteVisitorB visited ConcreteElementB"]
```

### 12. Null Object

```python
class AbstractCustomer:
    def is_null(self):
        pass

    def get_name(self):
        pass

class RealCustomer(AbstractCustomer):
    def __init__(self, name):
        self.name = name

    def is_null(self):
        return False

    def get_name(self):
        return self.name

class NullCustomer(AbstractCustomer):
    def is_null(self):
        return True

    def get_name(self):
        return "Not Available"

customers = [RealCustomer("Alice"), RealCustomer("Bob"), NullCustomer()]

for customer in customers:
    print(f"Customer: {customer.get_name()}, Null: {customer.is_null()}")
# Output:
# "Customer: Alice, Null: False"
# "Customer: Bob, Null: False"
# "Customer: Not Available, Null: True"
```

### 13. Servant

```python
class Servant:
    def serve(self):
        pass

class Maid(Servant):
    def serve(self):
        return "Maid: Serving breakfast"

class Butler(Servant):
    def serve(self):
        return "Butler: Serving tea"

class Guest:
    def __init__(self, servant):
        self.servant = servant

    def make_request(self):
        return self.servant.serve()

maid = Maid()
butler = Butler()

guest1 = Guest(maid)
guest2 = Guest(butler)

result1 = guest1.make_request()
result2 = guest2.make_request()

print(result1)  # Output: "Maid: Serving breakfast"
print(result2)  # Output: "Butler: Serving tea"
```

### 14. Specification

```python
class Specification:
    def is_satisfied(self, item):
        pass

class Item:
    def __init__(self, name, size, price):
        self.name = name
        self.size = size
        self.price = price

class SizeSpecification(Specification):
    def __init__(self, size):
        self.size = size

    def is_satisfied(self, item):
        return item.size == self.size

class PriceSpecification(Specification):
    def __init__(self, price):
        self.price = price

    def is_satisfied(self, item):
        return item.price == self.price

class AndSpecification(Specification):
    def __init__(self, spec1, spec2):
        self.spec1 = spec1
        self.spec2 = spec2

    def is_satisfied(self, item):
        return self.spec1.is_satisfied(item) and self.spec2.is_satisfied(item)

item1 = Item("Shirt", "Large", 20)
item2 = Item("Pants", "Medium", 30)
item3 = Item("Hat", "Small", 10)

large_spec = SizeSpecification("Large")
cheap_spec = PriceSpecification(20)

spec = AndSpecification(large_spec, cheap_spec)

items = [item1, item2, item3]
filtered_items = [item for item in items if spec.is_satisfied(item)]

for item in filtered_items:
    print(f"{item.name}: Size {item.size}, Price ${item.price}")
# Output:
# "Shirt: Size Large, Price $20"
```

### 15. Command Processor

```python
class Command:
    def execute(self):
        pass

class Light:
    def on(self):
        return "Light is on"

    def off(self):
        return "Light is off"

class LightOnCommand(Command):
    def __init__(self, light):
        self.light = light

    def execute(self):
        return self.light.on()

class LightOffCommand(Command):
    def __init__(self, light):
        self.light = light

    def execute(self):
        return self.light.off()

class RemoteControl:
    def __init__(self):
        self.command = None

    def set_command(self, command):
        self.command = command

    def press_button(self):
        if self.command:
            return self.command.execute()

light = Light()
light_on = LightOnCommand(light)
light_off = LightOffCommand(light)

remote = RemoteControl()

remote.set_command(light_on)
result1 = remote.press_button()

remote.set_command(light_off)
result2 = remote.press_button()

print(result1)  # Output: "Light is on"
print(result2)  # Output: "Light is off"
```

### 16. Event Aggregator

```python
class EventAggregator:
    def __init__(self):
        self.subscribers = []

    def add_subscriber(self, subscriber):
        self.subscribers.append(subscriber)

    def publish_event(self, event):
        for subscriber in self.subscribers:
            subscriber.handle_event(event)

class Subscriber:
    def handle_event(self, event):
        pass

class Logger(Subscriber):
    def handle_event(self, event):
        print(f"Logger received event: {event}")

class Emailer(Subscriber):
    def handle_event(self, event):
        print(f"Emailer received event: {event}")

class Event:
    def __init__(self, name):
        self.name = name

event_aggregator = EventAggregator()
logger = Logger()
emailer = Emailer()

event_aggregator.add_subscriber(logger)
event_aggregator.add_subscriber(emailer)

event1 = Event("Event 1")
event2 = Event("Event 2")

event_aggregator.publish_event(event1)
event_aggregator.publish_event(event2)
# Output:
# "Logger received event: Event 1"
# "Emailer received event: Event 1"
# "Logger received event: Event 2"
# "Emailer received event: Event 2"
```

### 17. Publish-Subscribe

```python
from abc import ABC, abstractmethod

class Publisher:
    def __init__(self):
        self.subscribers = []

    def add_subscriber(self, subscriber):
        self.subscribers.append(subscriber)

    def remove_subscriber(self, subscriber):
        self.subscribers.remove(subscriber)

    def notify_subscribers(self, message):
        for subscriber in self.subscribers:
            subscriber.update(message)

class Subscriber(ABC):
    @abstractmethod
    def update(self, message):
        pass

class ConcreteSubscriberA(Subscriber):
    def update(self, message):
        print(f"ConcreteSubscriberA received message: {message}")

class ConcreteSubscriberB(Subscriber):
    def update(self, message):
        print(f"ConcreteSubscriberB received message: {message}")

publisher = Publisher()
subscriber_a = ConcreteSubscriberA()
subscriber_b = ConcreteSubscriberB()

publisher.add_subscriber(subscriber_a)
publisher.add_subscriber(subscriber_b)

publisher.notify_subscribers("Hello, subscribers!")
# Output:
# "ConcreteSubscriberA received message: Hello, subscribers!"
# "ConcreteSubscriberB received message: Hello, subscribers!"
```
