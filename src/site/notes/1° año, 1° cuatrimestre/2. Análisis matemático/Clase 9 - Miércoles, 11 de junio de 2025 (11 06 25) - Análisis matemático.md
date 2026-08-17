---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/2-analisis-matematico/clase-9-miercoles-11-de-junio-de-2025-11-06-25-analisis-matematico/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía Académica: Funciones Inversas y Resolución de Sistemas de Ecuaciones mediante el Método de Gauss
> 
> Este documento constituye un material de estudio integral basado en los contenidos de análisis matemático, específicamente enfocados en la aplicabilidad de restricciones de dominio para funciones cuadráticas y la resolución avanzada de sistemas de ecuaciones lineales de 2 \times 2 y 3 \times 3.
> 
> ## 1. Introducción General
> 
> El estudio del análisis matemático requiere una comprensión profunda de cómo las funciones pueden ser transformadas para cumplir con propiedades específicas y cómo los sistemas de ecuaciones pueden ser resueltos de manera eficiente. Este apunte aborda dos grandes pilares:
> 
> 1. **La restricción de funciones no biyectivas** para permitir la existencia de una función inversa.
> 2. **El Método de Gauss** como una herramienta algorítmica y programable para resolver sistemas de ecuaciones, superando las limitaciones de los métodos tradicionales de sustitución e igualación.
> 
> ## 2. Marco Conceptual: Funciones e Inversión
> 
> Para que una función posea una inversa, debe cumplir con la condición de ser **biyectiva**.
> 
> ### Conceptos Clave
> 
> - **Biyectividad:** Una función es biyectiva si es, simultáneamente, inyectiva y sobreyectiva.
> - **Inyectividad:** Condición donde a distintos valores del dominio le corresponden distintos valores de la imagen. En términos prácticos, no pueden existir dos valores de x que devuelvan el mismo valor de y.
> - **Sobreyectividad:** Se relaciona con la definición del codominio. Para fines prácticos en este nivel, se asume que ajustando el codominio a los reales positivos (o al rango pertinente), la función cumple esta condición.
> - **Restricción de Dominio:** Es la acción de definir un subconjunto de valores de x donde la función existe, con el fin de forzar una propiedad (como la inyectividad) que la función original no posee en su dominio natural.
> 
> ### El Caso de la Función Cuadrática
> 
> Las funciones cuadráticas (parábolas) son simétricas, lo que significa que existen pares de valores de x que tienen la misma imagen. Por lo tanto, **no son inyectivas por naturaleza**.
> 
> - **¿Cómo obtener su inversa?** Se debe aplicar una restricción tomando solo una de las ramas de la parábola.
> - **Punto de división:** La división de las ramas ocurre en el **eje de simetría**, definido por la coordenada x del vértice (x_v).
> - **Convención:** Por costumbre académica, se suele trabajar con la rama derecha, restringiendo el dominio desde el vértice hacia el infinito positivo: [x_v, +\infty).
> - **Resultado:** Una vez restringida, la inversa de una función cuadrática resulta ser una raíz cuadrada.
> 
> ## 3. Desarrollo del Tema: Sistemas de Ecuaciones Lineales
> 
> Un sistema de ecuaciones es una combinación de n ecuaciones con n incógnitas. El objetivo es encontrar el conjunto solución que satisfaga todas las igualdades simultáneamente.
> 
> ### El Método de Gauss
> 
> A diferencia de los métodos de sustitución o igualación, el Método de Gauss se basa en la creación de **sistemas equivalentes** mediante operaciones entre renglones (ecuaciones).
> 
> - **Ventajas:** Es altamente programable (pensamiento computacional) y mantiene su eficiencia en sistemas de grandes dimensiones (3 \times 3, 4 \times 4, etc.), donde otros métodos se vuelven excesivamente complejos.
> - **Procedimiento General:** Consiste en escribir los coeficientes de las incógnitas y los términos independientes en una matriz y realizar operaciones para lograr una **triangulación de ceros**.
> 
> ### Tipos de Sistemas según su Solución
> 
> |   |   |   |
> |---|---|---|
> |Tipo de Sistema|Interpretación Geométrica (2 \times 2)|Resultado en Gauss|
> |**Compatible Determinado**|Dos rectas que se cortan en un punto único.|Se obtienen valores específicos para cada incógnita.|
> |**Compatible Indeterminado**|Dos rectas superpuestas (infinitas soluciones).|Se anula un renglón completo (0 = 0).|
> |**Incompatible**|Dos rectas paralelas y separadas (sin solución).|Se llega a una contradicción matemática (ej. 0 = 9).|
> 
> ## 4. Guía Paso a Paso: Método de Gauss (3 \times 3)
> 
> Para un sistema de tres ecuaciones con tres incógnitas (x, y, z), el objetivo es anular los coeficientes debajo de la diagonal principal.
> 
> ### Paso 1: Organización
> 
> Escribir los coeficientes en columnas (x, y, z) y la columna de resultados (K).
> 
> ### Paso 2: Primera Triangulación
> 
> Anular los coeficientes de x en la segunda y tercera ecuación (E_2 y E_3) utilizando la primera ecuación (E_1).
> 
> - E'_1 = E_1 (se mantiene igual).
> - E'_2 = E_2 + (n \cdot E_1) (donde n es un escalar que anula el coeficiente de x).
> - E'_3 = E_3 + (m \cdot E_1).
> 
> ### Paso 3: Segunda Triangulación
> 
> Anular el coeficiente de y en la tercera ecuación (E_3) utilizando la **segunda ecuación modificada** (E'_2).
> 
> - **Advertencia Importante:** No usar la E_1 en este paso, ya que se perderían los ceros logrados en la primera columna.
> 
> ### Paso 4: Resolución por Sustitución Inversa
> 
> Una vez lograda la forma triangular:
> 
> 1. Despejar z de la última ecuación.
> 2. Sustituir z en la segunda ecuación para hallar y.
> 3. Sustituir z e y en la primera ecuación para hallar x.
> 
> ## 5. Ejemplos Prácticos Aplicados
> 
> ### Caso A: Producción de Válvulas
> 
> Un taller fabrica válvulas "Estándar" (E) y de "Lujo" (L) usando un Torno y una Prensa.
> 
> - **Datos:**
>     - Torno: Disponible 4 horas (240 min). Requiere 5 min por E y 9 min por L.
>     - Prensa: Disponible 7 horas (420 min). Requiere 10 min por E y 15 min por L.
> - **Ecuaciones:**
>     1. 5E + 9L = 240
>     2. 10E + 15L = 420
> - **Resolución:** Aplicando Gauss, se descubre que el sistema es Compatible Determinado, resultando en la producción de **20 válvulas de Lujo** y **12 válvulas Estándar**.
> 
> ### Caso B: Conteo de Fichas
> 
> Se tienen 29 fichas en total, algunas de 5 puntos y otras de 20 puntos, sumando 400 puntos.
> 
> - **Ecuaciones:**
>     1. F_5 + F_{20} = 29
>     2. 5F_5 + 20F_{20} = 400
> - **Resultado:** El sistema arroja que existen **12 fichas de 5 puntos** y **17 fichas de 20 puntos**.
> 
> ## 6. Errores Comunes y Aclaraciones
> 
> - **Confusión en la Sobreyectividad:** No profundizar en el exceso de rigor matemático; se soluciona definiendo correctamente el codominio.
> - **Error en la Triangulación:** En sistemas 3 \times 3, intentar anular el segundo coeficiente de la tercera fila usando la primera fila. Esto suele reintroducir un valor en la primera columna (donde ya había un cero). Siempre se debe usar la segunda fila modificada.
> - **Operaciones con Escalares:** Olvidar multiplicar el término independiente (K) al realizar operaciones entre ecuaciones. Toda la fila debe ser multiplicada por el escalar.
> - **Orden de Columnas:** Aunque se puede cambiar el orden de las columnas (ej. poner z primero), no se recomienda al inicio para evitar confusiones en el despeje final.
> 
> ## 7. Síntesis y Puntos Clave
> 
> - **Restricción Cuadrática:** Es obligatoria para hallar la inversa. Se usa x_v como límite del nuevo dominio.
> - **Esencia de Gauss:** Buscar sistemas equivalentes que no modifiquen el conjunto solución.
> - **Triangulación:** El objetivo es el "triángulo de ceros" en la esquina inferior izquierda de la matriz de coeficientes.
> - **Sistemas Especiales:** 0=0 implica infinitas soluciones; 0=K (donde K \neq 0) implica que no hay solución.
> 
> ## 8. Preguntas de Repaso (Tipo Examen)
> 
> 1. **(Básico)** ¿Qué condición debe cumplir una función para que se pueda calcular su inversa?
> 2. **(Básico)** ¿Por qué una función cuadrática requiere una restricción de dominio para ser inyectiva?
> 3. **(Intermedio)** En un sistema de 3 \times 3, si al aplicar Gauss un renglón se convierte en 0 = 0, ¿qué tipo de sistema es y qué significa geométricamente?
> 4. **(Avanzado)** Explique por qué el Método de Gauss es preferible al de sustitución en sistemas de ecuaciones de 4 \times 4 o superiores.
> 5. **(Práctico)** Dado el sistema de ecuaciones de las válvulas, plantee la matriz inicial y realice el primer paso de anulación para la variable E.
> 
> ## 9. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de la sesión, se establecen las siguientes pautas para la evaluación:
> 
> - **Fecha del Examen (Parcial):** Miércoles 18 de octubre.
> - **Horario:** 19:00 horas.
> - **Modalidad:** Presencial.
> - **Temario Confirmado:**
>     1. Composición de funciones.
>     2. Función inversa (incluyendo restricciones).
>     3. Sistemas de ecuaciones lineales (Resolución obligatoria mediante el **Método de Gauss**).
> - **Indicaciones del Profesor:**
>     - En el examen, los sistemas de 3 \times 3 ya vendrán planteados (no habrá que interpretar problemas de texto para esa dimensión, pero sí para 2 \times 2).
>     - Se subirán ejercicios resueltos al campus para práctica adicional antes del parcial.
>     - Se enfatiza el uso del método mecánico de Gauss para asegurar el éxito en la evaluación.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 9 - Análisis matemático" src="https://www.youtube.com/embed/jYK7tvG4Hrc?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1O280Olti3Gc3SrD5-R_1zz_p49pDOjZS/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/14T8C9S6z2UwysWAwSizf1gtVT1Y58Z1M/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>