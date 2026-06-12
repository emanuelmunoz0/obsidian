---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/3-desarrollo-de-sistemas-orientado-a-la-gestion/clase-9-martes-09-de-junio-de-2026-09-06-26-desarrollo-de-sistemas-orientado-a-la-gestion/","dg-note-properties":{}}
---


> [!quote]- Resumen
> # Desarrollo de Sistemas Orientados a la Gestión: Administración, Paginación y Asistencia por IA
> 
> Este documento constituye una síntesis exhaustiva de los contenidos abordados en la novena sesión del curso, enfocada en la culminación de un Producto Mínimo Viable (MVP) para la gestión empresarial. Se detallan las estrategias de organización de equipos, el desarrollo de paneles administrativos, la implementación técnica de paginación en APIs y la integración de asistentes de inteligencia artificial en el flujo de trabajo profesional.
> 
> ## 1. Introducción y Contexto del Proyecto
> 
> El desarrollo de software orientado a la gestión ha evolucionado desde la conceptualización de reglas de negocio y restricciones hasta la creación de una arquitectura funcional. El objetivo central es construir una herramienta que facilite la toma de decisiones gerenciales.
> 
> En esta etapa del curso, el enfoque se desplaza hacia la consolidación de la interfaz de administración y la optimización del rendimiento de las aplicaciones mediante el manejo eficiente de datos. El proyecto se encuentra en una fase de transición crítica donde se integran la lógica de negocio, la seguridad de rutas y la eficiencia en la consulta de catálogos extensos.
> 
> ## 2. Marco Conceptual y Definiciones Clave
> 
> Para comprender la arquitectura del sistema, es imperativo dominar los siguientes conceptos fundamentales:
> 
> - **Panel de Administrador:** Interfaz de usuario intuitiva diseñada específicamente para la gestión interna de la aplicación, permitiendo operaciones sobre productos, clientes, descuentos y categorías.
> - **Paginación:** Técnica de optimización que consiste en dividir los resultados de una consulta a la base de datos en bloques manejables (páginas), evitando la saturación del sistema por exceso de datos.
> - **API (Application Programming Interface):** Interfaz que permite la comunicación entre el frontend y el backend, gestionando las peticiones de datos bajo parámetros específicos.
> - **Middleware:** Capa de software que se ejecuta entre la petición del usuario y el controlador final, utilizada principalmente para la protección de rutas y validación de perfiles (Admin vs. Cliente).
> - **Desarrollo Asistido por IA:** Metodología de programación donde se utilizan agentes de inteligencia artificial para explicar, generar o depurar código, actuando como un asesor técnico dentro del entorno de desarrollo.
> 
> ## 3. Desarrollo del Tema
> 
> ### 3.1. Organización del Flujo de Trabajo con Git
> 
> La gestión de repositorios es fundamental para el trabajo colaborativo. Las prácticas recomendadas extraídas de la experiencia de los grupos incluyen:
> 
> - **Uso de Ramas (Branches):** Cada integrante desarrolla una funcionalidad en una rama independiente para evitar conflictos en los artefactos del código.
> - **Fusión (Merge):** Integración de las ramas una vez completada la tarea.
> - **Programación en Parejas (Pair Programming):** Práctica de programar en conjunto mediante sesiones virtuales para compartir conocimientos y resolver problemas en tiempo real.
> 
> ### 3.2. El Panel de Administración y la Toma de Decisiones
> 
> El panel administrativo no solo sirve para la carga de datos, sino como una herramienta estratégica. Sus funciones principales incluyen:
> 
> - **Gestión de Entidades:** Control total sobre productos, categorías, clientes y descuentos.
> - **Filtros de Búsqueda:** Capacidad de localizar información por diversos criterios (nombre, email, identificador, zona geográfica).
> - **Exportación de Datos:** Funcionalidad para bajar información a formatos como Excel. Esto es vital para departamentos comerciales y de marketing (por ejemplo, para filtrar clientes de una zona específica y realizar campañas segmentadas).
> 
> ### 3.3. Implementación Técnica de la Paginación
> 
> La paginación es una restricción necesaria en cualquier API profesional para evitar errores de _timeout_ (tiempo de espera agotado) cuando el catálogo es extenso.
> 
> **Parámetros fundamentales en el Controlador:**
> 
> 1. **Page (Página):** El número de bloque de datos que se desea visualizar.
> 2. **Limit (Límite):** La cantidad de ítems a mostrar por página (comúnmente 10, 30 o 50).
> 
> **Lógica del Offset:** El programa calcula automáticamente qué registros mostrar basándose en estos parámetros. Si se solicita un límite de 50 y la página 3, el sistema ignorará los primeros 100 registros y devolverá del 101 al 150 mediante una consulta SQL optimizada.
> 
> ### 3.4. Integración de Inteligencia Artificial en el Desarrollo
> 
> El mercado laboral actual exige el uso de herramientas de IA. Se destacan dos enfoques:
> 
> - **IA como Asesor:** No se trata de pedir que la IA "haga todo", sino de atomizar las tareas, preguntar para entender conceptos (por qué se usa un controlador o un middleware) y aprender durante el proceso.
> - **Herramientas en el Entorno (IDE):** Uso de extensiones como **Codex** o **GitHub Copilot** dentro de Visual Studio Code. Estas herramientas permiten interactuar directamente con el contexto del repositorio local.
> 
> ## 4. Relaciones entre Conceptos
> 
> La efectividad del sistema reside en la conexión de sus partes:
> 
> 1. **Login y Perfiles:** El inicio de sesión determina si el usuario es "Cliente" o "Administrador".
> 2. **Middlewares y Seguridad:** Basándose en el perfil definido, el Middleware permite o bloquea el acceso a las rutas del Panel de Administración.
> 3. **Arquitectura y IA:** Para usar la IA de forma efectiva, el desarrollador debe conocer la base (qué es una API, por qué se pagina, cómo funciona la seguridad), ya que de lo contrario existe un "gap" de conocimiento que impide validar la calidad del código generado.
> 
> ## 5. Ejemplos Prácticos
> 
> ### Ejemplo de Paginación Matemática
> 
> Si un sistema tiene un total de 23 productos y se establece un límite de 5 productos por página:
> 
> - **Total de páginas:** 5 páginas.
> - **Consulta para Página 2:** Mostrará los productos del 6 al 10.
> - **Petición a la API:** `GET /productos?page=2&limit=5`
> 
> ### Caso de Uso: Marketing
> 
> Un gerente comercial necesita realizar una promoción exclusiva para la zona de Mendoza.
> 
> 1. Accede al **Panel de Administrador**.
> 2. Filtra la lista de **Clientes** por zona.
> 3. Utiliza la función **Bajar a Excel**.
> 4. Carga esa lista en una plataforma de campañas (Facebook, Instagram) para publicidad dirigida.
> 
> ## 6. Errores Comunes y Confusiones
> 
> - **No Paginación:** Intentar cargar miles de productos de una sola vez, lo que provoca la caída del servicio por _timeout_.
> - **Dependencia Ciega de la IA:** Solicitar código sin entender la arquitectura subyacente. Se enfatiza que no se debe subir un _commit_ que no haya sido supervisado o que no se pueda explicar su funcionamiento base.
> - **Confusión de Roles:** No proteger las rutas administrativas con middlewares, permitiendo que un perfil de cliente acceda a funciones de edición o borrado de productos.
> 
> ## 7. Síntesis y Conclusiones
> 
> El desarrollo actual se centra en cerrar el ciclo del MVP. Los pilares actuales son:
> 
> - La implementación de un **CRUD** (Crear, Leer, Actualizar, Borrar) funcional en el panel administrativo.
> - La optimización de consultas mediante **paginación**.
> - La **protección de rutas** para diferenciar el acceso entre clientes y administradores.
> - La adopción de **IA generativa** como un compañero de desarrollo que aporta contexto y velocidad, siempre bajo la supervisión de un programador con bases técnicas sólidas.
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuáles son los dos parámetros esenciales que debe recibir un controlador para realizar una paginación?
> 2. ¿Para qué sirve la función de exportar a Excel en un panel de administración?
> 
> ### Nivel Intermedio
> 
> 1. Explique cómo funciona un Middleware en la protección de rutas del administrador.
> 2. ¿Cuál es la diferencia entre usar Chat GPT de forma abierta y usar una extensión como Codex dentro de Visual Studio Code?
> 
> ### Nivel Avanzado
> 
> 1. Si una base de datos tiene 500 registros y el usuario solicita la página 5 con un límite de 50, ¿qué registros (rango numérico) debería devolver la consulta SQL? Explique el concepto de _offset_.
> 2. Analice la importancia estratégica de comprender las "reglas de negocio" antes de comenzar la codificación con asistencia de IA.
> 
> ## 9. Fechas Importantes y Avisos Académicos
> 
> A continuación, se detallan las fechas clave para el cierre del cuatrimestre y las consignas del profesor:
> 
> |   |   |   |
> |---|---|---|
> |Fecha|Tipo de Evento|Descripción Detallada|
> |**16 de Junio**|Clase de Cierre/Repaso|Última clase de contenidos teóricos y revisión de temas pendientes antes de la entrega.|
> |**23 de Junio**|**Demo Final (Presentación)**|Presentación presencial de la aplicación terminada (MVP). Debe incluir vista de cliente, carrito, login con perfiles y al menos una pantalla de administración operativa.|
> |**30 de Junio**|Recuperatorio / Taller de Publicación|Fecha destinada a quienes deban recuperar o ajustar la entrega. Se aprovechará para subir las aplicaciones a la web (ej. Versel) para que queden como catálogo personal.|
> |**3 de Julio**|Fin del Cuatrimestre|Cierre oficial de actas y finalización del periodo lectivo.|
> 
> **Recordatorios Importantes:**
> 
> - **Requisito de Aprobación:** La aplicación debe tener, como mínimo, una pantalla de administración funcional que permita agregar/editar datos y bajar información a Excel.
> - **Asistencia por IA:** Se recomienda empezar a utilizar asistentes de IA (Codex/Copilot) para avanzar en el código de las clases restantes.
> - **Estado del Proyecto:** Los grupos que ya tengan el login y la protección de rutas (Middlewares) están muy avanzados y cerca del objetivo de aprobación. Una vez hecha una pantalla de administración, el resto es "copiar, pegar y adaptar datos".

  
> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 9 (09 06 26) - Desarrollo de sistemas orientado a la gestión" src="https://www.youtube.com/embed/TDtdM3U0K1E?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/11v3T72wVuxHiIQA3ySIX-MeZUICRW0aK/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/18xpyUlf7V292Ttm-TWmHo4r6YL6V37SY/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>