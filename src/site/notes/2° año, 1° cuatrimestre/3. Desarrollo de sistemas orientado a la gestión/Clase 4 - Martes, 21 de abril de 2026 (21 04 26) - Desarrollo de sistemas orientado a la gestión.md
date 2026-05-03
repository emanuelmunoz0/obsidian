---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/3-desarrollo-de-sistemas-orientado-a-la-gestion/clase-4-martes-21-de-abril-de-2026-21-04-26-desarrollo-de-sistemas-orientado-a-la-gestion/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio: Desarrollo de Sistemas Orientado a la Gestión - Construcción de un MVP E-commerce
> 
> Este documento constituye un manual de estudio integral sobre el desarrollo de sistemas de gestión, enfocado en la implementación técnica de un Producto Mínimo Viable (MVP) utilizando tecnologías modernas de desarrollo web.
> 
> ## 1. Introducción General
> 
> El desarrollo de sistemas orientado a la gestión se centra actualmente en la creación de aplicaciones funcionales que resuelvan necesidades de negocio específicas. En este contexto, el aprendizaje se estructura a través de la **práctica profesional**, donde el objetivo no es solo la programación técnica, sino la capacidad de presentar, defender y vender un producto terminado.
> 
> El proyecto central de este curso consiste en la evolución progresiva de un sistema de comercio electrónico (**e-commerce**), diseñado para que el estudiante comprenda tanto la perspectiva del usuario final como la del administrador del sistema.
> 
> ## 2. Marco Conceptual y Definiciones Clave
> 
> Para abordar el desarrollo del sistema, es fundamental comprender los siguientes términos y herramientas:
> 
> |Concepto|Definición|
> |---|---|
> |**MVP (Minimum Viable Product)**|Producto Mínimo Viable. Es una versión de un producto que permite a un equipo recaudar la máxima cantidad de aprendizaje validado sobre los clientes con el menor esfuerzo posible. Debe ser usable y funcional.|
> |**Node.js**|Entorno de ejecución para JavaScript construido con el motor de Chrome, que permite ejecutar código del lado del servidor.|
> |**Express**|Framework web para Node.js, mínimo y flexible, que proporciona un conjunto robusto de características para aplicaciones web y móviles.|
> |**Bootstrap**|Biblioteca multiplataforma o conjunto de herramientas de código abierto para diseño de sitios y aplicaciones web. Se utiliza para resolver la estética y el diseño responsivo de forma rápida.|
> |**Card (Tarjeta)**|Elemento de interfaz gráfica que agrupa información relacionada (imagen, título, precio) sobre un solo objeto, en este caso, un producto.|
> |**Badge**|Pequeña etiqueta o icono que se utiliza en la interfaz para resaltar información importante, como un descuento o una promoción.|
> |**CDN (Content Delivery Network)**|Sistema de servidores que entregan contenido web a los usuarios. Se usa aquí para cargar la librería de Bootstrap mediante un enlace en el HTML.|
> 
> ## 3. Desarrollo del Tema: Configuración y Construcción
> 
> El desarrollo se divide en dos grandes áreas: la configuración del servidor (Backend inicial) y la creación de la interfaz de usuario (Frontend).
> 
> ### A. Configuración del Entorno con Node.js
> 
> Para poner en marcha el sistema, se deben seguir pasos técnicos precisos en la consola o terminal:
> 
> 1. **Inicialización del proyecto:** `npm init -y` Este comando crea el archivo `package.json` con una configuración por defecto, preparando el entorno para gestionar dependencias.
> 2. **Instalación de dependencias:** `npm install express` Instala el framework necesario para levantar el servidor web.
> 3. **Creación del Servidor:** Se debe redactar un código básico que escuche las peticiones en un puerto (generalmente el **3000**) y confirme en la consola que el servidor está activo.
> 
> ### B. Construcción del Frontend y UI
> 
> Una vez que el servidor responde, se procede a crear la "maqueta" del e-commerce:
> 
> - **HTML Base:** Se genera un archivo `index.html` que incluya el enlace al CDN de Bootstrap.
> - **Componentes de Producto:** Se implementan "Cards" que deben contener:
>     - Contenedor para la imagen del producto.
>     - Nombre del producto.
>     - Precio original y precio con descuento.
>     - Un **Badge** para productos en promoción.
>     - Botón de "Agregar al carrito".
> 
> ### C. Lógica de Persistencia y Carrito
> 
> La funcionalidad mínima del carrito de compras requiere:
> 
> 1. **Selección:** Al hacer clic en el botón de agregar, el producto debe sumarse a una lista.
> 2. **Visualización:** Debajo de las tarjetas de productos, debe aparecer un listado con los productos seleccionados y sus cantidades.
> 3. **Cálculo:** El sistema debe realizar la suma automática de lo que el usuario va gastando directamente en el navegador.
> 
> ## 4. Relación entre Conceptos y Evolución del Proyecto
> 
> El sistema no es estático; evoluciona a través de **iteraciones**. La relación entre las partes se define por dos vistas principales:
> 
> - **Vista del Usuario:** Enfocada en la experiencia de compra (navegación de productos, aplicación de descuentos y gestión del carrito).
> - **Vista del Administrador:** Enfocada en la gestión del negocio, incluyendo el mantenimiento de productos, configuración de descuentos y generación de informes (como el top de ventas).
> 
> **Conexión Lógica:** El frontend diseñado en Bootstrap se comunica con el servidor Node.js/Express. Inicialmente, los datos de los productos se "instancian" directamente en el código (sin base de datos) para probar la lógica de la interfaz antes de proceder a la persistencia real de datos.
> 
> ## 5. Ejemplos Prácticos y Actividades
> 
> ### Caso: Creación de una Tarjeta de Producto (Card)
> 
> Para cumplir con los estándares del proyecto, una tarjeta de producto debe seguir esta estructura paso a paso:
> 
> 1. **Contenedor Principal:** Un `div` con la clase de Bootstrap correspondiente.
> 2. **Imagen:** Uso de un _placeholder_ si no se tiene la imagen final.
> 3. **Cuerpo de la Tarjeta:** Título y descripción breve.
> 4. **Lógica de Descuento:** Si el producto tiene descuento, se debe mostrar el **Badge** llamativo (similar a sitios como Fravega o Adidas).
> 5. **Interacción:** El botón "Agregar" debe disparar la función que actualiza el listado del carrito en la parte inferior de la página.
> 
> ## 6. Errores Comunes y Aclaraciones
> 
> - **Uso de Bootstrap:** No es obligatorio usar Bootstrap de forma estricta. Si un estudiante está familiarizado con otras herramientas o frameworks de diseño, tiene total libertad para utilizarlos. Bootstrap se ofrece como una guía para facilitar el desarrollo rápido de un MVP.
> - **Gestión de Base de Datos:** En las etapas iniciales de la construcción de las "Cards", **no se debe usar base de datos**. Se recomienda instanciar los productos directamente en el código para validar primero la visualización y la lógica del carrito.
> - **Confusión con la Modalidad de Entrega:** Aunque el proyecto final es grupal, ciertas entregas técnicas (como la creación de las tarjetas de productos) son de carácter **individual** para asegurar que todos los integrantes adquieran las habilidades técnicas básicas.
> 
> ## 7. Síntesis y Conclusiones
> 
> - La materia tiene un enfoque **100% práctico**, eliminando los exámenes parciales tradicionales en favor de la evaluación por desempeño y entregas.
> - El objetivo final es la **defensa de un producto** ante un tribunal simulado (coordinadora y equipo de proyectos), actuando como una venta profesional.
> - El desarrollo técnico se apoya en el ecosistema de **Node.js** y el diseño con **Bootstrap** para lograr un MVP funcional en un tiempo limitado.
> - La metodología de trabajo implica iterar sobre una base de código hasta alcanzar una versión que permita comprar, aplicar descuentos y, idealmente, procesar pagos.
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de las sesiones, se establecen los siguientes puntos clave sobre la organización de la materia:
> 
> |Categoría|Detalle|
> |---|---|
> |**Exámenes Parciales**|**No habrá parciales teóricos.** La materia es totalmente práctica y se evalúa mediante la participación y entregas.|
> |**Entrega Actual (Individual)**|**Creación de Tarjetas (Cards) de productos y lógica de carrito.** Debe subirse a la plataforma en formato `.zip`.|
> |**Fecha de Entrega**|Para la **próxima clase**. Se permite trabajar durante la semana y realizar consultas por mail o aula virtual.|
> |**Evaluación Final**|Defensa del producto final en una clase especial. Consiste en simular una venta ante la coordinación y el profesor.|
> |**Asistencia**|El profesor no toma lista; lo hace personal de **Bedelía** que ingresa a la reunión.|
> |**Requisito de Cámara**|Es obligatorio tener las **cámaras encendidas** durante las clases virtuales para facilitar el registro de asistencia por parte de Bedelía.|
> |**Trabajo Grupal**|La próxima semana, los grupos elegirán el mejor diseño individual de "Cards" para integrarlo al proyecto grupal definitivo.|
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la función del comando `npm init -y`?
> 2. ¿Qué elementos mínimos debe contener una "Card" de producto según la guía del profesor?
> 3. ¿Por qué se utiliza un CDN para Bootstrap en este proyecto?
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia entre la vista de usuario y la vista de administrador en el proyecto de e-commerce.
> 5. ¿Cuál es la importancia de desarrollar un MVP en lugar de un producto completo desde el inicio?
> 6. ¿Cómo se gestiona la persistencia del carrito en la etapa actual del desarrollo?
> 
> ### Nivel Avanzado
> 
> 7. Describa el flujo de trabajo desde la instalación de Node.js hasta la visualización de un servidor activo en el puerto 3000.
> 8. Si se decide no utilizar Bootstrap, ¿qué consideraciones de diseño deben mantenerse para asegurar que el componente sea funcional para el proyecto grupal?
> 9. Analice la metodología de evaluación de la materia: ¿Por qué se sustituye el parcial por una "defensa de venta" del producto?

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 4 (21 04 26) - Desarrollo de sistemas orientado a la gestión" src="https://www.youtube.com/embed/6GVfecbsCgs?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1oI-PDxp1HXM0DxdJMuYB8K43koMZrZCH/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1wo7EixQGX_RiLKuyJMrJTCepAX2ZvdPg/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>