---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/3-desarrollo-de-sistemas-orientado-a-objetos/clase-11-miercoles-29-de-octubre-de-2025-29-10-25-desarrollo-de-sistemas-orientado-a-objetos/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio: Desarrollo de Sistemas Web y Programación Orientada a Objetos
> 
> Este documento constituye un material de estudio integral sobre el desarrollo de aplicaciones web utilizando el entorno de Node.js, el framework Express y bases de datos relacionales. Está diseñado para proporcionar una comprensión desde los niveles fundamentales hasta la implementación práctica de lógica de negocio y persistencia de datos.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción al Entorno de Desarrollo
> 
> El desarrollo de sistemas modernos se basa en una arquitectura de capas donde interactúan el servidor web, la lógica de aplicación y el servidor de base de datos. El stack tecnológico abordado utiliza **Node.js** como motor de ejecución y **Express** como framework para la gestión de rutas y peticiones.
> 
> ### Contexto y Relevancia
> 
> El dominio de estas herramientas permite construir aplicaciones escalables y modulares. Se enfatiza la importancia de configurar correctamente el entorno local, incluyendo la gestión de servidores y librerías, para asegurar que el flujo de datos entre el navegador (frontend) y el servidor (backend) sea eficiente y seguro.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual y Definiciones Clave
> 
> Para comprender el desarrollo web orientado a objetos, es necesario manejar los siguientes términos fundamentales:
> 
> - **Node.js:** Entorno de ejecución para JavaScript en el servidor.
> - **Express:** Framework web para Node.js que simplifica el manejo de rutas (URLs) y respuestas HTTP.
> - **Middleware/Módulos:** Archivos separados que organizan el código (ej. constantes, clases, rutas).
> - **Ruta (Route):** Punto de acceso URL que activa una funcionalidad específica en el servidor (ej. `/productos`, `/login`).
> - **Puerto (Port):** "Puerta" virtual de comunicación en el servidor. Express usa habitualmente el 3000, pero puede configurarse (ej. 3060). MariaDB usa por defecto el 3306.
> - **Query (Consulta):** Sentencia en lenguaje SQL para interactuar con la base de datos (SELECT, INSERT, etc.).
> - **Pool de Conexiones:** Sistema que mantiene múltiples conexiones abiertas a la base de datos para reutilizarlas, evitando el costo de crear una nueva conexión en cada consulta.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Arquitectura de la Aplicación y Manejo de Datos
> 
> La aplicación se organiza de forma modular para facilitar su mantenimiento.
> 
> ### Gestión de Bases de Datos
> 
> Existen diversas opciones para la persistencia de datos:
> 
> - **MariaDB:** Una rama de código abierto derivada de MySQL, recomendada por su estabilidad y filosofía _open source_.
> - **MySQL:** Actualmente bajo una administración comercial que genera incertidumbre sobre futuras funcionalidades pagas.
> - **PostgreSQL:** Considerada una opción más avanzada, con módulos de vectorización y soporte para grafos, situándose un paso adelante en el ecosistema actual.
> 
> **Herramientas Visuales:** Para interactuar con la base de datos sin depender exclusivamente de la línea de comandos, se recomienda **DBeaver** (versión gratuita y funcional) o **HeidiSQL**.
> 
> ### Estructura de Archivos Recomendada
> 
> |   |   |
> |---|---|
> |Carpeta/Archivo|Función|
> |`express_0.js`|Archivo principal. Inicia el servidor y define las rutas principales.|
> |`code/const.js`|Módulo de constantes (configuración de DB, fragmentos HTML, fechas).|
> |`code/clases.js`|Lógica de negocio (clase Login, Usuario, etc.).|
> |`public/`|Archivos estáticos: CSS (`estilos.css`), imágenes y scripts de frontend.|
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Desarrollo del Frontend: Estructura y Estética
> 
> El frontend se construye mediante fragmentos de HTML enviados por el servidor, utilizando **CSS Grids** para la disposición de los elementos.
> 
> ### El uso de CSS Grids
> 
> Esta tecnología permite definir áreas de la página de forma flexible:
> 
> 1. **Grid Container:** Define el área total de la página (display: grid).
> 2. **Grid Elements:** Componentes como `header`, `nav`, `main` y `footer`.
> 3. **Responsive Design (Viewport):** Mediante el uso de `@media` en el CSS, el diseño se adapta automáticamente. Por ejemplo, en móviles (600px o menos), las columnas se convierten en una sola fila para facilitar la lectura.
> 
> ### Fragmentación de HTML
> 
> Para mantener la coherencia visual, el HTML se divide en constantes (ej. `Grid1` y `Grid2`). El servidor envía la primera parte, inserta el contenido dinámico en el `main`, y luego cierra el documento con la segunda parte.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Lógica de Negocio y Autenticación (Login)
> 
> El proceso de autenticación ilustra cómo se conectan todas las piezas del sistema.
> 
> ### Flujo de Autenticación
> 
> 4. **Acceso Inicial:** El usuario entra a la raíz (`/`). El parámetro de operación (`OP`) está vacío, por lo que se muestra el formulario de login.
> 5. **Envío de Datos:** El usuario ingresa credenciales. Al presionar "Login", se envía una petición con `OP=out`.
> 6. **Procesamiento en el Servidor:**
>     - Se instancia la clase `Login`.
>     - Se invoca el método `autenticar`.
>     - Se solicita una conexión al **Pool de conexiones**.
> 7. **Verificación de Seguridad:**
>     - No se comparan contraseñas en texto plano.
>     - Se realiza un **Hash** de la contraseña ingresada y se compara con el hash almacenado en la base de datos.
> 8. **Respuesta:** El servidor devuelve un mensaje de "Éxito" o "Error" integrado en la estructura HTML.
> 
> ### Registro de Nuevos Usuarios
> 
> Sigue un flujo similar pero con la operación `OP=new` y luego `OP=submit`. Se utiliza la instrucción SQL `INSERT INTO usuarios` y el sistema devuelve el ID generado automáticamente (autoincremental).
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Relaciones entre Conceptos
> 
> - **Asincronía (Async/Await):** Fundamental en Node.js. El servidor no debe detenerse mientras espera la respuesta de la base de datos; se usa `await` para pausar solo esa ejecución específica hasta obtener los datos.
> - **Modularidad:** El uso de `require` y `module.exports` permite que las constantes de conexión a la base de datos sean accesibles desde cualquier clase o archivo de ruta.
> - **Seguridad:** El uso de campos `hidden` en formularios permite pasar parámetros de control (como el tipo de operación) sin que el usuario tenga que interactuar con ellos directamente.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Errores Comunes y Aclaraciones
> 
> - **Confusión con Puertos:** Es común intentar levantar Express en un puerto ya ocupado por la base de datos (3306). Deben ser distintos.
> - **Sintaxis de Importación:** En Node.js se usa mayoritariamente `require`. Para usar `import`, se debe modificar el `package.json` agregando `"type": "module"`.
> - **Persistencia de la Conexión:** Siempre se debe realizar el `release` de la conexión después de una consulta para devolverla al pool, de lo contrario, el sistema podría quedarse sin conexiones disponibles.
> - **Rutas Libres:** Express requiere la instrucción `express.static('public')` para que el navegador pueda acceder a los archivos CSS e imágenes sin restricciones de ruta.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de las fuentes, se han identificado las siguientes fechas y directivas:
> 
> - **29 de Octubre:** Fecha de la sesión actual. Restan 3 clases adicionales antes del cierre.
> - **05 de Noviembre:** Próxima clase. Se deben presentar avances del desarrollo o consultas sobre la codificación.
> - **26 de Noviembre:** Fecha de finalización programada.
>     - Originalmente destinada a **Presentaciones de Proyectos**.
>     - **Advertencia:** Si el avance no es suficiente para el 05/11, la clase del 26/11 podría convertirse en una instancia de **Evaluación Parcial o Trabajo Práctico** en lugar de presentaciones.
> - **Directiva del Profesor:** Se recomienda no profundizar excesivamente en el diseño visual (CSS) si esto impide avanzar en la funcionalidad (Base de Datos y Rutas). Se permite copiar y pegar estructuras base para priorizar que la aplicación "funcione".
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la función de Express en este stack tecnológico?
> 2. ¿Qué diferencia hay entre MariaDB y MySQL según lo discutido en clase?
> 3. ¿Para qué sirve el archivo `public` en un proyecto de Node.js?
> 
> ### Nivel Intermedio
> 
> 4. Explique el concepto de "Pool de conexiones" y por qué es más eficiente que abrir conexiones individuales.
> 5. Describa cómo el CSS Grid ayuda a que una página sea "Responsive".
> 6. ¿Qué sucede en el servidor cuando el parámetro `OP` es igual a `out`?
> 
> ### Nivel Avanzado
> 
> 7. ¿Por qué es necesario usar `async/await` al realizar consultas a la base de datos?
> 8. Describa el proceso de seguridad que ocurre desde que el usuario escribe su contraseña hasta que la base de datos valida el acceso (mencione el concepto de Hash).
> 9. Si un grupo decide usar un framework como Bootstrap o Tailwind, ¿qué impacto tiene esto en la lógica de las rutas de Express? (Pista: La lógica de rutas permanece igual, solo cambia la estética).

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 11 - Desarrollo de sistemas orientado a objetos" src="https://www.youtube.com/embed/VbWs-yZg5rs?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1b_HCa6hO65rSRgETE_-SSDum2msgivbA/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1z5aJcYe6EqK6gxVMyvMSqzyiVBc9ifE1/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>