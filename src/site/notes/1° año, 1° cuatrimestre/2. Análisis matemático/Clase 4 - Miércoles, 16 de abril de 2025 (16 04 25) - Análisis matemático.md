---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/2-analisis-matematico/clase-4-miercoles-16-de-abril-de-2025-16-04-25-analisis-matematico/","dg-note-properties":{}}
---

> [!quote]- Resumen
> Guía de Estudio Completa: Análisis Matemático - Inecuaciones y Función Lineal
> 
> Este documento constituye un material de estudio integral basado en las sesiones académicas sobre Análisis Matemático. Cubre desde la resolución de desigualdades complejas hasta los fundamentos y aplicaciones de la función lineal, proporcionando las herramientas necesarias para el dominio teórico y práctico de la materia.
> 
> 1. Introducción General
> 
> El estudio del análisis matemático en este nivel se centra en dos grandes pilares: la resolución de inecuaciones (desigualdades) y el estudio de las funciones, con especial énfasis en la función lineal. Estos conceptos no solo son fundamentales para la matemática pura, sino que tienen aplicaciones directas en áreas como la programación (lógica de funciones y búsqueda) y la economía (modelado de costos).
> 
> 2. Contexto del Tema e Importancia
> 
> El dominio de las desigualdades permite entender rangos de soluciones en lugar de valores únicos, lo cual es vital para establecer condiciones de contorno. Por otro lado, la función lineal representa la relación más simple y directa entre dos variables, sirviendo como base para modelos más complejos. En el ámbito académico, estos temas son esenciales para el primer parcial, excluyendo por el momento funciones de mayor grado como la cuadrática.
> 
> 3. Marco Conceptual y Definiciones Clave
> 
> Para abordar el tema desde cero, es necesario clarificar los términos fundamentales:
> 
> * Inecuación: Una desigualdad de expresiones algebraicas donde se busca un conjunto de valores (intervalo) que satisfagan la condición.
> * Módulo (Valor Absoluto): Representa la distancia de un número al cero. Al resolver inecuaciones con módulo, se deben considerar los casos positivos y negativos (apertura del módulo).
> * Función: Relación entre un conjunto de entrada (Dominio) y un conjunto de salida (Codominio/Imagen), donde a cada elemento de entrada le corresponde un único elemento de salida.
> * Dominio: Conjunto de todos los valores de entrada posibles (generalmente en el eje X).
> * Codominio e Imagen: El codominio es el conjunto de llegada teórico, mientras que la Imagen son los valores que la función efectivamente toma como resultado.
> * Regla de la Función: Es la operatoria o fórmula que transforma la entrada en salida. En programación, equivale al cuerpo de una función o método de búsqueda.
> 
> 4. Desarrollo del Tema
> 
> 4.1. Inecuaciones y Desigualdades Dobles
> 
> Para resolver una desigualdad doble (ej. A < B \leq C), el procedimiento correcto es separarla en dos partes y resolverlas simultáneamente:
> 
> 5. Resolver A < B.
> 6. Resolver B \leq C.
> 7. La solución final es la intersección de ambos resultados (los valores que cumplen ambas condiciones a la vez).
> 
> Regla Crítica: Al multiplicar o dividir ambos miembros de una desigualdad por un número negativo, el sentido de la desigualdad debe invertirse.
> 
> 4.2. Inecuaciones con Cocientes y Productos
> 
> Cuando hay variables en el denominador o multiplicándose, no se debe simplificar arbitrariamente para no perder condiciones iniciales (como que el denominador no puede ser cero).
> 
> * Se debe llevar la expresión a una comparación con cero (ej. > 0 o < 0).
> * Se aplica la regla de los signos:
>   * Para que un cociente sea > 0, tanto numerador como denominador deben tener el mismo signo (ambos + o ambos -).
>   * Para que sea < 0, deben tener signos opuestos.
> 
> 4.3. La Función Lineal
> 
> Se define como una función de los Reales en los Reales (f: \mathbb{R} \to \mathbb{R}) con la forma general: f(x) = a \cdot x + b
> 
> * Pendiente (a): Indica la inclinación de la recta.
>   * Si a > 0: La función es creciente.
>   * Si a < 0: La función es decreciente (se lee de izquierda a derecha).
>   * Si a = 0: Es una función constante (recta horizontal).
> * Ordenada al origen (b): Es el valor donde la recta corta al eje vertical (Y). Representa el valor de la función cuando x = 0.
> 
> 5. Relaciones entre Conceptos y Estructuras
> 
> Relación entre Rectas
> 
> Las rectas pueden interactuar entre sí según sus pendientes:
> 
> Relación	Condición de la Pendiente	Descripción
> Paralelas	a_1 = a_2	Tienen la misma inclinación, nunca se cruzan.
> Perpendiculares	a_1 = -1 / a_2	Las pendientes son inversas y de signo opuesto. Forman un ángulo de 90°.
> 
> Nota: La ordenada al origen (b) no influye en si las rectas son paralelas o perpendiculares.
> 
> 6. Ejemplos Prácticos Paso a Paso
> 
> Caso A: Inecuación con Módulo y Fracción
> 
> Ejercicio: | \frac{1}{x} + 3 | > 3
> 
> 1. Operar dentro del módulo: Sacar denominador común x: |\frac{1 + 3x}{x}| > 3.
> 2. Abrir el módulo:
>   * Caso 1: \frac{1 + 3x}{x} > 3
>   * Caso 2: \frac{1 + 3x}{x} < -3
> 1. Resolver Caso 1: \frac{1+3x}{x} - 3 > 0 \implies \frac{1+3x-3x}{x} > 0 \implies \frac{1}{x} > 0. Solución: (0, +\infty).
> 2. Resolver Caso 2: \frac{1+3x}{x} + 3 < 0 \implies \frac{1+3x+3x}{x} < 0 \implies \frac{1+6x}{x} < 0. Se analizan los signos para que el cociente sea negativo. Solución: (-\frac{1}{6}, 0).
> 3. Solución Final: (-\frac{1}{6}, 0) \cup (0, +\infty).
> 
> Caso B: Modelado Lineal (El Taxi)
> 
> * Entrada: Cantidad de fichas.
> * Salida: Costo del viaje.
> * Datos: Bajada de bandera (valor inicial) = \$80. Valor por ficha = \$8.
> * Fórmula: f(x) = 8x + 80.
> * Aquí, el dominio son números enteros (no hay "media ficha"), lo que muestra cómo una función lineal puede aplicarse a valores discretos para su estudio.
> 
> 7. Errores Comunes y Confusiones
> 
> 8. Olvidar invertir el signo: Es el error más frecuente en inecuaciones al pasar un número negativo multiplicando o dividiendo.
> 9. Confundir puntos con intervalos: En el plano cartesiano, P(1, 3) es un punto (coordenada x=1, y=3), no un intervalo de números entre 1 y 3.
> 10. Simplificar variables: Eliminar una x del numerador con una del denominador en una inecuación sin analizar que esa x podría cambiar el signo de la desigualdad o que no puede ser cero.
> 11. Asumir que si no hay 'b', no pasa por cero: Si una función no tiene término independiente (b=0), siempre pasa por el origen de coordenadas (0,0).
> 
> 12. Síntesis y Conclusiones
> 
> * Para resolver inecuaciones complejas, la clave es la organización y el estudio de los signos comparados con cero.
> * Una función lineal queda definida por su pendiente y su ordenada al origen. Con dos puntos, o un punto y la pendiente, se puede hallar su ecuación única.
> * La representación gráfica requiere solo dos puntos; uno de ellos puede ser la ordenada al origen (0, b) y el otro se obtiene reemplazando cualquier valor de x en la fórmula.
> 
> 7. Preguntas de Repaso
> 
> Nivel Básico
> 
> 8. ¿Qué sucede con el sentido de una desigualdad si divido ambos miembros por -2?
> 9. En la función f(x) = -3x + 5, ¿la función es creciente o decreciente? ¿Por qué?
> 10. ¿Cuál es el valor de la ordenada al origen en la función f(x) = \frac{1}{2}x?
> 
> Nivel Intermedio
> 
> 11. Si dos rectas son paralelas y una tiene pendiente a = 4, ¿cuál es la pendiente de la otra?
> 12. Explique la diferencia entre dominio e imagen utilizando el ejemplo del viaje en taxi.
> 13. ¿Cómo se abre el módulo en la expresión |x + 5| \geq 3?
> 
> Nivel Avanzado
> 
> 14. Dada una recta que pasa por los puntos P(-1, 3) y Q(5, -3), determine su ecuación utilizando la fórmula de los dos puntos.
> 15. Si una recta es perpendicular a y = 2x - 4 y pasa por el punto (0, 6), ¿cuál es su ecuación final?
> 16. ¿Por qué se dice que una función no puede tener dos imágenes para un mismo valor del dominio (ejemplo del DNI y el nombre)?
> 
> 17. Fechas importantes y avisos académicos
> 
> Basado en el análisis de las fuentes de la Clase 4, se detallan los siguientes avisos:
> 
> * Contenido del Primer Parcial:
>   * Incluye: Todo lo visto hasta Función Lineal inclusive.
>   * Excluye: La Función Cuadrática no entra en el primer parcial.
> * Trabajo Práctico (TP2):
>   * El TP2 está disponible en el aula virtual.
>   * Aclaración importante: El profesor indicó que el TP no es para entregar, sino que su propósito es la práctica obligatoria para el examen.
> * Cronograma: Ya fue distribuido en sesiones anteriores (referirse al documento de cronograma para fechas exactas de examen, aunque no se mencionaron días específicos en esta sesión).
> * Uso de Materiales: Se ha subido una versión actualizada del PDF de la Unidad 2 (Parte 1) al aula virtual con la nomenclatura "2025" para corregir errores de versiones anteriores.
> 

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 4 - Análisis matemático" src="https://www.youtube.com/embed/4S2CU1M39wQ?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1vf_PIvfTtNIEd7AOdRwNzIph80Rj6Tnp/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/15JyqOpbKSdfoWhMZyaqGaZ08deToJNQS/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>