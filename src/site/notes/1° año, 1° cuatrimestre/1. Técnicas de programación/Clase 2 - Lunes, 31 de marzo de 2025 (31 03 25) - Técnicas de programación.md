---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/1-tecnicas-de-programacion/clase-2-lunes-31-de-marzo-de-2025-31-03-25-tecnicas-de-programacion/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio Integral: Técnicas de Programación y Estructuras de Control
> 
> Este documento constituye el material de estudio principal para la materia de Técnicas de Programación, sintetizando los conceptos teóricos, las prácticas técnicas y las pautas académicas discutidas en clase. Su objetivo es proporcionar un dominio completo de las estructuras de control y la lógica de programación en JavaScript desde cero hasta un nivel avanzado.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> La programación se fundamenta en la capacidad de dar instrucciones precisas a una computadora para procesar datos. Este proceso no se limita a escribir código, sino a desarrollar un **pensamiento computacional** que permita desglosar problemas complejos en pasos lógicos. El enfoque de esta materia es puramente práctico: "ejercicio, ejercicio y más ejercicio", priorizando la lógica de resolución sobre la simple memorización de sintaxis.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual: Fundamentos de JavaScript
> 
> Para programar de manera efectiva, es imperativo comprender cómo el lenguaje gestiona la información en la memoria del sistema.
> 
> ### Definición de Conceptos Clave
> 
> |   |   |
> |---|---|
> |Concepto|Descripción|
> |**Variable**|Una posición de memoria (celda) con una etiqueta que almacena un dato que puede cambiar durante la ejecución.|
> |**Constante**|Una posición de memoria cuyo valor se asigna una sola vez y no puede ser modificado posteriormente.|
> |**Compilación**|El proceso por el cual el lenguaje traduce el código humano a instrucciones que la computadora entiende. JavaScript compila solo lo que necesita ejecutar en el momento.|
> |**Indentación**|El uso de espacios o tabulaciones para organizar visualmente los bloques de código, facilitando su lectura y mantenimiento.|
> 
> ### Gestión de Variables y Memoria (`const`, `let`, `var`)
> 
> JavaScript ofrece tres formas de declarar espacios en memoria, cada una con implicaciones de rendimiento y alcance (scope):
> 
> 1. `**const**`: Se utiliza para valores que no cambian. Es la opción más eficiente porque el compilador reserva un espacio optimizado sabiendo que no habrá modificaciones. **Regla de oro:** Usar siempre que sea posible.
> 2. `**let**`: Define variables cuyo valor cambiará. Su alcance está restringido al bloque de código (entre llaves `{}`) donde fue definida.
> 3. `**var**`: Una forma antigua de declarar variables. A diferencia de `let`, es accesible en todo el programa. Se recomienda evitar su uso en favor de `let` para prevenir errores de colisión de nombres en programas complejos.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: Herramientas Nativas y Lógica Aplicada
> 
> ### Operadores de Comparación
> 
> La diferencia entre la comparación simple y la estricta es fundamental para evitar errores lógicos:
> 
> - `**==**` **(Igualdad débil):** Compara solo el valor. Por ejemplo, `5 == "5"` es **verdadero** (true), aunque uno sea número y otro sea texto.
> - `**===**` **(Igualdad estricta):** Compara valor y tipo de dato. Por ejemplo, `5 === "5"` es **falso** (false).
> 
> ### Librería Matemática (`Math`) y Tratamiento de Números
> 
> JavaScript provee el objeto `Math` para realizar operaciones avanzadas:
> 
> - `**Math.PI**`: Provee el valor exacto de la constante Pi.
> - `**Math.round(x)**`: Redondea al entero más cercano (0.5 hacia arriba).
> - `**Math.ceil(x)**`: Redondea siempre hacia arriba (techo).
> - `**Math.floor(x)**`: Redondea siempre hacia abajo (suelo).
> - `**.toFixed(n)**`: Método para limitar la cantidad de decimales a mostrar.
> - `**parseInt()**` **/** `**parseFloat()**`: Funciones para convertir texto (strings) a números enteros o decimales respectivamente.
> 
> ### Estructuras de Control: Iteraciones (Loops)
> 
> Las iteraciones permiten repetir un bloque de instrucciones múltiples veces sin necesidad de duplicar el código.
> 
> #### El Bucle `for`
> 
> Es la estructura ideal cuando se conoce de antemano cuántas veces se debe repetir una acción. Su sintaxis se divide en tres partes:
> 
> 1. **Inicialización:** Se define el índice de inicio (ej. `let i = 0`).
> 2. **Condición:** El bucle se ejecuta mientras esta sea verdadera (ej. `i < 5`).
> 3. **Incremento:** Se actualiza el índice al final de cada repetición (ej. `i++`).
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Relaciones entre Conceptos
> 
> La programación es la interconexión de tres pilares fundamentales:
> 
> 4. **Instrucciones:** Asignaciones de valores y cálculos.
> 5. **Estructuras de Control:** Deciden qué camino toma el programa (`if/else`) o cuántas veces se repite (`for`, `while`).
> 6. **Estructuras de Datos:** Cómo se organiza la información (ej. _Arrays_, que se verán próximamente).
> 
> **Dependencia lógica:** Un bucle `for` depende de una condición lógica (booleana). Si la condición no se plantea correctamente, el programa puede caer en un "bucle infinito" o no ejecutarse nunca.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Ejemplos Prácticos Paso a Paso
> 
> ### Caso 1: Conversión de Tiempo (Lógica de Resto)
> 
> **Problema:** Convertir segundos ingresados por el usuario a horas y minutos.
> 
> 7. **Horas:** Se obtiene dividiendo los segundos por 3600 y usando `Math.floor` para quedarnos con el entero.
> 8. **Resto:** Usamos el operador módulo `%` para saber cuántos segundos sobran tras extraer las horas.
> 9. **Minutos:** Dividimos ese resto por 60.
> 
> ```javascript
> let totalSegundos = 3700;
> let horas = Math.floor(totalSegundos / 3600);
> let minutos = Math.ceil((totalSegundos % 3600) / 60); 
> console.log(`Resultado: ${horas} horas y ${minutos} minutos.`);
> ```
> 
> ### Caso 2: Uso de Template Literals (Acento Grave)
> 
> Para concatenar texto y variables de forma prolija, se utiliza el acento grave (backtick `` ` ``) y la sintaxis `${variable}`.
> 
> - _Forma antigua:_ `"El promedio es: " + promedio + " puntos."`
> - _Forma moderna:_ `` `El promedio es: ${promedio} puntos.` ``
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores Comunes y Confusiones
> 
> - **Asignación en Constantes:** Intentar cambiar el valor de una `const` provocará un `TypeError`. Las constantes se definen y asignan en una sola línea inicial.
> - **Confusión con la Consola:** Muchos estudiantes olvidan que `console.log()` es para el desarrollador (depuración), mientras que `alert()` o escribir en el HTML es para el usuario final.
> - **Prioridad de Materias:** Un error común es descuidar las materias troncales (Técnicas, Lógica, Base de Datos) por materias complementarias. La programación requiere práctica constante; si se deja de practicar, se pierde el ritmo.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Fechas Importantes y Avisos Académicos
> 
> |   |   |   |
> |---|---|---|
> |Fecha|Evento|Descripción|
> |**07 de abril**|**Clase Presencial de Repaso**|**Optativa**. Dirigida a estudiantes que necesiten refuerzo o tengan dificultades con los trabajos prácticos (TP).|
> |**28 de abril**|**Primer Parcial (Estimado)**|Fecha sujeta a modificaciones. El examen será presencial y eminentemente práctico (ejercicios de programación).|
> |**Semana próxima**|**Entrega de ejercicios**|Se espera que los alumnos hayan avanzado con el TP1 y comiencen el TP2 (Loops).|
> 
> **Avisos Críticos:**
> 
> - **Modalidad del Parcial:** Se realiza preferentemente en computadora. En caso de fallas técnicas, se permite papel y lápiz.
> - **Criterio de Evaluación:** El nivel de dificultad del parcial será similar a los ejercicios de los TP3 y TP4. Quien resuelva bien los TP, aprobará el parcial.
> - **Aula Virtual:** Actualmente presenta fallas de permisos. La comunicación oficial se mantiene vía WhatsApp y la carpeta compartida de Google (asistencias y links).
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Síntesis y Conclusiones
> 
> - La programación se domina mediante la **resolución de problemas**, no solo escribiendo código.
> - Es vital diferenciar entre `let` y `const` para optimizar el uso de recursos.
> - Las estructuras de control como el `for` son herramientas para automatizar tareas repetitivas.
> - El uso de la consola del navegador (`F12` o Inspeccionar) es la herramienta principal para encontrar errores (_debugging_).
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia técnica entre declarar una variable con `let` y una con `const`?
> 2. ¿Para qué sirve el operador `%` (módulo) en un cálculo matemático?
> 3. ¿Cómo se abre la consola de desarrollador en un navegador?
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia entre `5 == "5"` y `5 === "5"`. ¿Cuál es más segura de usar y por qué?
> 5. Si tengo un bucle `for (let i = 0; i < 10; i++)`, ¿cuál es el último valor que toma `i` dentro del bloque de instrucciones?
> 6. ¿En qué casos usaría `Math.ceil()` en lugar de `Math.floor()`?
> 
> ### Nivel Avanzado (Tipo Examen)
> 
> 7. Diseñe la lógica para un programa que pida 10 notas de alumnos y muestre el promedio general al final, utilizando un solo bucle `for`.
> 8. En un sistema de estacionamiento, si el usuario paga por mes, no se le deben calcular horas. ¿Cómo estructuraría los condicionales (`if/else`) para que el programa sea eficiente y no realice cálculos innecesarios?

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 2 - Técnicas de programación" src="https://www.youtube.com/embed/T4Jcx6L0Iuo?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/17Gwjd4s018ThwvFi8w_DzK88YUpDbAtL/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1eQySHvua49E7TmRzs-KmkEjwxkhcedOV/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>