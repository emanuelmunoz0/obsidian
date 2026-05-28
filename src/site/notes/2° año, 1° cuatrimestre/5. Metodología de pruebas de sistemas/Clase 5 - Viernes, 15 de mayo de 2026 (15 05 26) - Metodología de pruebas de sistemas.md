---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/5-metodologia-de-pruebas-de-sistemas/clase-5-viernes-15-de-mayo-de-2026-15-05-26-metodologia-de-pruebas-de-sistemas/","dg-note-properties":{}}
---


> [!quote]- Resumen
> # Metodología de Pruebas de Sistemas: Guía Completa de Pruebas Funcionales y Técnicas de Diseño
> 
> Este documento constituye un material de estudio integral sobre la metodología de pruebas de sistemas, centrándose específicamente en las pruebas funcionales dirigidas por datos y técnicas de optimización de casos de prueba.
> 
> ## 1. Introducción a las Pruebas Funcionales
> 
> Las pruebas funcionales tienen como objetivo primordial validar los requerimientos funcionales del software. Se basan en verificar que el sistema haga lo que se supone que debe hacer desde la perspectiva del usuario y el negocio.
> 
> ### Contexto e Importancia
> 
> En el desarrollo de software, la ejecución de pruebas no puede ser infinita debido a restricciones económicas y de tiempo. Por ello, el concepto de **cobertura de pruebas** es fundamental: se busca realizar la menor cantidad de pruebas posibles que aseguren la mayor cobertura de la funcionalidad, optimizando recursos y detectando la mayor cantidad de errores.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual y Definiciones Clave
> 
> Para entender las pruebas de sistemas, es necesario dominar los siguientes conceptos fundamentales:
> 
> ### El Caso de Prueba (Test Case)
> 
> Es el documento que plasma las instrucciones detalladas para el personal que ejecutará las pruebas. Un caso de prueba completo debe contener, al menos, cinco elementos esenciales:
> 
> 1. **Flujo y pasos de ejecución:** Las acciones específicas (clics, completar campos, selecciones).
> 2. **Juego de datos:** Los valores específicos con los que se operará.
> 3. **Estado inicial:** El punto de partida del sistema (ej. estar logueado en una pantalla específica).
> 4. **Valor esperado:** La respuesta que el sistema debería mostrar por pantalla.
> 5. **Estado final:** El registro o cambio interno que el sistema debe realizar (aunque no sea visible por pantalla).
> 
> ### Tipos de Pruebas según el Conocimiento del Tester
> 
> - **Testing de Caja Blanca:** Se basa en el análisis del código y el conocimiento del procesamiento interno. El tester entiende cómo los datos de entrada se transforman en salida y puede investigar errores en la lógica interna o bases de datos.
> - **Testing de Caja Negra:** El tester ignora el procesamiento interno. Se enfoca exclusivamente en entradas y salidas, similar a cómo interactuaría un usuario final.
> 
> ### Casos de Prueba Abstractos vs. Específicos
> 
> - **Abstractos:** Funcionan como un "template" o diseño lógico. Definen la secuencia de pasos y las variables, pero sin datos específicos.
> - **Específicos:** Son instancias del caso abstracto donde se han asignado datos concretos y sus respectivos resultados esperados.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Pruebas Dirigidas por Datos (Data-Driven Testing)
> 
> Esta metodología se centra en que el diseño de las pruebas sea guiado por las variables y los datos de entrada. El proceso sigue una secuencia lógica:
> 
> 1. Identificar las variables (campos del formulario).
> 2. Seleccionar valores para esas variables (válidos e inválidos).
> 3. Definir las reglas de negocio que aplican a cada dato.
> 
> ### Clases de Equivalencia (Partición de Equivalencia)
> 
> Es una técnica que divide el dominio de entrada de un programa en clases de datos de las que se pueden derivar casos de prueba.
> 
> - **Concepto:** Se asume que si un valor de una "clase" funciona (o falla), cualquier otro valor de esa misma clase se comportará igual.
> - **Objetivo:** Reducir drásticamente el número de pruebas. En lugar de probar todos los números de un rango (ej. del 1 al 30), se prueba solo uno que represente a todo el grupo.
> 
> ### Análisis de Valores Límite (Boundary Value Analysis)
> 
> Esta técnica complementa a las clases de equivalencia. Se basa en que los errores suelen ocurrir con mayor frecuencia en los "bordes" o límites de los rangos (donde el programador pudo olvidar un "mayor o igual" o un "menor").
> 
> - **Aplicación:** Se prueban los valores exactamente en el límite, el valor inmediatamente anterior y el inmediatamente posterior.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Desarrollo de Técnicas y Aplicación Práctica
> 
> ### Ejemplo: Formulario de Solicitud de Viáticos
> 
> Imaginemos un sistema con tres campos: **Legajo**, **Monto por día** y **Vehículo**.
> 
> #### 1. Identificación de Clases (Reglas de Negocio)
> 
> - **Legajo:** El primer carácter debe ser una letra (Válido). Si no empieza con letra, es Inválido.
> - **Monto:** Rango de 1 a 999.
>     - De 1 a 500: Válido (sin autorización).
>     - De 501 a 999: Válido (requiere autorización).
>     - Menor a 1 o mayor a 999: Inválido.
> - **Vehículo:** Auto, Ómnibus, Avión (Válido). Taxi/Remis (Inválido).
> 
> #### 2. Matriz de Clases de Equivalencia
> 
> |   |   |   |
> |---|---|---|
> |Variable|Clase Válida|Clase Inválida|
> |**Legajo**|Comienza con letra (C.1)|No comienza con letra (C.2)|
> |**Monto**|1 a 500 (C.3), 501 a 999 (C.4)|< 1 (C.5), > 999 (C.6)|
> |**Vehículo**|Auto (C.7), Avión (C.8)|Taxi (C.9)|
> 
> #### 3. Diseño de Casos de Prueba
> 
> - **Regla de Oro para Válidos:** Se pueden combinar varias clases válidas en un solo caso de prueba para ganar eficiencia.
> - **Regla de Oro para Inválidos:** **Nunca combinar clases inválidas.** Se deben probar de a una por vez para evitar que un error enmascare a otro y asegurar que el sistema captura cada error específico.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Técnicas Avanzadas de Combinatoria y Estado
> 
> ### Pairwise Testing (Pruebas de a Pares)
> 
> Cuando existen múltiples variables con muchas opciones (ej. abrir una cuenta bancaria con diferentes tipos de cliente, tipos de cuenta y provincias), la combinatoria total puede ser inmanejable (ej. 192 combinaciones).
> 
> - **Fundamento:** La mayoría de los errores son provocados por la interacción de dos variables.
> - **Técnica:** Se utiliza una herramienta (como _Pairwise Tool_) que selecciona un subconjunto de combinaciones asegurando que todos los pares de variables hayan sido probados entre sí al menos una vez. Esto puede reducir, por ejemplo, 192 pruebas a solo 48, manteniendo una alta cobertura.
> 
> ### Diagrama de Transición de Estados
> 
> Se utiliza para modelar sistemas donde el comportamiento depende del historial o del estado actual de un objeto (ej. el ciclo de vida de una reserva de vuelo o el estado civil de una persona).
> 
> Existen dos niveles de cobertura:
> 
> 1. **Cobertura de Estados:** Asegurarse de que el sistema pueda llegar a cada estado posible (ej. Registrada, Pagada, Cancelada). Es un testing más débil.
> 2. **Cobertura de Transiciones:** Probar todos los caminos o "flechas" que conectan los estados. Es el método recomendado y más robusto, ya que valida cada evento que provoca un cambio de estado.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores Comunes y Confusiones
> 
> - **Confundir Clase con Valor Límite:** La clase es el "paquete" o rango; el valor límite es el punto exacto donde el rango cambia. No existe valor límite sin haber definido primero la clase de equivalencia.
> - **Enmascaramiento de Errores:** Ocurre al cargar dos datos inválidos a la vez. Si el sistema arroja un error, el tester no sabe cuál de los dos campos lo disparó o si ambos están siendo validados correctamente.
> - **Reglas de Negocio vs. Lógica:** No todas las validaciones son por lógica (ej. edades negativas); muchas son decisiones del negocio (ej. "en este club no se inscriben menores de 4 años"). Ambas deben probarse.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Síntesis y Conclusiones
> 
> - La **Metodología de Pruebas** busca eficiencia: máxima detección de errores con el mínimo de casos.
> - Las **Clases de Equivalencia** permiten agrupar datos, mientras que los **Valores Límite** refinan la búsqueda en puntos críticos.
> - El **Pairwise Testing** es la solución técnica para explosiones combinatorias de datos.
> - El **Diagrama de Estados** es esencial para sistemas con lógica de procesos secuenciales.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Preguntas de Repaso
> 
> ### Básicas
> 
> 1. ¿Cuáles son los 5 elementos esenciales de un caso de prueba?
> 2. ¿Qué diferencia hay entre testing de caja negra y caja blanca?
> 3. Defina "Clase de Equivalencia".
> 
> ### Intermedias
> 
> 4. ¿Por qué es una mala práctica probar dos clases de equivalencia inválidas en un mismo caso de prueba?
> 5. Explique la diferencia entre un rango de datos continuo y uno discreto.
> 6. ¿En qué situaciones es más útil aplicar la técnica de Pairwise Testing?
> 
> ### Avanzadas
> 
> 7. En un diagrama de estados, ¿qué diferencia hay entre la cobertura de estados y la cobertura de transiciones? ¿Cuál ofrece mayor calidad?
> 8. Dada una regla de negocio que dice: "Descuento del 10% para compras entre $1000 y $5000", identifique las clases de equivalencia y los valores límite para las pruebas.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Fechas Importantes y Avisos Académicos
> 
> ### Organización de la Materia
> 
> - **Asistencia:** Los alumnos deben conectarse con su **nombre completo** en la plataforma. Aquellos que solo utilicen su nombre de pila serán considerados **ausentes**.
> - **Dinámica de Clase:** Se recomienda ingresar 10-15 minutos antes de las 19:00 para asegurar que todos estén presentes al inicio de la explicación.
> 
> ### Evaluaciones y Tareas
> 
> - **Trabajo Práctico (TP) Grupal:**
>     - **Fecha de Entrega:** Próximo viernes a las 17:00 hs (vía aula virtual).
>     - **Componentes del Trabajo:**
>         1. **Formulario:** Identificación de variables y reglas de negocio.
>         2. **Tabla de Datos:** Matriz completa de clases de equivalencia y valores límite (organizada y estética, preferentemente en Excel).
>         3. **Diagrama de Estados:** Modelado en UML de una entidad del sistema.
>         4. **Listado de Transiciones:** Detalle de todos los recorridos necesarios para probar todas las transiciones del diagrama.
>     - **Indicaciones del Docente:** Se evaluará la prolijidad, el orden lógico de las variables y que la tabla sea fácilmente legible. No es necesario generar los casos de prueba detallados aún, solo la identificación y análisis de datos/estados.
> - **Presentación:** En la próxima clase, los grupos deberán presentar y comentar sus avances para recibir feedback presencial.
> - **Material de Estudio:** Se encuentran disponibles en la plataforma lecturas de Presman (Ingeniería de Software), Federico Toledo (Pruebas Funcionales) y material sobre técnicas de prueba (certificación ISTQB). El PPT utilizado en clase se usará durante todo el cuatrimestre.

