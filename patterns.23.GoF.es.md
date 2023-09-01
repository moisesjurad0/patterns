# patterns GoF | 23

## Patrones Creacionales | 5

1. **Singleton:** Asegura que una clase tenga solo una instancia y proporciona un punto de acceso global a esa instancia.
2. **Factory Method:** Define una interfaz para crear un objeto, pero permite a las subclases alterar el tipo de objetos que se crean.
3. **Abstract Factory:** Proporciona una interfaz para crear familias de objetos relacionados sin especificar sus clases concretas.
4. **Builder:** Separar la construcción de un objeto complejo de su representación, permitiendo la creación de diferentes representaciones.
5. **Prototype:** Permite la creación de nuevos objetos copiando un objeto existente, conocido como prototipo.

## Patrones Estructurales | 7

1. **Adapter:** Permite que interfaces incompatibles trabajen juntas, convirtiendo la interfaz de una clase en otra esperada por el cliente.
2. **Bridge:** Separa una abstracción de su implementación para que ambas puedan variar independientemente.
3. **Composite:** Permite componer objetos en estructuras de árbol para representar jerarquías de parte-todo.
4. **Decorator:** Agrega comportamiento adicional a objetos dinámicamente, sin afectar a otros objetos del mismo tipo.
5. **Facade:** Proporciona una interfaz simplificada para un conjunto más grande de clases y funcionalidades.
6. **Flyweight:** Comparte de manera eficiente objetos que son utilizados comúnmente para conservar recursos.
7. **Proxy:** Controla el acceso a un objeto proporcionando un representante o sustituto.

## Patrones de Comportamiento | 11

1. **Chain of Responsibility:** Permite pasar una solicitud a lo largo de una cadena de manejadores. Cada manejador decide si procesa la solicitud o la pasa al siguiente.
2. **Command:** Encapsula una solicitud como un objeto, permitiendo parametrizar los objetos con operaciones y realizar operaciones encoladas, reversibles o registrables.
3. **Interpreter:** Define una gramática para un lenguaje y proporciona un intérprete para evaluar sentencias en ese lenguaje.
4. **Iterator:** Proporciona una forma de acceder secuencialmente a los elementos de una colección sin exponer su representación subyacente.
5. **Mediator:** Define un objeto que coordina la comunicación entre objetos en lugar de que estos se comuniquen directamente.
6. **Memento:** Captura y externaliza el estado interno de un objeto de manera que el objeto pueda ser restaurado a ese estado en el futuro.
7. **Observer:** Define una dependencia uno a muchos entre objetos para que cuando uno cambie su estado, todos sus dependientes sean notificados y actualizados automáticamente.
8. **State:** Permite que un objeto altere su comportamiento cuando su estado interno cambia. El objeto parecerá cambiar de clase.
9. **Strategy:** Define una familia de algoritmos, encapsula cada uno de ellos y los hace intercambiables. Permite que el algoritmo varíe independientemente de los clientes que lo usan.
10. **Template Method:** Define el esqueleto de un algoritmo en una operación, permitiendo que las subclases modifiquen ciertos pasos de ese algoritmo.
11. **Visitor:** Permite agregar operaciones adicionales a objetos sin tener que modificarlos.
