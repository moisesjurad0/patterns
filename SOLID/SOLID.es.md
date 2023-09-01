# SOLID | es

Estos principios SOLID son fundamentales para escribir código orientado a objetos de alta calidad y ayudan a mejorar la mantenibilidad y extensibilidad del software a lo largo del tiempo.

Los principios SOLID son un conjunto de pautas de diseño de software que ayudan a crear código más limpio, mantenible y extensible. Cada letra en "SOLID" representa uno de estos principios:

Estos ejemplos ilustran cómo aplicar los principios SOLID en Python para escribir código más modular, extensible y mantenible

## Principios SOLID

### 1. Principio de Responsabilidad Única (SRP)

- **Explicación:** Una clase debe tener una única razón para cambiar. Esto significa que una clase debe tener una única responsabilidad y no debe tener más de una razón para cambiar. Si una clase tiene más de una responsabilidad, es más probable que cambie debido a diferentes razones, lo que puede hacer que el código sea más frágil y difícil de mantener.

**Ejemplo en Python:**

```python
# Mal ejemplo: Una clase con múltiples responsabilidades
class Customer:
    def __init__(self, name):
        self.name = name

    def calculate_discount(self, order):
        # Cálculo del descuento
        pass

    def send_email_confirmation(self, order):
        # Envío de correo de confirmación
        pass
```

### 2. Principio de Abierto/Cerrado (OCP)

- **Explicación:** Las entidades de software (clases, módulos, etc.) deben estar abiertas para su extensión pero cerradas para su modificación. Esto significa que debe ser posible agregar nuevas funcionalidades a un sistema sin modificar el código existente. La extensión se logra a través de la herencia, la composición y la implementación de interfaces.

**Ejemplo en Python:**

```python
# Buen ejemplo: Extensión a través de herencia
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

### 3. Principio de Sustitución de Liskov (LSP)

- **Explicación:** Las subclases deben ser sustituibles por sus clases base sin afectar la integridad del programa. Esto significa que si una clase A es una subclase de una clase B, cualquier instancia de B debe poder reemplazarse por una instancia de A sin que el programa se comporte incorrectamente.

**Ejemplo en Python:**

```python
# Buen ejemplo: Sustitución de Liskov
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

### 4. Principio de Segregación de Interfaces (ISP)

- **Explicación:** Los clientes no deben verse obligados a depender de interfaces que no utilizan. En lugar de tener una única interfaz grande, es preferible tener varias interfaces más pequeñas y específicas que los clientes puedan implementar según sus necesidades. Esto evita que los clientes dependan de métodos que no utilizan.

**Ejemplo en Python:**

```python
# Buen ejemplo: Interfaces segregadas
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

### 5. Principio de Inversión de Dependencia (DIP)

- **Explicación:** Los módulos de alto nivel no deben depender de módulos de bajo nivel. Ambos deben depender de abstracciones. Además, las abstracciones no deben depender de los detalles, sino que los detalles deben depender de las abstracciones. Este principio promueve la dependencia de interfaces y abstracciones en lugar de clases concretas, lo que facilita la flexibilidad y la extensibilidad del código.

**Ejemplo en Python:**

```python
# Buen ejemplo: Inversión de Dependencia
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

# El código de alto nivel depende de la abstracción (Switchable) en lugar de las implementaciones concretas (LightBulb, Fan).
```
