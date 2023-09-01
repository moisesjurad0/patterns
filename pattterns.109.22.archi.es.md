# pattterns.22.archi.es

## Patrones Arquitectónicos (22)

1. **Modelo-Vista-Controlador (MVC):** Separa una aplicación en tres componentes interconectados: Modelo (datos y lógica de negocio), Vista (interfaz de usuario) y Controlador (gestiona la entrada del usuario y la comunicación).
2. **Modelo-Vista-Presentador (MVP):** Separa una aplicación en Modelo (lógica de negocio y datos), Vista (interfaz de usuario) y Presentador (maneja la entrada del usuario y comunica entre Modelo y Vista).
3. **Modelo-Vista-ViewModel (MVVM):** Separa una aplicación en Modelo (datos y lógica), Vista (interfaz de usuario) y ViewModel (gestiona la lógica de presentación y la comunicación entre Modelo y Vista).
4. **Arquitectura en Capas:** Organiza una aplicación en capas distintas (por ejemplo, presentación, lógica de negocio, datos) para mejorar la modularidad y el mantenimiento.
5. **Microservicios:** Descompone una aplicación en servicios pequeños, independientemente desplegables, que se comunican a través de APIs, permitiendo escalabilidad y flexibilidad.
6. **Arquitectura Orientada a Servicios (SOA):** Estructura una aplicación como una colección de servicios débilmente acoplados que interactúan a través de interfaces bien definidas.
7. **Patrón Repositorio:** Separa la lógica que recupera datos del almacenamiento subyacente, proporcionando una interfaz unificada para acceder a los datos.
8. **Unidad de Trabajo:** Gestiona los cambios en los datos de manera transaccional, generalmente utilizado con el patrón Repositorio.
9. **CQRS (Command Query Responsibility Segregation):** Separa las operaciones de lectura y escritura para el almacenamiento de datos, permitiendo la optimización de cada tipo de operación.
10. **Event Sourcing:** Almacena el estado de una aplicación como una secuencia de eventos, lo que permite la reconstrucción del estado en cualquier momento.
11. **Arquitectura Hexagonal:** Se enfoca en la interacción entre una aplicación y sistemas externos, aislando la lógica de negocio central.
12. **Arquitectura Limpia:** Enfatiza la separación de preocupaciones, con capas distintas para reglas de negocio, interfaces y dependencias externas.
13. **Diseño Dirigido por Dominio (DDD):** Centra el desarrollo en una comprensión compartida del dominio del problema, promoviendo un modelo de dominio rico.
14. **Pipes y Filtros:** Divide una tarea de procesamiento en una serie de etapas secuenciales e independientes (filtros) conectadas por tuberías.
15. **Patrón Pizarra (Blackboard):** Integra diversas fuentes de conocimiento para resolver problemas complejos mediante la colaboración.
16. **Cliente-Servidor:** Separa una aplicación en componentes cliente y servidor, permitiendo el procesamiento y la comunicación distribuidos.
17. **Maestro-Esclavo:** Distribuye tareas entre múltiples nodos de trabajo, con un nodo (maestro) coordinando a los demás (esclavos).
18. **Punto a Punto (Peer-to-Peer):** Permite que los nodos interconectados compartan recursos e información directamente, sin un servidor central.
19. **Corredor (Broker):** Introduce un intermediario (corredor) para gestionar la comunicación entre componentes o servicios distribuidos.
20. **Arquitectura Basada en Componentes:** Estructura una aplicación como una composición de componentes reutilizables y autocontenidos.
21. **Arquitectura Orientada a Eventos (EDA):** Enfatiza la producción, detección, consumo y reacción a eventos en un sistema.
22. **Arquitectura en N Capas:** Divide una aplicación en múltiples capas, cada una responsable de funcionalidades o servicios específicos.
