# patterns (109)

## Patrones Creacionales (16)

1. **Singleton:** Asegura que una clase tenga solo una instancia y proporciona un punto de acceso global a esa instancia.
2. **Factory Method:** Define una interfaz para crear un objeto, pero permite a las subclases alterar el tipo de objetos que se crean.
3. **Abstract Factory:** Proporciona una interfaz para crear familias de objetos relacionados sin especificar sus clases concretas.
4. **Builder:** Separa la construcción de un objeto complejo de su representación, permitiendo la creación de diferentes representaciones.
5. **Prototype:** Permite la creación de nuevos objetos copiando un objeto existente, conocido como prototipo.
6. **Object Pool:** Mantiene un conjunto de objetos listos para su uso en lugar de crearlos y destruirlos continuamente.
7. **Dependency Injection:** Suministra las dependencias que una clase necesita desde el exterior, en lugar de crearlas internamente.
8. **Simple Factory:** Permite crear objetos de diferentes tipos sin exponer la lógica de creación al cliente.
9. **Lazy Initialization:** Retarda la creación de un objeto hasta que sea necesario.
10. **Factory Kit:** Define una interfaz para crear familias de objetos relacionados, pero usa métodos estáticos en lugar de clases.
11. **Multiton:** Similar al Singleton, pero gestiona múltiples instancias con nombres o claves.
12. **Singleton Registry:** Permite acceder a instancias Singleton mediante un registro central.
13. **Singleton Per Thread:** Proporciona una instancia Singleton por hilo de ejecución.
14. **Singleton Per Request:** Proporciona una instancia Singleton por solicitud en una aplicación web.
15. **Static Factory:** Utiliza métodos estáticos para crear objetos en lugar de constructores.
16. **Multiton Registry:** Un registro central que gestiona múltiples instancias de Multiton.

## Patrones Estructurales (29)

1. **Adapter:** Permite que interfaces incompatibles trabajen juntas, convirtiendo la interfaz de una clase en otra esperada por el cliente.
2. **Bridge:** Separa una abstracción de su implementación para que ambas puedan variar independientemente.
3. **Composite:** Permite componer objetos en estructuras de árbol para representar jerarquías de parte-todo.
4. **Decorator:** Agrega comportamiento adicional a objetos dinámicamente, sin afectar a otros objetos del mismo tipo.
5. **Facade:** Proporciona una interfaz simplificada para un conjunto más grande de clases y funcionalidades.
6. **Flyweight:** Comparte de manera eficiente objetos que son utilizados comúnmente para conservar recursos.
7. **Proxy:** Controla el acceso a un objeto proporcionando un representante o sustituto.
8. **Module:** Agrupa componentes relacionados en un solo módulo o unidad.
9. **Private Class Data:** Oculta los detalles de implementación mediante la separación de la interfaz pública y los datos privados.
10. **Faceted:** Divide una interfaz en múltiples interfaces más pequeñas, llamadas facetas.
11. **Pluggable Selector:** Permite a un objeto seleccionar su comportamiento de entre varios algoritmos.
12. **Aggregate:** Agrupa objetos en una única entidad para tratarlos como una unidad.
13. **Role Object:** Representa un rol o conjunto de comportamientos que un objeto puede asumir.
14. **Tree Structure:** Organiza objetos en una estructura jerárquica de árbol.
15. **Hierarchical:** Organiza objetos en una estructura de jerarquía anidada.
16. **Event-Based Composition:** Composición de objetos basada en eventos.
17. **Layers:** Divide una aplicación en capas, cada una con una responsabilidad específica.
18. **Component Configurator:** Configura objetos mediante componentes separados.
19. **Double Buffer:** Almacena dos copias de un conjunto de datos para mejorar el rendimiento.
20. **Service Locator:** Proporciona una ubicación centralizada para buscar servicios.
21. **Resource Acquisition Is Initialization (RAII):** Gestiona la adquisición y liberación de recursos automáticamente.
22. **Handle-Body Idiom:** Oculta la implementación de un objeto detrás de un puntero o handle.
23. **Metadata Mapping:** Asocia metadatos con objetos.
24. **Half-Object + Protocol:** Divide un objeto en dos partes, una local y una remota, para reducir la comunicación en red.
25. **Type Object:** Utiliza un objeto para representar y gestionar tipos de datos.
26. **Role Object:** Representa un rol o conjunto de comportamientos que un objeto puede asumir.
27. **Super Type:** Agrupa tipos relacionados en una jerarquía común.
28. **Sub Type:** Define un nuevo tipo que hereda de un tipo existente.
29. **Mixin:** Combina comportamientos de varias clases en una sola.

