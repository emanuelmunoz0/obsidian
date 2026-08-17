---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/3-logica-computacional/clase-3-jueves-03-de-abril-de-2025-03-04-25-logica-computacional/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía Completa de Lógica Computacional: Argumentos, Paradojas y Reglas de Formación
> 
> Este documento constituye un material de estudio integral sobre los fundamentos de la lógica computacional, centrándose en la distinción entre proposiciones y otras formas expresivas, la estructura de los argumentos válidos, el tratamiento de las paradojas y las reglas sintácticas para la formación de fórmulas en el lenguaje lógico.
> 
> ## 1. Contextualización del Tema
> 
> La lógica computacional se basa en el análisis de enunciados declarativos. Un concepto fundamental es la distinción entre el valor de verdad de las proposiciones atómicas (que pueden ser variables o estar ya definidas) y el significado de las proposiciones compuestas o traducciones, el cual se representa a través de la tabla de verdad completa. En el lenguaje natural, las proposiciones atómicas suelen ser variables, por lo que es necesario considerar todas las combinaciones posibles de sus valores de verdad para entender el significado global de una expresión.
> 
> ## 2. Marco Conceptual: Definición de Conceptos Clave
> 
> ### ¿Qué es una Proposición?
> 
> Una proposición es un enunciado declarativo que posee un único valor de verdad: es verdadera o es falsa.
> 
> ### Expresiones que NO son Proposiciones
> 
> Existen expresiones en el lenguaje natural que, aunque parecen proposiciones, carecen de un valor de verdad definido o no cumplen la función de afirmar algo sobre la realidad:
> 
> - **Órdenes o instrucciones:** (Ej: "Hagan esto", "Levántense"). No afirman hechos.
> - **Preguntas:** (Ej: "¿Está lloviendo?"). No son aseveraciones.
> - **Argumentos:** Son conjuntos de proposiciones, pero el argumento en sí no es verdadero ni falso, sino válido o inválido.
> - **Paradojas:** Expresiones que se contradicen a sí mismas y no pueden recibir un valor de verdad estable.
> 
> ## 3. Los Argumentos en la Lógica
> 
> Un argumento (o razonamiento) es un conjunto de proposiciones con una estructura específica donde una de ellas se deriva de las demás.
> 
> ### Estructura de un Argumento
> 
> - **Premisas:** Proposiciones que sirven de base o punto de partida.
> - **Conclusión:** La proposición que se sigue necesariamente de las premisas.
> 
> ### Validez vs. Verdad
> 
> Es crucial distinguir entre la **verdad** de las proposiciones y la **validez** del argumento:
> 
> - **Verdad:** Se refiere a si una proposición individual coincide con la realidad.
> - **Validez:** Se refiere a la forma lógica. Un argumento es válido si, **en caso de que todas las premisas sean verdaderas, la conclusión es necesariamente verdadera**. No puede existir un contraejemplo donde las premisas sean ciertas y la conclusión falsa.
> 
> **Nota importante:** Un argumento puede ser válido aunque sus premisas sean falsas, siempre que la estructura lógica se mantenga.
> 
> ### Formas Argumentales Comunes
> 
> #### Modus Ponens (Silogismo Estándar)
> 
> Es la forma más básica de la lógica. Se compone de una premisa general, una particular y una conclusión.
> 
> |   |   |   |
> |---|---|---|
> |Componente|Estructura Lógica|Ejemplo|
> |Premisa General|Todo X es Y|Todos los hombres son mortales.|
> |Premisa Particular|Z es X|Sócrates es un hombre.|
> |**Conclusión**|**Z es Y**|**Sócrates es mortal.**|
> 
> #### Falacias e Invalidez
> 
> Un argumento es inválido si la conclusión no tiene una conexión lógica necesaria con las premisas. Por ejemplo, afirmar "Todo X es Y" y "Z es Y" no permite concluir que "Z es X", ya que el conjunto Y puede ser más amplio que el conjunto X.
> 
> ## 4. Paradojas y Problemas del Lenguaje
> 
> ### La Paradoja del Mentiroso
> 
> Ejemplo: _"Esta proposición es falsa"_. Si es verdadera, entonces es falsa; si es falsa, entonces es verdadera. La lógica resuelve esto mediante la **Metalógica**, distinguiendo entre el lenguaje objeto (L) y el lenguaje que habla sobre el lenguaje (LM).
> 
> ### Entidades No Existentes
> 
> Un problema histórico en la lógica es cómo tratar proposiciones sobre sujetos que no existen (Ej: _"El rey de Francia es calvo"_).
> 
> - **Resolución:** Se utiliza el concepto de **Mundos Posibles**. La lógica no se refiere a la realidad física, sino a la coherencia del lenguaje. En un mundo posible donde exista un rey de Francia, la proposición tendrá un valor de verdad.
> - **Enfoque de los Griegos:** La lógica debe desentenderse de la realidad para lograr significados necesarios, refiriéndose únicamente al logos (lenguaje).
> 
> ## 5. Reglas de Formación del Lenguaje L
> 
> Para que una expresión sea considerada una "proposición de L" (fórmula bien formada), debe seguir estrictamente cuatro reglas:
> 
> 1. **Regla 1 (Letras Proposicionales):** Toda letra proposicional (P, Q, R, etc.) es una proposición de L.
> 2. **Regla 2 (Negación):** Si Q es una proposición, entonces \neg Q (no Q) también lo es. El símbolo de negación siempre precede a la proposición.
> 3. **Regla 3 (Conectores Binarios y Paréntesis):** Si P y Q son proposiciones, entonces (P \land Q), (P \lor Q) y (P \to Q) también lo son. **Nota:** Esta regla exige el uso de paréntesis al introducir conectores.
> 4. **Regla 4 (Cláusula de Cierre):** Solo son proposiciones aquellas expresiones generadas mediante las reglas 1, 2 y 3 en un número finito de pasos.
> 
> ### Uso de Paréntesis
> 
> - Técnicamente, cada conector binario requiere un par de paréntesis.
> - En la práctica, los paréntesis externos de una proposición completa pueden omitirse por convención, ya que no generan ambigüedad. Sin embargo, en expresiones internas son obligatorios para determinar el alcance de los conectores.
> 
> ## 6. Ejemplos Prácticos y Errores Comunes
> 
> ### Ambigüedad en la Negación
> 
> En el lenguaje natural, el alcance de "No es el caso que..." puede ser ambiguo.
> 
> - _Traducción 1:_ \neg P \land (Q \lor S) (La negación solo afecta a P).
> - _Traducción 2:_ \neg ( (Q \lor S) \to P ) (La negación afecta a toda la estructura). Ambas pueden ser correctas dependiendo de la interpretación del contexto, pero darán tablas de verdad distintas.
> 
> ### Errores en Argumentos
> 
> Un error común es invertir el antecedente y el consecuente en un condicional.
> 
> - **Correcto:** Si llueve (antecedente), entonces hay nubes (consecuente).
> - **Incorrecto:** Si hay nubes, entonces llueve. (No es una deducción necesaria).
> 
> ## 7. Síntesis y Conclusiones
> 
> - La lógica se ocupa del **lenguaje**, no de la realidad empírica.
> - Un **argumento** es válido por su forma, independientemente de la verdad de sus premisas.
> - El **significado** de una proposición compuesta es su tabla de verdad completa.
> - Las **reglas de formación** aseguran que el lenguaje sea artificialmente preciso y libre de las ambigüedades del lenguaje natural.
> 
> ## 8. Preguntas de Repaso
> 
> **Básicas:**
> 
> 1. ¿Cuál es la definición de proposición en lógica?
> 2. ¿Por qué una pregunta o una orden no son proposiciones?
> 3. ¿Cuál es la diferencia entre una proposición atómica y una compuesta?
> 
> **Intermedias:** 4. Explique la diferencia entre validez y verdad en un argumento. 5. ¿Cuáles son los elementos que componen un Modus Ponens? 6. Si una expresión en L no tiene paréntesis al usar un conector condicional, ¿es una proposición válida según las reglas de formación?
> 
> **Avanzadas:** 7. ¿Cómo resuelve la metalógica la paradoja del mentiroso? 8. Explique por qué el argumento "Todos los animales son amarillos; mi pez es amarillo; por lo tanto, mi pez es un animal" es inválido, aunque todas sus partes puedan parecer verdaderas en algún contexto.
> 
> ## 9. Fechas importantes y avisos académicos
> 
> Basado en la sesión analizada, se establecen los siguientes recordatorios y avisos:
> 
> - **Lunes (Próxima sesión): Clase Presencial**
>     - **Horario estimado:** 18:45 hs (apertura del instituto 18:30 hs).
>     - **Ubicación:** Laboratorio (y aula adicional con Netbooks si es necesario).
>     - **Objetivo:** Repaso personalizado y paso a paso de los ejercicios para estudiantes que tengan dificultades con el arranque de la materia.
>     - **Recomendación:** Los estudiantes que ya resuelven los ejercicios sin inconvenientes no tienen obligación de asistir, para permitir mayor concentración en quienes necesitan apoyo.
> - **Lunes (Sesión Virtual): Meet de consulta**
>     - **Horario:** 20:00 hs a 21:00 hs.
>     - **Descripción:** El profesor se conectará al Meet habitual para resolver dudas de quienes no asistieron a la parte presencial o tengan consultas finales.
> - **Material de estudio:**
>     - Las grabaciones de las clases están disponibles en el **archivo de asistencias**.
>     - Los archivos de anotaciones y resolución de TP1 y TP2 se encuentran en la carpeta compartida.
> - **Recordatorios de Tareas:**
>     - Se debe completar la resolución del **Trabajo Práctico 2 (TP2)**, específicamente la sección de Reglas de Formación (Ejercicio C).
>     - Revisar las correcciones del **TP1** (valores de verdad y traducciones).

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 3 - Lógica computacional" src="https://www.youtube.com/embed/PTEj6A6Ld6E?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1f1ZcJOh2SD9uWAk9KWJyxmsVNwMvnPKD/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1OpcgFucLFdettRlAC6GHUIWDaPc55J6a/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>