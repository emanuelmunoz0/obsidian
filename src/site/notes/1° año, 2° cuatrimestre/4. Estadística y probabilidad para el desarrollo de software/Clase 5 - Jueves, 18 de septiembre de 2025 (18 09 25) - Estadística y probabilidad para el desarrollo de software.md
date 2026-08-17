---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/4-estadistica-y-probabilidad-para-el-desarrollo-de-software/clase-5-jueves-18-de-septiembre-de-2025-18-09-25-estadistica-y-probabilidad-para-el-desarrollo-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio: Medidas de Tendencia Central y Dispersión en Estadística
> 
> Este documento constituye un material de estudio exhaustivo basado en la sesión académica del 18 de septiembre sobre Estadística y Probabilidad aplicada al desarrollo de software. El contenido profundiza en el cálculo de la mediana mediante interpolación en intervalos de clase y proporciona una introducción técnica a la desviación media.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> En el análisis estadístico, el manejo de grandes volúmenes de datos requiere su agrupación en **intervalos de clase**. A diferencia de los datos aislados, los datos agrupados demandan métodos matemáticos específicos para hallar valores representativos. Esta guía se centra en la transición de conceptos básicos a la aplicación de fórmulas de interpolación para determinar la mediana y el estudio de la variabilidad mediante la desviación media.
> 
> ### Contexto y Relevancia
> 
> El estudio de estas medidas permite comprender la distribución de una muestra o población. Mientras que la media aritmética proporciona un promedio ponderado, la mediana identifica el centro exacto de la distribución, siendo menos sensible a valores extremos. Estas herramientas son fundamentales para la creación de gráficas y la toma de decisiones basada en datos en el ámbito del desarrollo de software.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual: Definiciones Clave
> 
> Para abordar los temas avanzados, es imperativo comprender los siguientes términos fundamentales:
> 
> - **Frecuencia (****f****):** Cantidad de veces que se repite un valor o cae dentro de un intervalo.
> - **Marca de Clase:** El punto medio de un intervalo de clase.
> - **Límites Reales (Inferior y Superior):** Los puntos exactos que delimitan un intervalo, evitando brechas entre ellos (ej. 144.5 a 149.5).
> - **Mediana (****Me****):** Parámetro que indica el centro de la muestra, dividiéndola en dos partes iguales (50% por encima y 50% por debajo).
> - **Media (****\bar{x}****):** Promedio de los datos. En intervalos, se sitúa cerca de los rangos con mayor población o frecuencia.
> - **Interpolación:** Método matemático para estimar un valor intermedio dentro de un intervalo de clase cuando se conoce la posición de la mediana pero no su valor exacto.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: La Mediana en Datos Agrupados
> 
> Cuando se trabaja con intervalos, la mediana no se encuentra simplemente seleccionando un número, sino mediante un proceso de **interpolación lineal**.
> 
> ### 3.1. Procedimiento de Cálculo (Paso a Paso)
> 
> 1. **Identificar el Total de la Muestra (****N****):** Sumar todas las frecuencias.
> 2. **Determinar la Posición de la Mediana:** Dividir N por 2 (N/2).
>     - _Nota:_ Si N es impar (ej. 41), se puede redondear o usar el valor exacto (20.5), ya que la diferencia en el resultado final es mínima.
> 3. **Localizar el Intervalo de la Mediana:** Sumar las frecuencias de forma acumulada desde el primer intervalo hasta llegar o sobrepasar el valor de N/2.
> 4. **Aplicar el Concepto de "Préstamo":** Si la suma de las frecuencias anteriores no alcanza a N/2, se identifica cuánto falta y se le "pide" esa cantidad al intervalo siguiente (el intervalo donde reside la mediana).
> 
> ### 3.2. Fórmulas de Interpolación
> 
> El documento identifica dos variantes de la fórmula, siendo la versión reducida la más práctica para el uso en herramientas como Excel:
> 
> **Fórmula Reducida:** Me = LRI + \left( \frac{\text{Cantidad faltante para llegar a } N/2}{\text{Frecuencia del intervalo actual}} \right) \times \text{Amplitud del intervalo}
> 
> Donde:
> 
> - **LRI:** Límite Real Inferior del intervalo donde se encuentra la mediana.
> - **Amplitud:** Diferencia entre el Límite Real Superior y el Límite Real Inferior.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Relación entre Conceptos y Parámetros
> 
> Es crucial distinguir cómo interactúan la media, la mediana y la moda:
> 
> - **Proximidad:** Idealmente, en una distribución simétrica, la media y la mediana deberían coincidir o estar muy próximas.
> - **Sensibilidad a la Población:** La media siempre se desplazará hacia el intervalo con mayor frecuencia o población (ponderación), mientras que la mediana se mantiene estrictamente en el centro geométrico de los datos.
> - **Utilidad Gráfica:** La mediana sirve como el parámetro central para construir y entender la simetría de las gráficas estadísticas.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Ejemplos Prácticos
> 
> ### Caso 1: Muestra Par (N=40)
> 
> Se tiene una tabla con frecuencias acumuladas. El objetivo es hallar la mediana.
> 
> 1. **Posición:** 40 / 2 = 20.
> 2. **Acumulación:** La suma de las primeras tres frecuencias da 17 (3 + 5 + 9 = 17).
> 3. **Diferencia:** Faltan 3 para llegar a 20.
> 4. **Intervalo Siguiente:** El siguiente intervalo tiene una frecuencia de 12 y un LRI de 144.5.
> 5. **Cálculo:**
>     - Proporción: 3 / 12 = 0.25.
>     - Amplitud del intervalo: 149.5 - 144.5 = 5.
>     - Ajuste: 0.25 \times 5 = 1.25.
>     - **Resultado Final:** 144.5 + 1.25 = 145.75 (o valores cercanos según la precisión del Excel, ej. 146.35 en el caso discutido en clase).
> 
> ### Caso 2: Muestra Impar (N=41)
> 
> 6. **Posición:** 41 / 2 = 20.5 (se puede tomar 20 para facilitar el cálculo).
> 7. **Acumulación:** Se llega a una frecuencia de 11 antes del intervalo crítico.
> 8. **Diferencia:** Se necesitan 9 adicionales para llegar a 20.
> 9. **Cálculo:** Se toma el LRI del intervalo actual, se suma la proporción de 9 sobre la frecuencia del intervalo, multiplicada por la diferencia de los límites reales.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Introducción a la Desviación Media
> 
> La **Desviación Media** mide cuánto se alejan, en promedio, los valores de una población respecto a su media aritmética.
> 
> ### Proceso de Cálculo para Poblaciones (Datos No Agrupados)
> 
> 10. **Calcular la Media (****\bar{x}****):** Promedio simple de todos los valores.
> 11. **Calcular Desviaciones:** Restar la media a cada valor individual (x - \bar{x}).
>     - _Verificación:_ La suma de todas las desviaciones (con sus signos) debe ser **cero**.
> 12. **Aplicar Valor Absoluto (Función ABS en Excel):** Convertir todos los resultados negativos en positivos.
> 13. **Promediar:** Sumar los valores absolutos y dividir por el total de la población (N).
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Errores Comunes y Aclaraciones
> 
> - **Confusión de Límites:** No utilizar los límites reales (con decimales .5) puede sesgar el resultado de la interpolación.
> - **Signos en Desviación:** Un error frecuente es sumar las desviaciones sin aplicar el valor absoluto, lo cual resultará siempre en cero y no proporcionará información sobre la dispersión.
> - **Uso de Fórmulas en Excel:** Para poblaciones directas (datos no agrupados), es más eficiente usar las funciones integradas de Excel en lugar de la fórmula manual de interpolación.
> - **Redondeo en Impares:** En muestras impares, redondear la posición N/2 no afecta significativamente la validez académica del ejercicio en este nivel.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> Basado en la comunicación directa durante la sesión, se establecen los siguientes puntos:
> 
> |   |   |   |
> |---|---|---|
> |Fecha|Evento / Actividad|Descripción Detallada|
> |**02 de octubre**|**Primer Examen Parcial**|Evaluación bajo modalidad "Blitz". Duración estimada: 15 minutos.|
> |**25 de septiembre**|Clase de Desarrollo|Se profundizará en Desviación Media y otros parámetros de dispersión.|
> |**30 de noviembre**|Fin de cursada|Fecha estimada de finalización del periodo lectivo.|
> 
> **Recordatorios Académicos:**
> 
> - **Metodología del Parcial:** Los cálculos se realizan en Excel para mayor agilidad, pero los resultados finales deben entregarse de forma manuscrita (a mano).
> - **Material de Estudio:** Es vital dominar el cálculo de la **media**, ya que es el parámetro de referencia para todos los temas subsiguientes (como la desviación media).
> - **Uso de Fórmulas:** El profesor permite tener las fórmulas disponibles durante los ejercicios, priorizando la comprensión del proceso sobre la memorización.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia principal entre la media y la mediana en términos de qué representan?
> 2. ¿Por qué la suma de las desviaciones respecto a la media (x - \bar{x}) siempre da cero?
> 
> ### Nivel Intermedio
> 
> 1. En una muestra de 60 datos agrupados, si las frecuencias acumuladas hasta el intervalo 2 suman 25, ¿cuántas unidades debes "pedirle" al intervalo 3 para hallar la mediana?
> 2. ¿Qué función de Excel se utiliza para convertir las desviaciones negativas en positivas al calcular la desviación media?
> 
> ### Nivel Avanzado
> 
> 1. Explique por qué en una distribución con una frecuencia muy alta en los valores iniciales, la media tiende a alejarse del centro geométrico mientras que la mediana permanece en él.
> 2. Realice el cálculo de la mediana para un intervalo con LRI = 100, LRS = 110, frecuencia del intervalo = 10, y una necesidad de "préstamo" de 4 unidades. (Respuesta esperada: 100 + (4/10) \times 10 = 104).

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 5 - Estadística y probabilidad para el desarrollo de software" src="https://www.youtube.com/embed/slsvfHDOybA?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1gX1OWmff6_X2o0402KJklQX3O9kssHag/preview" width="640" height="480"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1PihhJ4a8zoLFcATTmkEWj-_7ENON4W-l/preview" width="640" height="480"></iframe>