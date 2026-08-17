---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/4-estadistica-y-probabilidad-para-el-desarrollo-de-software/clase-7-jueves-09-de-octubre-de-2025-09-10-25-estadistica-y-probabilidad-para-el-desarrollo-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía Académica: Estadística y Probabilidad - Desviación y Tipificación de Variables
> 
> Este documento constituye un material de estudio integral sobre las medidas de dispersión y la transformación de variables, basado en las sesiones de la cátedra de Estadística y Probabilidad para el desarrollo de software.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> En el análisis de datos para el desarrollo de software, no basta con conocer el promedio (media) de un conjunto de datos. Es fundamental comprender qué tan dispersos se encuentran esos datos respecto a su centro. Este documento aborda tres pilares del análisis estadístico descriptivo: la **desviación media**, la **desviación típica** y la **tipificación de variables**. Estos conceptos permiten realizar un análisis más fino, preparar los datos para su visualización y establecer las bases para modelos de probabilidad avanzados.
> 
> ## 2. Contexto e Importancia
> 
> El estudio de la variabilidad permite determinar la confiabilidad de la media. Si los datos están muy dispersos, la media es menos representativa. En el desarrollo de software, esto es vital para el análisis de rendimiento, tiempos de respuesta y pruebas de calidad, donde se busca que los procesos sean consistentes y las desviaciones sean mínimas o estén controladas.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Marco Conceptual: Definiciones Clave
> 
> Para abordar estos temas desde cero, es necesario clarificar los siguientes términos:
> 
> - **Rango:** Es la diferencia entre el valor máximo y el valor mínimo de un conjunto de datos (R = V_{max} - V_{min}). Indica la amplitud total de la muestra.
> - **Media (****\bar{x}****):** El promedio aritmético de los valores. Es el punto de referencia central sobre el cual se calculan las desviaciones.
> - **Valor Absoluto (****|x|****):** Función que convierte cualquier número en positivo. Es esencial en la desviación media para evitar que las diferencias positivas y negativas se anulen entre sí.
> - **Varianza (****S^2****):** Es el promedio de los cuadrados de las desviaciones respecto a la media. Es el paso previo al cálculo de la desviación típica.
> - **Desviación Típica o Estándar (****\sigma****):** Es la raíz cuadrada de la varianza. Proporciona una medida de dispersión en las mismas unidades que los datos originales.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Desarrollo del Tema
> 
> ### 4.1 Desviación Media (DM)
> 
> La desviación media mide la distancia promedio de cada dato respecto a la media aritmética, utilizando valores absolutos.
> 
> #### Procedimiento de Cálculo (Datos Individuales):
> 
> 1. **Ordenar los datos:** Aunque no es estrictamente obligatorio para la fórmula, se recomienda para facilitar el cálculo del rango y mantener el orden.
> 2. **Calcular el Rango:** Identificar los extremos de la muestra.
> 3. **Calcular la Media (****\bar{x}****):** Sumar todos los valores y dividir por n (cantidad de elementos).
> 4. **Calcular la diferencia:** Restar la media a cada valor (x_i - \bar{x}).
>     - _Nota de validación:_ La suma de todas estas diferencias (sin valor absoluto) **siempre debe ser cero**.
> 5. **Aplicar Valor Absoluto:** Convertir todos los resultados del paso anterior en positivos (|x_i - \bar{x}|).
> 6. **Sumar y dividir:** Sumar todos los valores absolutos y dividir el resultado por n.
> 
> #### Desviación Media con Intervalos de Clase:
> 
> Cuando los datos están agrupados, se utiliza la **Marca de Clase** (X_i).
> 
> - Se calcula la diferencia entre la marca de clase y la media.
> - Se aplica el valor absoluto.
> - **Crucial:** Se debe multiplicar cada valor absoluto por la **frecuencia** (f_i) de ese intervalo antes de realizar la suma total y dividir por N (total de la población).
> 
> --------------------------------------------------------------------------------
> 
> ### 4.2 Desviación Típica o Estándar
> 
> Es un análisis más refinado que la desviación media. Al elevar las diferencias al cuadrado, se penalizan más las desviaciones grandes, lo que permite un estudio más preciso.
> 
> #### Procedimiento de Cálculo:
> 
> 1. **Calcular la Media.**
> 2. **Diferencia al cuadrado:** Restar la media a cada valor y elevar el resultado al cuadrado: (x_i - \bar{x})^2. Esto garantiza resultados positivos.
> 3. **Varianza:** Sumar esos cuadrados y dividir por n (o n-1 según el tipo de muestra).
> 4. **Raíz Cuadrada:** Aplicar la raíz cuadrada al resultado de la varianza para obtener la desviación típica.
> 
> --------------------------------------------------------------------------------
> 
> ### 4.3 Tipificación de Variables (Puntaje Z)
> 
> La tipificación consiste en transformar una variable para que tenga una escala estándar. Esto permite comparar datos de diferentes poblaciones o con diferentes unidades.
> 
> **Fórmula de Tipificación (****Z****):** Z = \frac{x_i - \bar{x}}{\sigma}
> 
> Donde:
> 
> - x_i es el valor original.
> - \bar{x} es la media.
> - \sigma es la desviación típica.
> 
> **Características de la variable tipificada:**
> 
> - Permite un cambio de coordenadas/escala.
> - Los valores resultantes suelen oscilar entre **-3 y 3**.
> - Introduce valores negativos y positivos centrados en el cero, facilitando la construcción de gráficas de distribución.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Aplicación en Excel
> 
> El uso de software de hojas de cálculo simplifica estos procesos mediante funciones específicas:
> 
> |   |   |
> |---|---|
> |Concepto|Función de Excel|
> |**Media**|`=PROMEDIO(rango)`|
> |**Desviación Media**|`=DESVPROM(rango)`|
> |**Desviación Típica (Población)**|`=DESVEST.P(rango)`|
> |**Valor Absoluto**|`=ABS(valor)`|
> |**Raíz Cuadrada**|`=RAIZ(valor)`|
> |**Contar elementos (****n****)**|`=CONTAR(rango)`|
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Ejemplos Prácticos
> 
> ### Caso 1: Cálculo de Desviación Media (Datos: 8 elementos)
> 
> Supongamos una media calculada de 9,5.
> 
> 1. **Restas:** (Valor 1 - 9,5), (Valor 2 - 9,5)... Algunos darán negativo (ej. -2,5).
> 2. **Comprobación:** La suma de las restas debe dar 0.
> 3. **Absoluto:** -2,5 se convierte en 2,5.
> 4. **Suma de absolutos:** Supongamos que la suma es 34.
> 5. **Resultado:** 34 / 8 = 4,25 (Desviación Media).
> 
> ### Caso 2: Tipificación
> 
> Si un valor es 12, la media es 9 y la desviación típica es 1,5:
> 
> - Z = (12 - 9) / 1,5
> - Z = 3 / 1,5 = 2 Este "2" es la nueva coordenada del valor en una escala estandarizada.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Errores Comunes y Confusiones
> 
> 1. **Olvidar el valor absoluto en la DM:** Si no se aplica, la suma de las desviaciones será cero y no se podrá calcular la dispersión.
> 2. **Confundir Varianza con Desviación Típica:** La varianza es el valor previo a la raíz cuadrada. Si no se aplica la raíz, la medida está en "unidades al cuadrado", lo cual no sirve para la tipificación.
> 3. **Suma en Intervalos:** Un error frecuente es sumar las restas de las marcas de clase sin multiplicarlas por su frecuencia respectiva. Si hay 18 elementos en un intervalo, esa desviación debe contarse 18 veces.
> 4. **Uso de Datos Desordenados:** Aunque Excel lo resuelve, trabajar manualmente con datos desordenados aumenta la probabilidad de omitir valores o calcular mal el rango.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Síntesis y Conclusiones
> 
> - La **Desviación Media** es una medida de dispersión lineal y simple basada en valores absolutos.
> - La **Desviación Típica** es más robusta y es la base para la mayoría de los cálculos estadísticos avanzados.
> - La **Tipificación** es un proceso de "cambio de escala" que permite trabajar en un rango controlado (generalmente de -3 a 3) sin perder la distribución original de los datos. Esto es fundamental para graficar y comparar variables de distinta naturaleza.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia principal entre el rango y la desviación media?
> 2. ¿Por qué la suma de las diferencias respecto a la media siempre da cero si no se usa valor absoluto?
> 3. ¿Qué función de Excel se utiliza para calcular la desviación promedio de forma directa?
> 
> ### Nivel Intermedio
> 
> 4. En una tabla de intervalos, ¿por qué es necesario multiplicar la desviación por la frecuencia?
> 5. Explique el proceso para obtener la desviación típica a partir de la varianza.
> 6. ¿Qué sucede con el signo de un valor menor a la media cuando se calcula su desviación típica?
> 
> ### Nivel Avanzado
> 
> 7. ¿Cuál es el objetivo primordial de tipificar una variable (convertirla a valor Z)?
> 8. Si un valor tipificado da como resultado 4, ¿qué se puede inferir sobre ese dato considerando el rango estándar de -3 a 3?
> 9. Describa cómo la desviación típica y la media actúan en conjunto para realizar un cambio de coordenadas en un conjunto de datos.
> 
> --------------------------------------------------------------------------------
> 
> ## 10. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de la sesión del **9 de octubre**, se destacan los siguientes puntos:
> 
> - **Próxima Clase:** El **jueves de la semana siguiente**. En esta sesión se retomará con mayor profundidad el tema de tipificación de variables y su representación gráfica.
> - **Aviso de Suspensión:** Se informa explícitamente que **mañana no hay clase**.
> - **Indicación del Profesor:** Para la próxima clase, se espera que los estudiantes puedan realizar tres pasos fundamentales sobre cualquier serie de datos:
>     1. Cálculo de la media.
>     2. Cálculo de la desviación típica.
>     3. Tipificación de la variable.
> - **Recomendación Metodológica:** El profesor insiste en la importancia de **ordenar los datos siempre**, ya que esto facilita todos los cálculos posteriores y previene errores, aunque la fórmula de Excel no lo requiera estrictamente.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 7 - Estadística y probabilidad para el desarrollo de software" src="https://www.youtube.com/embed/CKTbgM1Agc4?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/11fLmwSXtzJ7BeyI51LNmNQanu2KCp6lW/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1fgDEsYi8_j7RO1ZU3ds9GYFI_r6gRWYY/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>