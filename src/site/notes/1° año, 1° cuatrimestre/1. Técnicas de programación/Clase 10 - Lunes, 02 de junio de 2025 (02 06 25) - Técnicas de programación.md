---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/1-tecnicas-de-programacion/clase-10-lunes-02-de-junio-de-2025-02-06-25-tecnicas-de-programacion/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio: Técnicas de Programación y Manipulación de Arrays
> 
> Este documento constituye un material de estudio integral sobre las técnicas de programación aplicadas a estructuras de datos tipo array (vectores), basándose en el análisis detallado de la lógica algorítmica, comparación, ordenamiento y búsqueda de datos.
> 
> ## 1. Introducción General
> 
> El manejo de arrays es una de las habilidades fundamentales en la programación. Un array es una estructura de datos que permite almacenar múltiples valores bajo un mismo nombre, accesibles mediante un índice. Esta guía profundiza en cómo manipular estas estructuras de manera eficiente, desde la comparación de igualdad entre vectores hasta la implementación de algoritmos complejos de ordenamiento y búsqueda binaria.
> 
> ## 2. Marco Conceptual y Definiciones Clave
> 
> Para comprender los algoritmos avanzados, es necesario establecer una base sólida sobre los términos y convenciones utilizados en el desarrollo:
> 
> ### Conceptos Fundamentales
> 
> - **Array (Vector):** Una colección ordenada de elementos. En JavaScript, su longitud es dinámica y se accede a través de la propiedad `.length`.
> - **Índice:** La posición de un elemento dentro del array. En programación, el primer elemento siempre ocupa la posición `0`.
> - **Iteración:** El proceso de recorrer un array, generalmente mediante un ciclo `for` o `while`.
> - **Parámetros de Función:** Valores que una función recibe para trabajar. Una práctica recomendada mencionada es anteponer una "P" (ej. `Pbec1`) para identificar visualmente qué variables son parámetros dentro del cuerpo de la función.
> - **Ámbito (Scope):** Las variables definidas con `let` o `const` dentro de un bloque (como un `for`) solo son accesibles allí. Las variables globales son accesibles desde cualquier parte del código.
> 
> ### Operadores Especiales
> 
> - **Operador Ternario:** Una forma abreviada de escribir un `if-else`.
>     - _Estructura:_ `condición ? acción_si_verdadero : acción_si_falso`
>     - _Ejemplo:_ `longitud1 == longitud2 ? comparar() : "No son iguales"`
> 
> ## 3. Desarrollo del Tema: Manipulación de Arrays
> 
> ### A. Comparación de Arrays
> 
> Determinar si dos arrays son iguales no se limita a comparar sus nombres; se debe evaluar su contenido y estructura.
> 
> 1. **Validación de Longitud:** El primer paso lógico es comparar el tamaño. Si `vec1.length !== vec2.length`, los arrays son automáticamente diferentes.
> 2. **Comparación Elemento por Elemento:** Si las longitudes coinciden, se utiliza un ciclo para comparar cada índice `i`. Si en alguna posición `vec1[i] !== vec2[i]`, se determina que no son iguales y se rompe el ciclo o se retorna un valor falso.
> 
> ### B. Combinación de Arrays Ordenados (Merge)
> 
> Este procedimiento busca generar un tercer array ordenado a partir de dos arrays que ya están ordenados individualmente.
> 
> - **Lógica de Índices:** Se utilizan dos punteros o índices independientes (`i` para el array 1 y `j` para el array 2).
> - **Proceso de Selección:**
>     - Se compara `vec1[i]` con `vec2[j]`.
>     - El valor menor se inserta en el array final y se incrementa únicamente el índice del array del cual se tomó el valor.
> - **Finalización:** Cuando uno de los arrays se agota, se deben copiar todos los elementos restantes del otro array al final del vector resultante, ya que estos son necesariamente mayores que los ya insertados.
> 
> ### C. Algoritmos de Ordenamiento (Método de Intercambio o Burbujeo)
> 
> El objetivo es reorganizar los elementos de un array desordenado. El método discutido utiliza dos ciclos anidados:
> 
> 1. **Ciclo Externo (i):** Fija una posición de referencia.
> 2. **Ciclo Interno (j):** Compara el elemento en la posición `i` con todos los elementos siguientes (`i + 1`).
> 3. **Swap (Intercambio):** Si el elemento en `i` es mayor que el elemento en `j` (para orden ascendente), se intercambian sus valores. Al terminar la primera vuelta del ciclo externo, el menor valor queda garantizado en la primera posición.
> 
> ## 4. Técnicas de Búsqueda
> 
> Existen dos métodos principales para localizar un elemento dentro de una colección:
> 
> ### Búsqueda Lineal
> 
> Es el método más básico. Consiste en recorrer el array desde el inicio hasta el final, comparando cada elemento con el valor buscado.
> 
> - **Ventaja:** Funciona en arrays desordenados.
> - **Desventaja:** Es ineficiente en colecciones grandes si el elemento está al final.
> 
> ### Búsqueda Binaria (Divide y Vencerás)
> 
> Este método es significativamente más rápido pero requiere que el **array esté ordenado previamente**.
> 
> - **Funcionamiento:**
>     1. Se define un índice `inicial` (0) y uno `final` (longitud - 1).
>     2. Se calcula el punto `medio`.
>     3. Se compara el valor buscado con el elemento en el `medio`.
>     4. Si el valor buscado es menor, se descarta la mitad derecha (el nuevo `final` será `medio - 1`).
>     5. Si es mayor, se descarta la mitad izquierda (el nuevo `inicial` será `medio + 1`).
>     6. El proceso se repite hasta encontrar el valor o hasta que el rango de búsqueda se agote.
> 
> ## 5. Ejemplos Prácticos Explicados
> 
> ### Ejemplo de Ordenamiento Paso a Paso
> 
> Supongamos el array: `[3, 1, 5, 2]`
> 
> 1. **Primera vuelta (i=0):**
>     - ¿3 > 1? Sí -> Intercambio: `[1, 3, 5, 2]`
>     - ¿1 > 5? No.
>     - ¿1 > 2? No.
>     - _Resultado:_ El `1` queda fijo en la posición 0.
> 2. **Segunda vuelta (i=1):**
>     - ¿3 > 5? No.
>     - ¿3 > 2? Sí -> Intercambio: `[1, 2, 5, 3]`
> 3. **Tercera vuelta (i=2):**
>     - ¿5 > 3? Sí -> Intercambio: `[1, 2, 3, 5]`
> 
> - **Fin:** Array ordenado.
> 
> ## 6. Errores Comunes y Confusiones
> 
> |   |   |
> |---|---|
> |Error Común|Aclaración Correcta|
> |**Uso de paréntesis en índices:** `vec(i)`|Los arrays siempre usan corchetes para los índices: `vec[i]`.|
> |**Confusión de tipos de datos:**|JavaScript puede comparar números y strings, pero es vital asegurar que los datos en el array sean consistentes para que el ordenamiento sea lógico.|
> |**Acceso fuera de límites:**|Intentar acceder a una posición igual a `.length` dará error o `undefined`, ya que el último índice es `.length - 1`.|
> |**Búsqueda binaria en desorden:**|Nunca aplicar búsqueda binaria si el array no ha sido ordenado previamente; los resultados serán incorrectos.|
> 
> ## 7. Síntesis y Conclusiones
> 
> - **Modularización:** Es preferible encapsular la lógica (como la comparación de arrays) en funciones genéricas para reutilizar el código.
> - **Eficiencia:** El uso de índices (`inicial`, `final`, `medio`) en la búsqueda binaria evita tener que "eliminar" datos realmente, optimizando el uso de memoria.
> - **Nomenclatura:** Usar nombres de variables significativos y convenciones claras (como el prefijo 'P' para parámetros) facilita la lectura del código por terceros.
> 
> ## 8. Preguntas de Repaso (Tipo Examen)
> 
> 1. **Básica:** ¿Por qué es necesario comparar la longitud de dos arrays antes de iterar para comprobar su igualdad?
> 2. **Intermedia:** En el algoritmo de ordenamiento por intercambio, si tengo un array de 10 elementos, ¿cuántas comparaciones realiza el ciclo externo?
> 3. **Avanzada:** Describa el estado de los índices `inicial` y `final` en una búsqueda binaria cuando el elemento buscado no existe en el array.
> 4. **Lógica:** ¿Qué sucede en JavaScript si intentas acceder a un índice que no existe? ¿Cómo difiere esto de otros lenguajes de programación según lo discutido?
> 
> ## 9. Fechas Importantes y Avisos Académicos
> 
> A partir del análisis de la fuente, se identifican los siguientes compromisos y avisos:
> 
> - **Entrega de Notas de Parciales:**
>     - **Fecha:** Próximo lunes.
>     - **Descripción:** El profesor se comprometió a tener los resultados de los exámenes parciales para la siguiente clase.
> - **Próximos Temas de Estudio:**
>     - **Combinatoria:** Incluye permutaciones, combinaciones con y sin repetición (ej. problemas de ubicación de personas en asientos).
>     - **Estructuras Avanzadas:** Listas y Árboles (se abordarán si el tiempo lo permite después de combinatoria).
> - **Tareas y Material:**
>     - Se actualizaron los archivos de resoluciones del **TP5** (incluyendo los ejercicios 6 y 10).
>     - Se espera que los alumnos revisen el **TP6**, el cual se centrará en métodos de búsqueda y ordenamiento.
>     - **Aviso:** Algunos ejercicios de ordenamiento podrían requerir que el alumno explique el algoritmo paso a paso en lugar de solo programarlo.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 10 - Técnicas de programación" src="https://www.youtube.com/embed/XkUVONMiGO8?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1gZ4-Uiu5BvzQ0vAVWlGJ_uObGtnZ6WJw/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1B38upQ6Se10NBl4lrsPyArSNiZ4IdbrX/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>