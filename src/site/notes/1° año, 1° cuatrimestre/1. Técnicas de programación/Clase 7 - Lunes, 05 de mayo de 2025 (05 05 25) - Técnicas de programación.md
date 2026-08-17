---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/1-tecnicas-de-programacion/clase-7-lunes-05-de-mayo-de-2025-05-05-25-tecnicas-de-programacion/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio Integral: Técnicas de Programación y Estructuras de Datos
> 
> Este documento constituye un material de estudio exhaustivo basado en las sesiones de resolución de trabajos prácticos y la introducción a estructuras de datos avanzadas. Está diseñado para proporcionar una comprensión profunda de los algoritmos clásicos, el manejo de arreglos y la preparación para evaluaciones académicas.
> 
> ## 1. Introducción General
> 
> El estudio de las técnicas de programación se centra en la resolución lógica de problemas mediante el uso de estructuras de control y de datos. En esta etapa, el enfoque se desplaza desde la lógica básica hacia la manipulación de **estructuras de datos lineales** (Arreglos) y la implementación de algoritmos matemáticos complejos, como la serie de Fibonacci y la identificación de números de Armstrong.
> 
> El objetivo principal es transitar de la resolución de problemas aislados a la creación de código reutilizable, mantenible y comprensible, priorizando la lógica manual sobre las funciones automatizadas del lenguaje para fortalecer la capacidad analítica del programador.
> 
> ## 2. Marco Conceptual y Definiciones Clave
> 
> Para comprender el desarrollo técnico, es fundamental asentar los siguientes conceptos:
> 
> ### 2.1 Arreglos (Arrays)
> 
> Un **Array** es una estructura de datos que permite almacenar múltiples valores bajo un mismo nombre de variable.
> 
> - **La Analogía de la Cajonera:** Si una variable simple es un "cajón" que guarda un valor, un Array es una "cajonera". Cada cajón (posición) tiene un número de índice que permite acceder a su contenido.
> - **Índices:** En programación, el conteo de los cajones siempre comienza en **0**. Por lo tanto, en un arreglo de 5 elementos, los índices van del 0 al 4.
> - **Dinamicidad:** En lenguajes como JavaScript, no es estrictamente necesario definir el tamaño del vector de antemano; este puede crecer o contraerse interactivamente.
> 
> ### 2.2 Métodos Comunes de Arreglos
> 
> Aunque existen múltiples funciones nativas, las más fundamentales son:
> 
> |   |   |
> |---|---|
> |Método|Función|
> |`push`|Agrega un nuevo elemento al final del arreglo (añade un "cajón").|
> |`pop`|Elimina el último elemento del arreglo.|
> |`length`|Propiedad que indica la cantidad total de elementos en el arreglo.|
> |`join`|Une todos los elementos del arreglo en una cadena de texto (string).|
> 
> ### 2.3 Strings como Arreglos
> 
> Un concepto avanzado pero crucial es que las cadenas de texto (**strings**) pueden ser tratadas como arreglos de caracteres. Cada letra o símbolo ocupa una posición indexada, lo que permite recorrer una palabra o número dígito por dígito utilizando estructuras de repetición.
> 
> ## 3. Desarrollo del Tema: Algoritmos y Lógica Aplicada
> 
> ### 3.1 La Serie de Fibonacci
> 
> La serie de Fibonacci es una secuencia matemática donde cada número es la suma de los dos anteriores, comenzando generalmente por 0 y 1.
> 
> - **Lógica de cálculo:**
>     1. Se definen valores base: F(0) = 0, F(1) = 1.
>     2. Para cualquier posición n > 1, la fórmula es: F(n) = F(n-1) + F(n-2).
> - **Implementación con Arreglos:** Para mostrar la serie completa hasta una posición X, se utiliza un ciclo `for` que calcula el siguiente valor, lo almacena en una variable temporal y luego lo añade al arreglo mediante el método `push`.
> 
> ### 3.2 Números de Armstrong (Narcisistas)
> 
> Un número de Armstrong es aquel que es igual a la suma de sus propios dígitos elevados a la potencia de la cantidad de dígitos que tiene.
> 
> - **Ejemplo paso a paso (153):**
>     1. Contar dígitos: 3.
>     2. Separar dígitos: 1, 5, 3.
>     3. Elevar cada uno a la potencia de 3: 1^3 + 5^3 + 3^3 = 1 + 125 + 27 = 153.
>     4. Resultado: 153 es un número de Armstrong.
> - **Técnica de programación:** Para resolver esto, se convierte el número a `string` para poder iterar sobre cada carácter (dígito), se realiza el cálculo matemático y se compara con el valor original.
> 
> ### 3.3 Construcción de Patrones Visuales (Pirámides)
> 
> La creación de patrones (como pirámides de asteriscos o números) requiere el uso de **bucles anidados** (un `for` dentro de otro `for`).
> 
> - **Bucle Exterior:** Controla las filas (la altura de la pirámide).
> - **Bucle Interior:** Controla las columnas (espacios en blanco y caracteres por fila).
> - **Desafío técnico:** El error común es no gestionar correctamente los espacios en blanco iniciales, lo que causa que la pirámide se alinee a la izquierda en lugar de quedar centrada.
> 
> ## 4. Buenas Prácticas y Depuración
> 
> ### 4.1 Refactorización y Legibilidad
> 
> Se recomienda "refactorizar" el código evitando métodos nativos complejos (como `filter`, `map` o `sort`) durante el aprendizaje. Utilizar estructuras básicas de iteración (`for`, `while`) hace que el código sea:
> 
> 1. **Más intuitivo:** Se entiende exactamente qué hace el algoritmo en cada paso.
> 2. **Más mantenible:** Es más fácil detectar errores si la lógica es explícita.
> 3. **Reusable:** El código basado en lógica pura es más fácil de trasladar entre diferentes lenguajes de programación.
> 
> ### 4.2 Errores Comunes
> 
> - **Asignación vs. Comparación:** Olvidar el signo igual (`=`) al declarar arreglos o confundir `=` con `==`.
> - **Bucles Infinitos:** No modificar la variable de control dentro de un ciclo, lo que bloquea el programa.
> - **Incompatibilidad de Navegadores:** Se ha detectado que en navegadores basados en Chromium (Edge, Brave), el uso rápido y sucesivo de ventanas emergentes (`alert`, `confirm`) puede bloquear la respuesta del mouse. En estos casos, usar la **barra espaciadora** para aceptar o cambiar a Firefox suele resolver el problema.
> 
> ## 5. Fechas Importantes y Avisos Académicos
> 
> Basado en el análisis de la comunicación docente y el cronograma, se establecen los siguientes puntos clave:
> 
> |   |   |   |
> |---|---|---|
> |Evento|Fecha / Detalle|Descripción Académica|
> |**Examen Parcial Presencial**|**12 de Mayo**|Examen de Técnicas de Programación.|
> |**Horario de Inicio**|18:30 a 18:45|El instituto abre a las 18:30; el examen suele iniciar 18:45.|
> |**Formato del Parcial**|Computadora / Papel|Se prefiere en computadora (envío por mail), pero se permite papel y lápiz.|
> |**Contenido del Parcial**|3 ejercicios|Generalmente: 1 fácil y 2 de mayor dificultad (similares a los TP).|
> |**Trabajo Práctico 4 (Lógica)**|Pendiente|Se resolverá/subirá próximamente tras el viaje del docente.|
> |**Trabajo Práctico 5**|Tarea / Post-Parcial|Incluye Arreglos (Arrays), pero **no entra en este parcial**.|
> 
> **Advertencia Académica:** El ayudante de cátedra podría estar presente para la toma de exámenes, aunque existe cierta incertidumbre sobre su nivel de información actual respecto a los temas específicos.
> 
> ## 6. Síntesis y Preguntas de Repaso
> 
> ### Ideas Principales
> 
> - Los **Arrays** son estructuras fundamentales para gestionar colecciones de datos mediante índices.
> - La **serie de Fibonacci** y los **números de Armstrong** son ejercicios clásicos para practicar la manipulación de tipos de datos y ciclos.
> - La claridad del código es preferible a la brevedad que ofrecen las funciones nativas avanzadas.
> 
> ### Preguntas de Repaso
> 
> 1. **Básica:** ¿Cuál es el índice del primer elemento en cualquier arreglo y por qué es importante recordarlo?
> 2. **Intermedia:** Explique cómo se puede usar una variable de tipo `string` para procesar los dígitos individuales de un número.
> 3. **Avanzada:** En un algoritmo de Fibonacci que utiliza arreglos, ¿por qué es necesario inicializar las dos primeras posiciones antes de comenzar el ciclo de suma?
> 4. **Lógica:** Si desea centrar una pirámide de asteriscos, ¿qué debe calcular el bucle interior antes de imprimir el primer asterisco de cada fila?

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 7 - Técnicas de programación" src="https://www.youtube.com/embed/Fc0LYXTN-KA?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1rfWL7i9eplcHFZFMT2wE3DMCn1ZKJiGj/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1KH3Xq3T90emBbmqLPlXPKicA42XquHzV/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>