# Patterns (62) | Python Examples

## Architectural Patterns (15)

### 1. Model-View-Controller (MVC)

```python
class Model:
    def __init__(self, data):
        self.data = data

    def get_data(self):
        return self.data

class View:
    def show_data(self, data):
        print(f"View: Displaying data - {data}")

class Controller:
    def __init__(self, model, view):
        self.model = model
        self.view = view

    def update_view(self):
        data = self.model.get_data()
        self.view.show_data(data)

model = Model("Sample Data")
view = View()
controller = Controller(model, view)

controller.update_view()
# Output: "View: Displaying data - Sample Data"
```

### 2. Model-View-Presenter (MVP)

```python
class Model:
    def __init__(self, data):
        self.data = data

    def get_data(self):
        return self.data

class View:
    def set_data(self, data):
        print(f"View: Setting data - {data}")

class Presenter:
    def __init__(self, model, view):
        self.model = model
        self.view = view

    def update_view(self):
        data = self.model.get_data()
        self.view.set_data(data)

model = Model("Sample Data")
view = View()
presenter = Presenter(model, view)

presenter.update_view()
# Output: "View: Setting data - Sample Data"
```

### 3. Model-View-ViewModel (MVVM)

```python
import tkinter as tk

class Model:
    def __init__(self, data):
        self.data = data

    def get_data(self):
        return self.data

class ViewModel:
    def __init__(self, model):
        self.model = model

    def get_data(self):
        return self.model.get_data()

class View:
    def __init__(self, root, view_model):
        self.root = root
        self.view_model = view_model
        self.label = tk.Label(root, text=self.view_model.get_data())
        self.label.pack()

model = Model("Sample Data")
view_model = ViewModel(model)
root = tk.Tk()
view = View(root, view_model)
root.mainloop()
```

### 4. Layered Architecture

La arquitectura en capas es un enfoque de organización de un sistema en capas con responsabilidades específicas. No proporcionaré un ejemplo específico, ya que la implementación puede variar según las necesidades del proyecto.

### 5. Microservices

La arquitectura de microservicios es un enfoque en el que una aplicación se divide en pequeños servicios independientes que se pueden desarrollar, desplegar y escalar de forma independiente. La implementación de microservicios puede variar significativamente según el proyecto.

### 6. Service-Oriented Architecture (SOA)

La arquitectura orientada a servicios (SOA) es un enfoque que utiliza servicios independientes para lograr funcionalidades específicas y se comunica a través de estándares como HTTP o SOAP. La implementación de SOA puede variar según las tecnologías utilizadas.

### 7. Repository Pattern

El patrón Repository se utiliza para separar la lógica que recupera los datos de la lógica del negocio. No proporcionaré un ejemplo específico, ya que su implementación puede variar según el lenguaje y el marco de trabajo utilizados.

### 8. Unit of Work

El patrón Unit of Work se utiliza para gestionar transacciones y cambios en la base de datos. No proporcionaré un ejemplo específico, ya que su implementación puede variar según el lenguaje y el marco de trabajo utilizados.

### 9. CQRS (Command Query Responsibility Segregation)

CQRS es una arquitectura que separa las operaciones de lectura y escritura de los datos. No proporcionaré un ejemplo específico, ya que su implementación puede variar según el lenguaje y el marco de trabajo utilizados.

### 10. Event Sourcing

Event Sourcing es una técnica en la que se almacenan todos los cambios en el estado de una aplicación como eventos. No proporcionaré un ejemplo específico, ya que su implementación puede variar según el lenguaje y el marco de trabajo utilizados.

### 11. Hexagonal Architecture

La arquitectura hexagonal (también conocida como puertos y adaptadores) se enfoca en aislar el núcleo de la aplicación de los detalles técnicos y de infraestructura. No proporcionaré un ejemplo específico, ya que su implementación puede variar según el lenguaje y el marco de trabajo utilizados.

### 12. Clean Architecture

La arquitectura limpia se basa en el principio de separación de preocupaciones y dependencias inversas. No proporcionaré un ejemplo específico, ya que su implementación puede variar según el lenguaje y el marco de trabajo utilizados.

### 13. Domain-Driven Design (DDD)

El Diseño Guiado por el Dominio (DDD) es un enfoque que se centra en el diseño del dominio del problema. No proporcionaré un ejemplo específico, ya que su implementación puede variar según el lenguaje y el marco de trabajo utilizados.

### 14. Pipes and Filters

Pipes and Filters es una arquitectura que divide el procesamiento en una serie de etapas independientes. No proporcionaré un ejemplo específico, ya que su implementación puede variar según el lenguaje y el marco de trabajo utilizados.

### 15. Blackboard Pattern

El patrón Blackboard es un enfoque de solución de problemas que involucra múltiples fuentes de conocimiento colaborando para resolver un problema. No proporcionaré un ejemplo específico, ya que su implementación puede variar según las necesidades del proyecto.

Ten en cuenta que la implementación de estos patrones puede variar según las tecnologías y marcos de trabajo utilizados en tu proyecto. Los ejemplos anteriores son conceptuales y pueden requerir adaptaciones específicas para tu caso de uso.