## Patrones de Comportamiento (45)

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
12. **Null Object:** Proporciona un objeto de reemplazo que no hace nada en lugar de un objeto nulo.
13. **Servant:** Agrupa métodos que se pueden aplicar a varias clases en un único objeto.
14. **Specification:** Define una especificación de negocio como un objeto y permite comprobar si un objeto cumple con esa especificación.
15. **Command Processor:** Ejecuta comandos en una cola de manera asíncrona.
16. **Event Aggregator:** Combina eventos de múltiples fuentes en un único evento.
17. **Publish-Subscribe:** Permite que los objetos se suscriban y reciban notificaciones de eventos de otros objetos.
18. **Scheduler:** Programa tareas para su ejecución en un momento específico.
19. **Scheduler (Threaded):** Programa tareas para su ejecución en hilos de ejecución separados.
20. **Two-Step View:** Divide la vista en dos partes, una para la lógica y otra para la presentación.
21. **Delegation:** Delega responsabilidades entre objetos para evitar la duplicación de código.
22. **Chain of Command:** Encadena objetos de comando para realizar acciones en secuencia.
23. **Priority Queue:** Organiza elementos según su prioridad.
24. **Bytecode:** Utiliza un conjunto de instrucciones en lugar de código fuente directo.
25. **Reflection:** Permite examinar y modificar la estructura y comportamiento de los objetos en tiempo de ejecución.
26. **Event Queue:** Almacena y gestiona eventos para su procesamiento posterior.
27. **Asynchronous Method Invocation:** Invoca métodos de manera asíncrona.
28. **Futures and Promises:** Proporciona un mecanismo para obtener un valor futuro de una operación asíncrona.
29. **Active Object:** Proporciona un objeto intermedio para realizar llamadas de método de manera asíncrona.
30. **Monitor Object:** Sincroniza el acceso a objetos compartidos.
31. **Half-Sync/Half-Async:** Divide una aplicación en dos partes, una asíncrona y otra síncrona.
32. **Thread Pool:** Administra un conjunto de hilos para ejecutar tareas en paralelo.
33. **Double-Checked Locking:** Mejora el rendimiento de la inicialización de Singleton utilizando bloqueo solo cuando es necesario.
34. **Thread-Specific Storage:** Proporciona almacenamiento específico para hilos.
35. **Balking Pattern:** Evita que un objeto realice una acción si ciertas condiciones no se cumplen.
36. **Barrier Pattern:** Sincroniza múltiples hilos en un punto específico.
37. **Worker Thread:** Utiliza hilos de trabajo para realizar tareas en segundo plano.
38. **Leaders/Followers:** Administra un grupo de hilos de manera eficiente.
39. **Proactor:** Inicia acciones de manera asíncrona y asocia manejadores de eventos para su procesamiento.
40. **Reactor:** Gestiona eventos y las operaciones asociadas.
41. **Read-Write Lock:** Permite el acceso simultáneo de lectura y escritura a recursos compartidos.
42. **Lock:** Proporciona exclusión mutua para recursos compartidos.
43. **Thread-Local Storage:** Almacena datos de manera local en cada hilo.
44. **Thread-Specific Storage:** Almacena datos específicos de un hilo.
45. **Thread-Safe Interface:** Garantiza que las operaciones en una interfaz sean seguras para hilos.

## Patrones de Arquitectura (22)

1. **Model-View-Controller (MVC):** Separa una aplicación en tres componentes interconectados: Modelo (datos y lógica de negocio), Vista (interfaz de usuario) y Controlador (gestiona la entrada del usuario y la comunicación).
2. **Model-View-Presenter (MVP):** Separa una aplicación en Modelo (lógica de negocio y datos), Vista (interfaz de usuario) y Presentador (maneja la entrada del usuario y la comunicación entre Modelo y Vista).
3. **Model-View-ViewModel (MVVM):** Separa una aplicación en Modelo (datos y lógica), Vista (interfaz de usuario) y ViewModel (gestiona la lógica de presentación y la comunicación entre Modelo y Vista).
4. **Layered Architecture:** Organiza una aplicación en capas distintas (por ejemplo, presentación, lógica de negocio, datos) para mejorar la modularidad y el mantenimiento.
5. **Microservices:** Descompone una aplicación en servicios pequeños e independientes que se comunican a través de API, permitiendo la escalabilidad y la flexibilidad.
6. **Service-Oriented Architecture (SOA):** Estructura una aplicación como una colección de servicios débilmente acoplados que interactúan a través de interfaces bien definidas.
7. **Repository Pattern:** Separa la lógica que recupera datos del almacenamiento subyacente, proporcionando una interfaz unificada para acceder a los datos.
8. **Unit of Work:** Gestiona los cambios en los datos de manera transaccional, generalmente utilizado con el patrón Repository.
9. **CQRS (Command Query Responsibility Segregation):** Separa las operaciones de lectura y escritura para el almacenamiento de datos, permitiendo la optimización de cada tipo de operación.
10. **Event Sourcing:** Almacena el estado de una aplicación como una secuencia de eventos, lo que permite la reconstrucción del estado en cualquier momento.
11. **Hexagonal Architecture:** Se centra en la interacción entre una aplicación y los sistemas externos, aislando la lógica de negocio central.
12. **Clean Architecture:** Enfatiza la separación de preocupaciones, con capas distintas para reglas de negocio, interfaces y dependencias externas.
13. **Domain-Driven Design (DDD):** Centra el desarrollo en una comprensión compartida del dominio del problema, promoviendo un modelo de dominio rico.
14. **Pipes and Filters:** Divide una tarea de procesamiento en una serie de etapas secuenciales e independientes (filtros) conectadas por tuberías.
15. **Blackboard Pattern:** Integra diversas fuentes de conocimiento para resolver problemas complejos mediante la colaboración.
16. **Client-Server:** Separa una aplicación en componentes cliente y servidor, permitiendo el procesamiento y la comunicación distribuidos.
17. **Master-Slave:** Distribuye tareas entre múltiples nodos de trabajo, con un nodo (maestro) coordinando a los demás (esclavos).
18. **Peer-to-Peer:** Permite que los nodos interconectados compartan recursos e información directamente, sin un servidor central.
19. **Broker:** Introduce un intermediario (broker) para gestionar la comunicación entre componentes o servicios distribuidos.
20. **Object-Relational Mapping (ORM):** Mapea objetos a tablas de base de datos, permitiendo que datos orientados a objetos y relacionales funcionen juntos.
21. **Publish-Subscribe:** Permite que objetos se suscriban y reciban notificaciones de eventos de otros objetos.
22. **Event-Driven Architecture (EDA):** Enfatiza la producción, detección, consumo y reacción a eventos en un sistema.
