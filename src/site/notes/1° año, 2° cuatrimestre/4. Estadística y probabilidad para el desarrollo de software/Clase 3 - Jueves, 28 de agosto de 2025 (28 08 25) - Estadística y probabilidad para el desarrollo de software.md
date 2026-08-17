---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/4-estadistica-y-probabilidad-para-el-desarrollo-de-software/clase-3-jueves-28-de-agosto-de-2025-28-08-25-estadistica-y-probabilidad-para-el-desarrollo-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía Universitaria: Estadística y Probabilidad - Organización de Datos y Distribución de Frecuencias
> 
> Esta guía constituye un material de estudio integral sobre el tratamiento de datos estadísticos, centrándose en la transición de datos brutos a estructuras organizadas mediante intervalos y su posterior representación gráfica. El contenido se basa en las metodologías aplicadas en el desarrollo de software y análisis de poblaciones.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> La estadística es una disciplina fundamental que permite transformar grandes volúmenes de datos dispersos en información comprensible y accionable. En el contexto del desarrollo de software y el análisis de datos, la capacidad de agrupar información en intervalos es crucial para identificar patrones que no son visibles en una lista desordenada de números. Este proceso facilita el estudio de poblaciones extensas y permite la creación de herramientas visuales para la toma de decisiones.
> 
> ### Importancia y Relevancia
> 
> Organizar datos no es solo un paso administrativo, sino una necesidad técnica. Trabajar con "población" (datos individuales) puede ser ineficiente cuando se manejan miles de registros. El uso de tablas de frecuencia e intervalos permite:
> 
> - Simplificar la complejidad de los datos.
> - Calcular parámetros de tendencia central (media, mediana, moda) con mayor agilidad.
> - Visualizar la distribución de los datos a través de histogramas y polígonos de frecuencia.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual y Definiciones Clave
> 
> Para comprender la organización de datos desde cero, es necesario dominar los siguientes conceptos fundamentales:
> 
> - **Población:** El conjunto total de datos o individuos que se desean estudiar.
> - **Rango (****R****):** Es la diferencia entre el valor máximo y el valor mínimo de un conjunto de datos ordenados. Su fórmula es: R = Valor Máximo - Valor Mínimo.
> - **Intervalo:** Una subdivisión del rango total que agrupa valores. Permite clasificar los datos en "clases".
> - **Límites de Intervalo:**
>     - **Límite Inferior (****LI****):** El valor más pequeño de un intervalo.
>     - **Límite Superior (****LS****):** El valor más grande de un intervalo.
> - **Límites Reales (****LRI** **y** **LRS****):** Son ajustes técnicos que se realizan a los límites para asegurar que no haya saltos entre intervalos. Se calculan restando o sumando la mitad de la unidad de medida mínima (comúnmente 0.5 o 0.005).
> - **Marca de Clase (****MC****):** Es el punto medio de un intervalo. Se calcula sumando los límites y dividiendo por dos: (LI + LS) / 2. Representa a todo el intervalo en cálculos posteriores.
> - **Frecuencia (****f****):** La cantidad de veces que aparece un dato dentro de un rango o intervalo específico.
> - **Frecuencia Relativa:** La proporción que representa la frecuencia de un intervalo respecto al total de la población (f / n).
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: Proceso de Organización de Datos
> 
> El procedimiento para transformar datos desordenados en una tabla de frecuencias sigue una lógica rigurosa de seis pasos:
> 
> ### Paso 1: Ordenamiento
> 
> Se deben organizar los números de menor a mayor (criterio estándar). Este paso es vital; omitirlo puede llevar a errores críticos en el cálculo del rango y en el conteo de frecuencias.
> 
> ### Paso 2: Cálculo del Rango
> 
> Se identifica el valor más alto y el más bajo para determinar la amplitud total de los datos.
> 
> ### Paso 3: Determinación del Tamaño del Intervalo
> 
> La estadística establece criterios matemáticos para decidir cuántos intervalos usar y qué ancho deben tener. Una regla práctica es:
> 
> 1. Dividir el **Rango por 5** (obteniendo un valor máximo sugerido para el intervalo).
> 2. Dividir el **Rango por 20** (obteniendo un valor mínimo sugerido).
> 3. El intervalo elegido debe estar comprendido entre estos dos resultados.
> 
> **Nota:** La elección final del intervalo (siempre que esté en el rango permitido) depende del criterio del analista. Un intervalo más pequeño ofrece mayor precisión gráfica, mientras que uno más grande simplifica la tabla.
> 
> ### Paso 4: Construcción de Intervalos y Límites Reales
> 
> Se definen los límites inferiores y superiores. Es recomendable que el primer límite inferior sea un poco menor al dato mínimo de la población para asegurar una cobertura completa. Los límites reales se calculan para que el límite superior de un intervalo coincida exactamente con el límite inferior del siguiente.
> 
> ### Paso 5: Cálculo de la Marca de Clase
> 
> Se determina el centro de cada intervalo, que servirá como referencia para las gráficas.
> 
> ### Paso 6: Conteo de Frecuencias
> 
> Se recorre la población ordenada y se cuenta cuántos datos caen en cada intervalo definido. La suma de todas las frecuencias **debe ser igual** al total de datos de la población.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Representación Gráfica
> 
> Los datos organizados en tablas se visualizan mediante dos gráficos principales:
> 
> 4. **Histograma:** Un gráfico de barras donde el ancho de la barra representa el intervalo (límites reales) y la altura representa la frecuencia.
> 5. **Polígono de Frecuencias:** Un gráfico de líneas que une los puntos medios (marcas de clase) de cada intervalo.
>     - **Regla de Cierre:** Para que el polígono "toque" el eje horizontal, se debe agregar un intervalo ficticio al inicio y otro al final con **frecuencia cero**. Esto cierra la figura geométrica.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Ejemplos Prácticos Aplicados
> 
> ### Caso A: Población de 80 Datos (Ejercicio 2.2)
> 
> - **Datos:** Valores entre 53 (mínimo) y 97 (máximo).
> - **Rango:** 97 - 53 = 44.
> - **Criterio de Intervalo:**
>     - 44 / 5 = 8.8 (Máximo)
>     - 44 / 20 = 2.2 (Mínimo)
>     - Se pueden elegir intervalos de 3, 4, 5, hasta 8.
> 
> **Comparativa de precisión según el intervalo:**
> 
> |   |   |   |
> |---|---|---|
> |Tipo de Intervalo|Resultado Visual|Precisión|
> |**Intervalo 4**|Gráfico con más picos y detalles (subidas y bajadas).|Alta|
> |**Intervalo 8**|Gráfico más suavizado, menos puntos de control.|Media|
> 
> ### Caso B: Mediciones Decimales (150 registros)
> 
> - **Mínimo:** 5.18 | **Máximo:** 7.44.
> - **Rango:** 2.26.
> - **Intervalos permitidos:** Entre 0.113 (2.26/20) y 0.452 (2.26/5).
> - **Decisión:** Se pueden usar intervalos de 0.20, 0.30 o 0.40.
> 
> **Ejemplo de Tabla (Intervalo 0.20):** | Límite Inferior | Límite Superior | Límite Real Inferior | Límite Real Superior | Marca de Clase | | :--- | :--- | :--- | :--- | :--- | | 5.10 | 5.29 | 5.095 | 5.295 | 5.195 | | 5.30 | 5.49 | 5.295 | 5.495 | 5.395 |
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores Comunes y Confusiones
> 
> - **No ordenar los datos:** Calcular el rango o las frecuencias con datos desordenados es el error más frecuente y distorsiona todo el análisis.
> - **Confusión entre Límites:** Creer que el Límite Superior y el Límite Real Superior son lo mismo. El límite real es necesario para que las barras del histograma estén juntas sin huecos.
> - **Suma de Frecuencias:** Olvidar verificar que la suma de las frecuencias de la tabla coincida con el total de la población. Si no coinciden, hay un error de conteo.
> - **Selección del Intervalo:** Elegir un intervalo fuera del rango [R/20, R/5] puede generar o demasiados intervalos (difícil de leer) o muy pocos (pérdida de información).
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Síntesis y Resumen de Puntos Clave
> 
> - La estadística busca la **precisión** a través del orden.
> - El **Rango** determina la amplitud del estudio.
> - La **Regla de 5 y 20** es la brújula para crear intervalos equilibrados.
> - La **Marca de Clase** es el representante matemático del intervalo.
> - Los **Gráficos** (Histograma y Polígono) son herramientas de diagnóstico visual; a menor intervalo, mayor es la precisión del gráfico.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es el primer paso obligatorio antes de realizar cualquier cálculo estadístico con una población?
> 2. Defina "Rango" y proporcione su fórmula.
> 3. ¿Cómo se calcula la Marca de Clase?
> 
> ### Nivel Intermedio
> 
> 4. Si tengo un rango de 60, ¿cuáles serían los valores mínimo y máximo permitidos para el ancho de mis intervalos según la regla de 5 y 20?
> 5. ¿Cuál es la diferencia técnica entre un Límite Superior y un Límite Real Superior?
> 6. ¿Para qué se añaden frecuencias de valor "cero" al inicio y al final de una tabla antes de graficar un polígono?
> 
> ### Nivel Avanzado
> 
> 7. Explique por qué un gráfico con intervalos más pequeños se considera "más preciso" que uno con intervalos grandes.
> 8. En una población de 150 mediciones con un rango de 2.26, justifique si un intervalo de 0.50 sería estadísticamente aceptable.
> 9. Describa la relación entre la Frecuencia Relativa y el valor total de la población (n).
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de la sesión, se destacan los siguientes puntos relevantes para el cronograma y el desempeño académico:
> 
> - **Próxima Clase:** Se iniciará el estudio de las **"Herramientas de Medición"**.
> - **Metodología de Estudio:** El profesor enfatiza que la "Clase 1" es la base de todo el cuatrimestre. Se recomienda revisar los conceptos de esa clase para no perder el hilo de las siguientes.
> - **Recordatorio Académico:** Se sugiere fuertemente el trabajo en grupos mediante reuniones virtuales (Meet) para practicar la construcción de tablas y el uso de software (Excel o Google Sheets).
> - **Material de Apoyo:** El archivo Excel resuelto en clase será enviado para su revisión y uso como plantilla modelo.
> 
> **Asistencia Notable (Mencionados en sesión):**
> 
> - Luciano But (Solicitó retiro anticipado).
> - Ignacio Vidal.
> - Carla Guisande.
> - Pablo De Martini.
> - (Entre otros alumnos presentes en el listado final).

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 3 - Estadística y probabilidad para el desarrollo de software" src="https://www.youtube.com/embed/OpkQUgPzTs4?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1mP_2jEkYF80xVp2UAwUmWJ-qINbiAhY4/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1dXFkoYoKzY7YISg-SYJ9IXNeJ3cQ_IHl/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>