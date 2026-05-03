---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/3-desarrollo-de-sistemas-orientado-a-la-gestion/clase-5-martes-28-de-abril-de-2026-28-04-26-desarrollo-de-sistemas-orientado-a-la-gestion/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio: Desarrollo de Sistemas y Arquitectura API REST
> 
> Este documento constituye un material de estudio integral diseñado para comprender la transición del desarrollo de interfaces visuales (frontend) a la integración funcional con servidores y bases de datos (backend), utilizando como eje central la arquitectura API REST y el formato de intercambio de datos JSON.
> 
> ## 1. Introducción General
> 
> El desarrollo de sistemas orientados a la gestión requiere una separación clara entre lo que el usuario ve y cómo se manipulan los datos. Hasta este punto, es común trabajar con datos "hardcodeados" (fijos en el código) para probar la visualización. Sin embargo, un sistema real depende de un **backend** robusto que gestione la persistencia de la información y un **frontend** que la presente de manera dinámica. Esta guía explica el "puente" que une ambos mundos: la **API REST**.
> 
> ## 2. Contexto del Tema
> 
> En el marco de la materia Desarrollo de Sistemas Orientado a la Gestión, se busca que los estudiantes avancen desde la creación de maquetas estáticas hacia la implementación de un sistema de gestión completo. El objetivo actual es integrar la lógica de servidor (Node.js/Express) para que los datos de productos, clientes y categorías no sean estáticos, sino que provengan de una fuente centralizada y puedan ser manipulados mediante operaciones de creación, lectura, actualización y borrado (CRUD).
> 
> ### Importancia y Relevancia
> 
> - **Escalabilidad:** Permite que múltiples plataformas (web, móvil) consuman los mismos datos.
> - **Eficiencia:** El uso de formatos modernos como JSON reduce la carga en la red y mejora la velocidad de las aplicaciones.
> - **Estandarización:** Seguir convenciones como REST permite que diferentes desarrolladores trabajen en un mismo proyecto bajo un "contrato" de comunicación claro.
> 
> ## 3. Marco Conceptual
> 
> Para entender el desarrollo backend, es fundamental dominar los siguientes términos:
> 
> ### Conceptos Clave
> 
> |Concepto|Definición|
> |---|---|
> |**Frontend**|La parte visual de la aplicación que se dibuja en el navegador (HTML, CSS, JavaScript).|
> |**Backend**|El acceso interno al servidor donde residen los datos y la lógica de negocio.|
> |**API (Application Programming Interface)**|Interfaz de programación que funciona como un puente de comunicación entre el cliente y el servidor.|
> |**REST (Representational State Transfer)**|Una convención o conjunto de reglas que definen cómo debe ser el formato y la estructura de la conexión en una API.|
> |**JSON (JavaScript Object Notation)**|Formato ligero de intercambio de datos, basado en texto, fácil de leer para humanos y máquinas.|
> |**CRUD / ABM**|Acrónimos para las operaciones básicas de gestión: Create, Read, Update, Delete (en español: Alta, Baja, Modificación).|
> 
> ## 4. Desarrollo del Tema: La Comunicación Cliente-Servidor
> 
> ### El Ciclo de Petición y Respuesta (Request/Response)
> 
> La interacción en la web se basa en un intercambio constante:
> 
> 1. **Request (Petición):** El cliente (navegador) solicita algo al servidor (ej. "dame la lista de productos").
> 2. **Response (Respuesta):** El servidor procesa la solicitud y devuelve los datos o una confirmación de la acción realizada.
> 
> ### Métodos HTTP (Verbos)
> 
> Para que el servidor sepa qué acción realizar, se utilizan métodos estandarizados:
> 
> - **GET:** Se utiliza para **leer** o consultar información. No suele requerir datos adicionales en el cuerpo del mensaje.
> - **POST:** Se utiliza para **crear** o agregar nuevos registros (ej. agregar un nuevo producto). Requiere enviar datos en el "body".
> - **PUT:** Se utiliza para **modificar** o actualizar registros existentes.
> - **DELETE:** Se utiliza para **eliminar** registros.
> 
> ### Formatos de Intercambio: Del XML al JSON
> 
> Históricamente, se utilizaba **XML** (un lenguaje de marcado similar al HTML, muy estructurado y pesado). Con la evolución de la web, nació **JSON**, que se ha convertido en el estándar moderno por las siguientes razones:
> 
> - **Menor peso:** No utiliza etiquetas de apertura y cierre complejas, lo que ahorra ancho de banda.
> - **Legibilidad:** Utiliza una estructura simple de llaves `{}` para objetos y corchetes `[]` para arreglos (colecciones).
> - **Velocidad:** Es más rápido de procesar por los navegadores modernos.
> 
> ## 5. Implementación Técnica
> 
> ### Estructura de un Objeto JSON
> 
> Un JSON mapea directamente con las clases que se definen en el código. Ejemplo de un producto:
> 
> ```json
> {
>   "id": 1,
>   "nombre": "Producto Ejemplo",
>   "precio": 1500,
>   "imagen": "ruta/imagen.jpg"
> }
> ```
> 
> ### El Backend con Express
> 
> Express es un framework de Node.js que facilita la creación de servidores. Permite definir **Endpoints** (rutas específicas) que "escuchan" las peticiones del cliente.
> 
> **Ejemplo de un Endpoint GET para obtener productos:**
> 
> ```jsx
> app.get('/api/productos', (req, res) => {
>     // El servidor responde con la colección de productos en formato JSON
>     res.json(listaDeProductos);
> });
> ```
> 
> ### Herramientas de Pruebas
> 
> Para validar que una API funciona antes de integrarla al frontend, se utilizan herramientas especializadas:
> 
> - **Postman:** Aplicación (web o escritorio) para realizar peticiones HTTP y ver las respuestas del servidor.
> - **Thunder Client:** Una extensión para Visual Studio Code que permite realizar las mismas funciones de Postman sin salir del editor de código.
> 
> ## 6. Relaciones entre Conceptos y Flujo de Trabajo
> 
> La conexión entre las partes del sistema sigue un orden lógico:
> 
> 1. **El Modelo:** Se definen las clases (Productos, Clientes).
> 2. **El Backend (API):** Se crean las rutas en Express que manejan estas clases.
> 3. **El Intercambio (JSON):** Los datos viajan del servidor al cliente en este formato.
> 4. **El Frontend (Fetch):** El navegador usa la función `fetch` para llamar a la URL de la API y obtener los datos para dibujarlos en la pantalla.
> 
> ## 7. Errores Comunes y Confusiones
> 
> - **Confusión del "Body":** No se debe confundir la etiqueta `<body>` de HTML con el **Body del mensaje HTTP**. El "body" en una API es el paquete de datos (JSON) que se envía en una petición POST o PUT.
> - **Creación vs. Prueba:** Un error común es pensar que las APIs se "crean" en Postman o Thunder Client. Estas herramientas son solo para **probar y validar**; la API se programa en el servidor (ej. con Node.js y Express).
> - **Estado de la Petición:** A veces se asume que si la página carga, la API funciona. Es necesario verificar el "Status OK" (Código 200) en las herramientas de desarrollo para asegurar que los datos llegaron correctamente.
> 
> ## 8. Síntesis y Conclusiones
> 
> - La **API REST** actúa como el contrato de comunicación entre el frontend y el backend.
> - **JSON** es el lenguaje universal de la web moderna por su ligereza y facilidad de uso frente al antiguo XML.
> - Un **CRUD** completo es la base de cualquier sistema de gestión, permitiendo el control total sobre las entidades del negocio (productos, clientes, etc.).
> - La integración exitosa requiere entender que el backend sirve los datos y el frontend se encarga únicamente de la presentación.
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Qué significa el acrónimo CRUD y cuál es su equivalente en español?
> 2. ¿Cuál es la diferencia visual básica entre un formato XML y un JSON?
> 3. ¿Para qué sirve el método HTTP **GET**?
> 
> ### Nivel Intermedio
> 
> 4. ¿Por qué se prefiere JSON sobre XML en las aplicaciones web actuales?
> 5. ¿Qué función cumple el "Body" en una petición de tipo **POST**?
> 6. ¿Cuál es la diferencia entre el **Frontend** y el **Backend** en términos de manejo de datos?
> 
> ### Nivel Avanzado
> 
> 7. Explique el proceso de "petición y respuesta" desde que el usuario solicita ver un catálogo hasta que los productos aparecen en pantalla.
> 8. ¿Cómo funciona Express en el contexto de una API Rest y qué es un "Endpoint"?
> 
> ## 10. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de las fuentes, se detallan los siguientes compromisos y directivas:
> 
> |Evento / Tarea|Fecha|Descripción Detallada|
> |---|---|---|
> |**Entrega Individual**|Clase 4 (Ya pasó / Pendiente)|Subir el avance individual en formato comprimido (.zip) a la plataforma. Es obligatorio para cerrar la etapa.|
> |**Clase Grabada**|28 de abril de 2026|Fecha de la sesión correspondiente a esta guía.|
> |**Actividad Grupal: CRUD Individual**|Próxima fase|Cada integrante del grupo debe elegir una clase/entidad (Producto, Cliente, Categoría, etc.) y realizar su ABM (CRUD) completo.|
> |**Integración de Proyecto**|En curso|Se debe designar a un responsable en el grupo para integrar los CRUDs individuales en el proyecto grupal principal.|
> 
> **Recordatorios Importantes:**
> 
> - **Nivelación:** El profesor enfatiza que los alumnos más avanzados deben ayudar a quienes tienen menos experiencia en frontend/backend para que todos alcancen un nivel sólido.
> - **Material Adicional:** Existe un anexo en la plataforma sobre qué es una API REST y ejemplos de JSON para quienes no han trabajado nunca con estos conceptos.
> - **Consultas:** Se recomienda el uso de Postman o Thunder Client para validar las APIs antes de intentar conectarlas al frontend.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 5 (28 04 26) - Desarrollo de sistemas orientado a la gestión" src="https://www.youtube.com/embed/irPvpc1xvVM?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1fdWsiRnfC8ihw-aQ69Ggnp75qt-a5LTy/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1KLAiz9McFVP2oV-zE9xp9mH4Uebnut2D/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>