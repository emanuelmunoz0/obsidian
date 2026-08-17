---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/3-desarrollo-de-sistemas-orientado-a-objetos/clase-10-miercoles-22-de-octubre-de-2025-22-10-25-desarrollo-de-sistemas-orientado-a-objetos/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio Avanzada: Desarrollo de Sistemas Orientados a Objetos y Arquitectura Web
> 
> Este documento constituye un material de estudio exhaustivo basado en las sesiones académicas sobre programación orientada a objetos (POO) y el inicio del desarrollo de aplicaciones web full-stack. Integra conceptos teóricos críticos, resoluciones técnicas de evaluaciones y la hoja de ruta para la implementación de proyectos integradores.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción y Contexto
> 
> El desarrollo de software contemporáneo exige una transición fluida entre los principios teóricos de la Programación Orientada a Objetos (POO) y su implementación práctica en entornos de servidor. El estudio se centra en dos grandes ejes: la clarificación de conceptos fundamentales (frecuentemente malinterpretados en la práctica académica) y la arquitectura de aplicaciones utilizando Node.js, Express y bases de datos relacionales.
> 
> La relevancia de este contenido radica en proporcionar la base técnica necesaria para que el estudiante progrese hacia materias de años superiores con un conocimiento sólido sobre cómo se conectan el front-end, el back-end y la persistencia de datos.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual: La Encapsulación en la POO
> 
> Uno de los puntos de mayor debate y confusión es la distinción entre el principio de diseño de encapsulación y la visibilidad de los atributos (público vs. privado).
> 
> ### 2.1 Definición de Encapsulación
> 
> La **encapsulación** es un principio fundamental de la POO que establece que la lógica interna y el funcionamiento mecánico de una clase deben estar ocultos para el usuario que interactúa con ella.
> 
> - **Analogía del automóvil:** Un conductor utiliza una palanca para hacer un cambio de marcha. El conductor no necesita conocer la mecánica interna (cómo engranan los piñones o actúa el embrague) para operar el vehículo. La mecánica está "encapsulada" detrás de una interfaz simple (la palanca).
> - **Propósito:** Evitar que el usuario dependa de la lógica interna, permitiendo que esta cambie sin afectar a quienes usan la clase.
> 
> ### 2.2 Atributos Privados vs. Encapsulación
> 
> Es un error común asociar unívocamente la encapsulación con el uso de atributos privados.
> 
> - **Atributos Privados (**`**#**` **en JavaScript):** Restringen el acceso directo para evitar modificaciones accidentales o no autorizadas y para proteger datos sensibles.
> - **Convención de Guion Bajo (**`**_**`**):** En JavaScript, el uso de un guion bajo antes del nombre de un atributo es meramente una convención de "buena práctica" que indica que el atributo no debería ser accedido directamente, pero técnicamente no restringe el acceso (no lo hace privado).
> - **Relación:** Se puede tener encapsulación sin que todos los atributos sean privados, siempre y cuando la interacción principal se realice a través de métodos (getters, setters y métodos de lógica de negocio).
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo Técnico: Arquitectura de Servidores con Node.js
> 
> Para construir aplicaciones modernas, se utiliza **Node.js** como entorno de ejecución y **Express** como framework para la gestión de servidores web.
> 
> ### 3.1 Estructura de un Servidor Express
> 
> Un servidor básico requiere cuatro pasos fundamentales:
> 
> 1. **Instalación:** Mediante el gestor de paquetes (`npm install express`).
> 2. **Importación e Inicialización:** Uso de `require('express')` y creación de la instancia de la aplicación.
> 3. **Definición de Rutas (Routing):** Especificar qué código se ejecuta según la URL solicitada por el usuario (ej. `/`, `/productos`, `/vendedor`).
> 4. **Puesta en Marcha:** Uso del método `app.listen(puerto)` para que el servidor comience a "escuchar" solicitudes.
> 
> ### 3.2 Modularización del Código
> 
> En proyectos complejos, no es recomendable tener todo el código en un solo archivo. Se utiliza la modularización:
> 
> - `**module.exports**`**:** Permite exportar variables, constantes o clases desde un archivo.
> - `**require()**`**:** Permite importar esos módulos en el archivo principal.
> - **Utilidad:** Facilita el mantenimiento y la separación de responsabilidades (ej. tener un archivo solo para constantes de configuración y otro para la lógica del servidor).
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Relación entre Conceptos: Herencia y Visibilidad
> 
> En el desarrollo de sistemas, las clases suelen heredarse (subclases). Aquí surge un problema técnico crítico cuando se usan atributos privados:
> 
> - **El problema de los Atributos Privados en la Herencia:** Si una clase `Persona` tiene un atributo privado `#nombre`, la subclase `Tecnico` **no hereda** ese atributo directamente. Intentar acceder a `this.#nombre` en la subclase resultará en un error de sintaxis o un valor `undefined`.
> - **La Solución:** La subclase debe acceder al dato a través de un método público o protegido de la clase padre (como un `getNombre()`), ya que los métodos sí se heredan.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Implementación Práctica: Ejemplo de Servidor y Rutas
> 
> A continuación, se presenta una estructura lógica de cómo se define una ruta y se capturan parámetros del usuario:
> 
> ```javascript
> // Definición de una ruta raíz que recibe parámetros
> app.get('/', (req, res) => {
>     // Captura de parámetros desde la URL (ej. ?usuario=pablo)
>     let usuario = req.query.usuario; 
>     
>     // Construcción de la respuesta HTML
>     let respuesta = `<h1>Bienvenido ${usuario}</h1>`;
>     respuesta += `<p>Esta es la ruta raíz del servidor.</p>`;
>     
>     // Envío de la respuesta al navegador
>     res.send(respuesta);
> });
> ```
> 
> ### Puertos de Conexión
> 
> Es fundamental elegir puertos que no estén en uso por otros servicios del sistema:
> 
> - **Puerto 80/8080:** Estándar para servidores web (frecuentemente ocupados).
> - **Puerto 21:** Reservado para FTP/Mails.
> - **Puerto 3306:** Estándar para bases de datos MariaDB/MySQL.
> - **Recomendación:** Usar puertos como el `3000` o `3060` para desarrollo local de Express.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores Comunes y Aclaraciones
> 
> 1. **Confundir Getter con Atributo:** En algunos entornos, el uso de getters puede parecer un acceso directo al atributo, pero es una llamada a una función.
> 2. **Setters innecesarios:** No siempre es obligatorio incluir métodos `set`. Si un dato se define en el constructor y no debe cambiar (como un DNI), se pueden omitir los setters para mayor seguridad.
> 3. **Indefinidos en la consola:** Si al imprimir un dato aparece `undefined`, usualmente se debe a que se está intentando acceder a un atributo privado desde fuera de su clase o a un error en la referencia del objeto (`this`).
> 4. **Localhost:** `localhost` es equivalente a la dirección IP `127.0.0.1`. Es la dirección de la propia máquina.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Planificación de Proyectos (Metodología Gantt)
> 
> Para el desarrollo de aplicaciones en equipo, se requiere una planificación mínima:
> 
> - **Diagrama de Gantt:** Una herramienta visual donde se desglosa el proyecto en tareas atómicas (mínimas).
> - **Elementos clave:**
>     - Tarea (ej. "Diseño de base de datos").
>     - Responsable asignado.
>     - Tiempo estimado de realización.
> - **Tareas típicas de un proyecto web:** Autenticación de usuarios (login), conexión a base de datos, diseño de front-end (formularios), e integración de APIs (como ChatGPT o Gemini).
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas importantes y avisos académicos
> 
> A partir del análisis de las fuentes, se identifican las siguientes informaciones de relevancia para la cursada:
> 
> ### 8.1 Organización de Grupos de Trabajo (TP Final)
> 
> - **Grupo 1:** Pía, Ludmila y Rodrigo (Se retiraron Tatiana Peralta y Guido Varela).
> - **Grupo 2:** Confirmado (sin cambios mencionados).
> - **Grupo 3:** Tatiana Peralta se integró a este grupo (Salió Friedman).
> - **Grupo 4:** Confirmado (sin cambios mencionados).
> - **Estudiante Independiente:** Graciela (trabaja de forma individual pero coordinada).
> 
> ### 8.2 Calendario de Entregas
> 
> - **Fecha de Finalización de Cursada / Entrega Final:** Miércoles 26 de noviembre (se menciona también el lunes 24 como referencia de última semana).
> - **Próxima Clase:** Se debe presentar la **temática de la aplicación** elegida por cada grupo y una **planificación inicial** (tareas y tiempos).
> 
> ### 8.3 Indicaciones del Profesor
> 
> - **Uso de IA:** Está permitido y se recomienda utilizar Inteligencia Artificial para generar estructuras de código HTML/CSS de forma rápida para el front-end.
> - **Tecnologías Obligatorias:** Node.js y Express para el back-end.
> - **Base de Datos:** Se comenzará a trabajar con MariaDB en las próximas sesiones.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Síntesis y Conclusiones
> 
> El éxito en el desarrollo de sistemas orientados a objetos aplicados a la web depende de entender que la **encapsulación es una estrategia de diseño** para simplificar la interacción con el código, más allá de los modificadores de privacidad. Por otro lado, la arquitectura de servidores con Node.js y Express permite crear sistemas modulares, escalables y capaces de gestionar datos de manera eficiente mediante rutas y parámetros.
> 
> --------------------------------------------------------------------------------
> 
> ## 10. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia entre `localhost` y una dirección IP pública?
> 2. ¿Qué comando se utiliza para instalar el framework Express?
> 3. ¿Para qué sirve el método `module.exports`?
> 
> ### Nivel Intermedio
> 
> 4. Explique la analogía del automóvil aplicada al concepto de encapsulación.
> 5. ¿Por qué un atributo definido con `#` en una clase padre da error al ser llamado en una subclase?
> 6. ¿Qué función cumple el objeto `req.query` en una ruta de Express?
> 
> ### Nivel Avanzado
> 
> 7. Diseñe una estructura de rutas para un sistema de e-commerce que incluya `/productos`, `/carrito` y `/usuarios`, explicando qué parámetros podría recibir cada una.
> 8. Compare el uso de un diagrama de Gantt frente a una lista de tareas simple para la gestión de un proyecto grupal de software. ¿Cuál es la ventaja de la granularidad en las tareas?

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 10 - Desarrollo de sistemas orientado a objetos" src="https://www.youtube.com/embed/QCu_X_2MNPw?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1TnDjy1voMEf06HGSJn26gJa068bV0pl-/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1KtCg_HK90QA2VPwRmBYDJnPGVSi_h5ns/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>