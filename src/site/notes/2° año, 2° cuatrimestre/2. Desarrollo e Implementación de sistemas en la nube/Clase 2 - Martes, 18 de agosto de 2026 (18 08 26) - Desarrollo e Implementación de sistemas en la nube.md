---
{"dg-publish":true,"permalink":"/2-ano-2-cuatrimestre/2-desarrollo-e-implementacion-de-sistemas-en-la-nube/clase-2-martes-18-de-agosto-de-2026-18-08-26-desarrollo-e-implementacion-de-sistemas-en-la-nube/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio: Desarrollo e Implementación de Sistemas en la Nube
> 
> Esta guía de estudio sintetiza los conceptos fundamentales abordados en la materia, centrada en la arquitectura de microservicios, el protocolo HTTP y la integración de sistemas modernos. El documento funciona como un material de referencia exhaustivo para comprender la dinámica de los sistemas distribuidos y la implementación técnica de aplicaciones web.
> 
> ## 1. Contexto y Relevancia del Tema
> 
> En la actualidad, el desarrollo de sistemas ha evolucionado desde estructuras monolíticas (donde todo el código reside en una sola aplicación) hacia arquitecturas de **microservicios**. Esta transición responde a la necesidad de escalabilidad y resiliencia en entornos de alto tráfico.
> 
> ### Importancia de la Arquitectura Distribuida
> 
> - **Escalabilidad selectiva:** Permite aumentar los recursos ("darle más fierro") solo a la parte del sistema que lo necesita (por ejemplo, el módulo de pagos durante un evento de ventas masivas como el Día de la Madre), en lugar de escalar toda la aplicación.
> - **Autonomía y Resiliencia:** Si un microservicio falla (por ejemplo, los pagos con una tarjeta específica), el resto del sistema (búsqueda de productos, carrito) sigue funcionando.
> - **Independencia Tecnológica:** Cada microservicio puede construirse de forma autónoma, lo que permite manejar grandes volúmenes de operaciones (ejemplos de la industria incluyen a Netflix con más de 4,000 backends y Mercado Libre con más de 7,000).
> 
> ## 2. Marco Conceptual: Conceptos Clave
> 
> ### Microservicios
> 
> Un microservicio es un componente de backend que debe ser **autónomo**. Entre todos los microservicios colaboran para generar un sistema integral.
> 
> - **Regla Fundamental:** Cada microservicio debe ser dueño de su propio destino de datos. Un backend **nunca** debe acceder directamente a la base de datos de otro backend; la comunicación debe realizarse siempre a través de servicios (APIs).
> 
> ### Bases de Datos en la Nube
> 
> - **Normalización:** Se refiere a las técnicas (como la 1ra, 2da y 3ra Forma Normal) para organizar tablas y evitar la redundancia.
> - **Evolución del almacenamiento:** Antiguamente, el espacio en disco era costoso y se priorizaba el ahorro de datos. Hoy en día, el almacenamiento es económico, por lo que a veces se opta por la **desnormalización** para ganar velocidad en las consultas (performance).
> - **Relaciones:** Lo más importante de las formas normales hoy es cómo se relacionan las tablas a través de índices y claves foráneas (_foreign keys_).
> 
> ## 3. Desarrollo del Tema: El Protocolo HTTP
> 
> El protocolo HTTP (_HyperText Transfer Protocol_) es la base de la comunicación en internet. Funciona mediante un ciclo de **Request** (Petición) y **Response** (Respuesta).
> 
> ### Componentes de una Comunicación HTTP
> 
> 1. **Cliente:** Quien realiza el requerimiento (puede ser un navegador o un backend llamando a otro).
> 2. **Servidor:** Quien procesa la solicitud y responde.
> 3. **Mensaje:** Compuesto por tres partes:
>     - **URL:** La dirección del recurso.
>     - **Headers (Cabeceras):** Metainformación y contexto.
>     - **Body (Cuerpo):** Los datos en sí mismos (generalmente en formato JSON).
> 
> ### Anatomía de una URL
> 
> Una URL se compone de varios elementos que definen la ruta hacia el recurso:
> 
> - **Protocolo:** Ej. `https://` o `http://`.
> - **Host:** El nombre del dominio que el **DNS** (Sistema de Nombres de Dominio) traduce a una dirección IP física.
> - **Puerto:** Convención numérica para la comunicación (HTTP usa por defecto el 80, HTTPS el 443).
> - **Recurso:** El camino o _path_ hacia la funcionalidad específica (ej. `/usuarios/perfil`).
> - **Query String:** Comienza con `?` y permite pasar parámetros clave-valor (ej. `?color=azul&marca=mercedes`).
> 
> ## 4. Métodos y Formatos de Datos
> 
> ### Métodos HTTP (Verbos)
> 
> Definen la acción que se desea realizar sobre el recurso:
> 
> |   |   |
> |---|---|
> |Método|Propósito|
> |**GET**|Recuperar o buscar información de un recurso.|
> |**POST**|Crear un nuevo recurso.|
> |**PUT**|Modificar un recurso de forma total (reemplazo).|
> |**PATCH**|Modificar un recurso de forma parcial.|
> |**DELETE**|Eliminar un recurso.|
> |**OPTIONS**|Obtener metainformación sobre las opciones de comunicación.|
> 
> ### Formatos del Body
> 
> Aunque existen varios formatos para estructurar los datos en el cuerpo del mensaje, el estándar predominante es **JSON**.
> 
> 1. **JSON (JavaScript Object Notation):** Es el más utilizado debido a su ligereza y facilidad de integración nativa con JavaScript.
> 2. **XML:** Formato basado en etiquetas, más verboso y común en sistemas antiguos.
> 3. **YAML/IML:** Basado en la indentación. Es muy legible pero propenso a errores de formato (se usa principalmente para archivos de configuración).
> 
> ### Headers Importantes
> 
> - **Content-Type:** Indica al receptor qué formato de datos se está enviando (ej. `application/json`).
> - **Accept:** Indica qué tipo de formato es capaz de recibir el cliente como respuesta.
> - **Cookies:** Se desaconseja su uso para información sensible debido a vulnerabilidades de seguridad; se recomienda el uso de **Local Storage** para guardar datos en el explorador.
> 
> ## 5. Códigos de Estado HTTP (Status Codes)
> 
> Los códigos de estado informan el resultado de la petición. Se dividen en rangos:
> 
> |   |   |   |
> |---|---|---|
> |Rango|Significado General|Códigos Clave|
> |**200-299**|**Éxito**|**200 OK:** Petición exitosa.<br>**201 Created:** Recurso creado con éxito (típico en POST).<br>**204 No Content:** Éxito, pero la respuesta no tiene cuerpo (típico en DELETE).|
> |**400-499**|**Error del Cliente**|**400 Bad Request:** Formato de datos incorrecto.<br>**401 Unauthorized:** Falta de autenticación (llave del edificio).<br>**403 Forbidden:** Autenticado, pero sin permiso para ese recurso (llave de otro departamento).<br>**404 Not Found:** Recurso no encontrado.<br>**422 Unprocesable Entity:** Datos válidos en formato, pero inválidos para la lógica de negocio.|
> |**500-599**|**Error del Servidor**|**500 Internal Server Error:** Indica un "bug" o falla en el código del backend.|
> 
> **Aclaración importante:** No es lo mismo un 404 que un 200 con array vacío. Si pides `autos/1` y no existe, es **404**. Si pides `autos?color=verde` y no hay verdes, es **200** con una lista vacía, porque el recurso "autos" sí existe.
> 
> ## 6. Diseño e Implementación Técnica
> 
> ### Diagramas de Secuencia
> 
> Antes de programar, es fundamental documentar la lógica mediante diagramas de secuencia que muestren la interacción entre el usuario, el frontend, el backend y la base de datos.
> 
> - Se pueden utilizar herramientas como **Mermaid** o **PlantUML**.
> - Estos diagramas permiten visualizar los flujos de éxito y los caminos de error (ej. qué responder si un usuario no existe).
> 
> ### Herramientas de Prueba
> 
> Para interactuar con las APIs sin necesidad de un frontend completo, se utilizan clientes HTTP:
> 
> - **cURL:** Herramienta de línea de comandos.
> - **Postman / Insomnia:** Interfaces gráficas para construir peticiones, ver cabeceras y analizar cuerpos de respuesta.
> 
> ### El rol de la Inteligencia Artificial (IA)
> 
> En este contexto académico, el uso de IA es una decisión permitida para agilizar la generación de código base o _boilerplate_. Sin embargo, es responsabilidad del desarrollador **corregir y validar** lo que la IA genera, ya que suele cometer errores de lógica o de integración de protocolos.
> 
> ## 7. Fechas Importantes y Avisos Académicos
> 
> A partir del análisis de las fuentes, se detallan las pautas para la organización del trabajo práctico y la materia:
> 
> - **Trabajo Práctico (TP):**
>     - **Requisito de Integración:** El sistema debe tener al menos tres sistemas integrados.
>     - **Estructura Mínima:** Un frontend conectado a dos backends (microservicios).
>     - **Libertad Tecnológica:** Los alumnos eligen el tema, el tamaño de la aplicación y la tecnología, siempre que esté dentro del _stack_ de la facultad.
>     - **Recomendación:** Se sugiere unificar el trabajo con las materias de Frontend y Backend que se cursan en simultáneo.
> - **Reglas de Aprobación/Reprobación:**
>     - Un backend **no puede** acceder a la base de datos de otro directamente.
>     - Tener más de un error **HTTP 500** en la entrega puede ser motivo de reprobación.
>     - El sistema debe manejar correctamente los códigos de error (400s) según la lógica de negocio.
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia principal entre un método GET y un método POST?
> 2. ¿Qué significa el código de estado 404?
> 3. ¿Por qué se prefiere JSON sobre XML en el desarrollo moderno?
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia entre un error 401 (Unauthorized) y un 403 (Forbidden) utilizando una analogía.
> 5. ¿Por qué un backend no debe acceder directamente a la base de datos de otro en una arquitectura de microservicios?
> 6. ¿En qué casos se debería devolver un código 204 No Content?
> 
> ### Nivel Avanzado
> 
> 7. Diseñe un flujo de comunicación donde se utilice el código 202 Accepted. ¿En qué tipo de tareas es común este código?
> 8. Analice las ventajas y desventajas de la desnormalización de bases de datos en un entorno de alta performance.
> 9. Ante una búsqueda filtrada que no arroja resultados, ¿por qué es incorrecto devolver un error 404? Justifique según el protocolo REST.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 2 (18 08 26) - Desarrollo e Implementación de sistemas en la nube" src="https://www.youtube.com/embed/1LFzrKzigEY?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1GtaAP-AtxkF7QABGEhCOc2bPOruYXHDP/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1a-NJ14XFKFzK4E3BPXt1bA1bS9vQT2-7/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>