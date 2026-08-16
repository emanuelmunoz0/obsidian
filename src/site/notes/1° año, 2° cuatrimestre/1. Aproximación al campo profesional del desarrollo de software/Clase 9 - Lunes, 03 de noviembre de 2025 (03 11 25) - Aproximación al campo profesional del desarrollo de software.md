---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/1-aproximacion-al-campo-profesional-del-desarrollo-de-software/clase-9-lunes-03-de-noviembre-de-2025-03-11-25-aproximacion-al-campo-profesional-del-desarrollo-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio: Integración de JavaScript y Desarrollo de Proyectos de Software
> 
> Este documento constituye un material de estudio exhaustivo basado en las directrices académicas y técnicas proporcionadas en el contexto de la materia. Se enfoca en la aproximación al campo profesional del desarrollo de software, específicamente en la integración de tecnologías para el desarrollo de aplicaciones funcionales.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> El desarrollo de software profesional exige la convergencia de diversas tecnologías y metodologías de trabajo. En el marco de la formación técnica, se ha identificado la necesidad de articular los conocimientos de **JavaScript (JS)** con la **Programación Orientada a Objetos (PPO)** para la creación de proyectos integradores.
> 
> Debido a la proximidad del cierre de la cursada, la metodología de enseñanza ha transitado hacia un modelo de **trabajo autónomo guiado**, donde los estudiantes aplican conceptos de frontend (HTML, CSS, JS) y backend (Node.js, Express, Bases de Datos) en proyectos reales como sistemas de reservas o plataformas de e-commerce.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual y Definiciones Clave
> 
> Para comprender la dinámica de trabajo propuesta, es fundamental definir los roles y herramientas involucradas desde una perspectiva profesional.
> 
> ### 2.1. Roles en la Metodología Ágil
> 
> El entorno de desarrollo se organiza bajo conceptos inspirados en marcos de trabajo ágiles:
> 
> - **Scrum Master:** Es el líder del equipo de desarrollo. Sus funciones principales incluyen motivar, organizar y asistir al equipo técnico (_Dev Team_). En el contexto académico, se requiere que posea conocimientos sólidos en JavaScript para guiar a sus compañeros.
> - **Product Owner:** Representado por el docente, es quien define los desafíos, establece los requerimientos del cliente y evalúa si las soluciones propuestas cumplen con los objetivos.
> - **Dev Team (Equipo de Desarrollo):** Estudiantes encargados de la codificación y resolución técnica de los requerimientos.
> 
> ### 2.2. Tecnologías y Herramientas del Ecosistema
> 
> El desarrollo se apoya en un _stack_ tecnológico específico:
> 
> |   |   |
> |---|---|
> |Tecnología|Descripción|
> |**JavaScript (JS)**|Lenguaje de programación fundamental para la lógica del lado del cliente y servidor.|
> |**Node.js**|Entorno de ejecución que permite correr JavaScript fuera del navegador.|
> |**Express**|Framework para Node.js que facilita la creación de servidores y el manejo de rutas.|
> |**MariaDB / PostgreSQL**|Sistemas de gestión de bases de datos para el almacenamiento persistente de información.|
> |**Visual Studio Code (VSC)**|Entorno de desarrollo integrado (IDE) estándar utilizado para escribir código.|
> |**Bootstrap**|Framework de CSS que permite el diseño de interfaces responsivas de forma acelerada.|
> 
> **Resumen Parcial:** La organización del trabajo se basa en roles (Scrum Master) y un conjunto de herramientas modernas (Node.js, Express, SQL) para construir proyectos que integren lógica y persistencia de datos.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: El Proyecto Integrador
> 
> La transición del aprendizaje teórico a la práctica profesional se manifiesta en la creación de una aplicación web completa. Este proceso implica tres dimensiones críticas: la estructura del código, la conexión con datos y la gestión del tiempo.
> 
> ### 3.1. Articulación entre Materias (PP1 y PPO)
> 
> El objetivo es que el proyecto de **Programación Orientada a Objetos (PPO)** se fusione con la **Práctica Profesional 1 (PP1)**. Mientras que PPO se encarga de la lógica de clases, herencia y modelos de datos, PP1 aporta la interactividad mediante JavaScript y el diseño con HTML/CSS.
> 
> ### 3.2. Estructura de una Aplicación con Express
> 
> Para poner en marcha un proyecto, se siguen pasos técnicos estandarizados en el entorno de desarrollo:
> 
> 1. **Instalación de dependencias:** Uso del comando `npm install express` en la terminal del IDE.
> 2. **Levantamiento del servidor:** Ejecución del archivo principal mediante el comando `node [nombre_archivo].js`.
> 3. **Acceso local:** Visualización a través de un puerto específico (ej. `localhost:3060`) en el navegador.
> 
> ### 3.3. Gestión de la Interfaz y el DOM
> 
> El documento de origen destaca el uso del **DOM (Document Object Model)** para manipular elementos HTML desde JavaScript. Un concepto clave mencionado es el método `appendChild`, que permite insertar nuevos nodos (como elementos de una lista o productos de un carrito) dinámicamente en la estructura de la página.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Relación entre Conceptos y Dependencias
> 
> La arquitectura del software requiere que los componentes se comuniquen entre sí. No basta con tener archivos aislados; debe existir un nexo.
> 
> - **HTML/CSS + JS:** La interfaz (HTML) se vincula con la lógica (JS) mediante etiquetas `<script>`.
> - **JS + Base de Datos (MariaDB):** Para que JavaScript pueda consultar o guardar datos, requiere un **conector específico** instalado en el proyecto. Sin este nexo, el código no puede identificar la existencia de la base de datos, aunque esta esté creada en el sistema.
> - **Lógica de Clases:** Las constantes y clases definidas en JavaScript sirven como moldes para los objetos que representarán entidades reales (clientes, habitaciones, productos).
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Ejemplos Prácticos y Aplicación
> 
> ### Caso: Ejecución de un Servidor Básico
> 
> Si un equipo desea probar su avance, la secuencia en la terminal de Visual Studio Code sería:
> 
> 1. `npm install express` (Solo la primera vez para descargar el framework).
> 2. `node server.js` (Suponiendo que el archivo principal se llama server.js).
> 3. Abrir el navegador y escribir `http://localhost:3060`.
> 
> ### Caso: Proyectos de Referencia
> 
> - **E-commerce:** Implementación de un carrito de compras donde se agregan productos mediante funciones de JavaScript.
> - **Sistema de Reservas de Hotel:** Gestión de clientes y disponibilidad de habitaciones mediante la interacción con tablas de una base de datos.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores Comunes y Aclaraciones Importantes
> 
> El análisis de las fuentes revela varios puntos de confusión frecuentes entre los estudiantes:
> 
> - **Falta del Conector de Base de Datos:** Es el error más común. Si al correr el código aparece un error tipo _"No se pudo encontrar el módulo MariaDB"_, es porque no se ha instalado el nexo entre el IDE y el motor de base de datos.
> - **Mezcla de HTML dentro de JS:** Algunos enfoques incluyen bloques de código HTML dentro de constantes de JavaScript. Esto puede dificultar la detección de errores de sintaxis (como etiquetas o llaves sin cerrar), ya que el editor de código no siempre resalta errores dentro de un bloque de texto.
> - **Diferencia entre Proyecto y Carpetas:** Al abrir archivos de scripts y HTML por separado, se pierde la relación mutua. Es vital mantener una estructura de carpetas donde un archivo principal relacione las constantes, los scripts de la interfaz y las hojas de estilo.
> - **Credenciales de Acceso:** No se puede conectar a una base de datos sin definir previamente el usuario y la contraseña en los parámetros de conexión del código.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Síntesis y Conclusiones
> 
> El desarrollo de software es una tarea integradora. El éxito de un proyecto depende de:
> 
> 1. **Organización del equipo:** Un Scrum Master que coordine y motive.
> 2. **Solidez técnica:** Conocimientos básicos de JavaScript aplicados al DOM y al servidor.
> 3. **Conectividad:** Asegurar que el servidor Express, la base de datos y la interfaz HTML estén correctamente vinculados.
> 
> La recomendación principal es avanzar en la estructura de clases y el diseño visual (apoyándose en herramientas como Bootstrap), para luego enfocarse en la complejidad de la conexión de datos.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de las fuentes, se detallan los siguientes hitos y directrices para el cierre de la cursada:
> 
> ### Calendario de Clases y Evaluaciones
> 
> - **Clases restantes:** 3 de junio, 10 de junio y 17 de junio.
> - **Feriado (Sin actividad):** 24 de junio (debido al feriado puente del 21 y el paso del feriado del 20 al lunes).
> - **Fecha límite de entrega (PPO):** Miércoles 26 de junio.
> - **Cierre de notas:** 29 de junio.
> 
> ### Horarios y Metodología
> 
> - **Conexión del profesor:** De 18:30 a 22:00 hs.
> - **Clase efectiva:** De 19:00 a 21:00 hs.
> - **Segundo Parcial:** Se evaluará mediante el trabajo práctico de JavaScript realizado en las últimas tres clases. No habrá un examen tradicional escrito, sino una evaluación del desarrollo del proyecto.
> 
> ### Advertencias Académicas
> 
> - Se insta a los grupos a utilizar el tiempo de clase para avanzar de forma autónoma en sus proyectos.
> - Los alumnos que no cursan PPO deben integrarse a sus grupos de trabajo y aportar en la parte de JavaScript y diseño.
> - El docente actuará como articulador para asegurar que las exigencias de PPO sean acordes al nivel actual de los estudiantes, facilitando la integración de conocimientos.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la función principal de un Scrum Master dentro de un equipo de desarrollo?
> 2. ¿Qué comando se utiliza para instalar el framework Express en un proyecto de Node.js?
> 3. ¿Cuál es el rol del "Product Owner" según la dinámica planteada en clase?
> 
> ### Nivel Intermedio
> 
> 4. Explique la importancia de los "conectores" al trabajar con bases de datos como MariaDB desde Visual Studio Code.
> 5. ¿Qué ventajas ofrece el uso de Bootstrap en un proyecto con tiempos de entrega reducidos?
> 6. ¿Por qué es problemático incluir grandes bloques de código HTML dentro de constantes de JavaScript?
> 
> ### Nivel Avanzado
> 
> 7. Describa el flujo completo desde que se inicia un servidor con Node.js hasta que el usuario ve el resultado en su navegador.
> 8. ¿Cómo se articulan los conceptos de clases y herencia de PPO con la interactividad de JavaScript en el frontend?
> 9. Analice las consecuencias de no tener una base de datos definida (tablas y campos) al momento de programar la lógica de una aplicación e-commerce.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 9 - Aproximación al campo profesional del desarrollo de software" src="https://www.youtube.com/embed/E1uprfLu1Xk?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1yUCf_M7FF8bFrlzGEWUBvjYwNhKNZifw/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1J2jZNmGI1Uv8upVdYTze08r3ZLXQqBrT/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>