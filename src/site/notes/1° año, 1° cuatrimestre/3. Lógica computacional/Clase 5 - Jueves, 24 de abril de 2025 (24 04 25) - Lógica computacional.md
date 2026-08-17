---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/3-logica-computacional/clase-5-jueves-24-de-abril-de-2025-24-04-25-logica-computacional/","dg-note-properties":{}}
---


> [!quote]- Resumen
> # Guía Integral de Lógica Computacional: Proposiciones, Argumentación y Evaluación Académica
> 
> Este documento constituye una síntesis exhaustiva de los fundamentos de la lógica proposicional y la teoría de la argumentación, diseñada como material de estudio avanzado. Cubre desde la estructura formal del lenguaje lógico hasta la validación de argumentos complejos y la identificación de falacias.
> 
> ## 1. Contexto e Importancia de la Lógica
> 
> La lógica se define como la **ciencia del razonamiento deductivo**. Su objeto de estudio es aquello que se sigue "necesariamente" de otras proposiciones; es decir, aquello que no puede variar y que debe ser de una forma específica sin lugar a la ambigüedad.
> 
> ### Relación entre Lenguaje Natural y Artificial
> 
> - **Lenguaje Natural (Castellano):** Es inherentemente ambiguo y depende del contexto de la vida cotidiana.
> - **Lenguaje Artificial (Lógica Proposicional -** **L****):** Es una construcción tecnológica que busca eliminar la confusión mediante reglas precisas. El significado en este ámbito se agota exclusivamente en el **valor de verdad** (verdadero o falso).
> 
> ## 2. Marco Conceptual: Definiciones Clave
> 
> Para comprender el desarrollo de la materia, es fundamental manejar los siguientes conceptos desde cero:
> 
> ### Letras Proposicionales y Variables
> 
> Las letras (como P, Q, R) son variables que representan proposiciones. No están comprometidas con un contenido específico, sino que pueden tomar valores de **1 (Verdadero)** o **0 (Falso)**.
> 
> ### Proposiciones Bien Formadas (PBF)
> 
> Una expresión solo se considera una proposición en el lenguaje L si cumple con las **reglas de formación**. Estas reglas determinan la correcta aplicación de negaciones, el uso de paréntesis y la disposición de conectores para evitar expresiones inválidas.
> 
> ### Tabla de Verdad y Significado
> 
> En lógica computacional, el significado de una proposición compuesta se expresa a través de su tabla de verdad. Esta muestra todas las combinaciones posibles de los valores de verdad de las proposiciones atómicas que la componen.
> 
> ### Tipos de Resultados en Tablas de Verdad
> 
> 1. **Tautología:** Cuando todas las combinaciones posibles de la proposición resultan en "Verdadero" (1). Es una verdad absoluta dentro del sistema lógico, independientemente del valor de las variables (ejemplo: P \lor \neg P).
> 2. **Contradicción:** Cuando todos los resultados son "Falso" (0).
> 3. **Contingencia:** Cuando los resultados varían entre verdadero y falso.
> 
> ### Conectores Especiales: El Bicondicional (\leftrightarrow)
> 
> A diferencia del condicional simple (\rightarrow), el bicondicional solo es verdadero cuando ambos componentes tienen el mismo valor de verdad.
> 
> |   |   |   |
> |---|---|---|
> |P|Q|P \leftrightarrow Q|
> |1|1|1|
> |1|0|0|
> |0|1|0|
> |0|0|1|
> 
> ## 3. Teoría de la Argumentación
> 
> Un argumento es una estructura compuesta por una o más **premisas** y una **conclusión**.
> 
> ### Validez vs. Valor de Verdad
> 
> Es crucial distinguir entre la validez de la **forma argumental** y el valor de verdad de las proposiciones:
> 
> - La validez depende de la estructura, no de si lo que se dice es fácticamente cierto en la realidad.
> - Se puede tener una forma argumental válida con premisas falsas.
> - **Definición de Argumento Válido:** Una forma argumental es válida si, y solo si, en todos los casos donde las premisas son verdaderas, la conclusión es **necesariamente** verdadera.
> 
> ### Demostración de Validez mediante Tablas de Verdad
> 
> Para verificar si un argumento es válido, se debe construir una proposición compuesta siguiendo estos pasos:
> 
> 1. Unir todas las premisas mediante conjunciones (\land).
> 2. Colocar esa unión como el **antecedente** de un condicional simple (\rightarrow).
> 3. Colocar la conclusión como el **consecuente**.
> 4. Si el resultado es una **tautología**, el argumento es válido.
> 
> ## 4. Formas Argumentales Clásicas
> 
> ### Modus Ponens (Válido)
> 
> Consiste en afirmar el antecedente de un condicional para obtener el consecuente.
> 
> - **Premisa 1:** P \rightarrow Q (Si es hombre, entonces es mortal)
> - **Premisa 2:** P (Sócrates es hombre)
> - **Conclusión:** Q (Sócrates es mortal)
> 
> ### Modus Tollens (Válido)
> 
> Consiste en negar el consecuente para negar el antecedente.
> 
> - **Premisa 1:** P \rightarrow Q (Si es hombre, entonces es mortal)
> - **Premisa 2:** \neg Q (Apolo no es mortal)
> - **Conclusión:** \neg P (Apolo no es hombre)
> 
> ### Silogismo Hipotético (Válido)
> 
> Establece una cadena de implicaciones.
> 
> - **Premisa 1:** P \rightarrow Q (Si hay sol, voy a la plaza)
> - **Premisa 2:** Q \rightarrow R (Si voy a la plaza, me quemo)
> - **Conclusión:** P \rightarrow R (Si hay sol, me quemo)
> 
> ### Falacia: Afirmación del Consecuente (Inválido)
> 
> Es una deformación del Modus Ponens y se considera una falacia porque, aunque las premisas sean verdaderas, la conclusión puede ser falsa.
> 
> - **Premisa 1:** P \rightarrow Q (Todo hombre es mortal)
> - **Premisa 2:** Q (Moby Dick es mortal)
> - **Conclusión:** P (Moby Dick es hombre) **-> FALSO**
> - **Análisis:** Esta forma es inválida porque permite un "contraejemplo": premisas verdaderas con conclusión falsa.
> 
> ## 5. Ejemplos Prácticos y Errores Comunes
> 
> ### El "Contraejemplo"
> 
> Para demostrar que un argumento es **inválido**, basta con encontrar un solo caso donde las premisas sean verdaderas pero la conclusión sea falsa (como el caso de Moby Dick siendo mortal pero no hombre).
> 
> ### Errores de Interpretación Frecuentes
> 
> - **Confundir Verdad con Validez:** Creer que porque la conclusión suena "lógica" o es "verdadera" en la realidad, el argumento es válido. La validez es puramente estructural.
> - **Uso de Falacias en la Retórica:** En política o publicidad se usan falacias (como la afirmación del consecuente) para convencer. Ejemplo: "Los deportistas exitosos usan esta marca; tú usas esta marca; por lo tanto, eres exitoso". La lógica demuestra que el éxito no se sigue necesariamente del uso de la marca.
> 
> ## 6. Fechas Importantes y Avisos Académicos
> 
> A partir del análisis de la sesión, se establecen los siguientes puntos clave para el trayecto de la materia:
> 
> - **Feriados:** Se confirman feriados el jueves 1 de mayo (Día del Trabajador) y el viernes 2 de mayo (feriado puente). No habrá actividad académica esos días.
> - **Fecha del Primer Parcial:** Jueves **8 de mayo**.
> - **Modalidad del Examen:** Se realizará en el laboratorio. Se prefiere la resolución en computadora (enviando el archivo por mail), aunque se permite el uso de papel y lápiz para quienes lo prefieran.
> - **Horario:** El ingreso es a las 18:30 hs, iniciando el examen aproximadamente a las 18:45 hs.
> 
> ### Contenidos Específicos del Parcial
> 
> El examen constará de tres puntos principales:
> 
> 1. **Traducción y Tablas:** Un enunciado en castellano para traducir a lenguaje formal L usando un diccionario, y la creación de su tabla de verdad.
> 2. **Verificación de PBF:** Identificar si expresiones dadas son "Proposiciones Bien Formadas" según las reglas de formación y corregir las que sean incorrectas.
> 3. **Argumentación / Equivalencia:** Determinar si un argumento es válido o inválido mediante tablas de verdad o verificar si dos proposiciones son equivalentes (tienen la misma tabla de verdad).
> 
> ## 7. Preguntas de Repaso (Tipo Examen)
> 
> ### Nivel Básico
> 
> 4. ¿Qué es una tautología y cómo se identifica en una tabla de verdad?
> 5. ¿Cuál es la diferencia principal entre el condicional (\rightarrow) y el bicondicional (\leftrightarrow)?
> 6. Si una expresión no cumple con las reglas de formación, ¿cómo se denomina en lógica?
> 
> ### Nivel Intermedio
> 
> 7. Dada la premisa P \rightarrow Q y la premisa \neg Q, ¿cuál es la conclusión válida según el Modus Tollens?
> 8. Explique por qué la validez de un argumento no depende de que sus premisas sean verdaderas en el mundo real.
> 9. ¿Qué sucede con el valor de verdad de un condicional si el antecedente es falso?
> 
> ### Nivel Avanzado
> 
> 10. Demuestre mediante una estructura de tabla de verdad por qué la "Afirmación del Consecuente" no es una tautología.
> 11. Construya un contraejemplo original para un argumento inválido que tenga la forma: P \rightarrow Q, Q \vdash P.
> 12. ¿Cuál es el procedimiento lógico paso a paso para unir premisas y conclusión en una sola fórmula para evaluar validez?

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 5 - Lógica computacional" src="https://www.youtube.com/embed/3_3QwALK-uc?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1o15dg2DhjRl1tOkDLzpYm4kiIVCipTaQ/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/17tOGC0hciW5vLFwo1rn2GhQ97rkky_XJ/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>