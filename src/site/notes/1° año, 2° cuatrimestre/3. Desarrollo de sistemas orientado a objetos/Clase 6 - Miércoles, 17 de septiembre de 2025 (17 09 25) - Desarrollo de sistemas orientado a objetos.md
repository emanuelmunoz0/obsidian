---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/3-desarrollo-de-sistemas-orientado-a-objetos/clase-6-miercoles-17-de-septiembre-de-2025-17-09-25-desarrollo-de-sistemas-orientado-a-objetos/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio: Programación Orientada a Objetos en JavaScript y Node.js
> 
> Este documento constituye un material de estudio integral basado en la sexta clase sobre el desarrollo de sistemas orientado a objetos. En él se sintetizan los conceptos técnicos, las implementaciones prácticas y las directrices académicas necesarias para dominar el modelado de sistemas en el entorno de Node.js.
> 
> ## Introducción General
> 
> El desarrollo de sistemas orientado a objetos (POO) permite estructurar el código de manera que refleje entidades del mundo real. A través de JavaScript, y específicamente bajo el entorno de ejecución Node.js, es posible construir arquitecturas complejas mediante el uso de clases, métodos y atributos. Este enfoque no solo organiza el código, sino que facilita la escalabilidad y el mantenimiento de aplicaciones que, aunque inicialmente se ejecutan en consola, sientan las bases para el desarrollo web profesional.
> 
> ## Contexto del Tema
> 
> En la etapa actual del aprendizaje, se transita desde ejercicios básicos hacia el modelado de sistemas interrelacionados. El foco principal es la creación de sistemas de gestión (como hoteles o agencias) donde las clases no operan de forma aislada, sino que colaboran entre sí. Se introducen conceptos de validación de datos y manejo de errores para garantizar que las aplicaciones sean robustas y no se interrumpan ante fallos inesperados en el tiempo de ejecución.
> 
> ### Importancia y Relevancia
> 
> Dominar la POO es fundamental para cualquier desarrollador, ya que:
> 
> 1. **Abstrae la complejidad:** Permite enfocarse solo en los detalles relevantes para el sistema.
> 2. **Facilita la integración:** Prepara al programador para trabajar con bases de datos y frameworks web como Express.
> 3. **Seguridad de datos:** Mediante el uso de atributos privados, se protege la integridad de la información interna de los objetos.
> 
> --------------------------------------------------------------------------------
> 
> ## Marco Conceptual
> 
> ### Definición de Conceptos Clave
> 
> |   |   |
> |---|---|
> |Concepto|Explicación|
> |**Abstracción**|Proceso de definir el nivel de detalle necesario para un objeto. No debe ser ni tan detallado que abrume, ni tan simple que falten datos requeridos por el sistema.|
> |**Atributo Privado**|Variable interna de una clase que no puede ser accedida directamente desde fuera de ella. En JavaScript, se denota con el prefijo `#`.|
> |**Método**|Función definida dentro de una clase que representa un comportamiento o acción del objeto.|
> |**Try-Catch**|Estructura de control utilizada para manejar excepciones o errores durante la ejecución del programa sin que este se detenga abruptamente.|
> |**Asincronía**|Capacidad del código para ejecutar tareas en paralelo (como una conexión a base de datos) sin detener la ejecución de la línea principal del programa.|
> 
> --------------------------------------------------------------------------------
> 
> ## Desarrollo del Tema
> 
> ### 1. Modelado de Clases y Atributos Privados
> 
> El uso del símbolo `#` antes del nombre de un atributo lo convierte en privado. Esto significa que si intentamos acceder a él desde el código principal (fuera de la clase), el programa arrojará un error de tipo `undefined` o de sintaxis. La única forma de interactuar con estos datos es a través de métodos públicos definidos dentro de la propia clase (Getters y Setters).
> 
> ### 2. Iteraciones Modernas: ForEach y Arrow Functions
> 
> En JavaScript moderno, es común reemplazar el ciclo `for` tradicional por métodos de arreglos más declarativos.
> 
> - **forEach:** Ejecuta una función específica para cada elemento de un arreglo.
> - **Arrow Functions (=>):** Una forma compacta de escribir funciones. Son especialmente útiles en procesos asíncronos y para simplificar la sintaxis de los métodos de arreglos.
> 
> ### 3. El Sistema de Manejo de Errores (Try-Catch-Finally)
> 
> El bloque `try-catch` es la herramienta principal para la resiliencia del software.
> 
> - **Try:** Se coloca el código que podría fallar (ej. acceso a una propiedad de un objeto inexistente).
> - **Catch:** Se captura el objeto de error. Permite mostrar un mensaje personalizado y evitar que el servidor se caiga.
> - **Finally:** Bloque opcional que se ejecuta siempre, haya habido error o no. Es ideal para cerrar conexiones a bases de datos o liberar recursos.
> 
> **Nota Crítica:** El `try-catch` **no captura errores de sintaxis** (errores de parseo o compilación). Si el código está mal escrito (ej. falta una llave o se viola una regla del lenguaje), el motor de JavaScript ni siquiera intentará ejecutar el programa.
> 
> ### 4. Validaciones de Datos
> 
> Antes de realizar operaciones críticas (como agregar una calificación a un alumno o registrar una reserva), es imperativo validar la entrada:
> 
> - **Rango:** Comprobar que los números estén entre valores permitidos (ej. notas de 0 a 10).
> - **Tipo:** Usar `typeof` para asegurar que el dato recibido sea un número, un string o un objeto, según corresponda.
> 
> --------------------------------------------------------------------------------
> 
> ## Relaciones entre Conceptos
> 
> Las ideas en POO se conectan a través de la jerarquía y la composición:
> 
> - **Composición:** Una clase `Agencia` puede tener un arreglo de objetos de la clase `Hotel`. La agencia "tiene" hoteles, y utiliza los métodos de la clase `Hotel` para obtener información.
> - **Dependencia de Abstracción:** El éxito de una validación (como la disponibilidad de una habitación) depende de cómo se hayan estructurado previamente las clases `Reserva` y `Habitacion`.
> - **Asincronía y Promesas:** Los métodos de una clase pueden realizar solicitudes que tardan tiempo. En estos casos, la POO se combina con la asincronía para que el sistema siga funcionando mientras espera una respuesta de una base de datos.
> 
> --------------------------------------------------------------------------------
> 
> ## Ejemplos Prácticos
> 
> ### Ejemplo 1: Clase Agencia con Arreglo de Hoteles
> 
> Este ejemplo muestra cómo una clase puede agrupar otros objetos y utilizar el método `forEach` con una _arrow function_ para listar información.
> 
> ```javascript
> class Agencia {
>     #hoteles; // Atributo privado
> 
>     constructor(nombre) {
>         this.nombre = nombre;
>         this.#hoteles = [];
>     }
> 
>     agregarHotel(hotel) {
>         this.#hoteles.push(hotel);
>     }
> 
>     listarHoteles() {
>         // Uso de forEach y Arrow Function
>         this.#hoteles.forEach(hotel => {
>             console.log(`Hotel: ${hotel.nombre}`);
>         });
>     }
> }
> ```
> 
> ### Ejemplo 2: Validación de Notas en Clase Estudiante
> 
> Muestra cómo prevenir datos erróneos antes de procesarlos.
> 
> ```javascript
> agregarCalificacion(nota) {
>     if (nota >= 0 && nota <= 10) {
>         this.calificaciones.push(nota);
>     } else {
>         console.log("Error: La nota debe estar entre 0 y 10.");
>     }
> }
> ```
> 
> --------------------------------------------------------------------------------
> 
> ## Errores Comunes y Confusiones
> 
> 1. **Confundir Atributos con y sin Numeral:** Referenciar `this.hoteles` en lugar de `this.#hoteles` dentro de una clase. JavaScript los tratará como dos variables distintas: una privada y otra que no existe (indefinida).
> 2. **Uso de Try-Catch para Sintaxis:** Intentar capturar un error de escritura de código con un `try-catch`. Los errores de sintaxis detienen el programa antes de que el `try` pueda siquiera ejecutarse.
> 3. **ToFixed en el lugar incorrecto:** Al calcular promedios, el método `.toFixed(2)` debe aplicarse al resultado final del cálculo numérico, no a la operación de división incompleta, para evitar errores de tipo.
> 4. **No usar el contexto de la clase:** Olvidar que para acceder a métodos o atributos dentro de la misma clase es obligatorio usar la palabra clave `this`.
> 
> --------------------------------------------------------------------------------
> 
> ## Síntesis y Conclusiones
> 
> - **Estructura:** La POO en JavaScript utiliza clases para encapsular lógica y datos.
> - **Privacidad:** El uso de `#` es la forma estándar de proteger atributos.
> - **Robustez:** Las validaciones manuales y el bloque `try-catch` son esenciales para que la aplicación no falle ante el usuario final.
> - **Modernidad:** El uso de _arrow functions_ y métodos como `forEach` simplifica el procesamiento de colecciones de objetos.
> - **Evolución:** El trabajo actual en consola es un paso previo necesario para la implementación de servidores web reales y conexiones a bases de datos.
> 
> --------------------------------------------------------------------------------
> 
> ## Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cómo se define un atributo como privado en una clase de JavaScript?
> 2. ¿Para qué sirve el método `forEach`?
> 3. ¿Cuál es la diferencia principal entre un ciclo `for` tradicional y una _arrow function_ dentro de un `forEach`?
> 
> ### Nivel Intermedio
> 
> 4. Si un atributo es privado, ¿cómo puede un programador acceder a su valor desde fuera de la clase de manera segura?
> 5. Explique por qué un error de sintaxis no es capturado por un bloque `try-catch`.
> 6. ¿Qué utilidad tiene el bloque `finally` en una estructura de manejo de errores?
> 
> ### Nivel Avanzado
> 
> 7. Describa un escenario donde la asincronía sea necesaria al trabajar con objetos y bases de datos.
> 8. En un sistema de reservas, ¿qué lógica debería seguir un método para validar si una habitación está disponible en un rango de fechas determinado?
> 
> --------------------------------------------------------------------------------
> 
> ## Fechas importantes y avisos académicos
> 
> A continuación, se detallan los hitos y recordatorios establecidos por el docente para la organización de la materia:
> 
> |   |   |   |
> |---|---|---|
> |Fecha|Evento|Descripción Detallada|
> |**24 de Septiembre**|**Clase Presencial / Virtual**|Aunque es una fecha de presencialidad, el docente permitirá la asistencia virtual. Se utilizará para despejar dudas finales y terminar ejercicios. El docente estará físicamente en el instituto.|
> |**01 de Octubre**|**Examen Parcial**|Evaluación presencial (con modalidad a definir en detalle). Se centrará en JavaScript y Node.js aplicado a POO.|
> 
> **Indicaciones del Profesor para el Parcial:**
> 
> - **Formato probable:** Se entregará un sistema de clases incompleto o con errores de diseño. El alumno deberá agregar métodos, clases nuevas o corregir la estructura (ej. implementar herencia o corregir atributos mal vinculados).
> - **Contenido:** Se evaluará la capacidad de codificar en JavaScript, modelar clases, manejar errores y aplicar lógica de POO.
> - **Entorno:** El examen se realizará utilizando el entorno de consola (Node.js).
> 
> **Avisos Adicionales:**
> 
> - **Práctica sugerida:** Se recomienda resolver el **Ejercicio 9 (Chatbot)**, que implica implementar subclases (clima, soporte, programación) con respuestas predefinidas y validaciones para preguntas no reconocidas.
> - **Entorno de Desarrollo:** Es fundamental tener instalado Node.js (versión estable o LTS) y familiarizarse con la terminal del editor de código.
> - **Trabajo Grupal:** Se adelantó que el proyecto final incluirá la transición a una plataforma web con servidores Express y bases de datos (MySQL/MariaDB).

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 6 - Desarrollo de sistemas orientado a objetos" src="https://www.youtube.com/embed/62aIcn6jTJo?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/18lMpUQHWzVfKNdQEOMHJ5gHst1JXhHd6/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1EWUHsIbLx02VINRe0-PuxjwyByUngGeG/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>