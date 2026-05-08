---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/3-desarrollo-de-sistemas-orientado-a-la-gestion/clase-6-martes-05-de-mayo-de-2026-05-05-26-desarrollo-de-sistemas-orientado-a-la-gestion/","dg-note-properties":{}}
---


> [!quote]- Resumen
> # Guía Integral de Desarrollo de Sistemas: Arquitectura MVC, Gestión de Repositorios y Diseño de APIs RESTful
> 
> ## 1. Introducción General
> 
> El desarrollo de sistemas modernos orientados a la gestión exige no solo funcionalidad, sino también una organización estructural que permita la escalabilidad y el mantenimiento del código. Este documento detalla la transición de una "prueba de concepto" inicial a una estructura profesional basada en estándares de la industria. Se aborda la gestión de repositorios mediante Git, la documentación con Markdown, y la implementación del patrón de diseño **Modelo-Vista-Controlador (MVC)** para la construcción de APIs robustas bajo el paradigma RESTful.
> 
> ## 2. Contexto del Tema
> 
> En las etapas iniciales de aprendizaje, es común que la lógica de un servidor (como Express) se encuentre concentrada en un solo archivo. Sin embargo, a medida que el proyecto crece, surge la necesidad de separar las responsabilidades. Este enfoque se alinea con la evolución de la web; por ejemplo, el concepto de **REST (Representational State Transfer)** surgió a principios de los años 2000 (impulsado por ingenieros de Yahoo) para optimizar la comunicación en una internet que era significativamente más lenta, buscando una transferencia de datos eficiente y enriquecida.
> 
> ### Importancia y Relevancia
> 
> Una estructura organizada permite:
> 
> - **Colaboración eficiente:** Varios desarrolladores pueden trabajar en diferentes entidades (productos, clientes, etc.) sin interferir entre sí.
> - **Seguridad:** Separar los secretos de configuración del código fuente.
> - **Escalabilidad:** Facilitar la integración futura de bases de datos persistentes.
> 
> ## 3. Marco Conceptual
> 
> ### Definición de Conceptos Clave
> 
> - **API (Application Programming Interface):** Es el puente o conector entre el _Backend_ (datos, lógica de negocio) y el _Frontend_ (interfaz visual del usuario).
> - **Git Ignore:** Archivo de configuración (`.gitignore`) que indica a Git qué archivos o carpetas debe omitir al subir el código al repositorio.
> - **Markdown (.md):** Formato de marcado ligero que permite crear documentos con texto enriquecido (títulos, negritas, listas) de forma simple, siendo el estándar para documentar proyectos en plataformas como GitHub.
> - **RESTful:** Un conjunto de reglas y convenciones para que las APIs hablen un "mismo lenguaje", utilizando los métodos HTTP de forma estandarizada.
> 
> ### Términos Fundamentales
> 
> |   |   |
> |---|---|
> |Término|Definición|
> |**Backend**|Parte del sistema que interactúa con los datos y las reglas de negocio.|
> |**Frontend**|La vista o interfaz que el usuario final ve en su navegador.|
> |**JSON (JavaScript Object Notation)**|Formato de intercambio de datos ligero y fácil de leer para humanos y máquinas, usado habitualmente en las respuestas de las APIs.|
> |**Endpoint**|Una URL específica en la API que representa un recurso.|
> 
> ## 4. Desarrollo del Tema
> 
> ### Gestión del Repositorio y Documentación
> 
> Un proyecto profesional debe estar correctamente configurado desde su raíz:
> 
> 1. **El archivo** `**.gitignore**`**:** Es vital para no saturar el repositorio con archivos innecesarios o sensibles.
>     - **node_modules/**: Nunca debe subirse, ya que es pesada y se puede regenerar con `npm install`.
>     - **.env**: Archivo donde se guardan "secretos" (credenciales de base de datos, tokens de seguridad).
>     - **Logs y archivos temporales**: Archivos de registro de errores que no son útiles para otros desarrolladores.
> 2. **El archivo** `**README.md**`**:** Es la carta de presentación del proyecto. Debe incluir:
>     - Descripción del proyecto.
>     - Tecnologías utilizadas.
>     - Instrucciones de instalación y despliegue (clonación del repositorio, ejecución del servidor).
>     - Estructura de la API (endpoints).
>     - Integrantes del equipo.
> 
> ### El Patrón Modelo-Vista-Controlador (MVC)
> 
> El objetivo es dividir el software en tres componentes principales para organizar las carpetas del proyecto:
> 
> - **Modelo (Model):** Representa los datos y la lógica de negocio (clases como Producto, Cliente).
> - **Vista (View):** Lo que el cliente ve (en este contexto, la carpeta `public` que contiene el HTML/CSS).
> - **Controlador (Controller):** El cerebro que recibe las peticiones, procesa la lógica y decide qué datos enviar de vuelta.
> 
> ### Estructura de Carpetas Estándar
> 
> Para implementar MVC, el proyecto debe organizarse de la siguiente manera:
> 
> - `/src` o raíz:
>     - `server.js`: Punto de entrada que levanta el servidor Express.
>     - `/routes`: Define las URLs (ej. `api/productos`) y delega la acción al controlador.
>     - `/controllers`: Contiene la lógica que se ejecuta al acceder a una ruta.
>     - `/models` (o clases): Definición de las entidades.
>     - `/public`: Archivos estáticos visibles para el cliente.
> 
> ## 5. Relaciones entre Conceptos
> 
> ### El Ciclo de una Petición (Request-Response)
> 
> La comunicación sigue un flujo lógico:
> 
> 1. El **Usuario** realiza una petición desde el navegador (Frontend).
> 2. El **Router** (Enrutador) identifica la URL y el método HTTP.
> 3. El **Controlador** recibe la orden del Router, verifica permisos y busca los datos.
> 4. El **Servidor** devuelve la respuesta en formato **JSON** al cliente.
> 
> ### Métodos HTTP y su Mapeo en el CRUD
> 
> La convención REST dicta que las URLs deben representar recursos (sustantivos), no verbos. La acción la define el método HTTP:
> 
> |   |   |   |
> |---|---|---|
> |Método HTTP|Acción CRUD|Endpoint Ejemplo|
> |**GET**|Leer (Todos)|`/api/productos`|
> |**GET**|Leer (Uno solo)|`/api/productos/:id`|
> |**POST**|Crear|`/api/productos`|
> |**PUT**|Actualizar|`/api/productos/:id`|
> |**DELETE**|Eliminar|`/api/productos/:id`|
> 
> ### Códigos de Respuesta HTTP
> 
> Para que el Frontend entienda qué pasó en el Backend, se usan códigos estandarizados:
> 
> - **200 (OK):** Petición exitosa.
> - **201 (Created):** Recurso creado con éxito (usado en POST).
> - **400 (Bad Request):** Error del cliente (URL mal escrita o datos inválidos).
> - **401 (Unauthorized):** El usuario no tiene permisos o no está autenticado.
> - **404 (Not Found):** El recurso solicitado no existe.
> 
> ## 6. Ejemplos Prácticos
> 
> ### Analogía del Restaurante
> 
> Para entender la separación de responsabilidades:
> 
> - **El Cliente:** Es el navegador/usuario.
> - **La Carta (URL):** Indica qué opciones hay disponibles.
> - **El Mozo (Router):** Toma el pedido del cliente y lo lleva al lugar correcto (la cocina).
> - **El Cocinero (Controlador):** Tiene la receta, verifica si hay ingredientes (datos) y prepara el plato.
> - **El Plato terminado (JSON):** Es la respuesta que vuelve al cliente.
> 
> ### Baja Lógica vs. Baja Física
> 
> Al implementar la función de eliminación en el controlador:
> 
> - **Baja Física:** Se borra el registro permanentemente de la base de datos.
> - **Baja Lógica:** Se cambia un estado (ej. `activo: false`). Esto es preferible para mantener la integridad referencial (por ejemplo, si un producto fue vendido, no se puede borrar físicamente porque el registro de venta quedaría huérfano).
> 
> ## 7. Errores Comunes y Confusiones
> 
> - **Verbos en la URL:** Un error frecuente es crear rutas como `/api/crearProducto`. Lo correcto es usar `/api/productos` con el método **POST**.
> - **Subir** `**node_modules**`**:** Olvidar el `.gitignore` genera repositorios extremadamente pesados y dificulta la colaboración.
> - **Confusión 401 vs 404:** El 401 indica que el usuario no tiene permiso para ver el recurso, mientras que el 404 indica que, tenga permiso o no, el recurso simplemente no está allí.
> 
> ## 8. Síntesis y Conclusiones
> 
> La adopción de la arquitectura MVC y los estándares RESTful transforma un código desordenado en un sistema profesional. La separación de responsabilidades en **Rutas** y **Controladores** facilita la gestión de errores, la implementación de seguridad (roles de administrador vs. usuario) y prepara el terreno para la integración de bases de datos. Documentar con `README.md` y proteger el código con `.gitignore` son prácticas obligatorias para cualquier desarrollo colaborativo.
> 
> ## 9. Fechas Importantes y Avisos Académicos
> 
> - **Fecha de la Clase:** 05 de mayo de 2026.
> - **Desafío Actual (Tarea):** Refactorizar el proyecto existente para cumplir con la organización MVC, agregar el archivo `.gitignore`, el archivo `README.md` y separar las rutas de los controladores.
> - **Próxima Clase:** Se abordará la conexión e implementación de **Bases de Datos** para reemplazar el almacenamiento temporal en memoria (arrays).
> - **Nota del Profesor:** Se compartirá un repositorio de ejemplo para que los grupos puedan comparar y estandarizar sus estructuras de carpetas.
> 
> ## 10. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la función principal de un archivo `.gitignore`?
> 2. ¿Qué significa el acrónimo API?
> 3. ¿Por qué no se debe subir la carpeta `node_modules` a Git?
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia entre un método GET y un método POST en una API RESTful.
> 5. ¿Qué componente del patrón MVC es responsable de manejar la lógica de negocio y las recetas de procesamiento de datos?
> 6. ¿Qué código de error HTTP debería devolver la API si un usuario intenta borrar un producto sin tener permisos de administrador?
> 
> ### Nivel Avanzado
> 
> 7. Compare la "Baja Física" con la "Baja Lógica". ¿En qué caso es recomendable usar cada una?
> 8. Describa el flujo de una petición desde que el usuario hace clic en "Ver Producto" hasta que recibe la información en su pantalla, mencionando el rol del Router y el Controlador.
> 9. ¿Por qué es importante que las URLs en REST representen sustantivos y no acciones/verbos?

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 6 (05 05 26) - Desarrollo de sistemas orientado a la gestión" src="https://www.youtube.com/embed/3upz_-mhQG4?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1P4PEjjUWyGqXRmpKMnrdVlniQqpA6XIb/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1fCdjjHvgTJ3rt3Qp4p08P7u63T79V4Tu/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>