---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/2-analisis-matematico/clase-8-miercoles-04-de-junio-de-2025-04-06-25-analisis-matematico/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía Integral de Estudio: Funciones Inversas, Compuestas y Sistemas de Ecuaciones Lineales
> 
> Este documento constituye un material de estudio exhaustivo basado en el análisis avanzado de funciones y la introducción a los sistemas de ecuaciones lineales. Está diseñado para facilitar el aprendizaje desde conceptos fundamentales hasta aplicaciones complejas, integrando teoría, procedimientos prácticos y advertencias académicas.
> 
> ## 1. Introducción General
> 
> El análisis matemático moderno se fundamenta en la comprensión de cómo las funciones interactúan entre sí y cómo pueden revertirse sus procesos. Este documento explora la **composición de funciones**, la naturaleza de la **invensibilidad** a través de la inyectividad y biyectividad, y los métodos algebraicos para resolver **sistemas de ecuaciones lineales**, con especial énfasis en el método de Gauss.
> 
> ## 2. Marco Conceptual y Definición de Conceptos Clave
> 
> Para comprender los temas avanzados, es imperativo dominar las siguientes definiciones desde cero:
> 
> ### A. Inyectividad
> 
> Una función es **inyectiva** cuando a elementos distintos del dominio les corresponden imágenes distintas.
> 
> - **En palabras sencillas:** No es posible que dos entradas diferentes produzcan la misma salida.
> - **Ejemplo:** Una función lineal es inyectiva. Una función cuadrática (parábola) **no** lo es, ya que, por su simetría, dos valores de x diferentes (como 2 y -2) pueden dar el mismo resultado de y (en este caso, 4).
> 
> ### B. Sobreyectividad
> 
> Una función es **sobreyectiva** cuando su imagen coincide plenamente con su codominio.
> 
> - **Contexto Académico:** En este nivel de estudio, se asume por convención que las funciones trabajadas son sobreyectivas, a menos que se aplique una restricción específica.
> 
> ### C. Biyectividad
> 
> Una función es **biyectiva** si cumple simultáneamente con ser inyectiva y sobreyectiva.
> 
> - **Importancia:** Este es el requisito indispensable para que una función admita una **función inversa**.
> 
> ### D. Función Identidad
> 
> Es aquella función donde el valor de entrada es igual al valor de salida (f(x) = x). Se denomina así porque no altera el elemento original tras su aplicación.
> 
> ## 3. Desarrollo del Tema: Composición y Función Inversa
> 
> ### 3.1 Composición de Funciones
> 
> La composición de funciones es el proceso de "anidar" funciones (función de función). Se representa como f(g(x)).
> 
> - **Condición de Existencia:** Para que la composición sea posible, la **imagen de la primera función** debe estar comprendida dentro del **dominio de la segunda función**. En términos prácticos: "lo que entrega la primera debe ser admitido por la segunda".
> - **Restricciones:** Si la condición de existencia no se cumple, es necesario restringir el dominio de la primera función para limitar su salida y que sea compatible con la entrada de la segunda.
> 
> ### 3.2 Función Inversa (f^{-1})
> 
> La función inversa consiste básicamente en intercambiar la entrada por la salida, o el dominio por la imagen.
> 
> #### Procedimiento para hallar la inversa:
> 
> 1. **Verificar Biyectividad:** Asegurarse de que la función sea inyectiva.
> 2. **Intercambio de Variables:** En la ecuación original, sustituir todas las x por y (o f), y las y por x.
> 3. **Despeje:** Resolver la ecuación para dejar la nueva y (la inversa) aislada.
> 
> **Nota Crítica sobre Nomenclatura:** El símbolo f^{-1} **no indica una potencia** (no significa elevar a la -1), sino que representa la función inversa, similar a la simbología utilizada en las calculadoras científicas.
> 
> ### 3.3 Restricción de Funciones Cuadráticas
> 
> Dado que las parábolas no son inyectivas (tienen dos ramas simétricas), para hallar su inversa es necesario realizar una **restricción de rama**:
> 
> - Se calcula el vértice de la parábola (x_v = -b / 2a).
> - Se selecciona, por convención, la **rama derecha** (desde el vértice hacia el infinito positivo).
> - Al trabajar solo con media parábola, la función se vuelve inyectiva y puede invertirse (resultando generalmente en una raíz cuadrada).
> 
> ## 4. Relación entre Conceptos: Verificación de Inversas
> 
> Una de las formas más seguras de comprobar si dos funciones son inversas entre sí es mediante la composición.
> 
> - **Regla de Oro:** Si componemos una función con su inversa, el resultado debe ser siempre la **función identidad** (x).
>     - f(f^{-1}(x)) = x
>     - f^{-1}(f(x)) = x
> - **Analogía:** Es como realizar una acción y luego su acción opuesta; se regresa exactamente al punto de inicio.
> 
> ## 5. Sistemas de Ecuaciones Lineales
> 
> Un sistema de ecuaciones consiste en un conjunto de igualdades con múltiples incógnitas que deben verificarse simultáneamente.
> 
> ### Clasificación de Sistemas
> 
> |   |   |   |
> |---|---|---|
> |Tipo de Sistema|Descripción Geométrica|Cantidad de Soluciones|
> |**Compatible Determinado**|Las rectas se cortan en un punto.|Una única solución.|
> |**Compatible Indeterminado**|Las rectas son coincidentes (una sobre otra).|Infinitas soluciones.|
> |**Incompatible**|Las rectas son paralelas y no se tocan.|No tiene solución.|
> 
> ### El Método de Gauss y Sistemas Equivalentes
> 
> El método de Gauss busca transformar un sistema complejo en uno más sencillo mediante **sistemas equivalentes**. Dos sistemas son equivalentes si tienen el mismo conjunto solución.
> 
> **Operaciones Permitidas (Algoritmo de Gauss):**
> 
> 1. Multiplicar una ecuación por un **escalar** (un número real distinto de cero).
> 2. Sumar o restar ecuaciones entre sí.
> 
> **Objetivo:** Utilizar estas operaciones para "anular" coeficientes (convertirlos en cero) y así despejar las incógnitas de forma progresiva.
> 
> ## 6. Ejemplos Prácticos
> 
> ### Ejemplo 1: Cálculo de Inversa (Función Lineal)
> 
> Sea f(x) = 3x + 2. Hallar f^{-1}.
> 
> 1. Intercambiamos: x = 3y + 2.
> 2. Despejamos y:
>     - x - 2 = 3y
>     - (x - 2) / 3 = y
> 3. Resultado: f^{-1}(x) = \frac{1}{3}x - \frac{2}{3}.
> 
> ### Ejemplo 2: Aplicación del Método de Gauss (2x2)
> 
> Ecuación 1: 2x_1 - x_2 = 3 Ecuación 2: x_1 + 2x_2 = -1
> 
> - Para anular x_1 en la segunda fila, podemos crear una fila equivalente: **(Fila 2 * 2) - Fila 1**.
> - Operación: (2*1 - 2) = 0; (2*2 - (-1)) = 5; (2*(-1) - 3) = -5.
> - Nueva Ecuación 2: 5x_2 = -5 \rightarrow x_2 = -1.
> 
> ## 7. Errores Comunes y Confusiones
> 
> - **Confusión de Potencia:** Creer que f^{-1}(x) es 1/f(x). En funciones, el superíndice -1 significa "inversa", no recíproco.
> - **Omitir la Verificación de Dominio:** Intentar componer funciones sin revisar si la imagen de la primera es admitida por el dominio de la segunda.
> - **Inconsistencias de Gauss:** En un sistema **incompatible**, el algoritmo de Gauss arrojará una contradicción matemática (ejemplo: 0 = 9). Si el sistema es **indeterminado**, un renglón completo se convertirá en ceros (0 = 0), indicando que una ecuación era dependiente de la otra.
> 
> ## 8. Síntesis y Conclusiones
> 
> - Para que exista una inversa, la función debe ser **biyectiva**.
> - Las funciones cuadráticas requieren **restricciones de dominio** para poder ser invertidas.
> - La **composición** de una función con su inversa siempre devuelve la **variable original (x)**.
> - Los sistemas de ecuaciones se resuelven mediante **operaciones de equivalencia** que no alteran la solución pero simplifican la estructura del sistema.
> 
> ## 9. Preguntas de Repaso
> 
> 1. **Básica:** ¿Cuál es la diferencia fundamental entre una función inyectiva y una que no lo es?
> 2. **Intermedia:** ¿Por qué es necesario calcular el vértice de una parábola antes de intentar hallar su función inversa?
> 3. **Avanzada:** Durante el método de Gauss, si al operar obtienes una fila con los valores [0, 0, 0], ¿qué puedes concluir sobre el sistema y sus soluciones?
> 4. **Práctica:** Realice la composición de f(x) = x + 1 y g(x) = \sqrt{x}. ¿Qué restricción debe aplicarse para que la composición sea válida?
> 
> ## 10. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de las directivas docentes, se establecen los siguientes puntos clave para el calendario académico:
> 
> - **Tercer Examen Parcial:**
>     - **Fecha:** 18 de junio (se adelantó una semana respecto a la fecha original).
>     - **Temario Incluido:**
>         - Función Inversa.
>         - Función Compuesta.
>         - Sistemas de Ecuaciones (Primera parte: conceptos y método de Gauss).
>     - **Formato:** Se indicó que el examen será más corto de lo habitual.
> - **Aviso sobre Casos Especiales:** Los alumnos que tengan dificultades con la nueva fecha debido al adelanto deben enviar un correo electrónico al profesor de forma anticipada explicando su situación.
> - **Estado de Calificaciones:** Las notas de los parciales anteriores aún no han sido enviadas; se encuentran en proceso de corrección final.
> - **Tareas Pendientes:** Realizar los ejercicios restantes del TP de Función Inversa (puntos A, B y D del ejercicio 4) y completar el ejercicio 1 para la próxima clase. En la siguiente sesión se corregirán estos ejercicios y se profundizará en Sistemas de Ecuaciones de 3x3.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 8 - Análisis matemático" src="https://www.youtube.com/embed/NlH45Zypoag?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1MFlbYO0gJrKFWC13T1zDDfr3eRzk-Uyf/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1nkLXOKOvGvZTxlN1PVG-nmle4yAIc_Vz/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>