---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/1-tecnicas-de-programacion/clase-11-lunes-09-de-junio-de-2025-09-06-25-tecnicas-de-programacion/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Algoritmos de Búsqueda y Ordenamiento: Guía Completa de Búsqueda Binaria y Burbujeo Optimizado
> 
> Este documento constituye una guía de estudio exhaustiva sobre dos de los procedimientos fundamentales en la ciencia de la computación: la búsqueda binaria y el método de ordenamiento por burbujeo (versión optimizada). El contenido sintetiza las explicaciones técnicas, la lógica algorítmica y las consideraciones académicas presentadas en la sesión de Técnicas de Programación.
> 
> ## 1. Introducción General
> 
> El manejo eficiente de colecciones de datos (arrays o arreglos) es un pilar fundamental de la programación. No basta con almacenar información; es imperativo saber localizar elementos específicos y organizar la estructura de los datos para optimizar procesos posteriores. Esta guía aborda la **Búsqueda Binaria**, un método altamente eficiente para encontrar valores, y el **Ordenamiento de Burbujeo**, una técnica clásica para organizar elementos de menor a mayor.
> 
> ## 2. Marco Conceptual y Definiciones
> 
> ### Búsqueda Binaria (Binary Search)
> 
> Es un algoritmo de búsqueda que encuentra la posición de un valor dentro de un array **ordenado**. Su eficiencia radica en la estrategia de "dividir para conquistar", reduciendo a la mitad el área de búsqueda en cada paso.
> 
> ### Ordenamiento por Burbujeo (Bubble Sort - Versión II)
> 
> Es un algoritmo de ordenamiento que funciona revisando repetidamente la lista que se va a ordenar, comparando cada par de elementos adyacentes e intercambiándolos si están en el orden incorrecto. En su versión optimizada, el algoritmo "recuerda" qué partes ya están ordenadas para evitar comparaciones innecesarias.
> 
> ### Conceptos Clave
> 
> - **Punteros/Índices:** Variables que almacenan las posiciones (0, 1, 2...) dentro del array.
> - **Copia por Referencia vs. Copia por Valor:**
>     - _Referencia:_ Dos variables apuntan al mismo espacio de memoria. Si se modifica una, la otra cambia.
>     - _Valor:_ Se crea un duplicado independiente del array original.
> - **Iteración:** La repetición de un bloque de instrucciones (usando bucles `while` o `for`).
> 
> ## 3. Desarrollo del Tema: Búsqueda Binaria
> 
> ### Requisito Fundamental
> 
> Para que la búsqueda binaria funcione, **el array debe estar obligatoriamente ordenado**. Sin este orden previo, la lógica de descartar mitades no tiene validez.
> 
> ### Mecanismo de los Tres Punteros
> 
> El algoritmo gestiona tres índices principales para acotar el rango de búsqueda:
> 
> 1. **Índice Inicial:** Comienza en 0.
> 2. **Índice Final:** Comienza en la longitud del array menos uno (`length - 1`).
> 3. **Índice Medio:** La posición central calculada entre el inicial y el final.
> 
> **Fórmula del Índice Medio:** Para evitar errores de redondeo y asegurar una posición válida, se utiliza la función `Math.floor` (o `Math.ceil` según la preferencia): `Índice Medio = Math.floor(inicial + (final - inicial) / 2)`
> 
> ### Procedimiento Lógico
> 
> 4. Se calcula el punto medio y se compara el valor allí alojado con el **número buscado**.
> 5. **Caso A (Igualdad):** Si el valor en el índice medio es igual al número buscado, se ha encontrado el elemento.
> 6. **Caso B (Menor):** Si el número buscado es _menor_ que el valor en el índice medio, se desestiman todos los números a la derecha. El nuevo `Índice Final` será `Medio - 1`.
> 7. **Caso C (Mayor):** Si el número buscado es _mayor_ que el valor en el índice medio, se desestima la parte izquierda. El nuevo `Índice Inicial` será `Medio + 1`.
> 8. Este proceso se repite en un bucle `while` mientras el `Índice Inicial` sea menor o igual al `Índice Final`.
> 
> ### Ejemplo Práctico de Búsqueda
> 
> Imaginemos buscar el número **18** en el siguiente array: `[3, 5, 7, 11, 15, 22, 256, 444]`.
> 
> |   |   |   |   |   |   |
> |---|---|---|---|---|---|
> |Paso|Inicial|Final|Medio|Valor en Medio|Acción|
> |1|0|7|3|11|18 > 11. Buscar a la derecha. Nuevo Inicial = 4.|
> |2|4|7|5|22|18 < 22. Buscar a la izquierda. Nuevo Final = 5.|
> |3|4|5|4|15|18 > 15. Nuevo Inicial = 5.|
> |4|5|5|5|22|Inicial y Final coinciden. 22 != 18. No encontrado.|
> 
> ## 4. Desarrollo del Tema: Ordenamiento Burbujeo II
> 
> Esta versión del algoritmo es más eficiente que el burbujeo simple, ya que utiliza una variable booleana para detectar si se realizaron cambios y reduce el rango de comparación en cada vuelta.
> 
> ### Lógica de Intercambio (Swap)
> 
> Para intercambiar dos valores sin perder información, se utiliza una **variable temporal**:
> 
> 9. `temporal = array[i]`
> 10. `array[i] = array[i+1]`
> 11. `array[i+1] = temporal`
> 
> ### El Proceso de "Burbujeo"
> 
> - El algoritmo compara la posición `i` con la `i + 1`.
> - Si el elemento de la izquierda es mayor que el de la derecha, los intercambia.
> - Al final de la primera iteración completa, el número más grande de toda la colección habrá "flotado" hasta la última posición.
> - **Optimización:** Dado que el último elemento ya está ordenado tras la primera vuelta, el `Índice Final` del bucle se decrementa en 1 en cada iteración posterior.
> 
> ### Copia de Arrays
> 
> Para conservar el array original antes de ordenarlo, no basta con igualar variables (esto sería una copia por referencia). Se recomienda usar:
> 
> - `let copia = [...original]` (Spread operator)
> - `let copia = original.slice()`
> 
> ## 5. Errores Comunes y Aclaraciones
> 
> 1. **Uso de Constantes:** Un error frecuente es definir el array o la variable de control (`encontrado`) como `const` cuando se pretende modificar sus valores internos o su estado durante el algoritmo. Debe usarse `let`.
> 2. **Cálculo del Índice Medio fuera del Bucle:** Si el índice medio no se recalcula dentro del bucle con los nuevos valores de `inicial` y `final`, el algoritmo entrará en un bucle infinito o dará resultados erróneos.
> 3. **Índice Final en Búsqueda:** Al inicializar el índice final, es vital usar `length - 1`. Usar `length` directamente causará un error de "fuera de rango" (out of bounds).
> 4. **Actualización del Índice Medio al Salir:** En algunos casos, cuando el bucle termina porque `inicial == final`, es necesario realizar una última comprobación o actualización para verificar el último elemento restante.
> 
> ## 6. Síntesis y Resumen de Algoritmos
> 
> ### Búsqueda Binaria
> 
> - **Objetivo:** Localizar un elemento en un conjunto ordenado.
> - **Complejidad:** Alta eficiencia, reduce el problema a la mitad en cada paso.
> - **Variables:** `inicial`, `final`, `medio`, `encontrado`.
> 
> ### Burbujeo II
> 
> - **Objetivo:** Organizar un conjunto desordenado.
> - **Estrategia:** Comparación de adyacentes e intercambio.
> - **Optimización:** Uso de bandera `sinCambio` y reducción del límite del array en cada vuelta.
> 
> ## 7. Preguntas de Repaso (Tipo Examen)
> 
> **Básicas:**
> 
> 1. ¿Cuál es el requisito indispensable para aplicar una búsqueda binaria?
> 2. Explique para qué sirve una variable "temporal" en un método de ordenamiento.
> 
> **Intermedias:** 3. Si un array tiene 10 elementos (índices 0 a 9), ¿cuáles son los valores de `inicial`, `final` y `medio` en la primera iteración de una búsqueda binaria? 4. ¿Por qué es más eficiente el método de Burbujeo II que el tradicional?
> 
> **Avanzadas:** 5. Describa la diferencia entre copiar un array por referencia y por valor, y por qué es relevante al mostrar resultados de ordenamiento. 6. En un algoritmo de búsqueda binaria, si el número buscado no está en el array, ¿en qué condición deben quedar los punteros `inicial` y `final` para finalizar el bucle?
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> A partir de las indicaciones proporcionadas durante la clase, se establece el siguiente cronograma y recordatorios:
> 
> |   |   |   |
> |---|---|---|
> |Fecha|Tipo de Evento|Descripción Detallada|
> |**Lunes 16 de junio**|**Feriado**|No habrá actividad académica (Día posterior al Día del Padre / Próximo lunes).|
> |**Domingo 23 de junio**|**Clase de Repaso**|Sesión de repaso general y presentación breve del tema **Combinatoria**.|
> |**Domingo 30 de junio**|**Examen Parcial**|Evaluación presencial/sincrónica de los contenidos de la materia.|
> |**Domingo 7 de julio**|**Recuperatorio**|Fecha destinada para quienes deban recuperar el parcial.|
> |**Semana del 14 de julio**|**Finales (1ra Llamada)**|Primera instancia de exámenes finales antes del receso de invierno.|
> |**Agosto (1ra semana)**|**Finales (2da Llamada)**|Segunda instancia de exámenes finales antes del inicio del segundo cuatrimestre.|
> 
> **Recordatorios Académicos Importantes:**
> 
> - **Promoción:** La materia se promociona con una nota mínima de **7 (siete)**.
> - **Asistencia:** El profesor recomienda tener cuidado con la asistencia. Aunque no se percibe una toma de lista estricta en todas las sesiones, personal de bedelía podría registrar ingresos a la sala virtual, lo cual impacta en la condición de alumno regular/promocional.
> - **Notas Actuales:** El profesor está finalizando la corrección de los parciales anteriores. Se enviarán las observaciones por correo electrónico individualmente y luego se subirán a la planilla compartida.
> - **Resultados Mencionados:** Se destacó el desempeño de alumnos como Ignacio (Nacho) y Carla. Pía obtuvo una nota de 7.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 11 - Técnicas de programación" src="https://www.youtube.com/embed/_lh4cxSIPyo?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1-WaV7xM-CNXFx3eI8UmW5jq5h5VVjgyU/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1HOv9VDNmcQrOwRFoKWZDm-kowi6Zywfc/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>