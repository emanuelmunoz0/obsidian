---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/4-estadistica-y-probabilidad-para-el-desarrollo-de-software/clase-11-jueves-06-de-noviembre-de-2025-06-11-25-estadistica-y-probabilidad-para-el-desarrollo-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio: Estadística, Distribución Normal y Ajuste de Curvas
> 
> Este documento constituye un material de estudio integral sobre el análisis de datos estadísticos, centrándose en la aplicación práctica de la distribución normal y las técnicas de ajuste de curvas para la interpretación de fenómenos en el desarrollo de software y la ciencia de datos.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> El análisis estadístico permite transformar datos brutos en información significativa. Este documento aborda dos grandes pilares: la **Distribución Normal**, que permite calcular probabilidades y frecuencias en poblaciones que siguen una campana de Gauss, y el **Ajuste de Curvas**, una técnica esencial para encontrar patrones y modelos matemáticos en conjuntos de datos dispersos. El dominio de estas herramientas es fundamental para la predicción de eventos y la toma de decisiones basada en evidencia.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual y Definiciones Clave
> 
> Para comprender los procedimientos avanzados, es necesario establecer los fundamentos teóricos:
> 
> ### Conceptos Fundamentales
> 
> - **Media (****\mu****):** Es el promedio aritmético de los datos. Representa el centro de la distribución.
> - **Desviación Típica o Estándar (****\sigma****):** Medida que indica cuánto se alejan, en promedio, los datos respecto a la media. Una desviación baja indica que los datos están agrupados; una alta, que están dispersos.
> - **Tipificación (Valor Z):** Proceso de transformar una variable aleatoria normal en una variable normal estándar (con media 0 y desviación 1). La fórmula es: Z = \frac{X - \mu}{\sigma}
> - **Límites Reales:** En distribuciones continuas, se aplican ajustes de \pm 0,5 a los valores discretos para cubrir el intervalo completo de la medición. Por ejemplo, para un valor de 120, el límite real inferior es 119,5.
> - **Área bajo la curva:** En una distribución normal, el área total es igual a 1 (o 100%). Las tablas de probabilidad (como el Anexo 2 mencionado en las fuentes) permiten calcular el área entre la media (Z=0) y un valor Z específico.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema
> 
> ### 3.1. Cálculo de Probabilidades en Distribución Normal
> 
> El análisis de una población bajo una distribución normal requiere seguir pasos lógicos para determinar cuántos individuos cumplen con ciertos criterios:
> 
> 1. **Definición de parámetros:** Identificar la media (\mu), la desviación típica (\sigma) y el tamaño de la muestra (N).
> 2. **Establecimiento de límites reales:** Ajustar los valores de búsqueda restando 0,5 al límite inferior y sumando 0,5 al límite superior.
> 3. **Tipificación de los límites:** Calcular el valor Z para ambos extremos del intervalo.
> 4. **Búsqueda en Tabla:** Localizar el área correspondiente a cada valor Z. Es importante recordar que el área para un Z negativo es idéntica a la de su contraparte positiva debido a la simetría de la curva.
> 5. **Cálculo del área total:** Sumar o restar las áreas según la posición respecto a la media.
> 6. **Cálculo de frecuencia:** Multiplicar el área total (en decimal) por el tamaño de la muestra (N).
> 
> ### 3.2. Ajuste de Curvas (Regresión)
> 
> Cuando las mediciones no siguen una gráfica conocida, se busca una "solución consensuada" mediante el ajuste.
> 
> - **Objetivo:** Trazar una línea o curva que pase lo más cerca posible de la mayoría de los puntos (mínimos cuadrados).
> - **Modelos de Ajuste:**
>     - **Lineal:** Una línea recta (y = mx + b). Es el modelo inicial recomendado.
>     - **Polinómico:** Curvas de grado 2, 3 o hasta 6. Ofrecen mayor precisión pero mayor complejidad.
>     - **Exponencial/Logarítmico:** Útiles cuando los datos muestran crecimientos o decrecimientos acelerados.
> - **Importancia en Software/Ciencia de Datos:** Estos modelos sirven para algoritmos de predicción. El ajuste permite realizar proyecciones y tendencias para la toma de decisiones futuras.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Ejemplos Prácticos Paso a Paso
> 
> ### Caso 1: Estudiantes y sus Pesos
> 
> **Datos:** N = 500, \mu = 151 libras, \sigma = 15 libras. **Pregunta:** ¿Cuántos estudiantes pesan entre 120 y 155 libras?
> 
> - **Paso 1 (Límites):** 119,5 y 155,5.
> - **Paso 2 (Tipificación):**
>     - Z_1 = (119,5 - 151) / 15 = -2,10
>     - Z_2 = (155,5 - 151) / 15 = 0,30
> - **Paso 3 (Áreas por tabla):**
>     - Área para Z=2,10: 0,4821
>     - Área para Z=0,30: 0,1179
> - **Paso 4 (Suma de áreas):** 0,4821 + 0,1179 = 0,60 (60% de la población).
> - **Resultado:** 500 \times 0,60 = 300 estudiantes.
> 
> ### Caso 2: Valores Extremos (Más de 185 libras)
> 
> **Datos:** Mismos parámetros anteriores. **Pregunta:** ¿Cuántos pesan más de 185 libras?
> 
> - **Paso 1 (Límite):** 185,5.
> - **Paso 2 (Tipificación):** Z = (185,5 - 151) / 15 = 2,30.
> - **Paso 3 (Cálculo):** Como se busca el área "más allá" de 2,30, se resta el área de la tabla a 0,5 (que es la mitad de la curva).
>     - 0,5 - 0,4893 = 0,0107 (aprox. 1%).
> - **Resultado:** 500 \times 0,0107 = 5,35. Se redondea a 5 o 6 estudiantes.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Errores Comunes y Aclaraciones
> 
> - **Uso de Límites Reales:** Un error frecuente es tipificar el valor exacto (ej. 120) en lugar del límite real (119,5). El ajuste de 0,5 es vital para la precisión.
> - **Simetría de la Curva:** No existen "áreas negativas". Si Z es -2,10, se busca 2,10 en la tabla y se utiliza ese valor positivo.
> - **Sobreajuste (Overfitting):** En el ajuste de curvas, usar un polinomio de grado muy alto (como grado 6) puede copiar los puntos perfectamente pero perder la capacidad de generalizar o predecir correctamente nuevos datos.
> - **Redondeo:** En estadística de poblaciones (personas, objetos), si el resultado decimal es 0,5 o superior, se debe redondear al entero siguiente.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Síntesis y Conclusiones
> 
> - La **distribución normal** permite calcular probabilidades sumando o restando áreas respecto a la media tras un proceso de tipificación.
> - El **ajuste de curvas** es la búsqueda de un modelo matemático (recta o parábola) que represente la tendencia de datos dispersos.
> - El uso de herramientas digitales (Excel, Google Sheets) facilita la obtención de **ecuaciones de tendencia**, permitiendo elegir entre modelos lineales o polinómicos según el grado de ajuste visual y matemático.
> - En la ciencia de datos, los modelos de predicción dependen de este ajuste para generar proyecciones válidas.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Qué representa el valor Z en una distribución normal?
> 2. ¿Por qué se utiliza el ajuste de 0,5 para establecer límites reales?
> 3. En una curva normal, ¿qué porcentaje de los datos se encuentra a cada lado de la media?
> 
> ### Nivel Intermedio
> 
> 4. Si un valor tipificado da negativo, ¿cómo se busca su área en la tabla de probabilidad?
> 5. ¿Cuál es la diferencia principal entre un ajuste lineal y un ajuste polinómico?
> 
> ### Nivel Avanzado
> 
> 6. Explique el procedimiento para calcular el número de individuos que se encuentran "por encima" de un valor determinado que es mayor a la media.
> 7. ¿En qué situaciones sería preferible usar un ajuste polinómico de grado 6 sobre uno lineal, y qué riesgos conlleva?
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de las fuentes, se identifican las siguientes indicaciones para el cronograma académico:
> 
> - **Examen Parcial:**
>     - **Fecha:** Jueves 20 de junio.
>     - **Modalidad:** El examen se realizará en **grupo**.
>     - **Descripción:** Evaluación de los contenidos desarrollados en clase (probabilidad, estadística y ajuste de curvas).
> - **Recordatorios importantes:**
>     - El profesor enfatiza la importancia de trabajar en grupo y compartir pantalla para mostrar resultados.
>     - Se recomienda iniciar siempre los análisis de tendencia probando primero el **modelo lineal** por ser el más clásico y sencillo de predecir.
>     - Es fundamental contar con las tablas de probabilidad (Anexo 2) para la resolución de ejercicios de distribución normal.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 11 - Estadística y probabilidad para el desarrollo de software" src="https://www.youtube.com/embed/LG4-sVvCYCU?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/14cSV9csTLToRCbX1Qzyv27TCpUqFrYcw/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1jAHpkA8CA1ms8isE2Rmgd7-zz9qM0oNk/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>