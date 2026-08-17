---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/4-estadistica-y-probabilidad-para-el-desarrollo-de-software/clase-4-jueves-04-de-septiembre-de-2025-04-09-25-estadistica-y-probabilidad-para-el-desarrollo-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Estadística y Probabilidad para el Desarrollo de Software: Medidas de Tendencia Central
> 
> Este documento constituye un apunte integral basado en la cuarta sesión académica sobre estadística y probabilidad. El objetivo es proporcionar una comprensión profunda de las medidas de tendencia central (media, mediana y moda), su cálculo manual y su implementación en herramientas de hoja de cálculo como Excel.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> En el análisis de datos para el desarrollo de software, la capacidad de resumir grandes conjuntos de información en valores representativos es fundamental. Las medidas de tendencia central permiten identificar el "centro" de una distribución de datos, facilitando la toma de decisiones basada en evidencia cuantitativa. El estudio se centra en dos escenarios principales: el trabajo con **poblaciones directas** y el trabajo con **datos agrupados en intervalos**.
> 
> ## 2. Marco Conceptual y Definiciones Clave
> 
> Para abordar el tema desde cero, es necesario clarificar los términos fundamentales que estructuran los cálculos estadísticos:
> 
> ### Conceptos Fundamentales
> 
> - **Población:** Conjunto total de elementos o datos que se están estudiando (ej. un listado de 80 valores).
> - **Intervalos (Clases):** Rangos numéricos utilizados para agrupar datos (ej. 60-62). Se utilizan cuando la variedad de datos es muy amplia.
> - **Frecuencia (****f****):** Cantidad de veces que un valor o rango de valores aparece en el conjunto de datos.
> - **Marca de Clase (****x****):** Es el punto medio de un intervalo. Se calcula sumando los límites inferior y superior del intervalo y dividiendo el resultado por dos.
>     - _Fórmula:_ x = \frac{Limite \ Inferior + Limite \ Superior}{2}
> - **Media Aritmética (****\bar{x}****):** El promedio de los datos. Representa el valor que tendrían todos los elementos si se repartieran de manera equitativa.
> - **Mediana:** El valor que se encuentra exactamente en el centro de un conjunto de datos ordenados.
> - **Moda:** El valor o categoría que cuenta con la mayor frecuencia (el que más se repite).
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: La Media Aritmética
> 
> La clase profundiza en el cálculo de la media, diferenciando entre datos poblacionales y datos organizados en intervalos.
> 
> ### 3.1. Cálculo de la Media con Datos en Intervalos
> 
> Existen dos técnicas principales para obtener la media cuando los datos están agrupados. Ambas deben arrojar el mismo resultado.
> 
> #### Técnica 1: Método Clásico (Frecuencia por Marca de Clase)
> 
> Es la técnica más directa y fácil de aplicar en Excel.
> 
> 1. **Calcular la Marca de Clase (****x****):** Para cada intervalo.
> 2. **Multiplicar** **f \cdot x****:** Se multiplica la frecuencia de cada renglón por su marca de clase correspondiente.
> 3. **Sumatoria:** Se suman todos los resultados del paso anterior.
> 4. **División Final:** Se divide el total de la sumatoria por el número total de datos (n).
> 
> #### Técnica 2: Método de Referencia o Desviación (Fórmula de A)
> 
> Este método utiliza un número de referencia para simplificar cálculos grandes o verificar resultados.
> 
> - **Paso 1: Identificar el valor** **A****:** Se busca la frecuencia más alta en la tabla. El valor A será la **Marca de Clase** asociada a esa frecuencia máxima.
> - **Paso 2: Calcular la desviación (****d****):** Para cada intervalo, se resta la marca de clase menos el valor A (d = x - A).
>     - _Nota:_ Los valores por debajo de A resultarán negativos, el valor en el renglón de A será cero, y por encima serán positivos.
> - **Paso 3: Multiplicar** **f \cdot d****:** Frecuencia de cada renglón por su desviación.
> - **Paso 4: Aplicar la fórmula:** \bar{x} = A + \frac{\sum (f \cdot d)}{n} Se divide la suma de los productos f \cdot d por el total de datos, y ese resultado se suma al valor A inicial.
> 
> ### 3.2. Cálculo de la Media con Población (Datos No Agrupados)
> 
> Cuando no hay intervalos, el proceso es más directo:
> 
> - **Manual:** Se suman todos los valores y se dividen por la cantidad total de elementos.
> - **Excel:** Se utiliza la función `=PROMEDIO(rango_de_datos)`. El orden de los datos no afecta el resultado de la media.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Mediana y Moda: Conceptos y Aplicación
> 
> ### 4.1. La Mediana
> 
> Representa el centro de la tabla. Para calcularla en una población, los datos **deben estar ordenados**.
> 
> - **Lógica para poblaciones pares (ej.** **n=80****):**
>     1. Se resta 2 al total: 80 - 2 = 78.
>     2. Se divide por 2: 78 / 2 = 39.
>     3. Esto indica que hay 39 datos al inicio y 39 al final. Se toman los dos valores centrales (posiciones 40 y 41), se suman y se dividen por 2.
> - **Lógica para poblaciones impares:** Se resta 1 al total, se divide por 2 y el valor siguiente es la mediana exacta.
> - **Excel:** Función `=MEDIANA(rango_de_datos)`.
> 
> ### 4.2. La Moda
> 
> Es el valor con mayor peso en la frecuencia.
> 
> - **Excel:** Se recomienda la función `=MODA.VARIOS(rango_de_datos)`. Al ser una función matricial en versiones antiguas, se utilizaba `Ctrl + Shift + Enter`. Esta función permite identificar si existen múltiples modas (distribuciones bimodales o multimodales).
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Ejemplos Prácticos Paso a Paso
> 
> ### Caso: Pesos en Intervalos
> 
> Supongamos la siguiente tabla de frecuencias:
> 
> |   |   |   |   |
> |---|---|---|---|
> |Intervalo|Frecuencia (f)|Marca de Clase (x)|f \cdot x|
> |60 - 62|5|61|305|
> |63 - 65|18|64|1152|
> |66 - 68|42|67|2814|
> |69 - 71|27|70|1890|
> |72 - 74|8|73|584|
> |**Total**|**100**|-|**6745**|
> 
> **Cálculo Media (Técnica 1):** 6745 / 100 = 67.45
> 
> **Cálculo Media (Técnica 2):**
> 
> 1. Frecuencia más alta = 42. Por lo tanto, **A = 67**.
> 2. Se calculan las desviaciones (x - 67) y se multiplican por f.
> 3. Si la suma de f \cdot d diera, por ejemplo, 45, la media sería: 67 + (45/100) = 67.45.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores Comunes y Aclaraciones
> 
> 4. **Confundir Media con Mediana:** La media es un promedio aritmético sensible a valores extremos; la mediana es una posición física en un conjunto ordenado.
> 5. **Cálculo de Marca de Clase:** Un error frecuente es no dividir por 2 o sumar mal los límites. Siempre debe ser el punto medio exacto del intervalo.
> 6. **Referencias en Excel:** Al aplicar la Técnica 2, es vital usar **referencias absolutas** (símbolo `$`, ej. `$C$21`) para el valor A, de modo que al arrastrar la fórmula el valor de referencia no cambie.
> 7. **Uso de Fórmulas en Intervalos vs. Población:** Las fórmulas automáticas de Excel como `=PROMEDIO` funcionan sobre la lista de datos crudos (población). Si solo se tiene la tabla de intervalos, se debe usar obligatoriamente el cálculo manual de f \cdot x.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Síntesis y Puntos Clave
> 
> - La **Marca de Clase** es el representante numérico de un intervalo.
> - La **Técnica 2** de la media sirve como verificación y se basa en el intervalo de mayor peso (mayor frecuencia).
> - La **Media** siempre debe caer dentro del rango de los datos y, generalmente, cerca del intervalo con mayor frecuencia (punto de interpolación).
> - Para la **Mediana**, el ordenamiento de los datos es un requisito indispensable en el cálculo manual.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> A partir del análisis de la fuente, se identifican los siguientes puntos relevantes para la organización de la materia:
> 
> - **Próxima Clase:** Se dará continuidad al tema de Mediana y Moda para datos agrupados en intervalos, además de otras medidas como la media geométrica, armónica y RMS.
> - **Material Complementario:** El profesor hace referencia a la entrega de apuntes sobre "Diagramas de Clases", los cuales son considerados de gran valor para la formación de los estudiantes.
> - **Cronograma Estimado:** Se menciona el "fin de septiembre" como una referencia temporal para el avance de los temas o evaluaciones (según el contexto de la despedida en el audio).
> - **Clases Adicionales:** Se menciona un encuentro con parte del grupo el día de mañana (posterior a la clase grabada).
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la fórmula para calcular la Marca de Clase?
> 2. ¿Qué función de Excel se utiliza para calcular la media de una población desordenada?
> 
> ### Nivel Intermedio
> 
> 1. En la Técnica 2 para calcular la media, ¿cómo se selecciona el valor A y qué representa?
> 2. Si un conjunto de datos tiene n=100, explique los pasos para encontrar la posición de la mediana manualmente.
> 
> ### Nivel Avanzado
> 
> 1. ¿Por qué se dice que el valor de la media es un "método de interpolación" cuando se trabaja con intervalos?
> 2. Si en una tabla de frecuencias dos intervalos tienen la misma frecuencia máxima, ¿afecta esto al resultado final de la media si se elige uno u otro como valor A? Justifique.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 4 - Estadística y probabilidad para el desarrollo de software" src="https://www.youtube.com/embed/EThK01sk2Q0?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1udV_7sa5KYKjpAZh59pD1wID8sZS0339/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1sVZPXmluyb8tmf2fRqHeTnaaAYCF0eET/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>