> [!quote]- Glosario
> # Glosario Académico: Metodología de Pruebas de Sistemas (Sesión 5)
> 
> ## 1. BLOQUE DE TÉRMINOS A - C
> 
> La estandarización terminológica en el diseño de pruebas constituye una necesidad estratégica fundamental para la ingeniería de software. Al unificar los conceptos de diseño —desde la estructura de un caso de prueba hasta la lógica de partición de datos—, los equipos de Aseguramiento de Calidad (QA) garantizan una comunicación técnica precisa y una trazabilidad libre de ambigüedades. Este rigor metodológico permite que cada esfuerzo de validación esté alineado con los requerimientos funcionales, asegurando que el proceso de detección de fallos sea sistemático, repetible y profesional.
> 
> ## Caso de Prueba (Test Case)
> 
> - **Definición:** Documento técnico que establece las instrucciones detalladas que el personal de QA debe seguir para validar una funcionalidad específica del software.
> - **Explicación ampliada:** Un caso de prueba formal debe integrar obligatoriamente cinco elementos críticos para considerarse completo: el flujo o secuencia de pasos (acciones como clics o completar campos), el juego de datos, un estado inicial (punto de partida del sistema), un valor esperado de respuesta (visualizable por pantalla) y un estado final, el cual suele consistir en un registro no visible en pantalla (como un cambio en la base de datos).
> - **Ejemplo:** Instrucciones para completar un formulario de solicitud de viáticos, partiendo desde la pantalla principal, ingresando datos específicos y esperando un mensaje de "Envío exitoso" junto con la creación del registro correspondiente en el servidor.
> 
> _Una vez definida su estructura general, es imperativo distinguir su nivel de abstracción lógica mediante el concepto de caso de prueba abstracto._
> 
> ## Caso de Prueba Abstracto
> 
> - **Definición:** Diseño lógico de una prueba que describe la secuencia de pasos operativos y el flujo de control sin asignar datos concretos ni valores específicos a las variables.
> - **Explicación ampliada:** Funciona como un "template" o plantilla reutilizable para el diseño de pruebas. Su propósito es definir la acción operativa (por ejemplo, validar la entrada en un campo de texto) de forma genérica, permitiendo que esta estructura lógica sea utilizada posteriormente para múltiples ejecuciones con diversos juegos de datos.
> - **Ejemplo:** Un diseño que indique: "Ingresar valor numérico en el campo Edad y presionar el botón Continuar", sin especificar si el número ingresado será un valor válido o inválido.
> 
> _Cuando este diseño lógico se aterriza con valores reales y respuestas condicionadas, se transforma en un caso de prueba específico._
> 
> ## Caso de Prueba Específico
> 
> - **Definición:** Instancia concreta de un caso de prueba en la que se han asignado datos particulares y resultados esperados determinados para una ejecución real.
> - **Explicación ampliada:** Este se deriva directamente del caso abstracto. En el caso específico, el resultado esperado tiene una dependencia directa con el dato ingresado: si se utilizan datos válidos, el resultado esperado será la continuidad del proceso; si se utilizan datos fuera de rango, el resultado esperado será un mensaje de error específico.
> - **Ejemplo:** Un caso derivado del abstracto de "Edad" donde se ingresa el dato "15" y se espera como resultado un mensaje de error que indique "Edad mínima no alcanzada".
> 
> _Para seleccionar los datos que alimentarán estos casos de manera eficiente, se emplea la técnica de clase de equivalencia._
> 
> ## Clase de Equivalencia (o Partición de Equivalencia)
> 
> - **Definición:** Técnica de optimización de pruebas que agrupa un rango de valores en un conjunto, "bolsa" o "paquete", donde cualquier elemento seleccionado representa el comportamiento de todo el grupo.
> - **Explicación ampliada:** También conocida como grupo de equivalencia, esta técnica asume que si el sistema procesa correctamente un valor de la clase, funcionará igual para todos los demás miembros. Es crucial distinguir entre variables de rango continuo (como montos con decimales o "floats") y rangos discretos (como enteros o "integers"), ya que esto define la granularidad de la partición.
> - **Ejemplo:** Para un campo que acepta nombres de hasta 30 caracteres, cualquier cadena de texto entre 1 y 30 caracteres (como "Federico") pertenece a la misma "bolsa" válida y representa a todos los nombres dentro de ese rango.
> 
> _La agrupación estratégica de datos en clases es el pilar fundamental para alcanzar una cobertura de pruebas óptima._
> 
> ## Cobertura de Pruebas
> 
> - **Definición:** Concepto métrico y estratégico que busca asegurar la validación de la mayor parte de la funcionalidad del software utilizando la menor cantidad de pruebas posibles.
> - **Explicación ampliada:** Su objetivo es la optimización de recursos económicos y de tiempo mediante una lógica de ejecución estratégica que evita pruebas redundantes o infinitas. Una cobertura inteligente prioriza los puntos críticos para maximizar la detección de errores con el mínimo esfuerzo operativo.
> - **Ejemplo:** En lugar de probar individualmente cada año de edad posible (del 1 al 300), se diseñan 6 pruebas estratégicas que cubren todas las particiones de edad definidas por las reglas de negocio, logrando una cobertura total del requerimiento.
> 
> _Esta búsqueda de cobertura se materializa mediante enfoques analíticos como las pruebas dirigidas por datos._
> 
> --------------------------------------------------------------------------------
> 
> ## 2. BLOQUE DE TÉRMINOS D - R
> 
> La evolución del testing moderno exige que la actividad deje de ser una respuesta reactiva para convertirse en una disciplina analítica basada rigurosamente en datos. El uso de metodologías dirigidas por datos, el modelado de estados y las técnicas de optimización combinatoria permiten a los ingenieros de QA predecir comportamientos complejos del sistema con base científica. Al centrar el análisis en las reglas de negocio y las variables de entrada, el proceso de prueba se transforma en una verificación matemática y lógica de la robustez del software bajo condiciones variables.
> 
> ## Data Driven Test (Pruebas dirigidas por datos)
> 
> - **Definición:** Enfoque de testing donde el juego de datos es el factor mandatario y principal que guía tanto el diseño como la ejecución de la prueba.
> - **Explicación ampliada:** En esta técnica, el foco reside en la manipulación sistemática de las variables de entrada. El tester selecciona valores válidos e inválidos y observa meticulosamente la respuesta del software, permitiendo que un mismo flujo operativo sea ejecutado repetidamente con diferentes combinaciones de datos provenientes de una fuente externa o tabla.
> - **Ejemplo:** Ejecutar un mismo script de login 50 veces utilizando un archivo Excel que contiene diferentes combinaciones de usuarios y contraseñas (válidos, inexistentes, bloqueados) para observar la respuesta del sistema en cada caso.
> 
> _Mientras que los datos guían la ejecución, el comportamiento dinámico de los objetos se visualiza mediante un diagrama de estados._
> 
> ## Diagrama de Estados
> 
> - **Definición:** Modelo gráfico (comúnmente en UML) que representa los distintos estados por los que pasa una entidad y los eventos que provocan cambios entre ellos a lo largo de su ciclo de vida.
> - **Explicación ampliada:** Esta técnica permite visualizar la evolución de un objeto (como un pedido o una persona). En testing, existe una distinción crítica: la "Prueba de Estados" (más débil) busca que el objeto pase por cada estado al menos una vez, mientras que la "Prueba de Transiciones" (más completa y fuerte) busca recorrer cada flecha o evento disparador del modelo para asegurar que ningún cambio de estado falle.
> - **Ejemplo:** Un modelo de reserva de vuelo que visualiza los estados: "Registrada", "Pagada", "Con Ticket Emitido" y "Utilizada", permitiendo verificar que no se pueda pasar de "Registrada" a "Utilizada" sin el evento intermedio del pago.
> 
> _Para sistemas que presentan múltiples estados y variables concurrentes, la optimización combinatoria de pairwise testing ayuda a gestionar la complejidad._
> 
> ## Pairwise Testing (Pruebas de a pares)
> 
> - **Definición:** Técnica de optimización combinatoria basada en la interacción de parámetros ortogonales para reducir escenarios de prueba masivos a un subconjunto representativo y manejable.
> - **Explicación ampliada:** Se fundamenta en la premisa de que la mayoría de los errores son provocados por la interacción de, como máximo, dos variables. La técnica selecciona combinaciones de a pares para cubrir el espectro de interacción necesario, eliminando casos redundantes donde la interacción entre dos valores específicos ya fue cubierta en una prueba anterior.
> - **Ejemplo:** Reducir un escenario de 192 combinaciones posibles entre tipos de cliente, cuentas y provincias a solo 48 casos de prueba que garantizan que cada par de valores ha interactuado al menos una vez.
> 
> _La efectividad de las combinaciones en pairwise testing depende estrictamente de las restricciones de validez dictadas por las reglas de negocio._
> 
> ## Reglas de Negocio
> 
> - **Definición:** Directrices y restricciones impuestas por el stakeholder o dueño del producto que definen el comportamiento esperado, los umbrales de decisión y la validez de los datos.
> - **Explicación ampliada:** Determinan qué datos son permitidos en el sistema y si un flujo requiere comportamientos adicionales (como una autorización superior) según ciertos valores. Son el marco de referencia absoluto para que el tester determine si un resultado es exitoso o fallido.
> - **Ejemplo:** Una regla que estipula que si un empleado solicita un monto de viáticos superior a 500 pesos, el sistema debe activar automáticamente un flujo de aprobación por parte de un gerente.
> 
> _Las reglas de negocio definen la lógica esperada, la cual es verificada en profundidad mediante el testing de caja blanca._
> 
> --------------------------------------------------------------------------------
> 
> ## 3. BLOQUE DE TÉRMINOS T - V
> 
> La precisión en los límites de los datos es el factor crítico que separa la estabilidad del software del fallo catastrófico en producción. Un error de un solo carácter o un operador lógico mal implementado en los bordes de una clase de equivalencia puede comprometer la integridad del sistema. Por ello, la síntesis entre el conocimiento de la arquitectura interna del código y la validación rigurosa de las fronteras de datos asegura que el software sea resiliente ante condiciones extremas y puntos de quiebre lógicos.
> 
> ## Testing de Caja Blanca
> 
> - **Definición:** Metodología de prueba realizada con conocimiento profundo de la estructura interna, el código fuente y la lógica de procesamiento del sistema.
> - **Explicación ampliada:** El tester analiza el procesamiento interno de los datos, posee capacidad para realizar consultas directas a la base de datos y comprende el flujo del algoritmo. Esto permite identificar errores en rutas lógicas, ciclos o condiciones que no son perceptibles desde la interfaz de usuario.
> - **Ejemplo:** Verificar mediante una consulta SQL que, tras presionar el botón "Guardar" en un formulario, los datos se hayan almacenado correctamente en la tabla correspondiente y con el formato de integridad esperado.
> 
> _Frente al enfoque de conocimiento interno, el testing de caja negra se posiciona desde la perspectiva externa del usuario final._
> 
> ## Testing de Caja Negra
> 
> - **Definición:** Método de prueba que se enfoca exclusivamente en las entradas y salidas del sistema, ignorando la estructura interna o el código fuente.
> - **Explicación ampliada:** Representa la perspectiva del usuario final. El evaluador ingresa datos a través de la interfaz y verifica si la respuesta obtenida coincide con los requerimientos funcionales, evaluando el "qué hace" el sistema en lugar del "cómo lo hace" internamente.
> - **Ejemplo:** Ingresar un legajo y un monto en un formulario web y verificar que el sistema muestre un mensaje de confirmación, sin tener acceso al código que procesó dicha solicitud.
> 
> _Dentro de esta perspectiva funcional, las interacciones del usuario provocan una transición que altera el estado del sistema._
> 
> ## Transición
> 
> - **Definición:** Evento, acción o paso específico que actúa como disparador para que un elemento cambie de un estado actual a uno nuevo dentro de un diagrama de estados.
> - **Explicación ampliada:** En el diseño de casos de prueba, el testing de transiciones es considerado el enfoque más exhaustivo y completo (en comparación con el de estados), ya que busca recorrer cada "flecha" del modelo para asegurar que todos los eventos de cambio funcionen correctamente bajo diversas condiciones.
> - **Ejemplo:** El acto de "Pagar" que convierte una reserva de estado "Registrada" a estado "Pagada"; la prueba debe validar que este evento específico ocurra solo cuando el pago es confirmado.
> 
> _Cada transición es activada frecuentemente por datos que residen en el borde de lo permitido, lo que obliga al uso estratégico de valores límites._
> 
> ## Valores Límites (o de Frontera)
> 
> - **Definición:** Técnica de testing que se aplica sobre las clases de equivalencia para validar los valores exactos donde ocurre un cambio de comportamiento o de regla lógica.
> - **Explicación ampliada:** Esta técnica **no existe sin las clases de equivalencia**, ya que se apoya en ellas para identificar los bordes. Se enfoca en el valor límite exacto, el inmediatamente anterior y el inmediatamente posterior (regla n-1, n, n+1). Es vital para detectar errores de programación en comparadores lógicos, como omitir un "igual" en un "mayor o igual".
> - **Ejemplo:** Si la edad válida es de 18 a 60 años, la prueba de valores límite evaluará específicamente los valores 17, 18, 19 (borde inferior) y 59, 60, 61 (borde superior).
> 
> _Para aplicar estos valores límites con éxito, es requisito cumplir con la fase preliminar de identificar cada variable presente en el sistema._
> 
> ## Variable
> 
> - **Definición:** Atributo, campo o elemento de entrada dentro de un formulario o sistema que puede adoptar distintos valores durante la ejecución.
> - **Explicación ampliada:** La identificación de variables constituye la **fase preliminar** y esencial de cualquier estrategia de pruebas dirigida por datos. Durante esta etapa, el tester debe catalogar cada campo (nombre, legajo, fecha) y determinar si su naturaleza es discreta o continua para definir posteriormente las clases de equivalencia adecuadas.
> - **Ejemplo:** Identificar que en un formulario de solicitud de viáticos existen tres variables principales: el "Legajo" (alfanumérico), el "Monto" (numérico continuo) y el "Vehículo" (conjunto de valores discretos).

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 4 (08 05 26) - Metodología de pruebas de sistemas" src="https://www.youtube.com/embed/dfV3JZL68BU?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1PoVIYlhJPHdDQbF15DAy8H7jBFueles0/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1u7LHAFBthXv3sd7s1wnP0W12rPW9Dfo8/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>