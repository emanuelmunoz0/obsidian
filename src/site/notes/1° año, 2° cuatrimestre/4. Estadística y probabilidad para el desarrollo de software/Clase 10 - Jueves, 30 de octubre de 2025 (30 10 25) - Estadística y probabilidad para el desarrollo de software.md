---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/4-estadistica-y-probabilidad-para-el-desarrollo-de-software/clase-10-jueves-30-de-octubre-de-2025-30-10-25-estadistica-y-probabilidad-para-el-desarrollo-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía Integral de Estudio: Estadística y Probabilidad - Distribución Normal y Uso de Tablas
> 
> Este documento constituye un material de estudio exhaustivo sobre el uso práctico de la distribución normal en estadística, centrándose específicamente en el cálculo de áreas y coordenadas mediante el uso de tablas (Apéndices 1 y 2). El objetivo es proporcionar una comprensión profunda de la metodología aplicada sin recurrir a ecuaciones complejas de cálculo diferencial o integral.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción al Análisis de la Curva Normal
> 
> En el desarrollo de software y el análisis de datos, el estudio de la probabilidad a través de la **curva normal** es fundamental. En lugar de utilizar fórmulas matemáticas complejas que requieren conocimientos avanzados de análisis matemático, la práctica estándar en este nivel académico se basa en el uso de **tablas estadísticas**.
> 
> Estas tablas permiten determinar la probabilidad (representada por el área bajo la curva) o las coordenadas específicas (valores de Z) de manera directa y eficiente.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual: Conceptos Clave desde Cero
> 
> Para dominar el uso de las tablas, es imperativo comprender la estructura y propiedades de la curva de distribución normal:
> 
> - **Área Total bajo la Curva:** El valor total del área encerrada bajo la curva de distribución normal es siempre igual a **1** (que representa el 100% de probabilidad).
> - **Simetría:** La curva es perfectamente simétrica respecto a su eje central vertical.
> - **El Valor Z = 0:** El eje vertical central se sitúa en Z = 0. Este punto divide la curva en dos mitades exactas.
> - **División por Mitades:**
>     - El área a la derecha de Z = 0 vale **0,5**.
>     - El área a la izquierda de Z = 0 vale **0,5**.
> - **Variable Z (Puntaje Estándar):** Es la coordenada sobre el eje horizontal que indica a cuántas desviaciones estándar se encuentra un punto del centro.
> - **Área como Probabilidad:** En estadística, el tamaño del área sombreada bajo la curva entre dos puntos de Z representa la probabilidad de que ocurra un evento en ese intervalo.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Las Herramientas de Cálculo: Apéndices 1 y 2
> 
> El estudio se apoya en dos tipos de tablas con funciones distintas:
> 
> ### Apéndice 2: Tabla de Áreas (La más utilizada)
> 
> Relaciona una coordenada Z con el área acumulada. Generalmente, las tablas del Apéndice 2 proporcionan el área desde el eje central (Z = 0) hasta un valor específico de Z.
> 
> - **Uso Directo:** Dado un valor de Z, encontrar el área.
> - **Uso Inverso:** Dada un área, encontrar la coordenada Z correspondiente.
> 
> ### Apéndice 1: Tabla de Ordenadas (Alturas)
> 
> Se utiliza para encontrar la altura de la curva en un punto específico de Z.
> 
> - **Coordenada de Z:** Indica la ubicación en el eje horizontal.
> - **Altura (Ordenada):** Indica qué tan alta es la curva en ese valor exacto de Z.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Desarrollo del Tema: Metodología de Resolución
> 
> ### A. Cálculo del Área dado un valor de Z
> 
> Para encontrar el área entre Z=0 y un punto positivo o negativo:
> 
> 1. Identificar el valor de Z (ejemplo: 1,44).
> 2. En la tabla, buscar la fila que corresponde al primer decimal (1,4) y la columna del segundo decimal (0,04).
> 3. El punto de intersección es el área buscada.
> 
> ### B. Casos Especiales de Suma y Resta de Áreas
> 
> No siempre se busca el área desde el centro. Existen variaciones:
> 
> |   |   |
> |---|---|
> |Caso|Procedimiento Lógico|
> |**Área en el extremo (cola) de la curva**|Se resta el área encontrada en la tabla a **0,5**.|
> |**Área que cruza el eje central (****Z=0****)**|Se calculan las áreas de ambos lados por separado y se **suman**.|
> |**Área total mayor a 0,5**|Se identifica que el área cubre una mitad completa (0,5) más una porción de la otra.|
> 
> ### C. Cálculo Inverso (Hallar Z a partir del área)
> 
> Cuando se conoce el área pero no la posición:
> 
> 4. Si el área es superior a 0,5, primero se le resta 0,5 para obtener el valor que figura en la tabla.
> 5. Se busca el valor resultante dentro del cuerpo de la tabla (donde están las áreas).
> 6. Se identifican la fila y la columna correspondientes para reconstruir el valor de Z.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Ejemplos Prácticos Paso a Paso
> 
> ### Ejemplo 1: Cálculo de Área Combinada
> 
> **Problema:** Calcular el área sombreada entre los extremos de la curva cuando se tienen puntos en Z = 2,05 y Z = 1,44.
> 
> - **Paso 1:** Hallar el área desde 0 hasta 2,05. Según tabla: **0,4798**.
> - **Paso 2:** Como queremos el pedazo pequeño de la "cola", restamos: 0,5 - 0,4798 = 0,0202.
> - **Paso 3:** Hallar el área desde 0 hasta 1,44. Según tabla: **0,4251**.
> - **Paso 4:** Para la otra "cola": 0,5 - 0,4251 = 0,0749.
> - **Paso 5:** Sumar ambos resultados si se requiere el área total de los extremos.
> 
> ### Ejemplo 2: Cálculo Inverso
> 
> **Problema:** Encontrar Z si el área a la izquierda de Z es **0,8621**.
> 
> - **Análisis:** Como el área es mayor a 0,5, sabemos que Z está a la derecha del centro.
> - **Operación:** 0,8621 - 0,5 = 0,3621.
> - **Búsqueda:** Buscamos 0,3621 dentro de la tabla del Apéndice 2.
> - **Resultado:** Corresponde a la fila 1,0 y la columna 0,09. Por lo tanto, **Z = 1,09**.
> 
> ### Ejemplo 3: Uso del Apéndice 1 (Alturas)
> 
> **Valores obtenidos de la tabla de ordenadas:**
> 
> - Para Z = 0,84 \rightarrow Altura = **0,2803**
> - Para Z = 1,27 \rightarrow Altura = **0,1781**
> - Para Z = 0,05 \rightarrow Altura = **0,3984**
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores Comunes y Confusiones
> 
> 1. **Confundir Apéndices:** Usar la tabla de alturas (Apéndice 1) para calcular probabilidades o áreas. El Apéndice 1 solo da la "forma" o altura de la curva.
> 2. **Error de Columna:** Al buscar en la tabla, es común desplazarse accidentalmente a una columna contigua (ej. buscar en 0,05 en lugar de 0,04).
> 3. **No Restar el 0,5:** Olvidar que la tabla mide desde el centro. Si el problema pide el área "a la derecha de Z", se debe restar el valor de la tabla a 0,5.
> 4. **Asumir simetría negativa:** Si bien el área es la misma para Z = 1,5 y Z = -1,5, la posición es opuesta. El razonamiento debe ajustarse según el gráfico.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Síntesis y Conclusiones
> 
> - La **Distribución Normal** es una herramienta mecánica pero requiere un razonamiento gráfico previo.
> - El **Área bajo la curva** es equivalente a la probabilidad.
> - Toda la curva suma **1**, y cada mitad respecto al cero suma **0,5**.
> - El uso de **Tablas** es un método académico más didáctico y directo que el uso de ecuaciones diferenciales para estudiantes que se inician en la materia.
> - Cada ejercicio es único y puede requerir sumas o restas de áreas dependiendo de qué sección de la curva se esté analizando.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> A partir de las indicaciones proporcionadas por el profesor, se establecen los siguientes puntos relevantes para la organización de la cursada:
> 
> - **Fecha del Parcial:** **Jueves 20 de junio**.
>     - _Nota:_ Se aclaró que para el curso de los jueves la fecha es el 20, mientras que para los alumnos de los martes la evaluación se adelanta al martes 18.
> - **Contenidos del Parcial:**
>     - Temas de Estadística y Probabilidad vistos hasta la fecha (incluyendo el uso de tablas).
>     - Dos temas adicionales que se verán próximamente (descritos como "ultramecánicos").
> - **Observación sobre la Metodología:** No se evaluarán herramientas de análisis matemático (cálculo diferencial/integral), sino el uso correcto de las tablas estadísticas.
> - **Próxima Clase:** Se terminarán de resolver los problemas pendientes del trabajo práctico actual y se dará por cerrado el tema.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es el valor total del área bajo la curva normal?
> 2. Si el área desde Z=0 hasta un punto Z_1 es 0,35, ¿cuál es el área restante en esa mitad de la curva?
> 3. ¿Para qué se utiliza específicamente el Apéndice 1?
> 
> ### Nivel Intermedio
> 
> 4. Si tengo un área de 0,8997 que parte desde el extremo izquierdo de la curva, ¿cómo debo buscar el valor de Z en la tabla?
> 5. Explique por qué el área correspondiente a Z=0,60 es inferior a 0,5.
> 
> ### Nivel Avanzado
> 
> 6. Si un área sombreada se encuentra entre Z = -1,5 y un punto Z desconocido, y el área total de ese segmento es 0,0217, describa el proceso lógico para hallar el valor de Z.
> 7. ¿Por qué es preferible el uso de tablas en lugar de ecuaciones de cálculo diferencial en este curso cuatrimestral? (Mencione la justificación académica del profesor).

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 10 - Estadística y probabilidad para el desarrollo de software" src="https://www.youtube.com/embed/GsaesXfj0OA?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1Gbk6hfi8fJTodF673k5wA-t8W4_RkhmL/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1KH_idkw_3foOclgWnC71WK14wJeSYeDf/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>