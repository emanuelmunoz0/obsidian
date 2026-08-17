---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/1-tecnicas-de-programacion/clase-5-lunes-21-de-abril-de-2025-21-04-25-tecnicas-de-programacion/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio: Técnicas de Programación y Lógica Algorítmica
> 
> Este documento constituye un material de estudio integral basado en las sesiones académicas sobre técnicas de programación en JavaScript. Su objetivo es proporcionar una base sólida desde los conceptos fundamentales hasta la resolución de problemas complejos y la optimización de código.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> La programación no consiste únicamente en escribir código, sino en un proceso metódico de resolución de problemas. El enfoque académico recomendado para enfrentar cualquier ejercicio de programación se basa en la **descomposición analítica**:
> 
> 1. **Comprensión del enunciado:** Antes de codificar, es imperativo entender qué se solicita exactamente.
> 2. **Definición de pasos (Algoritmo):** Diseñar la secuencia lógica de pasos necesarios para resolver el problema.
> 3. **Subdivisión de tareas:** Dividir el algoritmo en tareas básicas o subproblemas aislados.
> 4. **Resolución y prueba modular:** Resolver y verificar cada tarea por separado (módulos de código).
> 5. **Integración:** Reunir los fragmentos de código ya verificados para conformar la solución final.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual y Definición de Conceptos Clave
> 
> Para programar con eficacia, es necesario comprender cómo la computadora gestiona la información.
> 
> ### 2.1. Variables y Memoria
> 
> - **Variable:** Es una posición de memoria, específicamente una "celda" o espacio que almacena un valor. Aunque el nombre sugiera cambio, su contenido puede o no variar durante la ejecución.
> - **Constante (**`**const**`**):** Una variable definida como constante no admite cambios en su valor una vez asignado; intentar modificarlo generará un error.
> - **Variable de bloque (**`**let**`**):** Permite definir variables que pueden ser modificadas y tienen un alcance limitado al bloque donde se declaran.
> 
> ### 2.2. Tipos de Datos y Manipulación
> 
> - **Cadenas de caracteres (String):** Una sucesión de caracteres (letras, números, símbolos). Se indexan empezando desde la posición **0**.
> - **Números:** Tipo de dato numérico. A diferencia de los strings, los números no poseen métodos de manipulación de texto de forma nativa.
> - **Conversión de tipos:** Para aplicar funciones de texto a un número (como buscar un dígito específico), se debe convertir primero a string utilizando la función `.toString()`.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: Herramientas y Estructuras
> 
> ### 3.1. Métodos de Strings Fundamentales
> 
> - `**charAt(posición)**`**:** Devuelve el carácter en la posición indicada (parámetro numérico).
> - `**.length**`**:** Propiedad que indica la longitud total de la cadena.
>     - _Nota importante:_ Para obtener el último carácter de una palabra, se utiliza `palabra.charAt(palabra.length - 1)`, ya que las posiciones comienzan en cero.
> 
> ### 3.2. Funciones (Módulos de Código)
> 
> Las funciones son herramientas que permiten modularizar el código, haciéndolo más prolijo, legible y fácil de mantener.
> 
> - **Definición:** Se utiliza la palabra reservada `function` seguida del nombre y parámetros entre paréntesis.
> - **Parámetros:** Valores que la función recibe para operar.
> - **Retorno (**`**return**`**):** Envía un resultado de vuelta al cuerpo principal del programa.
> - **Ventaja didáctica:** Permiten encapsular una lógica compleja (como determinar si un número es primo) y reutilizarla simplemente invocando su nombre.
> 
> ### 3.3. Estructuras de Control e Iteración
> 
> - `**for**` **y** `**while**`**:** Ambas estructuras son intercambiables en lógica; cualquier algoritmo con `while` puede convertirse a `for`.
> - **Condicionales (**`**if/else**`**):** Permiten la toma de decisiones basada en comparaciones lógicas.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Desarrollo de Algoritmos Avanzados
> 
> ### 4.1. Método de Ordenamiento: Burbujeo (Bubble Sort)
> 
> Es una técnica para ordenar elementos (por ejemplo, 4 números) de menor a mayor. Su lógica consiste en:
> 
> 1. Comparar el primer número con todos los de su derecha. Si se encuentra uno menor, se intercambian las posiciones.
> 2. Al finalizar la primera vuelta, el menor de todos queda asegurado en la primera posición.
> 3. Se repite el proceso empezando desde la segunda posición, luego la tercera, y así sucesivamente.
> 4. **Intercambio de variables:** Se utiliza una variable auxiliar (`temp`) para no perder el valor de una variable al sobrescribirla con el valor de la otra.
> 
> ### 4.2. Identificación de Números Primos
> 
> Un número es primo si solo es divisible por sí mismo y por la unidad.
> 
> - **Lógica de implementación:** Se utiliza un bucle que prueba divisores desde el 2 hasta el número anterior al evaluado. Si encuentra algún divisor (donde el resto de la división es 0), el número no es primo.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Depuración (Debugging) y Herramientas
> 
> El seguimiento paso a paso es vital para detectar errores lógicos.
> 
> - **Python Tutor:** Herramienta visual para ejecutar algoritmos de JavaScript paso a paso y ver el estado de las variables.
> - **Inspector del Navegador (Debugger):**
>     - Uso de la instrucción `debugger` en el código para forzar una pausa.
>     - **Watch Expressions:** Permite seguir variables específicas y observar cómo cambia su valor en cada instrucción.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Ejemplos Prácticos Explicados
> 
> ### Caso 1: Los primeros 20 números primos
> 
> Para resolver esto, se utiliza un contador (`k_numeros_primos`) y un bucle que incrementa un número `i` indefinidamente. En cada vuelta, una función `es_primo(i)` valida el número. Si es verdadero, el contador sube. El programa termina cuando el contador llega a 20.
> 
> ### Caso 2: Caracteres Repetidos en un String
> 
> Para identificar qué letras se repiten en una palabra como "ABRACADABRA":
> 
> 1. Se usa un `for` externo para recorrer cada letra.
> 2. Se usa un `for` interno para comparar esa letra contra todas las demás.
> 3. Se debe incluir una condición (`if i != j`) para que la letra no se compare consigo misma.
> 4. Si hay coincidencia, se marca como repetida; si recorre todo el string sin coincidencias, es un carácter único.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Errores Comunes y Aclaraciones
> 
> |   |   |
> |---|---|
> |Error Frecuente|Aclaración Académica|
> |Aplicar `charAt` a un número.|Los números no tienen ese método. Debe usarse `numero.toString().charAt()`.|
> |Confusión entre índice y longitud.|El índice máximo siempre es `length - 1`.|
> |Comparar una variable consigo misma en bucles anidados.|En algoritmos de búsqueda de repetidos, se debe excluir la comparación del índice actual con sí mismo (`i != j`).|
> |Declarar con `const` variables que cambian.|Si una variable será intercambiada (como en el ordenamiento), debe declararse con `let`.|
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de las fuentes, se detallan las siguientes pautas para la organización de la materia:
> 
> - **Alcance del Examen Parcial:**
>     - Incluye los contenidos de los **Trabajos Prácticos (TP) 1, 2 y 3**.
>     - El **TP 4** podría verse en clase, pero **no entrará en el parcial**.
>     - **Estructuras de Datos:** No se evaluarán estructuras complejas como Arrays (arreglos) o matrices en este examen, aunque se mencionen en clases avanzadas. Los ejercicios se resolverán mediante variables individuales.
> - **Próximas Clases:**
>     - **Jueves:** Clase de Lógica.
> - **Tipos de Ejercicios para el Examen:**
>     - Evaluación de números especiales (primos, perfectos, etc.).
>     - Generación de figuras geométricas con caracteres (pirámides, rectángulos, estrellas).
>     - Series numéricas (identificar lógica y codificar continuación).
>     - Sistemas de procesamiento de datos para tiendas (registros y procesos largos).
> - **Apoyo Académico:** El profesor ofrece la posibilidad de realizar clases de apoyo, talleres o dedicar la última media hora de clase a resolver dudas si se detectan bloqueos en el aprendizaje (mínimo 3-4 alumnos interesados).
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia entre `let` y `const`?
> 2. Si un string tiene 5 caracteres, ¿cuál es el índice del último carácter?
> 3. ¿Para qué sirve el método `.toString()`?
> 
> ### Nivel Intermedio
> 
> 4. Explique el concepto de "variable auxiliar" en un algoritmo de intercambio de valores.
> 5. ¿Por qué es útil el uso de funciones en lugar de escribir todo el código en el cuerpo principal?
> 6. Describa cómo funciona la herramienta de "Watch Expressions" en un navegador.
> 
> ### Nivel Avanzado
> 
> 7. Describa la lógica del método de burbujeo para ordenar una lista de números.
> 8. En un algoritmo de búsqueda de caracteres repetidos con dos bucles `for` anidados, ¿por qué es necesaria la condición `i != j`?
> 9. ¿Cómo determinaría si un número es primo utilizando una función y una estructura de control?
> 
> --------------------------------------------------------------------------------
> 
> _Este documento resume la Clase 5 de Técnicas de Programación. Se recomienda practicar los ejercicios de los TP 2 y 3 para consolidar los conocimientos de cara al parcial._

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 5 - Técnicas de programación" src="https://www.youtube.com/embed/Xbq6WzTsJ78?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1Q9zNxjKpzMAJLzChGgr-S6qA0E2bGHQD/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1VbPPAi4dfEltzIKw2BV4PK2rAfuLxKAa/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>