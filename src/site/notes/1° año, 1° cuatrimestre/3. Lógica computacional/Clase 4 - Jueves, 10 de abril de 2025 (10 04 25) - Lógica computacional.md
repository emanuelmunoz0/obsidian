---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/3-logica-computacional/clase-4-jueves-10-de-abril-de-2025-10-04-25-logica-computacional/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía Completa de Estudio: Lógica Computacional y Técnicas de Programación
> 
> Este documento constituye una síntesis exhaustiva de los contenidos abordados en la cuarta sesión de la materia, diseñada para funcionar como material de referencia principal para el estudio avanzado de la lógica proposicional y su aplicación técnica.
> 
> ## 1. Introducción General
> 
> La lógica computacional es la base fundamental del razonamiento deductivo aplicado a la informática. Su propósito es transformar el lenguaje natural, inherentemente ambiguo y rico en matices, en un lenguaje artificial preciso (lógica proposicional) que pueda ser procesado por sistemas computacionales. Este proceso de traducción es crítico para la labor profesional, ya que permite convertir los requisitos de un cliente en instrucciones técnicas taxativas.
> 
> ## 2. Contexto y Relevancia
> 
> En el desarrollo de software, la lógica no es solo una disciplina teórica, sino una herramienta práctica. La capacidad de analizar enunciados complejos y determinar su valor de verdad es lo que permite construir estructuras condicionales e iterativas robustas.
> 
> ### Importancia en la Informática
> 
> - **Traducción de Requerimientos:** El programador actúa como puente entre el lenguaje del cliente y las condiciones del código.
> - **Precisión Técnica:** A diferencia del lenguaje humano, el lenguaje lógico solo admite dos significados: **verdad** y **falsedad**.
> - **Optimización:** El uso de herramientas de Inteligencia Artificial (como ChatGPT o Gemini) se destaca como una práctica complementaria para verificar traducciones y tablas de verdad, siempre bajo un criterio analítico humano.
> 
> ## 3. Marco Conceptual y Definiciones Clave
> 
> Para abordar el tema desde cero, es necesario comprender los componentes básicos del lenguaje de la lógica proposicional.
> 
> ### Conceptos Fundamentales
> 
> - **Variables Proposicionales:** Representadas por letras (P, Q, R, S, T), simbolizan afirmaciones que pueden ser verdaderas o falsas.
> - **Diccionario:** Es la tabla de equivalencias donde se define qué proposición del lenguaje natural corresponde a cada letra.
> - **Conectores Lógicos:** Constantes que vinculan proposiciones:
>     - **Negación (¬):** Invierte el valor de verdad.
>     - **Conjunción (y):** Verdadera solo si ambas partes lo son.
>     - **Disyunción (o):** Verdadera si al menos una parte lo es.
>     - **Condicional (entonces):** Establece una relación de causa (antecedente) y efecto (consecuente). Solo es falso si el antecedente es verdadero y el consecuente es falso.
>     - **Bicondicional (si y solo si):** Verdadera si ambas partes tienen el mismo valor de verdad.
> 
> ### Tipos de Resultados en Tablas de Verdad
> 
> 1. **Tautología:** La proposición es siempre verdadera, independientemente de los valores de las variables.
> 2. **Contradicción:** La proposición es siempre falsa.
> 3. **Contingencia:** El resultado puede ser verdadero o falso dependiendo de las combinaciones.
> 
> ## 4. Desarrollo del Tema: Traducción y Análisis Lógico
> 
> El análisis de la lógica se divide en dos grandes áreas: la **sintaxis** (formación correcta de las expresiones) y la **semántica** (el significado o valor de verdad).
> 
> ### Reglas de Formación Sintáctica
> 
> Para que una proposición sea considerada válida en el lenguaje lógico (L), debe cumplir reglas específicas:
> 
> - **Negación:** La negación se coloca a la izquierda de la proposición o letra. No requiere paréntesis adicionales por sí misma (ej. `¬¬P` es válido).
> - **Paréntesis:** Se utilizan para agrupar operaciones de conjunción, disyunción o condicional. Un error común es incluir paréntesis en letras solas o negaciones aisladas (ej. `(¬P)` es incorrecto si no hay una operación binaria asociada).
> - **Eliminación de Paréntesis:** El par de paréntesis más externo de una expresión puede omitirse por convención.
> 
> ### El Proceso de Traducción
> 
> Traducir implica identificar antecedentes y consecuentes, incluso si el orden en la oración original está invertido.
> 
> - **Horror al vacío (Horror Vacui):** Se debe evitar la tendencia a rellenar o complicar la traducción con elementos innecesarios solo para "completar" la expresión. La traducción debe ser lo más fiel y simple posible al significado lógico.
> 
> ## 5. Ejemplos Prácticos Explicados
> 
> ### Caso 1: Estructura de Antecedentes Invertidos
> 
> **Enunciado:** _"Si no está en verano, entonces está húmedo y hace frío si es de tarde o de noche"._
> 
> - **Diccionario:**
>     - P: Estamos en verano.
>     - Q: Está húmedo.
>     - R: Hace frío.
>     - S: Es de tarde.
>     - T: Es de noche.
> - **Análisis:** El antecedente principal es "no estar en verano" (`¬P`). Sin embargo, "si es de tarde o de noche" (`S ∨ T`) actúa como una condición adicional para que esté húmedo y haga frío (`Q ∧ R`).
> - **Traducción sugerida:** `¬P → ((S ∨ T) → (Q ∧ R))`
> - **Nota pedagógica:** Se debe priorizar la causalidad. No son dos oraciones separadas, sino una cadena de condiciones.
> 
> ### Caso 2: El "Solo Si" y el Condicional
> 
> **Enunciado:** _"Juan viene solo si Pedro no lo hace"._
> 
> - **Diccionario:**
>     - P: Juan viene.
>     - Q: Pedro viene.
> - **Traducción:** `P → ¬Q`
> - **Aclaración:** El "solo si" suele interpretarse como un condicional simple, no necesariamente un bicondicional, a menos que el contexto exija una equivalencia estricta en ambos sentidos.
> 
> ## 6. Técnicas de Programación Relacionadas
> 
> El manejo de la lógica es indisociable del uso de funciones nativas en lenguajes como JavaScript para resolver ejercicios prácticos (ej. el ejercicio del palíndromo).
> 
> |   |   |
> |---|---|
> |Función|Descripción|
> |`charAt()`|Permite acceder a un carácter específico en una cadena de texto.|
> |`toFixed(n)`|Formatea un número dejando exactamente `n` decimales.|
> |`Math.round()`|Redondea un número al entero más cercano.|
> 
> Estas funciones, combinadas con estructuras de **iteración** y **condicionales**, permiten resolver la totalidad de los problemas planteados hasta el nivel de examen parcial.
> 
> ## 7. Errores Comunes y Confusiones
> 
> 1. **Confusión entre Lenguaje Natural y Lógico:** En el lenguaje natural, una conjunción ("y") a veces puede sugerir una relación causal, pero en lógica es simplemente una unión de verdades.
> 2. **Uso Incorrecto de Paréntesis:** Agregar paréntesis a una letra proposicional sola (ej. `(P)`) o a una negación (ej. `(¬P)`) transgrede las reglas sintácticas de formación.
> 3. **Inversión de Antecedente/Consecuente:** Confundir la condición con el resultado. Siempre se debe buscar el "si" o el "cuando" para identificar el antecedente.
> 4. **Tiempos Verbales:** Generalmente, los tiempos verbales (pasado, presente, futuro) se simplifican a una única acción lógica, a menos que el cambio de tiempo altere el valor de verdad de manera independiente en la misma oración.
> 
> ## 8. Síntesis y Conclusiones
> 
> - La lógica proposicional reduce la ambigüedad del lenguaje humano a valores binarios (0 y 1).
> - La validez sintáctica de una expresión depende del cumplimiento estricto de las reglas de formación (paréntesis y posición de conectores).
> - Las tablas de verdad son el método para definir el significado semántico de una proposición.
> - El dominio de los condicionales y las iteraciones es suficiente para superar las evaluaciones de la primera unidad.
> 
> ## 9. Preguntas de Repaso (Tipo Examen)
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia entre una tautología y una contradicción?
> 2. Si una proposición tiene 3 letras proposicionales, ¿cuántas filas tendrá su tabla de verdad? (Respuesta: 2^3 = 8).
> 3. ¿Es válida la expresión `¬(¬P)` según las reglas de formación?
> 
> ### Nivel Intermedio
> 
> 4. Traduzca: "No te ayudaré si tú no me ayudas cuando te necesito".
> 5. Explique por qué el par de paréntesis más externo en una proposición puede ser omitido.
> 6. Dada la proposición `P → Q`, ¿en qué único caso el resultado es falso?
> 
> ### Nivel Avanzado
> 
> 7. Analice la siguiente expresión: `((P ∨ Q) ∧ ¬R) → S`. Si R es verdadero, ¿qué ocurre con el antecedente del condicional principal?
> 8. ¿Por qué se afirma que el bicondicional es difícil de hallar de forma pura en el lenguaje natural?
> 
> ## 10. Fechas Importantes y Avisos Académicos
> 
> Basado en la comunicación del profesor durante la clase:
> 
> - **Trabajos Prácticos:**
>     - **TP 1:** Debería estar corregido o con dudas ya despejadas.
>     - **TP 2:** Actualmente en resolución (ejercicios de traducción y tablas de verdad).
>     - **TP 3:** Ya se encuentra disponible para quienes deseen avanzar. Incluye temas de condicionales y estructuras de iteración.
> - **Próximas Clases:**
>     - **Lunes:** Clase de técnicas para terminar el TP 2 y comenzar el TP 3. Se recomienda traer dudas específicas sobre ejercicios como el del "palíndromo".
>     - **Semana Santa:** El jueves es feriado (no habrá clase). Se sugiere utilizar el lunes previo para consultas.
> - **Advertencia Académica:**
>     - Para el parcial, el manejo de condicionales e iteraciones es fundamental.
>     - En el parcial, si una tabla de verdad tiene 4 o más letras proposicionales (16+ combinaciones), no suele exigirse la tabla completa para optimizar tiempo, pero en los TPs es recomendable hacerla para practicar.
>     - Las tablas de 3 letras o menos **deben** realizarse de forma completa.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 4 - Lógica computacional" src="https://www.youtube.com/embed/027Fu0A3zIk?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/19YwpjmA7Nw0GFaEO8sxeHEioTcCdIeqw/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/15b69FwdAqAqLMvCX0gGBm4DXXJUyBkHw/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>