---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/3-logica-computacional/clase-10-jueves-19-de-junio-de-2025-19-06-25-logica-computacional/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio Completa: Lógica Computacional y Simplificación de Funciones Booleanas
> 
> Este documento constituye un material de estudio integral basado en los contenidos de la clase sobre lógica computacional, centrado en el análisis de proposiciones, el uso de tablas de verdad y, fundamentalmente, la simplificación de funciones mediante Mapas de Karnaugh.
> 
> ## 1. Introducción General
> 
> La lógica computacional es el pilar fundamental para el desarrollo de software y la arquitectura de sistemas. El estudio de esta disciplina permite transitar desde el lenguaje natural (la forma en que hablamos) hacia un lenguaje formal (matemático/lógico) que puede ser procesado por una computadora.
> 
> ### Contexto e Importancia
> 
> La relevancia de dominar la simplificación de funciones lógicas radica en la **eficiencia**. En la programación real (ya sea en Python, JavaScript o C#), una función simplificada consume menos recursos y es más fácil de mantener. Conceptos como la abstracción y el reconocimiento de patrones, tratados en esta guía, son aplicables desde el desarrollo de APIs hasta la implementación de modelos de _Machine Learning_.
> 
> ## 2. Marco Conceptual: Conceptos Clave
> 
> Para abordar la lógica computacional desde cero, es necesario definir los siguientes términos fundamentales:
> 
> - **Proposición:** Un enunciado que puede ser verdadero (1) o falso (0).
> - **Lenguaje Natural vs. Formal:** El proceso de "traducción" consiste en convertir oraciones cotidianas en expresiones lógicas utilizando variables (P, Q, R) y conectores (y, o, si... entonces).
> - **Tabla de Verdad:** Una herramienta gráfica que muestra todos los posibles resultados de una combinación lógica basándose en los valores de sus variables.
> - **Función Booleana:** Una expresión matemática que utiliza operadores lógicos. En el contexto de los mapas de Karnaugh, estas funciones se representan mediante ceros y unos.
> - **Mapa de Karnaugh (Mapa K):** Un método gráfico utilizado para simplificar funciones booleanas, reduciendo la cantidad de términos y variables necesarias.
> 
> ## 3. Desarrollo del Tema: Mapas de Karnaugh y Simplificación
> 
> La simplificación es el proceso de reducir una expresión lógica compleja a su forma mínima (**Función Mínima** o f_m).
> 
> ### 3.1. Proceso de Volcado en el Mapa
> 
> Cuando se tiene una función con variables (por ejemplo, A, B, C, D), cada término de la función representa un "1" en el mapa.
> 
> - Si una variable está negada (ej. \bar{A}), representa un 0.
> - Si una variable es normal (ej. A), representa un 1.
> 
> ### 3.2. Tratamiento de Variables Ausentes
> 
> Un error común es no saber cómo actuar cuando a un término le faltan variables (por ejemplo, en un sistema de 4 variables, tener solo el término AB).
> 
> - **Regla:** Si una variable no está especificada, se deben considerar **todos los valores posibles** para esa variable.
> - **Ejemplo:** Si tenemos solo A (donde A=0) en un sistema de 3 variables, debemos marcar en el mapa todas las combinaciones donde A es 0, independientemente de los valores de B y C (000, 001, 010, 011).
> 
> ### 3.3. Reglas de Agrupamiento (Grupitos)
> 
> Para simplificar, se deben agrupar los "unos" siguiendo reglas estrictas:
> 
> 1. **Potencias de 2:** Los grupos solo pueden ser de 1, 2, 4, 8 o 16 elementos. **No se permiten grupos de 3, 5 o 6.**
> 2. **Adyacencia:** Los "unos" deben estar uno al lado del otro (horizontal o vertical).
> 3. **Adyacencia Cíclica (Efecto "Pacman"):** El mapa es continuo. Los unos en los extremos izquierdo y derecho, o superior e inferior, se consideran adyacentes y pueden agruparse.
> 4. **Grupos más grandes:** Siempre se debe intentar realizar el grupo más grande posible para eliminar más variables.
> 
> ### 3.4. Técnica de Simplificación por Observación
> 
> Una vez formado un grupo, se observa qué variables cambian de valor dentro de ese grupo:
> 
> - Si una variable **cambia** (de 0 a 1 o de 1 a 0), esa variable **se elimina**.
> - Si una variable **se mantiene constante**, esa variable **permanece** en el término simplificado.
>     - Si se mantiene en 0, se escribe negada.
>     - Si se mantiene en 1, se escribe normal.
> 
> ## 4. Relaciones entre Conceptos y Estructuras
> 
> La lógica proposicional y los Mapas de Karnaugh están intrínsecamente conectados:
> 
> 1. **Enunciado en Lenguaje Natural** \rightarrow Traducción a Proposición.
> 2. **Proposición** \rightarrow Tabla de Verdad.
> 3. **Tabla de Verdad (valores verdaderos)** \rightarrow Mapa de Karnaugh.
> 4. **Mapa de Karnaugh** \rightarrow Simplificación (Función Mínima).
> 
> ## 5. Ejemplos Prácticos
> 
> ### Caso 1: Simplificación de 9 términos a 3
> 
> En una función con variables X, Y, Z, W, un mapa que inicialmente tiene 9 términos puede reducirse drásticamente. Si logramos un grupo de 4, eliminamos 2 variables de ese término. Si logramos un grupo de 8, eliminamos 3 variables.
> 
> ### Caso 2: Identificación en Exámenes (Opción Múltiple)
> 
> Para identificar qué función corresponde a un mapa sin resolver todo el ejercicio:
> 
> 1. Buscar un término que sea único en una de las opciones.
> 2. Verificar si ese término (y sus posibles combinaciones de variables ausentes) está representado en el mapa.
> 3. Descartar las opciones que no coincidan con la cantidad de términos o la posición de los "unos" clave.
> 
> ## 6. Errores Comunes y Confusiones
> 
> - **Inversión de Enunciados:** Un error frecuente ocurre al traducir frases como "Si se salvan vidas, entonces la gente usa cinturón". Muchos estudiantes confunden cuál es la causa (P) y cuál la consecuencia (Q). La estructura gramatical es vital para determinar el orden correcto en la fórmula lógica.
> - **Grupos no Óptimos:** Hacer muchos grupos pequeños en lugar de uno grande. Esto no invalida la función, pero no entrega la _función mínima_.
> - **Ignorar la Adyacencia de Extremos:** Olvidar que las esquinas o bordes opuestos pueden agruparse, lo que resulta en una simplificación incompleta.
> - **Confusión en Negaciones:** No prestar atención a si el negado aplica a una sola variable o a un paréntesis completo.
> 
> ## 7. Síntesis y Conclusiones
> 
> La lógica computacional no se trata solo de obtener un resultado "verdadero" o "falso", sino de entender la estructura del pensamiento y la eficiencia del procesamiento de datos. Los Mapas de Karnaugh son la herramienta visual por excelencia para lograr esta eficiencia, permitiendo que funciones extensas y "tediosas" se conviertan en expresiones elegantes y directas.
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> |   |   |   |
> |---|---|---|
> |Evento|Fecha|Descripción Detallada|
> |**Práctica 2: Mapas K**|Pendiente (esta semana)|Entrega virtual de ejercicios de Mapas de Karnaugh para justificar trabajo en clase.|
> |**Clase de Repaso / Juego**|Próxima clase|Se realizará un juego interactivo (Kahoot). El ganador podría quedar exento de traer insumos ("harinas") para el final.|
> |**Coloquio Final**|**3 de julio**|**Presencial.** Examen oral basado en la resolución de una función asignada.|
> 
> **Requisitos para el Coloquio Final (3 de julio):**
> 
> - Entregar una **hoja física** (impresa o manuscrita) que contenga: Nombre, Apellido, DNI, la función booleana asignada, la expresión binaria, el Mapa de Karnaugh con sus agrupaciones y la Función Mínima resultante.
> - **Instancia Oral:** El estudiante deberá explicar brevemente cómo pasó de la función al mapa, cómo agrupó y cómo simplificó.
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuáles son los tamaños permitidos para los grupos en un Mapa de Karnaugh?
> 2. ¿Qué sucede con una variable que cambia de valor (de 0 a 1) dentro de un grupo?
> 
> ### Nivel Intermedio
> 
> 1. Si tengo una función de 4 variables y un término es simplemente "A", ¿cuántos "unos" debo marcar en el mapa?
> 2. Explique el concepto de adyacencia cíclica con un ejemplo.
> 
> ### Nivel Avanzado
> 
> 1. Dada una tabla de verdad con 16 filas donde solo 4 resultados son "1", ¿cuál es la mejor estrategia para simplificar la función rápidamente?
> 2. ¿Por qué es fundamental realizar los grupos más grandes posibles en un Mapa K? Analice desde la perspectiva de la eliminación de variables.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 10 - Lógica computacional" src="https://www.youtube.com/embed/qWqBDGTtBSA?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1XE1YAN889eESo2Jh8U-Qb92In-HpZgjk/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1xLpVhCg6TFaPa6TCMnZkpR93Fb7as4iF/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>