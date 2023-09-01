# Patterns (62) | Python Examples

## Anti-Patterns (4)

### 1. Big Ball of Mud

El anti-patrón "Big Ball of Mud" se refiere a un código que es desordenado, difícil de mantener y carece de una estructura organizada. Aquí tienes un ejemplo simplificado:

```python
# Un ejemplo de "Big Ball of Mud" en Python
def big_ball_of_mud():
    # Este código es desorganizado y no sigue las mejores prácticas
    # No hay estructura ni modularidad
    print("This is a Big Ball of Mud!")

big_ball_of_mud()
```

### 2. Spaghetti Code

El anti-patrón "Spaghetti Code" se refiere a un código extremadamente desorganizado en el que las partes del programa están interconectadas de manera confusa. Aquí tienes un ejemplo:

```python
# Ejemplo de "Spaghetti Code" en Python
def step1():
    print("Step 1: Perform some task")

def step2():
    print("Step 2: Do something else")

def step3():
    print("Step 3: Continue the process")

def main():
    step1()
    step2()
    step3()

main()
```

### 3. God Object

El anti-patrón "God Object" se refiere a una clase que asume demasiadas responsabilidades y se convierte en un punto de mantenimiento complicado. Aquí tienes un ejemplo:

```python
# Ejemplo de "God Object" en Python
class GodObject:
    def __init__(self):
        self.data = []

    def add_data(self, item):
        self.data.append(item)

    def process_data(self):
        # Realiza múltiples tareas de procesamiento en los datos
        for item in self.data:
            # Realiza algún procesamiento
            pass

god = GodObject()
god.add_data("Item 1")
god.add_data("Item 2")
god.process_data()
```

### 4. Singletonitis

El anti-patrón "Singletonitis" se refiere a un exceso de uso del patrón Singleton en un código, lo que puede llevar a problemas de mantenimiento y acoplamiento excesivo. Aquí tienes un ejemplo:

```python
# Ejemplo de "Singletonitis" en Python
class Singleton:
    _instance = None

    def __new__(cls):
        if cls._instance is None:
            cls._instance = super(Singleton, cls).__new__(cls)
        return cls._instance

class SingletonClient:
    def __init__(self, name):
        self.name = name
        self.singleton = Singleton()

client1 = SingletonClient("Client 1")
client2 = SingletonClient("Client 2")

print(client1.singleton is client2.singleton)  # Ambos usan la misma instancia Singleton
```
