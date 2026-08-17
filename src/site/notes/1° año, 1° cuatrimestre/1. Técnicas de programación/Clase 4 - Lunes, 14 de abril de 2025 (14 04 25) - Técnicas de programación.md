---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/1-tecnicas-de-programacion/clase-4-lunes-14-de-abril-de-2025-14-04-25-tecnicas-de-programacion/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía Académica de Programación: Estructuras de Control y Lógica de Algoritmos
> 
> Este documento constituye un material de estudio integral para la Unidad 1 de la materia Técnicas de Programación. El contenido se enfoca en consolidar los conocimientos sobre variables, estructuras de control (condicionales e iteración) y su aplicación práctica en la resolución de problemas lógicos complejos.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> El dominio de la programación no solo requiere conocer la sintaxis de un lenguaje, sino desarrollar la capacidad de descomponer problemas complejos en pasos lógicos ejecutables. Este apunte abarca desde la gestión básica de datos hasta la implementación de algoritmos clásicos, como la detección de números primos, la verificación de palíndromos y la generación de patrones visuales mediante bucles anidados.
> 
> ## 2. Marco Conceptual y Definiciones Clave
> 
> Para programar de manera efectiva, es fundamental comprender el comportamiento de las herramientas básicas del lenguaje, especialmente en JavaScript.
> 
> ### 2.1. Gestión de Variables y Ámbito (Scope)
> 
> - `**let**`: Define variables con **ámbito de bloque**. Esto significa que la variable solo existe dentro de las llaves `{}` donde fue declarada (por ejemplo, dentro de un `if` o un `for`). Es la forma recomendada para declarar variables mutables.
> - `**const**`: Se utiliza para valores que no cambiarán tras su asignación inicial. Aunque técnicamente define un espacio de memoria constante, se usa para declarar constantes.
> - `**var**`: Una forma antigua de declarar variables con ámbito global o de función. Su uso se desaconseja en la programación moderna debido a que puede generar errores de referencia difíciles de detectar.
> 
> ### 2.2. Manipulación de Cadenas de Caracteres (Strings)
> 
> Para analizar texto, se utilizan métodos específicos que permiten acceder a la estructura interna de la cadena:
> 
> - `**.length**`: Propiedad que devuelve la cantidad total de caracteres de una cadena.
> - `**charAt(posición)**`: Método que devuelve el carácter ubicado en un índice específico.
>     - _Nota fundamental:_ Los índices comienzan siempre en **0**. Por lo tanto, el último carácter de cualquier cadena se encuentra en la posición `longitud - 1`.
> 
> ### 2.3. Funciones Matemáticas de Utilidad
> 
> El objeto `Math` en JavaScript proporciona herramientas para el manejo de números:
> 
> - `**Math.random()**`: Genera un número decimal aleatorio entre 0 (inclusive) y 1 (exclusive).
> - `**Math.floor(x)**`: Redondea un número hacia abajo al entero más cercano.
> - `**Math.ceil(x)**` (o _ceil_): Redondea un número hacia arriba al entero más cercano.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: Lógica de Algoritmos
> 
> ### 3.1. Intercambio de Valores (Técnica de la Variable Temporal)
> 
> Para intercambiar los valores entre dos variables (por ejemplo, variable A y variable B) sin perder información, se requiere una tercera variable auxiliar o temporal (`temp`).
> 
> |   |   |   |
> |---|---|---|
> |Paso|Acción|Resultado Lógico|
> |1|`temp = a;`|Se respalda el valor original de `a` en `temp`.|
> |2|`a = b;`|Se sobrescribe `a` con el valor de `b`.|
> |3|`b = temp;`|Se asigna a `b` el valor original de `a` (guardado en `temp`).|
> 
> ### 3.2. Lógica de los Números Primos
> 
> Un número es primo si solo es divisible por sí mismo y por la unidad (1). Para verificar esto mediante código, se utiliza un bucle `for` que prueba la divisibilidad (usando el operador de resto `%`) desde el número 2 hasta el `número - 1`. Si en algún punto el resto es 0, el número no es primo.
> 
> ### 3.3. Generación de Números Aleatorios en un Rango
> 
> Para obtener un número entero aleatorio entre 1 y N, se sigue la siguiente fórmula:
> 
> 1. Generar el decimal: `Math.random()`
> 2. Escalar el rango: `Math.random() * N`
> 3. Redondear y ajustar: `Math.ceil(Math.random() * N)` para obtener de 1 a N, o `Math.floor(Math.random() * N)` para obtener de 0 a N-1.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Ejemplos Prácticos Paso a Paso
> 
> ### Caso 1: Verificador de Palíndromos
> 
> Un palíndromo es una palabra que se lee igual de izquierda a derecha que de derecha a izquierda (ej. "Neuquén").
> 
> **Lógica de resolución:**
> 
> 4. Se definen dos índices: `i` (inicio, posición 0) y `z` (final, posición `longitud - 1`).
> 5. Se utiliza un bucle para comparar el carácter en `i` con el carácter en `z`.
> 6. Si son iguales, se incrementa `i` y se decrementa `z`, acercándose al centro.
> 7. Si en algún momento son distintos, se rompe el bucle (`break`) y se determina que no es palíndromo.
> 
> ### Caso 2: Generación de un Tablero de Ajedrez (Bucles Anidados)
> 
> El objetivo es imprimir un tablero cuadrado de N x N usando caracteres como `#` para negro y un espacio para blanco.
> 
> **Lógica de resolución:**
> 
> 8. Un **bucle externo** controla las filas.
> 9. Un **bucle interno** controla las columnas de cada fila.
> 10. Se debe alternar el carácter. Una técnica es verificar si la suma del índice de fila `i` y el índice de columna `j` es par o impar:
>     - Si `(i + j) % 2 === 0`, imprimir `#`.
>     - De lo contrario, imprimir espacio.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Errores Comunes y Aclaraciones
> 
> - **Ámbito de variables en el** `**for**`: Si se declara una variable con `let` dentro del encabezado de un bucle `for`, dicha variable no será accesible fuera del bucle. Si se necesita el valor final del índice fuera de la estructura, la variable debe declararse antes del `for`.
> - **El número 2 y el 1 en Primos**: El número 2 es el único primo par. El algoritmo debe contemplar que el bucle comience en 2. Si el número ingresado es menor a 2, el tratamiento debe ser específico.
> - **Confusión con** `**Math.random**`: Es un error común olvidar que `Math.random()` nunca llega a ser 1. Para obtener el número N como máximo, es necesario multiplicar y luego redondear adecuadamente.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Síntesis y Conclusiones
> 
> La programación de la Unidad 1 se basa en tres pilares:
> 
> 1. **Declaración correcta de datos**: Uso de `let` y `const` según la mutabilidad requerida.
> 2. **Control de flujo**: Uso de `if/else` para decisiones y `for/while` para tareas repetitivas.
> 3. **Abstracción**: Capacidad de convertir reglas matemáticas (como la definición de un número primo) en estructuras lógicas de comparación y repetición.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Preguntas de Repaso
> 
> **Básicas:**
> 
> 4. ¿Cuál es la diferencia de ámbito (scope) entre `let` y `var`?
> 5. ¿Cómo se obtiene el último carácter de un string llamado `texto`?
> 6. ¿Para qué sirve el operador `%` en la verificación de números primos?
> 
> **Intermedias:**
> 
> 7. Explique por qué es necesaria una variable `temp` para intercambiar los valores de dos variables.
> 8. En un bucle de generación de tablero, ¿qué sucede si solo usamos un bucle en lugar de dos anidados?
> 9. ¿Cómo transformaría un número generado por `Math.random()` para que devuelva un entero entre 1 y 50?
> 
> **Avanzadas:**
> 
> 10. Describa el proceso lógico para identificar un palíndromo utilizando dos punteros (índices) que se encuentran en el centro.
> 11. Si un navegador no arroja error al acceder a una variable de bloque fuera de su ámbito, ¿significa que el código es correcto? Justifique analizando el comportamiento de los motores de JavaScript.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de las sesiones de clase, se detallan las siguientes consideraciones para la organización de la materia:
> 
> ### Cronograma de Evaluaciones
> 
> - **Parcial de la Unidad 1 (Primer Parcial):**
>     - **Fecha tentativa 1:** 5 de mayo (Sujeto a votación y disponibilidad, ya que coincide con otras materias).
>     - **Fecha tentativa 2:** 12 de mayo.
>     - **Descripción:** Evaluará variables, estructuras de control (condicionales e iteración). Constará de 2 o 3 ejercicios de lógica y codificación.
> - **Límite para confirmación de fecha de parcial:** Viernes 25 de abril. Los alumnos deben comunicar si prefieren postergar la fecha original.
> 
> ### Avisos Académicos Importantes
> 
> - **Modalidad del Examen:** El examen será presencial en el laboratorio.
> - **Uso de Computadoras:** El profesor recomienda que los alumnos lleven sus propias computadoras si les es posible, debido a que están familiarizados con su configuración y se evitan bloqueos de sistema ("freezado") frecuentes en las máquinas del instituto.
> - **Conectividad:** El Wi-Fi del instituto es lento e intermitente. Se recomienda tener esto en cuenta para la entrega de ejercicios (que usualmente se realiza por correo electrónico).
> - **Herramientas de Práctica:** Se sugiere utilizar el entorno "Coding" para probar los ejercicios, ya que es el estándar utilizado por el docente para corregir y verificar el funcionamiento del código.
> - **Contenido de la Unidad 2:** Se anticipa que la segunda unidad introducirá los `Arrays` (estructuras de datos), pero la lógica de resolución de problemas seguirá siendo la base fundamental.
> 
> **Nota:** El docente estará ausente (viaje a Misiones) a partir del 29 de abril, lo cual motiva la flexibilidad en la reprogramación del parcial para asegurar una correcta asistencia.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 4 - Técnicas de programación" src="https://www.youtube.com/embed/LLfACPY07Eg?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1UY4g4HA4N8jYpMInFaAbfIQWDTVxw8xi/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1uqvxKLo2nFJxAq8MFPTvizPRDEaABVUq/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>