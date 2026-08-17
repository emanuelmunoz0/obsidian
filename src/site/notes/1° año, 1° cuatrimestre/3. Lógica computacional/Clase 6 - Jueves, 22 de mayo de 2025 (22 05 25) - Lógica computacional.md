---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/3-logica-computacional/clase-6-jueves-22-de-mayo-de-2025-22-05-25-logica-computacional/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio Completa: Lógica Computacional y Compuertas Lógicas
> 
> Este documento constituye un material de estudio integral sobre la lógica computacional aplicada a circuitos, sintetizando los conceptos fundamentales, el funcionamiento de las compuertas lógicas y la metodología para la interpretación de expresiones booleanas a partir de diagramas.
> 
> ## 1. Introducción General
> 
> Las compuertas lógicas son dispositivos electrónicos o abstracciones matemáticas que operan con **estados lógicos**. Su funcionamiento es análogo al de una calculadora: reciben datos de entrada, ejecutan una operación específica y entregan un resultado de salida. Mientras que una calculadora convencional realiza operaciones aritméticas, las compuertas lógicas ejecutan **operaciones lógicas**.
> 
> En el mundo real, estas compuertas no son solo dibujos en un papel, sino componentes físicos integrados en chips o circuitos integrados. Cada "patita" del chip puede representar una entrada o una salida, y el proceso interno determina el resultado basado en la presencia o ausencia de señales eléctricas.
> 
> ## 2. Marco Conceptual y Definiciones Clave
> 
> Para comprender la lógica computacional desde cero, es necesario dominar los siguientes términos:
> 
> ### Estados Lógicos (0 y 1)
> 
> La lógica computacional trabaja con un sistema binario. Estos estados se pueden interpretar de diversas formas según el contexto:
> 
> - **1:** Verdadero, "Hay energía", Voltaje alto, Encendido.
> - **0:** Falso, "No hay energía", Voltaje bajo (o nulo), Apagado.
> 
> ### Tablas de Verdad
> 
> Es una herramienta gráfica que muestra todas las posibles combinaciones de valores de entrada para un sistema lógico y sus respectivos valores de salida. Permite predecir el comportamiento de cualquier circuito o enunciado.
> 
> ### Normas de Representación
> 
> Generalmente se utiliza la norma **ANSI** para los gráficos de las compuertas. Cada operación tiene una forma geométrica distintiva para evitar errores de interpretación.
> 
> ### Reglas de Conexión de Cables
> 
> 1. **Sentido de flujo:** Por norma, los circuitos se leen de izquierda (entradas) a derecha (salidas).
> 2. **No cruce de señales:** No se pueden juntar dos señales distintas (A y B) en un solo cable sin que pasen por una compuerta.
> 3. **Nodos:** Un punto negro en una intersección de cables indica un "empalme" o unión, donde la misma señal se distribuye hacia dos o más direcciones.
> 4. **Saltos:** Si un cable pasa sobre otro sin conectarse, se suele representar con un pequeño arco o "saltito" para indicar que no hay contacto eléctrico.
> 
> ## 3. Desarrollo del Tema: Las Compuertas Lógicas
> 
> A continuación se detallan las compuertas fundamentales, su función y su representación algebraica y booleana.
> 
> ### A. Compuerta NOT (Inversora)
> 
> Es la única compuerta que recibe una sola entrada. Su función es invertir la señal.
> 
> - **Funcionamiento:** Si entra 1, sale 0. Si entra 0, sale 1.
> - **Representación:** Un triángulo con un pequeño círculo en la punta.
> - **Simbología:** En expresiones booleanas se usa una "L" acostada (\neg) o un signo menos (-). En álgebra se representa con una barra sobre la letra (\bar{A}).
> 
> ### B. Compuerta AND (Multiplicación Lógica)
> 
> Representa la conjunción "Y".
> 
> - **Funcionamiento:** La salida es 1 **solo si todas** las entradas son 1. Si hay una sola entrada en 0, el resultado es 0.
> - **Analogía:** Una puerta con múltiples trabas; solo se abre si todas las trabas están abiertas simultáneamente.
> - **Forma:** Similar a una letra "D".
> 
> ### C. Compuerta OR (Suma Lógica)
> 
> Representa la disyunción "O".
> 
> - **Funcionamiento:** La salida es 1 si **al menos una** de las entradas es 1. Solo da 0 cuando todas las entradas son 0.
> - **Forma:** Base curva y punta afilada (como una punta de flecha).
> 
> ### D. Compuertas Negadas (NAND y NOR)
> 
> Son versiones invertidas de las compuertas básicas. Se identifican por tener un círculo pequeño en la salida.
> 
> - **NAND (AND negada):** Da como resultado 0 solo cuando todas las entradas son 1. En cualquier otro caso, da 1.
> - **NOR (OR negada):** Da como resultado 1 solo cuando todas las entradas son 0. Si hay algún 1, la salida es 0.
> 
> ### E. Compuertas de Comparación (XOR y XNOR)
> 
> Estas compuertas suelen admitir solo dos entradas debido a su especificidad.
> 
> - **XOR (OR Exclusiva / SOR):** Detecta cuando las señales son **diferentes**. Da 1 si una entrada es 1 y la otra es 0. Si son iguales (ambas 0 o ambas 1), da 0.
> - **XNOR (NOR Exclusiva / SNOR):** Detecta cuando las señales son **iguales**. Da 1 si ambas entradas son 0 o ambas son 1.
> 
> ## 4. Relaciones entre Conceptos: De Circuitos a Expresiones
> 
> La conversión de un diagrama a una expresión booleana requiere un análisis secuencial:
> 
> 1. **Identificación de entradas:** Listar las variables (P, Q, R, etc.) situadas a la izquierda.
> 2. **Procesamiento por etapas:** Resolver de izquierda a derecha, creando sub-expresiones para cada compuerta.
> 3. **Uso de paréntesis:** Es fundamental para mantener el orden jerárquico. Lo que entra por la parte superior de una compuerta suele agruparse en un paréntesis, y lo que entra por la parte inferior en otro.
> 4. **Negaciones grupales:** Si una compuerta tiene un círculo a la salida (como NAND o NOR), la negación afecta a todo el bloque previo encerrado en paréntesis.
> 
> ## 5. Ejemplos Prácticos y Resolución Paso a Paso
> 
> ### Análisis de Circuitos Complejos
> 
> Para resolver un circuito extenso (denominado coloquialmente "un choclo"), se debe seguir esta lógica:
> 
> - **Paso 1:** Identificar qué señal llega a cada cable. Si hay un nodo, la señal se duplica.
> - **Paso 2:** Escribir la operación de la primera compuerta. Ejemplo: Si entra P y Q a un AND, escribimos `(P y Q)`.
> - **Paso 3:** Si esa salida va a un NOT, aplicamos la negación: `-(P y Q)`.
> - **Paso 4:** Unir las señales en la compuerta final. Si la última compuerta es un OR que recibe la señal de arriba (A) y la de abajo (B), la expresión final será `(A) o (B)`.
> 
> ### El concepto de Nodos
> 
> Si una señal `A` tiene un punto negro (nodo) y se bifurca en tres cables, esos tres cables transportan la señal `A`. No se requiere una compuerta nueva para duplicar una señal.
> 
> ## 6. Errores Comunes y Aclaraciones
> 
> - **Confusión de formas:** Confundir el AND (D plana) con el OR (punta curva). Esto altera totalmente la tabla de verdad del sistema.
> - **Negación mal ubicada:** Colocar el símbolo de negación delante de una variable (`-P`) no es lo mismo que colocarlo delante de un paréntesis (`-(P o Q)`). Lo primero niega solo a P; lo segundo es una compuerta NOR.
> - **Omisión de paréntesis:** En circuitos largos, no usar paréntesis o corchetes puede causar que se pierda la relación de qué señal entra en qué compuerta, invalidando el resultado final.
> - **Mezcla de señales:** Intentar unir dos cables directamente sin una compuerta. Esto está prohibido por las reglas de la lógica computacional.
> 
> ## 7. Síntesis y Conceptos Avanzados
> 
> ### Leyes de De Morgan
> 
> Permiten simplificar enunciados complejos. Establecen equivalencias entre negaciones de conjunciones y disyunciones. Por ejemplo, negar un "Y" es equivalente a un "O" con sus componentes negados individualmente.
> 
> ### Tautologías y Contradicciones
> 
> - **Tautología:** Cuando, sin importar los valores de entrada, la salida del circuito siempre es 1 (Verdadero).
> - **Contradicción:** Cuando la salida siempre es 0 (Falso), independientemente de las entradas.
> 
> ### Resumen de Operaciones
> 
> |   |   |   |
> |---|---|---|
> |Compuerta|Operación Aritmética|Condición para Salida = 1|
> |**AND**|Multiplicación|Todas las entradas en 1|
> |**OR**|Suma Lógica|Al menos una entrada en 1|
> |**NOT**|Inversión|Entrada en 0|
> |**XOR**|Comparación|Entradas diferentes|
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la función principal de una compuerta NOT?
> 2. ¿Qué forma geométrica identifica a una compuerta AND según la norma ANSI?
> 3. Si una compuerta OR tiene 10 entradas y solo una de ellas es 1, ¿cuál es el resultado de salida?
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia fundamental entre una compuerta OR y una compuerta XOR.
> 5. ¿Qué indica la presencia de un pequeño círculo en la salida de una compuerta?
> 6. ¿Cómo se representa algebraicamente una señal negada?
> 
> ### Nivel Avanzado
> 
> 7. Dada una compuerta NAND con entradas A y B, ¿en qué único caso la salida será 0?
> 8. Defina el concepto de Tautología y explique cómo se relaciona con las tablas de verdad.
> 9. Si un circuito tiene un nodo en la señal de entrada Q que se dirige a dos compuertas distintas, ¿qué valor recibe cada compuerta si Q = 1?
> 
> ## 9. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de la sesión, se destacan las siguientes informaciones relevantes para el seguimiento de la materia:
> 
> - **Cambio de Profesor:** Se informa que a partir de la próxima semana, el docente **Luciano** asumirá el dictado de las clases, relevando a los docentes actuales (Manu/Damián).
> - **Material de Estudio:** Todas las diapositivas, ejercicios y la imagen de referencia de las compuertas lógicas (machete) se encuentran disponibles en el **Aula Virtual** o mediante el enlace de Drive compartido durante la sesión.
> - **Próximos Temas:** Se anticipa que los siguientes contenidos de alta complejidad incluirán las **Leyes de De Morgan**, **Tautologías** y **Simplificación de enunciados**.
> - **Evaluación:** Se recomienda practicar la conversión de circuitos a expresiones booleanas, ya que es un tema central para las futuras evaluaciones.
> 
> **Nota:** Este documento es autosuficiente para el estudio del tema "Compuertas Lógicas" según lo impartido en la Clase 6 de Lógica Computacional.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 6 - Lógica computacional" src="https://www.youtube.com/embed/j_18MEemXnA?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1cGLy3OkRk_8qkivPlPsbbGOZhjJGCbNy/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1D6lUWHBR_c1llUcx55eUEyoWd0HVFKgp/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>