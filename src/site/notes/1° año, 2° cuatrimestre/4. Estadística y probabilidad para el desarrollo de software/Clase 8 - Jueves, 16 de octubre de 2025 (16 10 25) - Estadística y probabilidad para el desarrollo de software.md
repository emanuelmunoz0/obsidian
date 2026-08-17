---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/4-estadistica-y-probabilidad-para-el-desarrollo-de-software/clase-8-jueves-16-de-octubre-de-2025-16-10-25-estadistica-y-probabilidad-para-el-desarrollo-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio: Tipificación de Variables y Representación Gráfica en Estadística
> 
> Este documento constituye un material de estudio integral sobre el proceso de tipificación de variables, el cálculo de medidas de tendencia central y dispersión en datos agrupados, y la construcción técnica de gráficos estadísticos. El contenido se basa en las directrices académicas para el desarrollo de software, enfocándose en la precisión del cálculo manual y la interpretación de la distribución de datos.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> La estadística descriptiva permite resumir y organizar datos para facilitar su interpretación. En el ámbito del desarrollo de software y análisis de datos, la **tipificación de variables** es un proceso fundamental que permite transformar datos originales (con sus propias unidades y escalas) a una escala estandarizada. Este proceso es el paso previo necesario para el estudio de distribuciones normales y la aplicación de la Campana de Gauss.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual
> 
> Para comprender la tipificación, es esencial dominar los siguientes conceptos fundamentales:
> 
> ### Definiciones Clave
> 
> - **Marca de Clase (MC):** Es el valor representativo de un intervalo de datos. En los cálculos de datos agrupados, actúa como el valor "X" que representa a todo el grupo.
> - **Media (****\mu** **o** **\bar{x}****):** El promedio aritmético. En datos agrupados, se obtiene mediante la suma de los productos de cada marca de clase por su frecuencia, dividida por el total de datos (N).
> - **Desviación Típica (****\sigma** **o** **s****):** Una medida que indica qué tan dispersos están los datos con respecto a la media.
> - **Tipificación (Z):** Proceso de restar la media a un valor y dividir el resultado por la desviación típica. Permite saber a cuántas desviaciones estándar se encuentra un dato del centro de la distribución.
> - **Frecuencia Relativa:** La proporción que representa cada frecuencia sobre el total (f/N). La suma de todas las frecuencias relativas debe ser siempre igual a 1.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: El Proceso de Tipificación
> 
> ### A. Protocolo de Construcción de Tablas y Gráficos
> 
> Antes de iniciar los cálculos, existe un protocolo técnico para garantizar que los gráficos (como el polígono de frecuencias) sean representativos:
> 
> 1. **Cierre del Eje Horizontal:** El gráfico debe comenzar y terminar en el eje horizontal con una **frecuencia de cero**.
> 2. **Extensión de Marcas de Clase:** Se debe identificar el intervalo entre marcas de clase. Se resta un intervalo a la primera marca de clase y se suma un intervalo a la última.
>     - _Ejemplo:_ Si el intervalo es de 4 y la primera marca es 70, se agrega una marca previa de 66 con frecuencia 0.
> 
> ### B. Cálculo de la Media para Datos Agrupados
> 
> No se debe utilizar la función promedio simple de herramientas como Excel sobre las marcas de clase de forma aislada, ya que cada marca de clase tiene una carga (frecuencia) distinta.
> 
> - **Fórmula:** \mu = \frac{\sum (MC \cdot f)}{N}
> - **Procedimiento:** Se multiplica cada marca de clase por su frecuencia absoluta, se suman todos los resultados y se divide por el número total de observaciones.
> 
> ### C. Cálculo de la Desviación Típica Manual
> 
> En este contexto académico, se prioriza el cálculo mediante la fórmula de población adaptada a marcas de clase:
> 
> 1. A cada marca de clase se le resta la media: (MC - \mu).
> 2. El resultado se eleva al cuadrado: (MC - \mu)^2.
> 3. Ese valor se multiplica por su frecuencia respectiva: f \cdot (MC - \mu)^2.
> 4. Se suman todos estos valores y se dividen por N (esto es la varianza).
> 5. Se calcula la raíz cuadrada del resultado final para obtener la **desviación típica (****\sigma****)**.
> 
> ### D. Aplicación de la Variable Tipificada (Z)
> 
> La fórmula para tipificar cada valor de la tabla es: Z = \frac{MC - \mu}{\sigma} Este valor (Z) sitúa los datos en una escala que usualmente oscila entre -3 y 3, facilitando la creación de una curva de distribución simétrica.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Construcción del Gráfico (Polígono de Frecuencias)
> 
> Para graficar una variable tipificada, se utilizan los siguientes ejes:
> 
> - **Eje Horizontal (X):** Valores de **Z** (la variable tipificada).
> - **Eje Vertical (Y):** Valores de la **Frecuencia Relativa**.
> 
> El resultado esperado es una representación que se asemeje a una campana ideal, donde el punto más alto corresponde al centro de los datos y los extremos descienden hacia la frecuencia cero.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Ejemplos Prácticos y Casos de Estudio
> 
> ### Caso 1: Ajuste de Marcas de Clase
> 
> Si tenemos datos desde 70 hasta 126 con un intervalo de 4:
> 
> - Marca anterior: 70 - 4 = 66 (Frecuencia = 0).
> - Marca posterior: 126 + 4 = 130 (Frecuencia = 0).
> - Esto asegura que el polígono de frecuencias "toque" el suelo en ambos extremos.
> 
> ### Caso 2: Error en el cálculo de la Media
> 
> - **Incorrecto:** Sumar las marcas de clase y dividir por la cantidad de filas.
> - **Correcto:** Si MC = 70 tiene frecuencia 10, y MC = 74 tiene frecuencia 20, la media debe considerar que el 74 pesa el doble que el 70 en la distribución.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores Comunes y Confusiones
> 
> |   |   |
> |---|---|
> |Error|Aclaración Correcta|
> |Usar fórmulas automáticas de Excel (`PROMEDIO`, `DESVEST`)|Estas funciones no consideran la frecuencia de las marcas de clase. Se debe usar el cálculo manual según las fórmulas de estadística para datos agrupados.|
> |Olvidar las frecuencias cero|Si no se incluyen marcas de clase con frecuencia cero al inicio y al final, el gráfico quedará "abierto" y no cumplirá el protocolo de construcción.|
> |Confundir resta con división|En la fórmula de Z (Z = \frac{X - \mu}{\sigma}), el numerador es una resta. Un error en este signo altera toda la distribución.|
> |Escala del gráfico|Tipificar permite que los datos estén en una escala comparable. Si el gráfico no se ve simétrico, puede ser por un error en el cálculo de la desviación típica o la media.|
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Síntesis y Conclusiones
> 
> - La **tipificación** permite llevar cualquier conjunto de datos a una escala común (Z), facilitando su análisis.
> - La **precisión en los cálculos** de la media y la desviación típica es crítica; un error en la media se arrastra a la desviación típica, y ambos afectan el cálculo de Z.
> - La **frecuencia relativa** es esencial para el eje vertical si se busca una comparación estandarizada.
> - El objetivo final de estos procedimientos es la transición hacia el estudio de la **Campana de Gauss**, que representa una distribución ideal de probabilidades.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Qué representa la marca de clase en una tabla de frecuencias?
> 2. ¿Por qué es necesario agregar frecuencias de cero al inicio y al final de una tabla antes de graficar?
> 3. ¿Cuál es el valor de la suma de todas las frecuencias relativas?
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia entre calcular el promedio simple de las marcas de clase y calcular la media mediante la fórmula \frac{\sum (MC \cdot f)}{N}.
> 5. Si un valor de Z es negativo, ¿qué significa respecto a la posición de ese dato con respecto a la media?
> 
> ### Nivel Avanzado
> 
> 6. Describa paso a paso el procedimiento para calcular la desviación típica en datos agrupados sin utilizar funciones automáticas de software estadístico.
> 7. ¿Cómo afecta una desviación típica muy alta a la forma del polígono de frecuencias tipificado?
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Fechas Importantes y Avisos Académicos
> 
> Basado en las comunicaciones del profesor durante la sesión, se establecen los siguientes puntos relevantes para la organización de la materia:
> 
> - **Segundo Parcial:**
>     - **Fecha estimada:** Mediados de noviembre (posiblemente la tercera semana).
>     - **Límite administrativo:** Todas las evaluaciones deben concluir antes del **30 de noviembre**.
>     - **Observación:** La fecha exacta es flexible y se acordará con los alumnos para no interferir con otras materias, siempre que se respete el límite del 30 de noviembre.
> - **Contenidos del Parcial:** No todos los temas dados en clase serán evaluados. El profesor indicará cuáles son "temas de complemento" que, aunque se dictan para completar la planificación, no formarán parte del examen.
> - **Próxima Clase:**
>     - **Tema:** La Campana de Gauss (Curva de Gauss).
>     - **Requerimiento:** El profesor enviará una hoja/archivo que los alumnos deben **imprimir** para trabajar en clase, ya que resulta más cómodo el formato físico para este tema específico.
> 
> **Recordatorio Académico:** Es fundamental dominar el cálculo de la media y la desviación típica manualmente, ya que es la base para el trabajo práctico actual y los temas venideros.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 8 - Estadística y probabilidad para el desarrollo de software" src="https://www.youtube.com/embed/bbeQ-ZRsSCo?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1vKG_NHz1JxZvUmLi_94Rx2xGQoMuo20f/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1rgrxEPFLOX-5SrV1-2scoj0hRpFzoeIo/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>