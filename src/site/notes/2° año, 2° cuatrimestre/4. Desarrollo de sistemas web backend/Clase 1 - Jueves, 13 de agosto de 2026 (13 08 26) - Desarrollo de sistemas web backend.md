---
{"dg-publish":true,"permalink":"/2-ano-2-cuatrimestre/4-desarrollo-de-sistemas-web-backend/clase-1-jueves-13-de-agosto-de-2026-13-08-26-desarrollo-de-sistemas-web-backend/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Desarrollo de Sistemas Web Backend con Node.js: Fundamentos y Arquitectura
> 
> Este documento constituye una guía exhaustiva y técnica sobre el desarrollo de sistemas backend utilizando Node.js. Ha sido diseñado como material de estudio principal para comprender desde los conceptos más elementales hasta las implicancias arquitectónicas y de seguridad de esta tecnología en el entorno profesional.
> 
> ## 1. Introducción General
> 
> El desarrollo de sistemas web backend representa la lógica "detrás de escena" que permite que las aplicaciones modernas funcionen, procesen datos y se comuniquen con otros servicios. En este contexto, **Node.js** surge como una herramienta fundamental que permite ejecutar JavaScript fuera del navegador, específicamente en servidores.
> 
> Esta materia se sitúa en un punto medio crítico del trayecto formativo: se imparte en paralelo con Desarrollo Frontend y sirve como base necesaria para cursar Programación sobre Redes. El objetivo principal es integrar conocimientos previos de lógica de programación para construir APIs robustas, gestionar bases de datos y asegurar la persistencia de la información.
> 
> ## 2. Contexto e Importancia
> 
> ### Evolución de la Web: De lo Estático a lo Dinámico
> 
> Para entender Node.js, es necesario comprender la evolución tecnológica de la web:
> 
> 1. **Páginas Estáticas:** Basadas originalmente en HTML y CSS. Eran documentos fijos donde el contenido no cambiaba según la interacción del usuario.
> 2. **Páginas Dinámicas:** Con la aparición de JavaScript en el frontend (navegador) y luego herramientas como jQuery, el contenido empezó a tener "vida".
> 3. **Node.js y la Unificación:** Node.js permitió que el mismo lenguaje utilizado para dar interactividad en el navegador (JavaScript) pudiera usarse para gestionar archivos en un servidor, conectar con bases de datos y procesar lógica compleja de negocio.
> 
> ### Relevancia de Node.js
> 
> Node.js es valorado en la industria por su capacidad de **multiprosesamiento y concurrencia**. Es un lenguaje escalar, lo que significa que es ideal tanto para aplicaciones pequeñas como para infraestructuras en la nube (Cloud) mediante contenedores (Docker).
> 
> ## 3. Marco Conceptual y Definiciones Clave
> 
> ### ¿Qué es Node.js?
> 
> Es un entorno de ejecución de JavaScript orientado a eventos y de código abierto. Fue desarrollado por Google para potenciar la ejecución de código en el lado del servidor de manera eficiente.
> 
> ### Términos Fundamentales
> 
> - **Motor V8:** Es el motor desarrollado por Google (utilizado en Chrome) que traduce el código JavaScript a código de máquina (C++) para que el procesador pueda entenderlo. Es el responsable de la alta performance de Node.js.
> - **Libuv:** Una capa abstracta escrita en C++ que permite a Node.js interactuar con el sistema operativo (Linux, Windows o Mac) de forma agnóstica.
> - **Gestor de Paquetes (NPM):** _Node Package Manager_. Es un ecosistema masivo donde desarrolladores comparten librerías (módulos) de código para realizar tareas específicas sin tener que programarlas desde cero.
> 
> ## 4. Desarrollo del Tema: Arquitectura y Funcionamiento
> 
> ### El Event Loop (Bucle de Eventos)
> 
> Node.js funciona bajo una arquitectura **asíncrona y basada en un solo hilo (single-thread)**. Su funcionamiento se puede resumir en los siguientes componentes:
> 
> 1. **Event Queue (Cola de Eventos):** Todas las solicitudes (requests) o comandos ejecutados caen en una cola bajo el principio FIFO (_First In, First Out_: el primero en entrar es el primero en salir).
> 2. **Event Loop:** Un ciclo que consume permanentemente la cola de eventos.
> 3. **Worker Threads:** Cuando una tarea es pesada (como leer un archivo o consultar una base de datos), el Event Loop la delega a estos hilos de trabajo para no bloquear la ejecución principal.
> 4. **Callback Queue:** Una vez que la tarea delegada termina, el resultado se coloca en esta cola para ser devuelto al usuario.
> 
> ### Sincronía vs. Asincronía
> 
> - **Operaciones Síncronas (Bloqueantes):** El hilo principal se detiene hasta que la tarea termina. Si una tarea tarda mucho (ej. procesar un video), toda la aplicación queda "colgada" para el resto de los usuarios.
> - **Operaciones Asíncronas (No Bloqueantes):** Node.js da la orden de ejecución y continúa con la siguiente tarea. Cuando la operación inicial termina, recibe una notificación (callback).
> 
> **Resumen Parcial:** La potencia de Node.js reside en su capacidad de no bloquear el hilo principal, permitiendo manejar miles de conexiones concurrentes de manera eficiente.
> 
> ## 5. Seguridad en el Desarrollo Backend
> 
> El acceso directo al servidor y al sistema operativo que ofrece Node.js implica riesgos críticos que deben gestionarse:
> 
> ### Riesgos de Librerías de Terceros
> 
> Al instalar paquetes mediante NPM, se está inyectando código de terceros en el servidor. Si una librería no tiene mantenimiento o es vulnerada, un atacante podría:
> 
> - Realizar inyecciones de código.
> - Acceder a la base de datos y cifrarla (Ransomware).
> - Tomar control del servidor para realizar _overclocking_ o apagarlo.
> 
> ### Buenas Prácticas y Mantenimiento
> 
> Node.js ofrece diferentes versiones para gestionar la estabilidad:
> 
> - **LTS (Long Term Support):** Versiones con soporte extendido (usualmente 5 años). Son las recomendadas para proyectos profesionales ya que garantizan parches de seguridad y estabilidad.
> - **Current (Latest Release):** Versiones con las últimas funcionalidades, pero sujetas a cambios que podrían romper el código (deprecated methods).
> 
> ## 6. Ejemplos Prácticos y Aplicación
> 
> ### Instalación y Verificación
> 
> Para comenzar a trabajar, se debe instalar Node.js desde su página oficial. Una vez instalado, se verifican las versiones en la terminal:
> 
> ```bash
> node -v    # Muestra la versión del motor Node.js
> npm -v     # Muestra la versión del gestor de paquetes
> ```
> 
> ### Ejecución de Comandos y Scripts
> 
> Existen tres formas principales de ejecutar código Node.js:
> 
> 1. **REPL:** Escribir `node` en la terminal e interactuar directamente línea por línea.
> 2. **Parámetro -e:** Ejecutar código directamente desde la terminal: `node -e "console.log(os.userInfo())"`.
> 3. **Scripts:** Crear un archivo `.js` y ejecutarlo con `node nombre_archivo.js`.
> 
> ### Interacción con el Sistema Operativo (Módulo OS)
> 
> Node.js permite obtener información sensible y técnica del servidor:
> 
> - **Memoria Libre:** `os.freemem()`
> - **Información del Usuario:** `os.userInfo()`
> - **CPUs disponibles:** Permite saber cuántos hilos puede manejar el sistema.
> 
> ## 7. Relación entre Conceptos y Evolución del Curso
> 
> El aprendizaje de la materia se estructura de forma escalar:
> 
> 1. **Nivel Inicial:** Declaración de variables (`let`, `const`), funciones y módulos nativos.
> 2. **Nivel Intermedio:** Construcción de APIs, gestión de roles y permisos (RBAC), y manejo de logs (registros de actividad).
> 3. **Nivel Avanzado:** Conexión a bases de datos relacionales (SQL) y no relacionales mediante ORMs, criptografía (simétrica y asimétrica) y dockerización.
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> A continuación, se detallan las pautas organizativas y evaluativas de la cursada:
> 
> |   |   |   |
> |---|---|---|
> |Evento / Obligación|Detalles|Fecha Estimada|
> |**Inicio de Clases**|Jueves, 19:05 hs (Tolerancia hasta 19:10).|-|
> |**Primer Parcial**|Presentación individual presencial. Sistema de gestión de logs y autenticación básica.|Clase 6|
> |**Segundo Parcial**|Presentación individual presencial. Proyecto integrador final (API completa).|Clase 12|
> |**Recuperatorio**|Instancia para quienes desaprobaron o fallaron en una entrega (requiere asistencia previa).|Al finalizar la cursada|
> 
> ### Avisos Académicos Clave:
> 
> - **Régimen de Promoción:** La materia es promocionable si el promedio final es de **7 o más**.
> - **Modalidad de Examen:** Los exámenes consisten en la defensa oral del código frente al profesor. Se evalúa la lógica aplicada y la capacidad de explicar el funcionamiento de los módulos.
> - **Uso de IA:** Se permite el uso de Inteligencia Artificial como apoyo, pero el alumno debe ser capaz de fundamentar cada línea de código y explicar por qué eligió un método sobre otro.
> - **Plataforma:** Las clases se graban y suben a la plataforma. Los materiales complementarios y consignas viejas están disponibles como referencia, pero las nuevas consignas se publicarán oportunamente.
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia principal entre una página web estática y una dinámica?
> 2. ¿Para qué sirve el comando `npm` en el ecosistema de Node.js?
> 3. ¿Qué diferencia hay entre una variable declarada con `let` y una constante declarada con `const`?
> 
> ### Nivel Intermedio
> 
> 4. Explique con sus palabras el funcionamiento del _Event Loop_.
> 5. ¿Por qué es preferible utilizar una versión **LTS** de Node.js en un entorno de producción?
> 6. ¿Qué riesgos de seguridad implica el uso de librerías de terceros sin auditoría?
> 
> ### Nivel Avanzado (Tipo Examen)
> 
> 7. Describa una situación donde una operación síncrona podría causar un "cuello de botella" o _deadlock_ en una aplicación de Node.js.
> 8. ¿Cómo interactúa la capa **Libuv** con el sistema operativo y por qué se dice que es "agnóstica"?
> 9. Si una API de Node.js permite la ejecución de comandos en el sistema operativo sin sanitización, ¿qué tipo de ataques podría sufrir el servidor?

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 1 (13 08 26) - Desarrollo de sistemas web backend" src="https://www.youtube.com/embed/kwpNVj4RWHY?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1bDG8ZSmLOMgNtw0wqKjeRCvCWLFSlSPL/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1h1SRNDhJaW0EccdnrZenL1-5D-L7eXZG/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>