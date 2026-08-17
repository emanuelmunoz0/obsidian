---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/4-estadistica-y-probabilidad-para-el-desarrollo-de-software/clase-2-jueves-21-de-agosto-de-2025-21-08-25-estadistica-y-probabilidad-para-el-desarrollo-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio: Estadística y Probabilidad para el Desarrollo de Software
> 
> Este documento constituye un material de estudio integral basado en el análisis de datos agrupados, la construcción de tablas de frecuencia y su representación gráfica. Está diseñado para proporcionar una comprensión profunda de cómo organizar y visualizar información estadística para la toma de decisiones en el desarrollo de software.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> En el análisis estadístico, el procesamiento de grandes volúmenes de datos requiere métodos de organización que faciliten su interpretación. Una de las herramientas más potentes es la agrupación de datos en **intervalos de clase**. Este método permite pasar de una "población" de datos dispersos a una estructura organizada que resalta tendencias, crecimientos y comportamientos predominantes.
> 
> El objetivo central de esta unidad es dominar la construcción de distribuciones de frecuencia y sus representaciones gráficas (histogramas, polígonos de frecuencia y ojivas), herramientas fundamentales para el análisis de rendimiento de sistemas, estudios de usuarios o control de calidad en software.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual: Definiciones y Términos Fundamentales
> 
> Para trabajar con datos agrupados, es esencial comprender los elementos que componen una tabla de frecuencias desde cero:
> 
> ### 2.1. Intervalos de Clase
> 
> Son los rangos en los que se dividen los datos. Cada intervalo tiene un **límite inferior** y un **límite superior**.
> 
> - **Propósito:** Agrupar datos similares para simplificar el análisis.
> 
> ### 2.2. Límites Reales (LRI y LRS)
> 
> A diferencia de los límites nominales, los límites reales aseguran que no haya "huecos" entre las clases. Permiten que los intervalos se conecten físicamente.
> 
> - **Límite Real Inferior (LRI):** El punto de inicio exacto de un intervalo.
> - **Límite Real Superior (LRS):** El punto final exacto de un intervalo.
> - **Cálculo:** Se obtiene buscando el punto medio entre el límite superior de una clase y el inferior de la siguiente (semisuma). Por ejemplo, si una clase termina en 59.99 y la siguiente empieza en 60, el límite real es `(59.99 + 60) / 2 = 59.995`.
> 
> ### 2.3. Marca de Clase (MC)
> 
> Es el punto medio de cada intervalo. Representa a todos los datos contenidos en esa clase para cálculos posteriores (como la media).
> 
> - **Fórmula:** `(Límite Inferior + Límite Superior) / 2`.
> 
> ### 2.4. Frecuencia (f)
> 
> Indica la cantidad de datos que caen dentro de un intervalo específico. Por ejemplo, si en el intervalo [118-126] la frecuencia es 3, significa que hay 3 elementos cuyos valores están en ese rango.
> 
> ### 2.5. Anchura de Clase (A)
> 
> Es el tamaño del intervalo. Se calcula restando el Límite Real Superior menos el Límite Real Inferior de una misma clase.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: Procesamiento de la Información
> 
> ### 3.1. Construcción de la Tabla de Frecuencias
> 
> El proceso de organización sigue un orden lógico:
> 
> 1. **Definir los intervalos:** Establecer los rangos de interés.
> 2. **Calcular Límites Reales:** Para evitar la discontinuidad en los gráficos.
> 3. **Determinar Marcas de Clase:** Para tener un representante numérico de cada grupo.
> 4. **Asignar Frecuencias:** Contar cuántos elementos pertenecen a cada intervalo.
> 
> ### 3.2. Frecuencia Relativa y Porcentual
> 
> La **Frecuencia Relativa** expresa qué parte del total representa cada intervalo.
> 
> - **Fórmula:** `Frecuencia del intervalo / Total de la muestra (n)`.
> - **Importancia:** La suma de todas las frecuencias relativas debe ser igual a 1 (o 100% si se expresa en porcentaje). Esto permite ver la importancia de cada clase respecto al todo.
> 
> ### 3.3. Frecuencias Acumuladas (Ojiva)
> 
> La frecuencia acumulada indica cuántos datos son "inferiores a" un límite real determinado.
> 
> - Se construye sumando progresivamente las frecuencias de cada clase.
> - Permite observar el crecimiento o evolución de la muestra.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Representación Gráfica
> 
> El análisis visual es clave para detectar comportamientos de la población sin necesidad de leer tablas extensas.
> 
> ### 4.1. El Histograma
> 
> Es un gráfico de barras donde las bases representan los intervalos (usando límites reales) y las alturas representan la frecuencia.
> 
> - **Característica clave:** Las barras deben estar pegadas entre sí (gracias a los límites reales) para demostrar continuidad.
> 
> ### 4.2. El Polígono de Frecuencias
> 
> Es un gráfico de líneas que une los puntos medios (marcas de clase) de cada intervalo.
> 
> - **Preparación para el gráfico:** Para que el polígono "nazca" y "muera" en el eje horizontal (frecuencia cero), se debe agregar un intervalo imaginario antes del primero y otro después del último, manteniendo la misma anchura de clase pero con frecuencia 0.
> 
> ### 4.3. La Ojiva (Gráfico de Frecuencia Acumulada)
> 
> Representa la acumulación de datos.
> 
> - **Forma:** Siempre es ascendente (nunca baja).
> - **Eje X:** Se utilizan los Límites Reales Inferiores.
> - **Eje Y:** Se utiliza la frecuencia acumulada.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Ejemplos Prácticos Basados en Clase
> 
> ### Caso 1: Cálculo de Límites Reales y Marcas de Clase
> 
> Si tenemos los intervalos [50 - 59.99] y [60 - 69.99]:
> 
> 1. **Diferencia:** `60 - 59.99 = 0.01`.
> 2. **Ajuste:** `0.01 / 2 = 0.005`.
> 3. **LRS (Clase 1):** `59.99 + 0.005 = 59.995`.
> 4. **LRI (Clase 2):** `60 - 0.005 = 59.995`.
> 5. **Marca de Clase (Clase 1):** `(50 + 59.99) / 2 = 54.995`.
> 
> ### Caso 2: Preparación para Polígono de Frecuencia
> 
> Si la anchura es 10 y el primer intervalo empieza en 54.995:
> 
> - Se añade un punto en `44.995` con **frecuencia 0**.
> - Se añade un punto al final (después del último límite) con **frecuencia 0**.
> - Esto asegura que el gráfico sea una figura cerrada.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores Comunes y Aclaraciones
> 
> - **Redondeo:** No se deben redondear los valores de los límites reales (ej. usar 59.995 en lugar de 60), ya que se pierde la precisión necesaria para conectar los intervalos.
> - **Frecuencia vs. Datos Discriminados:** En una tabla de intervalos, sabemos cuántos sujetos hay (frecuencia), pero perdemos el valor exacto de cada uno. Solo sabemos que están "dentro del rango".
> - **Gráfico de Ojiva Descendente:** Si una ojiva baja en algún punto, el cálculo de la frecuencia acumulada es incorrecto; por definición, siempre debe sumar o mantenerse igual.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Síntesis y Conclusiones
> 
> - Los **intervalos** son herramientas para organizar poblaciones grandes y mejorar la atención en los datos relevantes.
> - Los **límites reales** son el "pegamento" que une las clases para una representación gráfica continua.
> - La **frecuencia acumulada** es fundamental para entender el crecimiento de la muestra.
> - El uso de software como **Excel o LibreOffice** facilita el cálculo, pero requiere una configuración manual precisa (especialmente para añadir las frecuencias cero en los extremos de los gráficos).
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> A partir de las instrucciones del docente, se establecen los siguientes puntos clave:
> 
> |   |   |   |
> |---|---|---|
> |Fecha|Tipo de Evento|Descripción Detallada|
> |**Viernes (Mañana)**|Clase de Modelado de Software|Horario: 18:45 a 20:00 hs. Se confirmó que será en modalidad **virtual** (no presencial).|
> |**Próxima Semana**|Clase de Estadística|Tema: **Población**. Se comparará el trabajo con poblaciones grandes frente al trabajo con intervalos para ver ventajas de organización.|
> |**Próxima Semana**|Entrega/Revisión|Se deben traer resueltos los ejercicios de construcción de gráficos (Histograma y Polígono) y tablas de frecuencia acumulada iniciados en la Clase 2.|
> |**Próximamente**|Evaluación (Aviso)|Las evaluaciones serán presenciales, en hoja, pero se permite el uso de **Excel** para los cálculos. Se evaluarán temas como media, mediana y moda (próximos a ver).|
> 
> **Recordatorio:** El docente enfatiza la importancia de no faltar a las primeras clases, ya que los conceptos de intervalos son la base para todo el cuatrimestre.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia entre un límite nominal y un límite real?
> 2. ¿Cómo se calcula la marca de clase y qué representa?
> 
> ### Nivel Intermedio
> 
> 1. ¿Por qué es necesario agregar frecuencias de valor cero al inicio y al final de una tabla para construir un polígono de frecuencias?
> 2. Si el total de una muestra es 100 y un intervalo tiene una frecuencia de 15, ¿cuál es su frecuencia relativa y qué porcentaje representa?
> 
> ### Nivel Avanzado
> 
> 1. Explique la relación entre la pendiente de una ojiva y la concentración de datos en un intervalo específico.
> 2. Ante una muestra de 2,500 datos, ¿cuáles son las ventajas y desventajas de trabajar con intervalos de clase versus trabajar con la población completa?

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 2 - Estadística y probabilidad para el desarrollo de software" src="https://www.youtube.com/embed/BQ_pePAIGto?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1eIvFX4TsIIc1VcGYtPBQQD2_ifDXFb4t/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1mgKBjeOPNnOrYzN51qpnbHSMXWaYBc0L/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>