---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/2-analisis-matematico/clase-3-miercoles-09-de-abril-de-2025-09-04-25-analisis-matematico/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio Integral: Análisis Matemático - Razones, Proporciones e Inecuaciones
> 
> Este documento constituye un material de estudio exhaustivo basado en las sesiones académicas sobre análisis matemático. Cubre desde la resolución de problemas prácticos de proporcionalidad hasta conceptos avanzados de inecuaciones con cocientes y valor absoluto.
> 
> ## 1. Introducción y Contexto
> 
> El análisis matemático no se limita a la resolución de ecuaciones abstractas; es una herramienta fundamental para modelar situaciones de la vida real. Este documento aborda la transición entre el razonamiento lógico-práctico (problemas de engranajes y consumo) y el rigor formal del álgebra (inecuaciones y módulos). El dominio de estos temas es esencial para avanzar hacia el estudio de funciones y el cálculo superior.
> 
> ## 2. Aplicaciones Prácticas de Proporcionalidad
> 
> ### 2.1 El Concepto de Avance en Engranajes
> 
> En un sistema de transmisión por cadena (como el de una bicicleta), la cadena se considera un elemento rígido que no se dilata ni se contrae. Esto implica que el "avance" lineal debe ser idéntico en ambos engranajes.
> 
> - **Propiedad Fundamental:** La cantidad de eslabones o "dientes" que pasan por un punto es la misma para el engranaje grande y el pequeño.
> - **Fórmula de Avance:** \text{Dientes} \times \text{Vueltas} = \text{Avance Total}
> 
> **Ejemplo Práctico:** Un engranaje grande de 48 dientes da 528 vueltas. ¿Cuántas vueltas dará un engranaje pequeño de 22 dientes?
> 
> 1. **Cálculo del avance:** 48 \text{ dientes} \times 528 \text{ vueltas} = 25,344 \text{ dientes de avance}.
> 2. **Igualación:** El engranaje pequeño debe avanzar los mismos 25,344 dientes.
> 3. **Resolución:** 22 \times X = 25,344 \rightarrow X = 25,344 / 22 = 1,152 \text{ vueltas}.
> 
> ### 2.2 Proporcionalidad Compuesta (Problema de Alfalfa)
> 
> Para resolver problemas de consumo y tiempo, la estrategia más eficiente es la **reducción a la unidad** o el análisis del **gasto extra**.
> 
> **Caso de Estudio:**
> 
> - **Datos Iniciales:** 7 vacas consumen 6,720 kg de alfalfa en 120 días.
> - **Cambio:** A los 15 días, se compran 3 vacas adicionales.
> - **Objetivo:** Determinar cuánto alimento faltará para cubrir el periodo original.
> 
> **Pasos para la resolución eficiente:**
> 
> 1. **Consumo por unidad:** 6,720 \text{ kg} / 7 \text{ vacas} / 120 \text{ días} = 8 \text{ kg por vaca al día}.
> 2. **Identificación del excedente de demanda:** Las 7 vacas originales ya tienen su alimento asegurado. El problema se reduce a alimentar a las **3 vacas nuevas**.
> 3. **Cálculo del tiempo restante:** 120 \text{ días} - 15 \text{ días} = 105 \text{ días}.
> 4. **Resultado:** 3 \text{ vacas} \times 8 \text{ kg/día} \times 105 \text{ días} = 2,520 \text{ kg de alfalfa faltante}.
> 
> ## 3. Inecuaciones con Cocientes y Productos
> 
> ### 3.1 Regla de los Signos
> 
> Para que un cociente o producto sea menor o mayor que cero, se debe analizar la relación entre los signos del numerador y el denominador:
> 
> |   |   |   |
> |---|---|---|
> |Resultado deseado|Signo del Numerador / Factor A|Signo del Denominador / Factor B|
> |**Positivo (> 0)**|Igual signo (+)|Igual signo (+)|
> |**Positivo (> 0)**|Igual signo (-)|Igual signo (-)|
> |**Negativo (< 0)**|Signo opuesto (+)|Signo opuesto (-)|
> |**Negativo (< 0)**|Signo opuesto (-)|Signo opuesto (+)|
> 
> ### 3.2 Restricción del Denominador
> 
> En cualquier inecuación que involucre un cociente, **el denominador nunca puede ser cero**. Este valor debe identificarse al inicio y excluirse de la solución final, independientemente de si la inecuación incluye un "igual" (\le o \ge).
> 
> ### 3.3 Operaciones Críticas
> 
> - **Cambio de sentido:** Al multiplicar o dividir ambos miembros de una desigualdad por un número negativo (o cambiar el signo de ambos lados), **el sentido de la desigualdad debe invertirse**.
>     - _Ejemplo:_ -x > -1 \implies x < 1.
> - **Búsqueda del cero:** Para resolver inecuaciones complejas, siempre es preferible trasladar todos los términos a un lado para comparar contra cero (>0 o <0).
> 
> ## 4. Marco Conceptual: Valor Absoluto (Módulo)
> 
> ### 4.1 Definición Matemática
> 
> El módulo de un número x, denotado como |x|, representa su distancia al origen (cero) en la recta numérica. Siempre es un valor no negativo.
> 
> - |x| = x si x \ge 0
> - |x| = -x si x < 0
> 
> ### 4.2 Distancia entre dos puntos
> 
> La distancia d entre dos números reales a y b se define como: d(a, b) = |b - a|
> 
> _Nota:_ Debido a la propiedad del módulo, |b - a| es equivalente a |a - b|.
> 
> ### 4.3 Resolución de Inecuaciones con Módulo
> 
> Al "abrir" un módulo en una inecuación, se generan dos casos:
> 
> 1. **Si** **|x| < a** **(Menor):** Se busca un intervalo acotado.
>     - -a < x < a (Intersección de soluciones).
> 2. **Si** **|x| > a** **(Mayor):** Se busca una unión de intervalos divergentes.
>     - x > a \quad \text{ó} \quad x < -a.
> 
> ## 5. Ejemplos Paso a Paso
> 
> ### Ejemplo 1: Inecuación con Cociente \frac{x}{x-1} \le 0
> 
> 1. **Exclusión:** x - 1 \neq 0 \implies x \neq 1.
> 2. **Planteo de signos opuestos:**
>     - Caso A: x \ge 0 y x - 1 < 0 \implies x \ge 0 y x < 1. Intervalo: [0, 1).
>     - Caso B: x \le 0 y x - 1 > 0 \implies x \le 0 y x > 1. (Imposible, solución vacía).
> 3. **Solución Final:** [0, 1). El 1 lleva paréntesis porque está excluido por el denominador.
> 
> ### Ejemplo 2: Distancia en la Recta Numérica
> 
> "Números cuya distancia a -3 es menor que 5":
> 
> 4. **Planteo:** d(x, -3) < 5.
> 5. **Módulo:** |x - (-3)| < 5 \implies |x + 3| < 5.
> 6. **Apertura:** -5 < x + 3 < 5.
> 7. **Despeje:** -5 - 3 < x < 5 - 3 \implies -8 < x < 2.
> 8. **Solución:** (-8, 2).
> 
> ## 6. Síntesis y Conclusiones
> 
> - **Relación de Engranajes:** El avance es constante; si un engranaje tiene menos dientes, debe dar más vueltas para compensar.
> - **Inecuaciones:** El análisis de signos es la clave. Nunca se debe olvidar excluir los valores que anulan el denominador.
> - **Valor Absoluto:** Actúa como una distancia. Las desigualdades de tipo "menor que" generan intervalos centrales, mientras que las de "mayor que" generan intervalos hacia los infinitos.
> - **Metodología:** Siempre graficar los intervalos en una recta numérica para identificar correctamente las intersecciones y uniones.
> 
> ## 7. Fechas Importantes y Avisos Académicos
> 
> |   |   |   |
> |---|---|---|
> |Fecha|Tipo de Evento|Descripción Detallada|
> |**30 de abril**|**Examen Parcial (Presencial)**|Comienza a las **19:00 horas**. Duración aproximada: 60 minutos.|
> |Próxima clase|Inicio de Unidad|Se comenzará con el tema de **Función Lineal**.|
> |-|Revisión de Tarea|Se recomienda completar los ejercicios 5 (e, f), 6 y 7 de la guía para la próxima clase.|
> 
> **Recordatorios:**
> 
> - El examen parcial abarca todos los temas vistos hasta **Función Lineal** inclusive.
> - Las soluciones de la guía están disponibles en el aula virtual para consulta.
> - El cronograma detallado se encuentra en la sección "Apertura" del aula virtual.
> 
> ## 8. Preguntas de Repaso (Tipo Examen)
> 
> ### Básicas
> 
> 1. Si un engranaje A tiene el doble de dientes que un engranaje B, ¿cuántas vueltas da B por cada vuelta de A?
> 2. Defina con sus palabras qué es el valor absoluto y proporcione un ejemplo de su uso para medir distancias.
> 
> ### Intermedias
> 
> 1. Resuelva la inecuación \frac{1-x}{1+x} > 0. No olvide indicar qué valor se excluye del dominio.
> 2. Represente como un intervalo el conjunto de números reales tales que su distancia a 3 es mayor o igual a 4.
> 
> ### Avanzadas
> 
> 1. Explique por qué en la inecuación \frac{1}{x} > -1 no es conveniente simplemente "pasar la x multiplicando" al otro lado. ¿Cuál es el procedimiento correcto?
> 2. Dado el intervalo solución (-8, 2), reconstruya la inecuación de valor absoluto que le dio origen.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 3 - Análisis matemático" src="https://www.youtube.com/embed/-vm1X0fkYuo?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1x7KBpyV-aC1JnnyiAKdVr56xd72mEuL1/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1lzLT8s09PnGhkHZRXpxXdspEBnEw8GbG/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>