---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/3-logica-computacional/clase-2-jueves-27-de-marzo-de-2025-27-03-25-logica-computacional/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio Integral: Lógica Proposicional y Computacional
> 
> Este documento constituye un material de estudio exhaustivo basado en las sesiones académicas sobre lógica computacional. Está diseñado para proporcionar una comprensión desde los fundamentos hasta los niveles avanzados de la lógica proposicional, su aplicación técnica y el marco normativo de la cursada.
> 
> ## 1. Introducción General
> 
> La **lógica computacional**, específicamente en su vertiente proposicional, es la ciencia del **razonamiento deductivo**. Su propósito no es estudiar la naturaleza o el mundo físico, sino establecer las reglas de transformación válidas de las proposiciones.
> 
> ### Importancia y Relevancia
> 
> En el ámbito de la informática, la lógica es fundamental para:
> 
> - **Demostraciones matemáticas:** Validar la veracidad de estructuras complejas.
> - **Optimización de procesos:** Transformar expresiones extensas en formas equivalentes más breves. Esto permite que un microprocesador resuelva condiciones utilizando menos ciclos de ejecución y menos instrucciones.
> - **Programación:** Establecer condiciones precisas en estructuras de control (como `if` o bucles `while/for`).
> 
> ## 2. Marco Conceptual: Definición de Conceptos Clave
> 
> Para entender la lógica desde cero, es necesario precisar sus componentes básicos:
> 
> ### La Proposición
> 
> Es un enunciado declarativo del cual se puede decir, de manera inequívoca, que es **verdadero** o **falso**.
> 
> - **Requisito de Inequivocidad:** Si una expresión es subjetiva (ej. "¡Qué lindo día!") o es una orden o pregunta, no se considera una proposición en este sistema.
> - **Tipos de Proposiciones:**
>     1. **Atómicas (Simples):** Afirmaciones básicas que no contienen conectores lógicos (ej. "El cielo es celeste").
>     2. **Compuestas:** Proposiciones formadas por dos o más proposiciones atómicas unidas por conectores (ej. "El cielo es celeste y el sol brilla").
> 
> ### El Significado en Lógica
> 
> A diferencia del lenguaje natural, donde el significado puede ser ambiguo o metafórico, en la lógica proposicional el significado es **binario**:
> 
> - **Verdad (1)**
> - **Falsedad (0)** Cualquier proposición que tenga el mismo valor de verdad que otra se considera **equivalente** en términos lógicos, independientemente de si sus temas guardan relación entre sí.
> 
> ## 3. Desarrollo del Tema: Conectores y Tablas de Verdad
> 
> Los conectores lógicos son constantes que determinan el valor de verdad de una proposición compuesta. En esta materia se trabajan cuatro conectores fundamentales:
> 
> ### A. Negación (¬ o ~)
> 
> Invierte el valor de verdad de una proposición.
> 
> - Si P es 1, \neg P es 0.
> - Si P es 0, \neg P es 1.
> 
> ### B. Conjunción (y / \land / &&)
> 
> Es verdadera **únicamente** cuando ambas proposiciones que la componen son verdaderas.
> 
> ### C. Disyunción (o / \lor / ||)
> 
> Es falsa **únicamente** cuando ambas proposiciones que la componen son falsas. En el resto de los casos, es verdadera.
> 
> ### D. Condicional (entonces / \rightarrow)
> 
> Este conector vincula un **antecedente** (izquierda) con un **consecuente** (derecha). Es el conector más contraintuitivo del lenguaje natural.
> 
> - **Regla de oro:** El condicional es **falso únicamente** cuando el antecedente es verdadero y el consecuente es falso.
> - **Casos especiales:** Si el antecedente es falso (0 \rightarrow 1 o 0 \rightarrow 0), el resultado es automáticamente verdadero (1). Esto se debe a que, al no cumplirse la condición inicial, no se puede demostrar que la relación sea falsa.
> 
> ### Tabla Comparativa de Conectores
> 
> |   |   |   |   |   |
> |---|---|---|---|---|
> |P|Q|Disyunción (P \lor Q)|Conjunción (P \land Q)|Condicional (P \rightarrow Q)|
> |0|0|0|0|1|
> |0|1|1|0|1|
> |1|0|1|0|0|
> |1|1|1|1|1|
> 
> ## 4. Relaciones entre Conceptos y Reglas de Formación
> 
> La lógica no permite unir conceptos de cualquier manera. Existen **reglas de transformación** que regulan estas uniones:
> 
> 1. **Uso de Paréntesis:** Al incorporar un conector que une dos proposiciones atómicas para formar una compuesta, se deben utilizar paréntesis para evitar ambigüedades (ej. (P \land Q)).
> 2. **Jerarquía de Operaciones:** Al igual que en matemáticas, se resuelven primero las operaciones dentro de los paréntesis y luego los conectores externos.
> 3. **Equivalencia:** Dos proposiciones son equivalentes si sus tablas de verdad finales son idénticas.
> 
> ### Principios Básicos de la Lógica
> 
> - **Identidad:** Una proposición es equivalente a sí misma (P \equiv P).
> - **No Contradicción:** No es posible que una proposición sea verdadera y falsa al mismo tiempo: \neg(P \land \neg P).
> 
> ## 5. Ejemplos Prácticos y Traducción al Lenguaje L
> 
> Para trabajar en lógica, se utiliza un proceso de tres pasos:
> 
> 1. **Diccionario:** Definir qué letra representa cada proposición atómica (siempre en positivo).
> 2. **Traducción:** Pasar del lenguaje natural al lenguaje formal (L).
> 3. **Tabla de Verdad:** Evaluar el significado de la expresión resultante.
> 
> ### Caso 1: El Motor
> 
> - **Enunciado:** "Este motor no es ruidoso, pero consume mucha energía".
> - **Diccionario:**
>     - P: Este motor es ruidoso.
>     - Q: Este motor consume mucha energía.
> - **Traducción:** \neg P \land Q (El "pero" se traduce como una conjunción adversativa).
> 
> ### Caso 2: El Viceversa (Bicondicional implicado)
> 
> - **Enunciado:** "Si a María le duelen las rodillas, entonces está lloviendo y viceversa".
> - **Traducción:** (P \rightarrow Q) \land (Q \rightarrow P).
> - **Análisis:** Esto indica que la lluvia y el dolor de rodillas están vinculados en ambos sentidos. Solo será verdadero si ambos ocurren o si ninguno ocurre.
> 
> ## 6. Errores Comunes y Confusiones
> 
> - **El antecedente falso en el condicional:** Muchos estudiantes creen que si el antecedente es falso, el resultado debe ser falso o inválido. En lógica proposicional, un antecedente falso hace que el condicional sea **verdadero** por definición.
> - **Incluir conectores en el diccionario:** Un error frecuente es definir P como "No llueve". Lo correcto es definir P como "Llueve" y luego usar el conector de negación (\neg P) en la traducción.
> - **Ambigüedad del lenguaje natural:** Palabras como "pero", "aunque" o "sin embargo" suelen traducirse como conjunciones (\land), aunque en el lenguaje natural tengan matices distintos.
> 
> ## 7. Síntesis y Conclusiones
> 
> - La lógica proposicional es un **lenguaje artificial y formal** diseñado para eliminar la ambigüedad.
> - Se basa en **variables** (proposiciones P, Q, R) y **constantes** (conectores).
> - El objetivo final es la **deducción**: transformar información manteniendo siempre el valor de verdad original para optimizar procesos computacionales.
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> Tras analizar las fuentes, se detallan las siguientes indicaciones del profesor Manuel Buset:
> 
> |   |   |   |
> |---|---|---|
> |Fecha|Evento / Tipo|Descripción Detallada|
> |**17 de abril**|Ajuste de Calendario|Se menciona en relación a las fechas cercanas al feriado de mayo.|
> |**1 de mayo**|Feriado Nacional|No hay clases.|
> |**8 de mayo**|**Primer Parcial (Presencial)**|Evaluación de la primera parte: Lógica Proposicional.|
> |**Fin de cursada**|**Segundo Parcial**|Puede ser virtual o presencial (a definir). Temas: Lógica de Predicados.|
> 
> ### Avisos Académicos Relevantes:
> 
> - **Material de Estudio:** El material principal reside en la carpeta de **Google Drive** y el cronograma en un **Google Sheet**. El aula virtual (campus) se usará de forma secundaria para enlaces y foros.
> - **Asistencia:** Cada alumno debe registrar su presente en la planilla de cálculo compartida en el Drive ("Asistencia Lógica Computacional 2024/25").
> - **Comunicación:** El profesor utiliza el mail `bardgrif@...` (referenciado como el que responde siempre) y existe un grupo de WhatsApp para avisos rápidos.
> - **Sobre los Trabajos Prácticos (TP):** No es obligatorio enviarlos todos para corrección individual, pero se recomienda hacerlos para resolver dudas en clase. No influyen directamente en la nota si no se entregan, pero son la base del examen.
> - **Bibliografía Recomendada:**
>     - _Irving Copy:_ Más accesible (recomendado para iniciar).
>     - _Gamut:_ Más complejo (para profundizar).
> 
> ## 9. Preguntas de Repaso (Tipo Examen)
> 
> ### Nivel Básico
> 
> 1. Defina qué es una proposición y dé un ejemplo de una expresión que NO lo sea.
> 2. ¿Cuál es el único caso en que una conjunción (\land) resulta verdadera?
> 3. Si P=1 y Q=0, ¿cuál es el valor de \neg P \lor Q?
> 
> ### Nivel Intermedio
> 
> 4. Dada la frase "No es cierto que llueva y haga sol", realice el diccionario y la traducción lógica.
> 5. Explique por qué en lógica se dice que el significado de los conectores es constante.
> 6. Construya la tabla de verdad para \neg(P \rightarrow Q).
> 
> ### Nivel Avanzado
> 
> 7. ¿Por qué es útil para un programador saber transformar una proposición larga en una equivalente más corta?
> 8. Demuestre mediante tablas de verdad si (P \rightarrow Q) es equivalente a (\neg P \lor Q).
> 9. Explique la dificultad de traducir el término "pero" del lenguaje natural al lenguaje L y qué se pierde en ese proceso.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 2 - Lógica computacional" src="https://www.youtube.com/embed/6pKlizWj4_s?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1UluKlD7Plm3KqcvLLy--ITCvkkdLIYYO/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/15t55cTxGBLvxvtvox7gbJSq9cR_-j9PT/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>