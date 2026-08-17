---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/2-analisis-matematico/clase-2-miercoles-26-de-marzo-de-2025-25-03-25-analisis-matematico/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía Integral de Análisis Matemático: Conjuntos Numéricos, Operaciones e Inecuaciones
> 
> Este documento constituye un material de estudio exhaustivo basado en las sesiones académicas de análisis matemático. Aborda desde la clasificación fundamental de los números hasta la resolución compleja de inecuaciones y problemas de aplicación práctica.
> 
> ## 1. Contexto e Importancia
> 
> El estudio del análisis matemático se fundamenta en la comprensión de los números reales y sus propiedades. El dominio de estos conceptos es esencial no solo para avanzar en materias como estadística, sino para la resolución de problemas técnicos donde la carga de datos y el control de procesos (apoyados hoy en software y calculadoras) requieren una base conceptual sólida para interpretar resultados.
> 
> ## 2. Marco Conceptual: La Jerarquía de los Números
> 
> El universo numérico se organiza de forma inclusiva, donde cada nuevo conjunto abarca a los anteriores:
> 
> - **Números Naturales (****\mathbb{N}****):** Los números básicos para contar.
> - **Números Enteros (****\mathbb{Z}****):** Incluyen los naturales, sus negativos y el cero.
> - **Números Racionales (****\mathbb{Q}****):** Se simbolizan con la "Q" (del término para "quebrado" o cociente). Se definen como el cociente \frac{a}{b} donde a y b son enteros y b \neq 0.
>     - **Fracciones Irreducibles:** Una fracción es irreducible si el numerador y el denominador son coprimos (no tienen divisores comunes). Aunque la simplificación manual es menos frecuente hoy debido a las calculadoras, sigue siendo un concepto base de la aritmética.
> - **Números Irracionales:** Aquellos que no pueden expresarse como una razón entre dos enteros. Poseen infinitos decimales no periódicos. Se dividen en:
>     - **Radicales:** Raíces cuadradas, cúbicas, etc., que no son exactas.
>     - **Números Trascendentes:** Surgen de funciones más complejas. Ejemplos clave son \pi (de funciones trigonométricas) y e (número de Euler, 2.71828..., de funciones exponenciales).
> - **Números Reales (****\mathbb{R}****):** Es el conjunto más abarcativo, formado por la unión de los racionales y los irracionales.
> 
> ## 3. Conversión de Expresiones Decimales a Fraccionarias
> 
> Pasar de una expresión decimal a una fracción depende del tipo de decimal:
> 
> ### A. Decimales Exactos (Sin periodo)
> 
> 1. **Numerador:** El número completo sin la coma.
> 2. **Denominador:** Un 1 seguido de tantos ceros como cifras decimales tenga el número.
>     - _Ejemplo:_ 3.87 = \frac{387}{100}.
> 
> ### B. Decimales Periódicos Puros
> 
> 1. **Numerador:** El número (o periodo) sin la coma.
> 2. **Denominador:** Tantos nueves como cifras tenga el periodo.
>     - _Ejemplo:_ 0.33... = \frac{3}{9} = \frac{1}{3}. Si el periodo fuera 0.2727..., sería \frac{27}{99}.
> 
> ### C. Decimales Periódicos Mixtos (Con parte entera o decimal no periódica)
> 
> 1. **Numerador:** El número completo (sin coma) menos la parte no periódica (todo lo que está antes del periodo).
> 2. **Denominador:** Tantos nueves como cifras tenga el periodo, seguidos de tantos ceros como cifras tenga la parte decimal no periódica.
>     - _Importante:_ La parte entera aporta al numerador en la resta, pero **no aporta ceros al denominador**.
> 
> |   |   |   |   |
> |---|---|---|---|
> |Tipo de Decimal|Ejemplo|Proceso de Conversión|Resultado|
> |**Exacto**|0.125|\frac{125}{1000}|1/8|
> |**Periódico Puro**|4.27...|\frac{427 - 4}{99}|423/99|
> |**Periódico Mixto**|0.328...|\frac{328 - 32}{900}|296/900|
> |**Periódico Mixto**|5.471...|\frac{5471 - 54}{990}|5417/990|
> 
> ## 4. Propiedades de las Operaciones en los Reales
> 
> ### Adición (Suma)
> 
> - **Conmutativa:** El orden de los sumandos no altera el total (a+b = b+a).
> - **Asociativa:** Permite realizar sumas parciales o agrupar términos sin alterar el resultado.
> - **Elemento Neutro:** El cero (0). Cualquier número sumado a cero es igual a sí mismo.
> 
> ### Multiplicación (Producto)
> 
> - **Conmutativa y Asociativa:** Igual que en la suma.
> - **Elemento Neutro:** El uno (1).
> - **Distributiva respecto a la suma:** a \cdot (b + c) = (a \cdot b) + (a \cdot c). Es fundamental para resolver ecuaciones y encontrar factores comunes.
> 
> ### La Resta y sus Limitaciones
> 
> A diferencia de la suma, la resta **solo cumple la propiedad del elemento neutro** (restar cero). No es conmutativa (5-3 \neq 3-5) ni asociativa.
> 
> ## 5. Lógica, Intervalos e Inecuaciones
> 
> ### Operadores Lógicos
> 
> - **Conjunción (****\land** **/ "y"):** Representado por una "v" invertida. Para que sea cierta, todas las condiciones deben cumplirse simultáneamente (ej. traer DNI **y** Certificado).
> - **Disyunción (****\lor** **/ "o"):** Representado por una "v". Es cierta si al menos una de las proposiciones lo es.
> 
> ### Intervalos
> 
> Representan subconjuntos de la recta real. Por convención, la recta se lee de **izquierda a derecha** y de **abajo hacia arriba** en el eje vertical.
> 
> - **Abierto** **(a, b)****:** No incluye los extremos.
> - **Cerrado** **[a, b]****:** Incluye los extremos.
> - **Infinito:** Los extremos que tienden a infinito (\infty) siempre llevan paréntesis, nunca corchete.
> - **Intersección (****\cap****):** Elementos en común entre dos conjuntos (donde se "superponen").
> 
> ### Inecuaciones
> 
> Resolver una inecuación significa hallar un **intervalo** de valores que satisfacen la desigualdad.
> 
> - _Regla de Oro:_ Si se multiplica o divide por un número negativo, el sentido de la desigualdad cambia (detalle a profundizar en clases posteriores).
> - **Producto de Factores:** Si (A) \cdot (B) > 0, existen dos casos:
>     
>     1. Ambas partes son positivas (A > 0 \land B > 0).
>     2. Ambas partes son negativas (A < 0 \land B < 0).
>     
>     - La solución final es la **unión** de los resultados de ambos casos.
> 
> ## 6. Resolución de Problemas Prácticos
> 
> ### Caso 1: Diferencia de Cuadrados de Números Consecutivos
> 
> - **Problema:** Hallar dos números naturales consecutivos cuya diferencia de cuadrados sea 23.
> - **Planteamiento:**
>     1. Sean los números x e y.
>     2. x^2 - y^2 = 23.
>     3. Como son consecutivos: x = y + 1.
>     4. Sustitución: (y + 1)^2 - y^2 = 23.
>     5. Aplicando distributiva/cuadrado: y^2 + 2y + 1 - y^2 = 23.
>     6. Resolución: 2y + 1 = 23 \rightarrow 2y = 22 \rightarrow y = 11.
> - **Resultado:** Los números son **11 y 12**.
> 
> ### Caso 2: Coincidencia de Salidas (MCM)
> 
> - **Problema:** Tres transportes con diferentes frecuencias y tiempos de espera. ¿Cuándo vuelven a coincidir si salieron a las 6:00?
> - **Método:** Usar el Mínimo Común Múltiplo (MCM).
>     - Transporte 1: 105 min viaje + 15 min espera = 120 min.
>     - Transporte 2: 65 min viaje + 7 min espera = 72 min.
>     - Transporte 3: 78 min viaje + 12 min espera = 90 min.
> - **Cálculo:** Descomposición en factores primos. El MCM de 120, 72 y 90 es **360 minutos (6 horas)**.
> - **Resultado:** Coinciden a las **12:00 del mediodía**.
> - **Viajes realizados:**
>     - T1: 360 / 120 = 3 viajes.
>     - T2: 360 / 72 = 5 viajes.
>     - T3: 360 / 90 = 4 viajes.
> 
> ## 7. Errores Comunes y Aclaraciones
> 
> - **Confusión en el Denominador:** Incluir la parte entera como un "cero" en el denominador de un decimal periódico. **Recordatorio:** Los ceros solo dependen de la parte decimal no periódica.
> - **División por Cero:** Nunca está definida. En fracciones \frac{a}{b}, b debe ser siempre distinto de cero.
> - **Intervalos e Igualdad:** Si una inecuación dice "menor que" (<), el extremo es un paréntesis (abierto). Si dice "menor o igual" (\leq), el extremo es un corchete (cerrado).
> - **Periodos "Incompletos":** No se puede definir un periodo de forma parcial (ej. tomar un periodo y medio). El periodo debe tomarse completo para que el cálculo sea exacto.
> 
> ## 8. Síntesis y Resumen
> 
> - Los números reales se dividen en racionales e irracionales.
> - Todo número periódico puede expresarse como fracción (es racional).
> - Las inecuaciones resultan en conjuntos de soluciones (intervalos).
> - El MCM se utiliza para encontrar puntos de coincidencia en eventos progresivos, mientras que el MCD se usa para dividir o reducir cantidades en partes comunes.
> 
> ## 9. Preguntas de Repaso (Tipo Examen)
> 
> 1. **Básica:** ¿Por qué el número \pi no pertenece al conjunto de los números racionales?
> 2. **Intermedia:** Explique paso a paso cómo convertir 2.1333... en fracción. ¿Cuál es el error más común al intentar calcular su denominador?
> 3. **Avanzada:** En la inecuación (x-2)(x+5) < 0, ¿qué condiciones lógicas deben cumplirse para hallar el intervalo solución? Explique por qué se utiliza la intersección de conjuntos en este caso.
> 4. **Aplicada:** Si dos engranajes tienen 48 y 22 dientes respectivamente, y el mayor da 528 vueltas, ¿cómo se calcula el número de vueltas del menor usando la lógica de avance?
> 
> ## 10. Fechas Importantes y Avisos Académicos
> 
> |   |   |   |
> |---|---|---|
> |Fecha|Evento / Aviso|Descripción|
> |**Próxima semana**|Feriado|**No hay clases.**|
> |**Miércoles 9**|Clase Presencial / Virtual|Retorno a las clases a las **18:30 hs.**|
> |**Próxima clase**|Continuación Práctica|Se corregirán los ejercicios 3 y 4 del TP. Se explicarán inecuaciones con cocientes (ejercicio 5B).|
> |**Recordatorio**|Entrega de TP|El Trabajo Práctico **no se envía por mail**; es para trabajar y corregir en clase.|
> 
> _Nota: Quienes no recibieron el material teórico o el TP por mail deben verificar sus datos con el profesor para ser incluidos en la lista de correo._

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 2 - Análisis matemático" src="https://www.youtube.com/embed/Yw-35Erso3k?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1kmux0OqT7Jgcrg9W1JVkLbefTCSgi6q3/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1fyVpvotGdX9W51U_I6cqlO8AnHUnuS0x/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>