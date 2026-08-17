---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/1-tecnicas-de-programacion/clase-8-lunes-19-de-mayo-de-2025-19-05-25-tecnicas-de-programacion/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio Avanzada: Técnicas de Programación, Algoritmos y Estructuras de Datos
> 
> Este documento constituye un material de estudio integral basado en la clase de Técnicas de Programación centrada en la resolución de problemas algorítmicos complejos, el uso de arreglos (arrays) y la implementación de lógica matemática aplicada a la informática.
> 
> ## 1. Introducción General
> 
> La programación se define fundamentalmente como la actividad de procesar datos mediante **algoritmos**, los cuales son secuencias de instrucciones diseñadas para obtener información específica. Existe una relación histórica y técnica intrínseca entre la informática y las matemáticas; de hecho, muchos conceptos de programación se resuelven y ejemplifican de manera óptima a través de problemas matemáticos (números perfectos, series, conjeturas) debido a que estos requieren una lógica estructurada y finita que encaja con la naturaleza de los lenguajes de programación.
> 
> ### Importancia y Relevancia
> 
> El dominio de los algoritmos y los arreglos permite al programador:
> 
> - Simular actividades del mundo real (como el registro de una tienda).
> - Resolver problemas de alta complejidad con pocas herramientas básicas.
> - Optimizar el procesamiento de datos sin necesidad de recurrir a procesos extensos o manuales.
> 
> ## 2. Marco Conceptual y Definiciones Clave
> 
> Para comprender los temas avanzados de esta guía, es necesario dominar los siguientes términos fundamentales:
> 
> - **Algoritmo:** Una secuencia lógica y ordenada de pasos para resolver un problema o realizar una tarea.
> - **Array (Arreglo):** Una estructura de datos que permite almacenar múltiples valores en una sola variable. Los elementos se acceden mediante índices (comenzando desde 0).
> - **Número Primo:** Aquel número mayor que 1 que solo es divisible por sí mismo y por la unidad.
> - **Conjetura:** En matemáticas, es una afirmación que se supone verdadera pero que no ha sido probada ni refutada fehacientemente.
> - **Iteración (Bucle/Loop):** Repetición de un bloque de código mientras se cumpla una condición (ej. `for`, `while`).
> - **Validación de Datos:** Proceso de asegurar que la entrada del usuario cumple con los requisitos necesarios (ej. que sea un número, que sea par, etc.) antes de procesarla.
> 
> ## 3. Desarrollo del Tema: Resolución de Problemas Complejos
> 
> ### A. La Conjetura de Goldbach
> 
> Esta conjetura afirma que **todos los números pares mayores que 2 pueden ser expresados como la suma de dos números primos.**
> 
> #### Lógica de Resolución (Algoritmo)
> 
> Para verificar esta conjetura en un programa, se pueden seguir dos enfoques:
> 
> 1. **Enfoque de Almacenamiento (Array):**
>     - Se solicitan los datos al usuario.
>     - Se genera un array con todos los números primos menores al número ingresado.
>     - Se utilizan dos bucles anidados para sumar cada elemento del array con los demás (incluyéndose a sí mismo) hasta encontrar la combinación que iguale al número original.
> 2. **Enfoque de Cálculo Directo (Optimizado):**
>     - Se recorre desde 2 hasta la mitad del número ingresado (`n`).
>     - Para cada número `i`, se calcula su complemento `j = n - i`.
>     - Se verifica si tanto `i` como `j` son primos simultáneamente. Si lo son, se ha encontrado la solución.
> 
> #### Optimización de la Función `es_primo`
> 
> Para determinar si un número es primo, no es necesario dividirlo por todos los números anteriores a él. Es suficiente probar divisores hasta su **raíz cuadrada** (`Math.sqrt(n)`). Si no se encuentra un divisor en ese rango, el número es primo. Esto reduce significativamente la cantidad de instrucciones que ejecuta la computadora.
> 
> ### B. Inserción Ordenada en Arreglos
> 
> Un problema común es mantener un array siempre ordenado mientras el usuario ingresa datos de forma aleatoria.
> 
> #### Pasos del Algoritmo:
> 
> 1. **Búsqueda de Posición:** Se recorre el array para encontrar el primer número que sea mayor al número ingresado por el usuario. Ese índice (`i`) será la posición correcta.
> 2. **Desplazamiento (Shifting):** Si el número debe ir en el medio o al principio, todos los elementos desde esa posición hacia adelante deben "moverse" un lugar a la derecha.
>     - _Importante:_ El desplazamiento debe hacerse **de atrás hacia adelante** (desde el último elemento hacia el índice `i`) para evitar sobrescribir y perder datos.
> 3. **Inserción:** Una vez generado el espacio, se coloca el nuevo número en la posición `i`.
> 
> ## 4. Relaciones entre Conceptos y Estructuras
> 
> La programación efectiva se basa en la combinación de herramientas simples para resolver problemas complejos:
> 
> - **Modularización:** Es fundamental separar la lógica en **funciones** (ej. una función específica para verificar si un número es primo y otra para la lógica principal). Esto facilita la prueba de errores y la reutilización de código.
> - **Anidamiento de Bucles:** Para comparar elementos entre sí (como buscar pares de números), se utilizan bucles uno dentro de otro. El bucle externo mantiene un valor fijo mientras el interno recorre las demás opciones.
> - **Ámbito de Variables (**`**let**` **vs** `**bar**`**):** Las variables definidas con `let` dentro de un bloque (como un `for`) solo existen allí. Si se necesita acceder al índice después de que el bucle termine, la variable debe definirse fuera del bloque.
> 
> ## 5. Ejemplos Prácticos y Casos Reales
> 
> ### Ejemplo: Implementación de la Conjetura de Goldbach
> 
> Si el usuario ingresa el número **16**:
> 
> 1. El programa identifica números primos menores a 16: `{2, 3, 5, 7, 11, 13}`.
> 2. Inicia comparaciones:
>     - 2 + 2 = 4 (No)
>     - 2 + 3 = 5 ... 2 + 13 = 15 (No)
>     - 3 + 3 = 6 ... 3 + 13 = **16** (¡Sí!)
> 3. Resultado mostrado: "3 y 13".
> 
> ### Ejemplo: Inserción de un número en Array ordenado
> 
> Array actual: `[10, 20, 40, 50]` Nuevo número: `30`
> 
> 4. Búsqueda: 30 es menor que 40. Posición detectada: Índice 2.
> 5. Desplazamiento: 50 pasa a posición 4, 40 pasa a posición 3.
> 6. Inserción: 30 se coloca en posición 2.
> 7. Resultado: `[10, 20, 30, 40, 50]`.
> 
> ## 6. Errores Comunes y Aclaraciones
> 
> - **Perder datos al desplazar:** Al intentar ordenar un array, si se mueven los elementos hacia adelante empezando por el principio, se terminará repitiendo el primer número en todas las posiciones. Siempre se debe empezar por el final del array.
> - **No validar el cero:** En bucles de ingreso de datos, es vital asegurarse de que el programa se detenga exactamente cuando se ingresa el valor de corte (ej. el número 0) sin procesar ese 0 como un dato válido.
> - **Confusión con el 1 y el 2 en Primos:** Recordar que el 1 no se considera primo en estos algoritmos y que el 2 es el único primo par.
> - **Índices fuera de rango:** Intentar acceder a `array[length]` causará un error o devolverá un valor indefinido, ya que el último índice es siempre `length - 1`.
> 
> ## 7. Síntesis y Conclusiones
> 
> La programación no se trata de conocer muchas herramientas, sino de saber combinar de forma lógica las pocas que existen (variables, bucles, arreglos y condicionales). La mejor forma de progresar es mediante la **práctica constante y variada**: resolver problemas de diferentes tipos ayuda a construir un "rompecabezas" de soluciones que luego pueden aplicarse a nuevos desafíos. La división de problemas grandes en módulos pequeños y testeables es la clave del éxito técnico.
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Qué es un algoritmo y cómo se relaciona con la matemática?
> 2. ¿Por qué el índice de un array comienza en 0 y no en 1?
> 3. ¿Para qué sirve la función `parseInt(prompt(...))`?
> 
> ### Nivel Intermedio
> 
> 4. Explique por qué es más eficiente buscar divisores hasta la raíz cuadrada de un número para saber si es primo.
> 5. En un proceso de inserción ordenada, ¿por qué el desplazamiento de elementos debe hacerse de atrás hacia adelante?
> 6. ¿Qué sucede si un usuario ingresa un dato que no es un número (`NaN`) y cómo se puede detectar?
> 
> ### Nivel Avanzado
> 
> 7. Describa la lógica necesaria para encontrar dos números primos que sumen un número par sin usar un array intermedio para guardarlos.
> 8. ¿Cómo afectaría el rendimiento de un programa el uso de bucles anidados si el array tuviera millones de elementos?
> 
> ## 9. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de la sesión, se destacan los siguientes puntos relevantes para la organización de la materia:
> 
> |   |   |
> |---|---|
> |Evento / Recurso|Detalle|
> |**Parcial**|Se hace mención a ejercicios típicos de parcial. El profesor indica que prefiere ejercicios breves de lógica matemática para los exámenes en lugar de sistemas extensos de carga de datos para evitar que sean demasiado largos.|
> |**Material Disponible**|El profesor subirá a la carpeta de la materia un archivo titulado `resoluciones TP5.txt` que contiene las soluciones a los ejercicios discutidos (Goldbach y Arreglos Ordenados).|
> |**Trabajo Práctico 5 (TP5)**|Se espera que los estudiantes completen los ejercicios restantes del TP5. El profesor enfatiza la importancia de la práctica constante con ejercicios de variada dificultad.|
> |**Recordatorio Académico**|Se advierte sobre la importancia de validar siempre los datos ingresados por el usuario, aunque en clase a veces se omita para simplificar la explicación del algoritmo principal.|
> 
> _Nota: No se mencionaron fechas específicas de calendario (día/mes) para el parcial en esta sesión, pero se sugiere estar atento a las actualizaciones en la carpeta de la materia mencionada por el docente._

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 8 - Técnicas de programación" src="https://www.youtube.com/embed/R9SJB-kurYs?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1Fh1HJckKe9ll1hFiGDzQo6CJ7jg6ymEQ/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1s3iPgqKf0EpyPr-RwGoIuMJ07BVmyWc5/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>