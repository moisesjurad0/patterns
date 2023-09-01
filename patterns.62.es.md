# Patrones de Diseño (62)

## Patrones Creacionales (7)

1. **Singleton:** Asegura que una clase tenga solo una instancia y proporciona un punto de acceso global a esa instancia.
2. **Factory Method:** Define una interfaz para crear un objeto, pero permite a las subclases alterar el tipo de objetos que se crean.
3. **Abstract Factory:** Proporciona una interfaz para crear familias de objetos relacionados sin especificar sus clases concretas.
4. **Builder:** Separar la construcción de un objeto complejo de su representación, permitiendo la creación de diferentes representaciones.
5. **Prototype:** Permite la creación de nuevos objetos copiando un objeto existente, conocido como prototipo.
6. **Object Pool:** Mantiene un conjunto de objetos en espera para ser reutilizados, mejorando el rendimiento y la eficiencia.
7. **Dependency Injection:** Suministra dependencias externas a una clase en lugar de crearlas internamente, promoviendo la flexibilidad y la prueba.

## Patrones Estructurales (11)

1. **Adapter:** Permite que interfaces incompatibles trabajen juntas, convirtiendo la interfaz de una clase en otra esperada por el cliente.
2. **Bridge:** Separa una abstracción de su implementación para que ambas puedan variar independientemente.
3. **Composite:** Permite componer objetos en estructuras de árbol para representar jerarquías de parte-todo.
4. **Decorator:** Agrega comportamiento adicional a objetos dinámicamente, sin afectar a otros objetos del mismo tipo.
5. **Facade:** Proporciona una interfaz simplificada para un conjunto más grande de clases y funcionalidades.
6. **Flyweight:** Comparte de manera eficiente objetos que son utilizados comúnmente para conservar recursos.
7. **Proxy:** Controla el acceso a un objeto proporcionando un representante o sustituto.
8. **Module:** Organiza el código en módulos que pueden ser cargados y descargados dinámicamente en tiempo de ejecución.
9. **Private Class Data:** Oculta los detalles de implementación de una clase al limitar el acceso a sus datos internos.
10. **Faceted:** Proporciona una interfaz sencilla para un conjunto complejo de subcomponentes.
11. **Pluggable Selector:** Permite que los clientes elijan entre varias implementaciones de un componente a través de una interfaz común.

## Patrones de Comportamiento (17)

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
12. **Null Object:** Proporciona un objeto de reemplazo que no hace nada, evitando comprobaciones nulas.
13. **Servant:** Ofrece algunas de sus funcionalidades a objetos colaboradores sin tener que duplicar el código.
14. **Specification:** Define una serie de reglas de negocio que se pueden combinar para formar una especificación compleja.
15. **Command Processor:** Gestiona comandos y su ejecución de manera eficiente y concurrente.
16. **Event Aggregator:** Permite que objetos se suscriban y reciban notificaciones de eventos desde múltiples fuentes.
17. **Publish-Subscribe:** Permite a objetos suscribirse y recibir notificaciones de eventos generados por otros objetos.

## Patrones de Arquitectura (15)

1. **Modelo-Vista-Controlador (MVC):** Separa una aplicación en tres componentes interconectados: Modelo (datos y lógica de negocio), Vista (interfaz de usuario) y Controlador (gestiona la entrada del usuario y la comunicación).
2. **Modelo-Vista-Presentador (MVP):** Separa una aplicación en Modelo (lógica de negocio y datos), Vista (interfaz de usuario) y Presentador (maneja la entrada del usuario y comunica entre Modelo y Vista).
3. **Modelo-Vista-ViewModel (MVVM):** Separa una aplicación en Modelo (datos y lógica), Vista (interfaz de usuario) y ViewModel (gestiona la lógica de presentación y la comunicación entre Modelo y Vista).
4. **Arquitectura en Capas:** Organiza una aplicación en capas distintas (por ejemplo, presentación, lógica de negocio, datos) para mejorar la modularidad y el mantenimiento.
5. **Microservicios:** Descompone una aplicación en servicios pequeños, independientemente desplegables, que se comunican a través de APIs, permitiendo escalabilidad y flexibilidad.
6. **Arquitectura Orientada a Servicios (SOA):** Estructura una aplicación como una colección de servicios débilmente acoplados que interactúan a través de interfaces bien definidas.
7. **Patrón Repositorio:** Separa la lógica que recupera datos del almacenamiento subyacente, proporcionando una interfaz unificada para acceder a los datos.
8. **Unidad de Trabajo:** Gestiona cambios en datos de manera transaccional, generalmente utilizado con el patrón Repositorio.
9. **CQRS (Command Query Responsibility Segregation):** Separa operaciones de lectura y escritura para el almacenamiento de datos, permitiendo optimización para cada tipo de operación.
10. **Event Sourcing:** Almacena el estado de una aplicación como una secuencia de eventos, permitiendo la reconstrucción del estado en cualquier momento.
11. **Arquitectura Hexagonal:** Se enfoca en la interacción entre una aplicación y sistemas externos, aislando la lógica de negocio central.
12. **Arquitectura Limpia:** Enfatiza la separación de preocupaciones, con capas distintas para reglas de negocio, interfaces y dependencias externas.
13. **Diseño Dirigido por Dominio (DDD):** Centra el desarrollo en una comprensión compartida del dominio del problema, promoviendo un modelo de dominio rico.
14. **Pipes and Filters:** Divide una tarea de procesamiento en una serie de etapas secuenciales e independientes (filtros) conectadas por tuberías.
15. **Patrón Pizarra (Blackboard):** Integra diversas fuentes de conocimiento para resolver problemas complejos mediante la colaboración.

## Patrones de Concurrencia (8)

1. **Active Object:** Permite que objetos se ejecuten de manera asincrónica sin preocuparse por los detalles de la concurrencia.
2. **Monitor Object:** Proporciona un mecanismo para que múltiples hilos de ejecución se sincronicen y se bloqueen según sea necesario.
3. **Half-Sync/Half-Async:** Divide la lógica de un sistema en dos partes: una que maneja tareas síncronas y otra que maneja tareas asíncronas.
4. **Thread Pool:** Gestiona un conjunto de hilos reutilizables para ejecutar tareas en paralelo.
5. **Double-Checked Locking:** Optimiza el acceso concurrente a datos compartidos utilizando una verificación adicional antes de adquirir un bloqueo completo.
6. **Thread-Specific Storage:** Permite que cada hilo de ejecución tenga su propia copia de datos, evitando conflictos de concurrencia.
7. **Balking Pattern:** Evita que un objeto realice una acción si ciertas condiciones no se cumplen.
8. **Barrier Pattern:** Sincroniza un grupo de hilos de ejecución en un punto de control hasta que todos los hilos estén listos para continuar.

## Patrones de Anti-Patrones (4)

1. **Big Ball of Mud:** Representa un diseño de software no estructurado y desorganizado.
2. **Spaghetti Code:** Se refiere a un código fuente desordenado y difícil de mantener.
3. **God Object:** Describe una clase o componente que realiza demasiadas funciones y contiene demasiada lógica.
4. **Singletonitis:** El uso excesivo de patrones Singleton, que puede llevar a problemas de mantenimiento y acoplamiento excesivo.
