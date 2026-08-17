---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/3-logica-computacional/clase-11-jueves-26-de-junio-de-2025-26-06-25-logica-computacional/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio Completa: Lógica Computacional y Fundamentos de Programación
> 
> Este documento constituye una síntesis exhaustiva de los temas abordados en la undécima sesión de la materia Lógica Computacional. Funciona como un manual de estudio integral que abarca desde la resolución práctica de problemas lógicos hasta la introducción al desarrollo de software y la arquitectura web.
> 
> ## 1. Introducción y Contexto del Tema
> 
> La sesión marca el cierre del cuatrimestre, vinculando la teoría abstracta de la lógica computacional con su aplicación práctica en el desarrollo de software moderno. Se enfatiza que, aunque la lógica y las técnicas de programación pueden parecer materias abstractas y complejas, constituyen la base inalterable de la carrera de un desarrollador. Mientras que los lenguajes y herramientas cambian con el tiempo, la capacidad de pensamiento abstracto y el reconocimiento de patrones lógicos son habilidades que no pierden vigencia.
> 
> ## 2. Marco Conceptual: Definiciones y Conceptos Clave
> 
> Para comprender la programación actual, es necesario distinguir entre las tecnologías que conforman el entorno de desarrollo:
> 
> ### 2.1. Lenguajes de Marcado vs. Lenguajes de Programación
> 
> - **HTML (HyperText Markup Language):** Es un lenguaje de marcado, **no** de programación. Su función es estructurar el contenido (títulos, párrafos, etiquetas). Es estático y no tiene capacidad para realizar operaciones lógicas.
> - **JavaScript (JS):** Es el lenguaje de programación que dota de dinamismo al HTML. Permite realizar operaciones, procesar instrucciones y reaccionar a eventos (como clics de usuario).
> 
> ### 2.2. Arquitectura de Software: Frontend y Backend
> 
> - **Frontend:** Todo lo que sucede en el navegador (intérprete). Se compone de HTML (contenido), CSS (forma y color) y JavaScript (lógica de interacción). Tiene limitaciones en cuanto al manejo y persistencia de grandes volúmenes de datos.
> - **Backend:** Se ejecuta en el servidor. Tiene la capacidad de almacenar datos de forma permanente y procesar operaciones complejas (ej.: gestión de legajos, historias clínicas). Se conecta con bases de datos.
> 
> ### 2.3. El Intérprete
> 
> El navegador (Chrome, Firefox, etc.) actúa como el intérprete que transforma el código escrito en un resultado visual para el usuario.
> 
> ## 3. Desarrollo del Tema: Lógica y Programación Dinámica
> 
> ### 3.1. Mapas de Karnaugh (Simplificación Lógica)
> 
> El Mapa de Karnaugh es una herramienta para optimizar expresiones booleanas. Durante la sesión se destacaron los siguientes puntos:
> 
> - **Conversión a Binario:** Las expresiones negadas se representan con 0 y las no negadas con 1.
> - **Agrupamiento (Adyacencia):** Se deben buscar grupos de unos (1s) adyacentes para simplificar términos.
> - **Términos no simplificables:** Si un "1" se encuentra solo y no tiene adyacencias posibles, no se puede simplificar y debe incluirse la expresión original de cuatro variables de forma íntegra en el resultado final.
> - **Optimización:** El objetivo es reducir la cantidad de expresiones mediante el agrupamiento más eficiente posible.
> 
> ### 3.2. Operadores Lógicos en JavaScript
> 
> La lógica computacional se traslada al código a través de operadores específicos:
> 
> |   |   |   |
> |---|---|---|
> |Operador Lógico|Representación en JS|Descripción|
> |**AND**|`&&`|Solo es verdadero si ambas condiciones se cumplen.|
> |**OR**|`||
> |**NOT**|`!`|Invierte el valor de verdad (verdadero a falso y viceversa).|
> 
> ### 3.3. Estructuras de Control e Interacción
> 
> - **Condicionales (If/Else):** Permiten que el programa tome decisiones basadas en evaluaciones lógicas.
> - **Eventos:** JavaScript permite capturar acciones del usuario (ej.: `onclick`) para disparar funciones que modifican el HTML en tiempo real.
> - **Consola del Navegador:** Herramienta de desarrollo (F12) utilizada para depuración (debugging) mediante `console.log()`.
> 
> ## 4. Ejemplos Prácticos
> 
> ### Ejemplo 1: Lógica de Negocio y Concatenación
> 
> Supongamos que queremos calcular el promedio de un alumno y mostrar un mensaje:
> 
> ```javascript
> let nota1 = 8;
> let nota2 = 7;
> let nota3 = 6;
> let promedio = (nota1 + nota2 + nota3) / 3;
> 
> if (promedio >= 7) {
>     console.log("El promedio del alumno es " + promedio + ". Estado: Aprobado.");
> } else {
>     console.log("El promedio del alumno es " + promedio + ". Estado: Recuperatorio.");
> }
> ```
> 
> ### Ejemplo 2: Dinamismo en el Frontend
> 
> Al presionar un botón, JavaScript puede cambiar el color de una sección del sitio web. Esto es posible porque el código JS accede al "lienzo" de HTML y modifica sus propiedades dinámicamente, algo que el HTML por sí solo no puede hacer.
> 
> ## 5. Errores Comunes y Aclaraciones Importantes
> 
> - **Confundir HTML con programación:** Se reitera que HTML solo estructura; la lógica reside exclusivamente en JavaScript.
> - **Persistencia de datos en Frontend:** Los datos manejados solo con JavaScript en el navegador se pierden al refrescar la página (memoria volátil), a menos que se use un Backend para guardarlos en un servidor.
> - **Uso de IA:** Se advierte que herramientas como ChatGPT pueden "delirar" o cometer errores graves en problemas de lógica pura, aunque son útiles para maquetación o diseño de frontend básico. El abuso de estas herramientas puede perjudicar el desarrollo cognitivo del estudiante.
> 
> ## 6. Síntesis y Conclusiones
> 
> - La lógica no vence: es la base para aprender cualquier lenguaje futuro.
> - El desarrollo profesional implica conectar el Frontend (interfaz) con el Backend (datos).
> - La simplicidad en el código es clave para la optimización (como se ve en los Mapas de Karnaugh).
> 
> ## 7. Fechas Importantes y Avisos Académicos
> 
> A partir del análisis de la fuente, se detallan las siguientes disposiciones para el cierre del cuatrimestre:
> 
> - **Evento:** Coloquio Final (Evaluación Obligatoria).
> - **Fecha:** Próximo jueves (clase siguiente).
> - **Modalidad:** **Virtual** (se suspende el encuentro presencial debido al cierre de la institución).
> - **Consigna:**
>     - Presentación individual de un ejercicio asignado (del listado de ejercicios 1 al 27 enviado por WhatsApp).
>     - Duración: 1 a 3 minutos por alumno.
>     - Requisito: Los archivos deben estar subidos a la plataforma antes de la clase.
> - **Asistencia:** Es obligatoria para ser evaluado y cargar las notas. Aquellos que ya aprobaron y no deben recuperar igualmente deben asistir para la entrega y verificación de notas.
> - **Recuperatorios:** La clase siguiente es originalmente para recuperatorios, pero debido a la organización de la materia, se utilizará para el coloquio de todos los alumnos.
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Por qué se afirma que HTML no es un lenguaje de programación?
> 2. ¿Cuál es la función del operador `||` en un bloque de código?
> 
> ### Nivel Intermedio
> 
> 1. Explique la diferencia entre el almacenamiento de datos en el Frontend y el Backend.
> 2. Si en un Mapa de Karnaugh un "1" no tiene vecinos, ¿cómo queda representado en la función simplificada?
> 
> ### Nivel Avanzado
> 
> 1. Describa el proceso lógico que ocurre cuando un usuario hace clic en un botón que cambia el contenido de un párrafo en una página web.
> 2. Analice la relación entre la tabla de verdad del condicional (`P -> Q`) y su representación en una estructura `if` de JavaScript.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 11 - Lógica computacional" src="https://www.youtube.com/embed/fTna8dyZJPw?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1xkXWF0dyWoqpZKqyH_DJe6K7_NMDh0Ig/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1yUQkw5EMGT8TPH9TTg7I_Fpjq7YZrtgI/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>