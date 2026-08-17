---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/3-logica-computacional/clase-9-jueves-12-de-junio-de-2025-12-06-25-logica-computacional/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio Avanzada: Mapas de Karnaugh y Simplificación de Funciones Booleanas
> 
> Esta guía constituye un material de estudio integral sobre los Mapas de Karnaugh, una herramienta fundamental en la lógica computacional para la minimización de expresiones booleanas. El documento detalla desde la construcción básica hasta las técnicas avanzadas de agrupamiento y simplificación necesarias para el nivel universitario.
> 
> ## 1. Introducción General
> 
> Los Mapas de Karnaugh son herramientas gráficas utilizadas para la simplificación de funciones lógicas. Su propósito principal es reducir la complejidad de las expresiones booleanas, lo que se traduce en una optimización a nivel de diseño de circuitos y procesos computacionales. Al minimizar una función, se busca obtener el menor número de términos y variables posibles sin alterar el resultado lógico de la operación original.
> 
> ## 2. Contexto del Tema
> 
> ### Importancia y Relevancia
> 
> En la computación, la eficiencia es clave. Una función lógica con múltiples variables y términos consume más recursos. Los mapas de Karnaugh permiten:
> 
> - **Optimización:** Pasar de expresiones extensas a formas mínimas y eficientes.
> - **Visualización:** Identificar patrones de simplificación que no son evidentes a simple vista en una tabla de verdad o mediante álgebra booleana pura.
> - **Diseño de Hardware:** Reducir la cantidad de compuertas lógicas necesarias en un diseño físico.
> 
> ### Marco Conceptual y Definiciones Clave
> 
> Para comprender los mapas de Karnaugh, es necesario dominar los siguientes conceptos:
> 
> - **Suma de Productos (SOP - Sum of Products):** Es el método más popular en la práctica. Bajo esta lógica:
>     - Una variable "verdadera" (A) tiene un valor de **1**.
>     - Una variable "negada" (A') tiene un valor de **0**.
> - **Producto de Sumas (POS - Product of Sums):** Un método alternativo donde los valores se invierten (A=0, A'=1). Aunque existe, el enfoque académico principal se centra en la Suma de Productos.
> - **Celdas:** Cada cuadro dentro del mapa que representa una combinación específica de las variables de entrada. El número de celdas depende de la cantidad de variables (2^n).
> - **Código Gray:** Sistema de numeración utilizado en los mapas donde, entre una celda y su adyacente, solo cambia el valor de una variable.
> 
> ## 3. Desarrollo del Tema: Construcción y Aplicación
> 
> ### Paso 1: Construcción de la Matriz
> 
> El tamaño del mapa está determinado por el número de variables de la función:
> 
> |   |   |   |
> |---|---|---|
> |Variables|Número de Celdas|Configuración Típica|
> |2 Variables|4 celdas|2x2|
> |3 Variables|8 celdas|2x4 (u horizontal/vertical por consenso)|
> |4 Variables|16 celdas|4x4 (Simétrico)|
> 
> **El Salto de Karnaugh:** En mapas de 3 y 4 variables, la secuencia de las columnas (o filas) no sigue el orden binario estándar (00, 01, 10, 11). Se utiliza el orden **00, 01, 11, 10**. Este cambio es crucial para que solo varíe un bit entre columnas adyacentes, permitiendo la simplificación matemática.
> 
> ### Paso 2: Volcado de Datos
> 
> Para completar el mapa:
> 
> 1. Se toma la expresión booleana dada.
> 2. Se traduce cada término a su equivalente binario (ej. A \bar{B} C = 101).
> 3. Se coloca un **1** en la celda donde se cumple esa combinación.
> 4. Se completan las celdas restantes con **0**.
> 
> ### Paso 3: Reglas de Agrupamiento (El Corazón de Karnaugh)
> 
> Una vez lleno el mapa, se deben agrupar los "1" siguiendo reglas estrictas basadas en potencias de 2:
> 
> - **Cantidades Permitidas:** Se pueden crear grupos de **1, 2, 4, 8 o 16** unos.
> - **Cantidades Prohibidas:** Nunca se deben hacer grupos de 3, 5, 6 o 7 elementos.
> - **Formas:** Solo se permiten rectángulos o cuadrados.
> - **Prohibición de Diagonales:** Los grupos solo pueden ser horizontales o verticales.
> - **Superposición:** Un "1" puede pertenecer a varios grupos si esto ayuda a crear grupos más grandes y óptimos.
> - **Objetivo de Optimización:** Se debe buscar siempre el menor número de grupos posibles que abarquen la mayor cantidad de unos.
> 
> ### Paso 4: Adyacencia y el Concepto "Pac-Man"
> 
> Los mapas de Karnaugh no deben verse como planos bidimensionales, sino como estructuras que se conectan por sus bordes:
> 
> - **Bordes Opuestos:** La columna de la extrema izquierda es adyacente a la de la extrema derecha.
> - **Bordes Superior/Inferior:** La fila superior es adyacente a la fila inferior.
> - Esto permite agrupar unos que parecen estar separados pero que, lógicamente, están "conectados" en los extremos del mapa.
> 
> ## 4. Simplificación de la Función
> 
> Para obtener la expresión mínima final a partir de los grupos, se aplican las reglas de identidad y complementación (Reglas 5 y 6 del álgebra de Boole):
> 
> 1. **Regla de Permanencia:** Si dentro de un grupo, una variable mantiene el mismo valor (siempre 0 o siempre 1) en todas las celdas del grupo, la variable **se queda** en la expresión final.
> 2. **Regla de Eliminación:** Si dentro de un grupo, una variable cambia su valor (pasa de 0 a 1 o viceversa), la variable **desaparece** (se simplifica).
> 3. **Estado de la Variable:**
>     - Si se mantiene en **1**, se escribe la variable verdadera (A).
>     - Si se mantiene en **0**, se escribe la variable negada (\bar{A}).
> 
> **Ejemplo de razonamiento:** En un grupo de cuatro unos, si observamos que la variable A vale 0 en dos celdas y 1 en las otras dos, A se elimina. Si la variable B vale 1 en las cuatro celdas, B sobrevive en la expresión final como una variable verdadera.
> 
> ## 5. Errores Comunes y Confusiones
> 
> - **Grupos de tamaño incorrecto:** Intentar agrupar tres unos en línea. Esto es matemáticamente inválido.
> - **No ser óptimo:** Hacer muchos grupos pequeños cuando se podría haber hecho un solo grupo grande. A grupos más grandes, menos variables tendrá el término resultante.
> - **Olvidar el Código Gray:** Colocar las columnas en orden 00, 01, 10, 11 invalidará toda la simplificación.
> - **Ignorar la adyacencia de bordes:** No ver que un "1" en la esquina superior izquierda puede agruparse con uno en la esquina superior derecha.
> 
> ## 6. Síntesis y Conclusiones
> 
> La minimización por Mapas de Karnaugh es un proceso de tres etapas: **Representación** (volcar los unos), **Identificación de Patrones** (agrupar según potencias de 2) y **Reducción Lógica** (eliminar variables que cambian). La clave del éxito radica en la observación de la adyacencia y en la prioridad de formar los grupos más grandes posibles para reducir la complejidad de la función final.
> 
> ## 7. Preguntas de Repaso (Tipo Examen)
> 
> **Básicas:**
> 
> 1. ¿Cuál es el valor binario de una variable negada en el método de Suma de Productos?
> 2. ¿Cuántas celdas tiene un mapa de 4 variables?
> 3. ¿Por qué no se pueden hacer grupos de 3 elementos?
> 
> **Intermedias:** 4. Explique el orden de las columnas en un mapa de 3 variables y por qué es necesario el "salto". 5. Si en un grupo de dos "1", la variable C cambia de 0 a 1, ¿qué sucede con ella en la simplificación? 6. ¿Qué significa que los bordes del mapa sean adyacentes?
> 
> **Avanzadas:** 7. Ante dos opciones de agrupamiento que cubren todos los "1", ¿cuál se considera la correcta o más óptima? 8. Describa el proceso para simplificar un grupo de 4 celdas en un mapa de 16 variables donde la fila se mantiene constante en "11" y las columnas varían entre "00, 01, 11, 10".
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> A partir del análisis de las fuentes, se identifican las siguientes actividades y requisitos académicos:
> 
> |   |   |   |
> |---|---|---|
> |Evento / Entrega|Fecha / Plazo|Descripción Detallada|
> |**Trabajo Práctico 2 (TP2)**|Próximas semanas (Consignas pronto)|Resolver ejercicios completos: pasar expresión a binario, volcar en mapa, agrupar y simplificar. Se debe subir en formato PDF al aula virtual.|
> |**Coloquio Final (TP Final)**|Cierre de cursada|Resolución de un Mapa de Karnaugh de **16 celdas** (4 variables). Se requiere justificación oral del agrupamiento y la simplificación.|
> |**Segunda Instancia Parcial**|Presencial|Examen escrito donde se deberá construir el mapa desde cero en hoja en blanco.|
> |**Clase de Repaso**|Próxima semana|Sesión dedicada exclusivamente a la práctica de ejercicios y resolución de dudas antes de las evaluaciones finales.|
> 
> **Recordatorios Importantes:**
> 
> - **Subjetividad en el Agrupamiento:** El profesor aclara que pueden existir diferentes formas de agrupar que sean válidas, aunque se evaluará la **optimización** (lograr la menor cantidad de términos).
> - **Requisito de Evaluación:** En el coloquio, es fundamental poder explicar el "por qué" se eligió cada grupo (ej. "elegí 4 en vez de 2 para optimizar la variable").
> - **Material de Práctica:** Se recomienda realizar al menos dos ejercicios completos del PDF proporcionado en clase para "calentar" y uno de alta complejidad para asegurar el dominio del tema.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 9 - Lógica computacional" src="https://www.youtube.com/embed/H5kniQv1nCw?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1uJgwVW7FDUiW4s6VWYSwfqNT17heHuDq/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1jnpfaGFLllWJq7aK1AEcOQufj1l-a78i/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>