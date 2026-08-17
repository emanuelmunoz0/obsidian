---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/4-administracion-de-base-de-datos/clase-2-viernes-28-de-marzo-de-2025-28-03-25-administracion-de-base-de-datos/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Administración de Bases de Datos: Fundamentos, Estructuras y Gestión de Información
> 
> Este documento constituye una guía de estudio integral y profunda sobre la administración de bases de datos, diseñada para proporcionar un entendimiento completo desde los conceptos básicos hasta los niveles técnicos y organizativos avanzados.
> 
> ## 1. Introducción General
> 
> En el ámbito de la informática y los sistemas, la gestión de datos es la piedra angular del funcionamiento de cualquier organización moderna. Un sistema computacional se define por cuatro operaciones fundamentales que permiten el ciclo de vida de la información:
> 
> 1. **Aceptar entradas:** Recepción de datos brutos.
> 2. **Procesar datos:** Manipulación y transformación de las entradas.
> 3. **Producir salidas:** Generación de resultados para el usuario o para otros sistemas.
> 4. **Almacenar información:** Persistencia de aquello que tiene valor para ser consultado en el futuro.
> 
> ### Contexto: Hardware y Software
> 
> El ecosistema donde ocurren estas operaciones se divide en dos grandes áreas:
> 
> - **Hardware:** Representa los componentes físicos, electrónicos y mecánicos (conocidos coloquialmente como "fierros"). Actualmente, se caracterizan por una creciente capacidad de procesamiento, mayor velocidad y miniaturización.
> - **Software:** Es el conjunto de instrucciones lógicas que indican al hardware cómo debe actuar para cumplir con los objetivos del sistema.
> 
> ## 2. Marco Conceptual: De Datos a Información
> 
> Para comprender las bases de datos, es imperativo distinguir entre los elementos básicos que la componen.
> 
> ### Definición de Conceptos Clave
> 
> |   |   |   |
> |---|---|---|
> |Concepto|Definición|Ejemplo|
> |**Dato**|Elemento básico que, por sí solo, no posee un valor agregado ni contexto.|El número "15".|
> |**Proceso**|Acciones con un orden específico, un principio y un fin definido que transforman el dato.|Relacionar "15" con un campo de "edad" en una ficha médica.|
> |**Información**|El resultado de procesar los datos dentro de un contexto para que adquieran significado.|"La edad de la paciente es 15 años y requiere una planificación de evento."|
> 
> **El Valor Estratégico de la Información** La información no es simplemente un subproducto; es un recurso que debe manejarse bajo criterios de costo-beneficio. Su producción, seguridad, distribución y almacenamiento implican costos asociados que una organización debe gestionar. Por ello, la información debe ser **útil** y utilizarse **estratégicamente**.
> 
> ## 3. Características de la Información Útil
> 
> Para que la información sea considerada un activo valioso en la toma de decisiones, debe cumplir con cinco atributos esenciales:
> 
> 1. **Relevante:** Debe estar directamente relacionada con el problema que se busca resolver.
> 2. **Completa:** La información parcial es riesgosa, ya que puede conducir a decisiones erróneas por falta de contexto.
> 3. **Precisa (Exacta):** La información errónea invalida cualquier proceso de decisión, aunque esté completa.
> 4. **Actual:** Debe reflejar la realidad del momento. Comparar datos de contextos temporales disímiles (ej. ventas en pandemia vs. ventas actuales) puede generar tendencias engañosas.
> 5. **Económica:** El costo de obtención debe ser menor o proporcional al beneficio que otorga. Las investigaciones de mercado, por ejemplo, son costosas y requieren un procesamiento riguroso para justificar la inversión.
> 
> ## 4. Sistemas de Información (SI)
> 
> Un **Sistema de Información** es un conjunto de componentes interrelacionados que recuperan, procesan, almacenan y distribuyen información. Su fin último es apoyar la toma de decisiones y el control de una organización.
> 
> En una empresa, el SI se refleja en su **organigrama**. Cada sector (Contabilidad, Recursos Humanos, Ventas, Producción) funciona como un módulo que genera y consume datos. Mientras que antiguamente estos sistemas dependían de procesos manuales (biblioratos, carritos de distribución de memorándums), hoy se gestionan de forma digital y automatizada.
> 
> ## 5. Roles en la Administración de Datos
> 
> La gestión de una base de datos profesional requiere la distinción de dos roles críticos que trabajan en conjunto:
> 
> ### Data Administrator (DA)
> 
> - **Perfil:** Gerencial o administrativo (Administrador de empresas, experto en marketing, directivo).
> - **Responsabilidad:** Es el responsable central de los datos. Decide qué datos deben almacenarse basándose en las necesidades del negocio.
> - **Función:** Establece las políticas de seguridad y acceso (quién puede ver qué). Posee la "llave maestra" del sistema.
> 
> ### Database Administrator (DBA)
> 
> - **Perfil:** Profesional técnico (IT).
> - **Responsabilidad:** Ejecuta las políticas dictadas por el DA.
> - **Función:** Crea las bases de datos, garantiza su funcionamiento, realiza consultas complejas (scripts), gestiona los accesos técnicos y asegura la integridad física de los datos.
> 
> ## 6. Persistencia y Almacenamiento
> 
> La **persistencia** es la capacidad de los datos de sobrevivir en el tiempo, asegurando que no se pierdan al apagar el sistema.
> 
> - **Almacenamiento Físico:** Evolución desde medios magnéticos antiguos (discos de 5 1/4" y 3 1/2") hasta la tecnología actual (discos sólidos SSD, pendrives, tarjetas de memoria y la Nube).
> - **Almacenamiento Lógico:** Se refiere a cómo se organizan los datos para su recuperación rápida y eficiente. Una mala organización lógica (como una carpeta de "Mis Documentos" desordenada) dificulta el acceso, mientras que una estructura de base de datos sólida permite un sistema veloz.
> 
> ## 7. El Sistema de Base de Datos (DBMS)
> 
> Un sistema de base de datos moderno se compone de tres elementos: **Datos, Hardware y Software.** El componente de software principal es el **Database Management System (DBMS)** o Gestor de Base de Datos.
> 
> ### Niveles de Abstracción
> 
> Para que un sistema sea funcional, el DBMS maneja tres niveles:
> 
> 1. **Nivel Físico:** El motor de la base de datos propiamente dicho (la implementación técnica en el almacenamiento).
> 2. **Nivel Lógico:** El nivel donde el DBA y los desarrolladores modelan las relaciones entre los datos.
> 3. **Nivel de Vistas:** Lo que el usuario final o una aplicación externa (vía API) ve. Por ejemplo, un formulario de login es una "vista" que oculta la complejidad de la base de datos subyacente.
> 
> ## 8. El Modelo Relacional y SQL
> 
> Aunque existen múltiples modelos (jerárquicos, de red, multidimensionales, NoSQL), el estándar más utilizado en la industria y el objeto principal de este estudio es el **Modelo Relacional**.
> 
> ### Lenguaje SQL (Structured Query Language)
> 
> Es el lenguaje estándar mundial (supervisado por ANSI) para interactuar con bases de datos relacionales. Se divide en dos sub-lenguajes:
> 
> - **DDL (Data Definition Language):** Se utiliza para definir la estructura.
>     - _Comandos:_ `CREATE` (crear tablas/bases), `DROP` (eliminar), `ALTER` (modificar estructuras).
> - **DML (Data Manipulation Language):** Se utiliza para operar con los datos existentes (proceso conocido como **CRUD**: Create, Read, Update, Delete).
>     - _Comandos:_ `INSERT` (insertar), `SELECT` (recuperar/leer), `UPDATE` (modificar datos), `DELETE` (eliminar datos).
> 
> ### Motores Principales
> 
> - **Comerciales:** Oracle, IBM DB2, SQL Server (Microsoft).
> - **Libre Distribución:** MySQL, MariaDB, PostgreSQL, SQLite.
> 
> ## 9. Ventajas del Uso de Bases de Datos
> 
> El uso de un DBMS profesional ofrece beneficios críticos frente al almacenamiento en archivos simples:
> 
> - **Evitar la redundancia:** No repetir datos innecesariamente.
> - **Consistencia e Integridad:** Asegurar que el dato sea sólido, robusto y correcto.
> - **Seguridad:** Restringir accesos y realizar copias de seguridad (backups).
> - **Compartición fluida:** Acceso simultáneo desde múltiples dispositivos y ubicaciones.
> - **Independencia del dato:** Facilidad para modificar la estructura sin perder la información.
> 
> ## 10. Errores Comunes y Confusiones
> 
> - **Dato vs. Información:** Es un error común usarlos como sinónimos. El dato es la materia prima; la información es el producto procesado y con valor.
> - **Dato en Reposo:** Antiguamente se definía a la base de datos como "datos en reposo". Hoy, con la globalización y servicios como Netflix o Instagram, el dato nunca "duerme"; siempre está siendo consultado o respaldado en algún lugar del mundo.
> - **Integridad vs. Seguridad:** La **integridad** se refiere a que el dato sea correcto y no esté corrupto (robustez). La **seguridad** se refiere a la protección contra accesos no autorizados o robos.
> 
> ## 11. Síntesis y Conclusiones
> 
> - La administración de bases de datos no es solo técnica, sino estratégica; la información debe ser útil para la toma de decisiones.
> - El **DA** define la estrategia y el **DBA** ejecuta la técnica.
> - El lenguaje **SQL** es la herramienta universal para gestionar estructuras (**DDL**) y manipular datos (**DML**).
> - La organización lógica es tan importante como la capacidad física para garantizar la velocidad y eficiencia del sistema.
> 
> ## 12. Preguntas de Repaso
> 
> ### Básicas
> 
> 1. ¿Cuál es la diferencia fundamental entre hardware y software?
> 2. Defina "Dato" e "Información" con un ejemplo original.
> 3. ¿Cuáles son las cuatro operaciones de un sistema computacional?
> 
> ### Intermedias
> 
> 4. Explique las cinco características de la información útil. ¿Por qué la "información parcial" puede ser peligrosa?
> 5. Compare los roles del DA y el DBA. ¿Quién posee la "llave maestra" y por qué?
> 6. ¿Qué es el CRUD y con qué parte del lenguaje SQL se relaciona (DDL o DML)?
> 
> ### Avanzadas
> 
> 7. Explique los tres niveles de abstracción de una base de datos. ¿En cuál de ellos se sitúa un usuario que completa un formulario web?
> 8. ¿Por qué la definición de base de datos como "lugar de datos en reposo" se considera obsoleta en la actualidad?
> 9. Diferencie entre Integridad y Seguridad de los datos en el contexto de un DBMS.
> 
> ## Fechas importantes y avisos académicos
> 
> A partir del análisis de la fuente, se identifican las siguientes indicaciones del profesor para la materia de Administración de Base de Datos en el **IFTS 16**:
> 
> - **Evento:** Entrega de Cuestionario (Unidad 1).
>     - **Fecha:** Inmediata (se menciona que "en un santamén les va a salir").
>     - **Medio de entrega:** Por correo electrónico (debido a la falta momentánea de aula virtual/Moodle).
>     - **Requisitos de formato:**
>         - **Asunto del mail:** Debe decir estrictamente: `IFTs 16, base de dato`.
>         - **Nombre del archivo:** Debe incluir el nombre del alumno para facilitar la identificación y la carga de notas.
>     - **Ubicación del cuestionario:** El profesor lo envió por el chat de la clase y también por el grupo de WhatsApp.
> - **Aviso sobre Grupos:** Se envió un formulario para la conformación de grupos. Una vez que el aula virtual esté operativa, la carga de notas y grupos se automatizará por esa vía.
> - **Próxima Clase:** Se iniciará con el tema de **Modelado de Datos**.
> - **Estado del Aula Virtual (Moodle):** Se encuentra fuera de servicio o inaccesible ("en reposo" según la broma académica de la clase), por lo que la comunicación se mantiene vía WhatsApp y Mail.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 2 - Administración de base de datos" src="https://www.youtube.com/embed/FlIap7mFKEk?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1XLwtGi5gDyw6kSYLff4WcQ8h_pH61a6C/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1Obc_v1ucNglYha6q5Q9rQWRQPuQPA_sg/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>