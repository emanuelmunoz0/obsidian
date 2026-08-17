---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/2-analisis-matematico/clase-7-miercoles-21-de-mayo-de-2025-21-05-25-analisis-matematico/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio Completa: Análisis Matemático - Función Cuadrática e Intersecciones
> 
> Este documento constituye un material de estudio exhaustivo basado en las sesiones académicas de Análisis Matemático. Cubre desde los fundamentos de la función cuadrática hasta conceptos avanzados de intersección y composición de funciones, proporcionando las herramientas necesarias para el dominio teórico y práctico de la materia.
> 
> ## 1. Introducción y Contexto del Tema
> 
> El estudio de las funciones es el pilar del análisis matemático. Mientras que las funciones lineales describen relaciones proporcionales simples, las **funciones cuadráticas** permiten modelar fenómenos más complejos que involucran aceleraciones, áreas y trayectorias parabólicas. Comprender sus componentes (vértice, raíces, concavidad) es esencial para interpretar el comportamiento de sistemas en diversas disciplinas técnicas y científicas.
> 
> ## 2. Marco Conceptual: Definición de Conceptos Clave
> 
> Para abordar el análisis de una función cuadrática, es necesario definir sus elementos fundamentales:
> 
> |   |   |
> |---|---|
> |Concepto|Definición|
> |**Función Cuadrática**|Función de segundo grado cuya representación gráfica es una parábola.|
> |**Vértice (****V****)**|Punto máximo o mínimo de la parábola. Tiene coordenadas (x_v, y_v).|
> |**Raíces (Ceros)**|Puntos donde la función corta el eje x (f(x) = 0).|
> |**Ordenada al Origen**|Punto donde la función corta el eje y (x = 0). Coincide con el valor de C.|
> |**Eje de Simetría**|Línea vertical que pasa por el vértice y divide a la parábola en dos partes iguales.|
> |**Concavidad**|Orientación de las ramas de la parábola (hacia arriba o hacia abajo).|
> |**Dominio**|Conjunto de todos los valores de entrada posibles (en estas funciones, siempre son todos los Reales).|
> |**Imagen**|Conjunto de valores de salida que efectivamente toma la función en el eje y.|
> 
> ## 3. Desarrollo del Tema: Análisis de la Función Cuadrática
> 
> El análisis de una función cuadrática se realiza habitualmente a partir de su forma polinómica: f(x) = ax^2 + bx + c.
> 
> ### 3.1. Cálculo del Vértice
> 
> El vértice es el punto crítico de la función.
> 
> - **Coordenada** **x_v****:** Se calcula con la fórmula x_v = \frac{-b}{2a}.
> - **Coordenada** **y_v****:** Se puede obtener reemplazando el valor de x_v en la función original o mediante la fórmula: y_v = \frac{4ac - b^2}{4a}.
> 
> ### 3.2. Determinación de las Raíces (Fórmula Resolvente)
> 
> Para hallar los puntos donde la parábola toca el eje x, se utiliza la fórmula: x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a} El término dentro de la raíz (b^2 - 4ac) se llama **discriminante**. Si es positivo, existen dos raíces reales; si es cero, una raíz doble (un punto de contacto); si es negativo, no hay raíces reales.
> 
> ### 3.3. Concavidad y Comportamiento
> 
> La concavidad depende exclusivamente del signo del coeficiente principal (a):
> 
> - **Si** **a > 0****:** Concavidad positiva ("carita feliz"). La función tiene un **mínimo** en el vértice. La imagen va desde y_v hasta +\infty.
> - **Si** **a < 0****:** Concavidad negativa ("carita triste"). La función tiene un **máximo** en el vértice. La imagen va desde -\infty hasta y_v.
> 
> ### 3.4. Intervalos de Crecimiento y Decrecimiento
> 
> El estudio del crecimiento se realiza siempre de izquierda a derecha (en el eje x):
> 
> - En una parábola con concavidad positiva, la función primero decrece hasta el vértice y luego crece.
> - En una parábola con concavidad negativa, la función primero crece hasta el vértice y luego decrece.
> - **Nota importante:** El vértice mismo no es creciente ni decreciente; es el punto de cambio.
> 
> ## 4. Intersección de Funciones
> 
> La intersección ocurre cuando dos funciones comparten el mismo punto (x, y).
> 
> ### 4.1. Procedimiento Analítico
> 
> Para hallar la intersección (ya sea entre dos parábolas o entre una parábola y una recta):
> 
> 1. **Igualar las funciones:** f(x) = g(x).
> 2. **Transponer términos:** Llevar todos los términos a un solo lado de la igualdad para que la ecuación quede igualada a cero.
> 3. **Aplicar la fórmula resolvente:** Resolver la ecuación cuadrática resultante para hallar los valores de x donde se cortan.
> 4. **Verificación:** Reemplazar los valores de x hallados en ambas funciones originales. Deben arrojar el mismo valor de y.
> 
> ### 4.2. Posibilidades de Intersección
> 
> - **Dos puntos:** Las funciones se cortan en dos lugares distintos.
> - **Un punto (Tangencia):** Las funciones se tocan en un solo punto.
> - **Ningún punto:** Las funciones no tienen contacto entre sí.
> 
> ## 5. Composición de Funciones (Anidación)
> 
> La composición consiste en aplicar una función sobre el resultado de otra, denotado como (g \circ f)(x) o g(f(x)).
> 
> - **Concepto:** La salida (imagen) de la primera función (f) se convierte en la entrada (dominio) de la segunda función (g).
> - **Condición de existencia:** Para que la composición sea posible, la imagen de la primera función debe estar contenida o incluida en el dominio de la segunda.
> - **Restricción de dominio:** Si lo que "sale" de la primera función no es admitido por la segunda (ejemplo: una raíz cuadrada que recibe un número negativo), se debe restringir el dominio de la primera función para asegurar que la cadena no se rompa.
> 
> ## 6. Ejemplos Prácticos Paso a Paso
> 
> ### Ejemplo 1: Estudio Completo de f(x) = \frac{1}{3}x^2 + 9x - 2
> 
> 1. **Datos:** a = 1/3, b = 9, c = -2.
> 2. **Vértice:**
>     - x_v = -9 / (2 \cdot 1/3) = -27/2 = -13,5.
>     - y_v = (4 \cdot 1/3 \cdot -2 - 9^2) / (4 \cdot 1/3) = -62,75.
> 3. **Imagen:** [-62,75; +\infty) ya que a > 0.
> 4. **Raíces:** Aplicando la resolvente, se obtienen valores aproximados: x_1 \approx 0,23 y x_2 \approx -27,23.
> 5. **Crecimiento:** Decrece en (-\infty; -13,5) y crece en (-13,5; +\infty).
> 
> ### Ejemplo 2: Intersección entre y = x^2 + 1 y y = x + 1
> 
> 6. Igualamos: x^2 + 1 = x + 1.
> 7. Llevamos a cero: x^2 - x = 0.
> 8. Factorizamos o usamos resolvente: x(x - 1) = 0 \implies x_1 = 0, x_2 = 1.
> 9. Buscamos y:
>     - Si x=0, y=1. Punto (0, 1).
>     - Si x=1, y=2. Punto (1, 2).
> 
> ## 7. Errores Comunes y Confusiones
> 
> - **Signos en la forma canónica:** La coordenada x del vértice en la forma canónica suele aparecer con el signo opuesto al valor real de x_v. Es fundamental recordar que la fórmula base es (x - x_v).
> - **Confusión en la Imagen:** La imagen depende de y_v y de la concavidad, no del valor de x_v.
> - **Orden de Composición:** g(f(x)) no es lo mismo que f(g(x)). El orden de anidación altera el resultado.
> - **Crecimiento:** Se debe expresar siempre en relación a los valores del eje x, aunque estemos mirando si la función sube o baja en el eje y.
> 
> ## 8. Síntesis y Conclusiones
> 
> - La función cuadrática es simétrica respecto a su eje de simetría.
> - El coeficiente a determina la forma y concavidad; c determina el cruce con el eje y.
> - Para intersecciones, la igualación y el uso de la resolvente son los métodos analíticos estándar.
> - En la composición, la compatibilidad entre la imagen de la función interna y el dominio de la externa es la regla de oro para evitar errores matemáticos.
> 
> ## 9. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de las fuentes, se establecen las siguientes fechas y advertencias:
> 
> - **Examen Parcial:**
>     - **Fecha:** Próxima semana (28 de este mes).
>     - **Hora:** 19:00 horas (Presencial). El profesor estará disponible desde las 18:30 para consultas.
>     - **Temas a evaluar:** Función cuadrática (estudio completo e intersecciones).
> - **Avisos Académicos:**
>     - **Material de estudio:** En el aula virtual, unidad de Función Cuadrática, se encuentran cargados dos ejemplos resueltos (uno en forma factorizada y otro en forma canónica).
>     - **Sobre el examen:** No se incluirán ejercicios con enunciados complejos (como el caso del rectángulo), se evaluará directamente la función y su estudio. La parte de intersección será solo analítica (sin gráfico obligatoriamente) para optimizar el tiempo.
>     - **Lógica:** Existe una inquietud sobre la falta de profesor en la materia de Lógica; se elevará la consulta a secretaría para obtener novedades sobre la clase de los miércoles.
> 
> ## 10. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. Si a es negativo, ¿la función tiene un máximo o un mínimo?
> 2. ¿Cómo se encuentra la ordenada al origen de cualquier función?
> 
> ### Nivel Intermedio
> 
> 1. Dada la función f(x) = -5x^2 + 10x, halle el vértice y las raíces.
> 2. Si la imagen de una función es (-\infty; 5], ¿cuánto vale y_v y cuál es su concavidad?
> 
> ### Nivel Avanzado
> 
> 1. Explique por qué es necesario restringir el dominio en la composición de g(f(x)) si f(x) = \sqrt{x} y g(x) = \sqrt{1-x}.
> 2. ¿Qué sucede con el discriminante en el caso de que dos parábolas sean tangentes entre sí al igualarlas?

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 7 - Análisis matemático" src="https://www.youtube.com/embed/gzDMj81c7m8?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1G1Nxg5fyNR-KaDltcr2eIEx3PteLGtO7/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1a0d9ZFQtsMAKnlQ_8BvDEPBg9ctiee9X/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>