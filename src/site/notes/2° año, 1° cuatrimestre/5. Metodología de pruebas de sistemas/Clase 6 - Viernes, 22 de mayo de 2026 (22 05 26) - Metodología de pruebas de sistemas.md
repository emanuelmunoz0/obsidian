---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/5-metodologia-de-pruebas-de-sistemas/clase-6-viernes-22-de-mayo-de-2026-22-05-26-metodologia-de-pruebas-de-sistemas/","dg-note-properties":{}}
---


> [!quote]- Resumen
> # Metodología de Pruebas de Sistemas: Guía Integral de Diseño y Gestión de Casos de Prueba
> 
> Este documento constituye un material de estudio exhaustivo sobre las técnicas avanzadas de testing, el diseño de casos de prueba y la gestión de la calidad en el desarrollo de software. Basado en las metodologías de pruebas dirigidas por datos y estados, este apunte ofrece una visión profunda para entender el "porqué" de cada técnica y cómo aplicarlas profesionalmente.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción general
> 
> El testing de software no consiste simplemente en ejecutar un programa para ver si falla, sino en una disciplina metódica que busca asegurar que el sistema cumpla con las reglas de negocio y los requisitos técnicos. Para lograr eficiencia, el tester debe aplicar técnicas que reduzcan la cantidad de pruebas necesarias sin perder cobertura de riesgos. Este documento detalla las herramientas para pasar de un testing intuitivo a uno profesional y documentado.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco conceptual: Técnicas fundamentales
> 
> Para entender el diseño de casos de prueba, es necesario dominar cuatro conceptos clave que optimizan la selección de datos:
> 
> ### Clases de equivalencia (Particiones de equivalencia)
> 
> Esta técnica consiste en agrupar un conjunto de datos que se espera que el sistema procese de la misma manera. En lugar de testear todos los valores posibles (lo cual es ineficiente), se elige un **representante de cada grupo**. Si ese valor funciona, se asume que todo el rango funcionará.
> 
> ### Valores límite (Boundary Value Testing)
> 
> Es una mejora de las clases de equivalencia. En lugar de elegir cualquier valor aleatorio dentro de un rango, se seleccionan los **extremos** (los límites).
> 
> - **Razón de ser:** Los programadores suelen cometer errores en las comparaciones lógicas (`<` en lugar de `<=`, o `>` en lugar de `>=`). Probar los límites es más efectivo para detectar estos errores que probar valores medios.
> 
> ### Pairwise Testing (Pruebas por pares)
> 
> Se utiliza cuando la combinatoria de datos es excesivamente amplia.
> 
> - **Justificación:** La mayoría de los errores se encuentran en la interacción de dos variables. El Pairwise reduce la cantidad de casos asegurando que todas las combinaciones posibles de _pares_ de datos se ejecuten al menos una vez, eliminando la necesidad de probar todas las combinaciones totales.
> 
> ### Diagrama de estados (Statewise Testing)
> 
> Se utiliza para verificar que un objeto o sistema pase por todas sus etapas lógicas correctamente.
> 
> - **Forma fuerte (Más segura):** Probar todas las **transiciones** (los caminos entre estados).
> - **Forma débil:** Probar, al menos, que el sistema pueda llegar a cada **estado** posible.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. El Caso de Prueba (Test Case): Anatomía y Diseño
> 
> Un caso de prueba es la documentación de todo lo necesario para que cualquier persona (ahora o en el futuro) ejecute una prueba exactamente como fue diseñada.
> 
> ### Elementos fundamentales (Obligatorios)
> 
> Para que un documento sea considerado un caso de prueba válido, debe contener:
> 
> 1. **Estado inicial / Precondiciones:** El punto de partida (ej. usuario logueado, registros existentes en la base de datos).
> 2. **Datos de entrada:** Los valores específicos con los que se operará (ej. Legajo: A100, Monto: 500).
> 3. **Pasos (Acciones):** La secuencia lógica de clics o ingresos de información.
> 4. **Resultado esperado:** Lo que el sistema debería mostrar visualmente (ej. mensaje de "Éxito").
> 5. **Estado final del sistema:** La comprobación técnica de cómo quedó el sistema internamente (ej. consulta a la base de datos para ver si el registro se guardó).
> 
> ### Gestión y campos administrativos
> 
> Además de lo funcional, un caso de prueba profesional incluye datos de gestión para trazabilidad y estadísticas:
> 
> - **ID del caso:** Para identificación rápida.
> - **Descripción / Objetivo:** Qué se está validando.
> - **Creador y Revisor:** Quién lo diseñó y quién dio el visto bueno técnico.
> - **Versión:** Control de cambios del documento.
> - **Prioridad/Criticidad:** Urgencia de la corrección si falla.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. La Matriz CRUD: Optimización de Cobertura
> 
> La matriz **CRUD** (Create, Read, Update, Delete) es una técnica de análisis para asegurar que cada entidad relevante del sistema (alumno, producto, factura) sea testeada en todo su ciclo de vida.
> 
> ### El Patrón CRUD
> 
> Toda entidad en un sistema suele pasar por estas cuatro acciones:
> 
> - **Create (Crear):** El "nacimiento" del dato (Alta).
> - **Read (Leer):** La consulta o listado del dato.
> - **Update (Actualizar):** La modificación o crecimiento del dato.
> - **Delete (Borrar):** La eliminación (física o lógica) del dato.
> 
> ### Metodología de la Matriz
> 
> Se construye una tabla donde las filas son las **funciones del sistema** y las columnas son las **entidades**. Se marca con las letras C, R, U, D cómo interactúa cada función con cada entidad.
> 
> **Objetivo:** Identificar la menor cantidad de funciones que, al ejecutarse, cubran todas las letras del CRUD para todas las entidades. Esto permite ahorrar tiempo de ejecución sin dejar huecos en la prueba de la lógica del negocio.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Ejemplos Prácticos explicados paso a paso
> 
> ### Caso A: Formulario de Viáticos (Pruebas dirigidas por datos)
> 
> Si testeamos un legajo que debe empezar con una letra y un monto que requiere autorización si supera los 500:
> 
> |   |   |   |   |
> |---|---|---|---|
> |Paso|Datos de entrada|Resultado Esperado|Comentario|
> |1. Completar campos|Legajo: A100, Monto: 100, Vehículo: Auto|Mensaje: "Viático aprobado"|Caso feliz (valores válidos).|
> |1. Completar campos|Legajo: 999, Monto: 100, Vehículo: Auto|Mensaje: "Legajo incorrecto"|Valor inválido (Clase de equivalencia).|
> 
> ### Caso B: Reservas de Vuelos (Pruebas de estados)
> 
> Para un diagrama de estados (Registrada -> Pagada -> Emitida -> Utilizada):
> 
> 1. **Caso de flujo feliz:** Registrar -> Pagar -> Emitir Ticket -> Simular Vuelo. Resultado: Estado "Utilizada".
> 2. **Caso de expiración:** Registrar -> Esperar tiempo de vencimiento (Timeout). Resultado: Estado "Cancelada por no pago".
>     - _Nota técnica:_ Para probar el paso del tiempo, a veces se debe "simular" cambiando la fecha del sistema o de la base de datos si no se puede esperar el tiempo real.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores comunes y aclaraciones importantes
> 
> - **Confusión entre Resultado Esperado y Estado Final:** El resultado esperado es lo que el usuario ve (la interfaz). El estado final es la realidad técnica del sistema (la base de datos).
> - **Reportar "Pass" erróneamente:** Si el sistema funciona pero tiene un error visual (ej. una falta de ortografía), **no se pone "Pass"**. Se reporta como un defecto (Bug). Los errores se clasifican por **criticidad** (cosméticos, menores, mayores, críticos).
> - **Precondiciones obvias:** No es necesario poner "el usuario está logueado" en cada uno de los 100 casos de prueba si es una condición general. Se pone cuando la precondición cambia drásticamente la lógica (ej. "el usuario no tiene permisos de administrador").
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Síntesis y Conclusiones
> 
> - **Eficiencia:** El buen tester no es el que más prueba, sino el que mejor elige qué probar usando técnicas como Clases de Equivalencia y Matrices CRUD.
> - **Documentación:** Un caso de prueba debe ser autosuficiente. Si el diseñador no está, cualquier otro debe poder ejecutarlo.
> - **Enfoque:** Existen pruebas de datos (validación de campos) y pruebas de estados (lógica de procesos). Ambas son necesarias para un testing integral.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas importantes y avisos académicos
> 
> A partir del análisis de la información proporcionada por la cátedra, se establecen los siguientes puntos clave:
> 
> - **Modificación de Fecha de Examen:** El segundo parcial ha sido reprogramado.
>     - **Fecha:** Viernes 12 de julio.
>     - **Tipo de evento:** Segundo Examen Parcial.
>     - **Descripción:** Se traslada la fecha original para permitir una clase adicional de repaso y consultas.
> - **Trabajo Práctico Obligatorio (Grupal):**
>     - **Tarea inmediata:** Cada grupo debe diseñar su propio "Template de Caso de Prueba" en Excel, definiendo qué campos incluirán y justificando por qué.
>     - **Entregable próximo:** Presentación de la tabla de variables y combinatoria de datos antes de redactar los casos finales.
>     - **Requisito de diseño:** No empezar a escribir casos de prueba sin haber realizado primero el análisis de particiones de equivalencia y valores límite.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuáles son los tres elementos mínimos que debe tener un caso de prueba?
> 2. ¿Qué diferencia hay entre una partición de equivalencia y un valor límite?
> 3. ¿Qué significa la sigla CRUD?
> 
> ### Nivel Intermedio
> 
> 4. En una matriz CRUD, ¿por qué buscamos la menor cantidad de funciones para ejecutar?
> 5. Si un caso de prueba falla en un detalle estético (color o tipografía), ¿se puede marcar como "Aprobado" (Pass)? Justifique.
> 6. ¿Cómo se prueba una transición de estado que depende de un tiempo de espera largo (ej. 48 horas)?
> 
> ### Nivel Avanzado
> 
> 7. Explique la diferencia de enfoque entre un caso de prueba para un formulario de carga de datos y un caso de prueba para un diagrama de estados.
> 8. ¿Por qué el Pairwise Testing es una técnica de optimización y en qué se basa su efectividad para detectar errores?

> [!quote]- Glosario
> # Glosario Académico: Metodología y Arquitectura de Pruebas de Sistemas
> 
> ## 1. Bloque Alfabético A - C
> 
> La sistematización del aseguramiento de calidad se axiomatiza a partir de la comprensión de la persistencia de datos, evolucionando progresivamente hacia la optimización intelectual del diseño de pruebas. El analista debe categorizar las acciones fundamentales de gestión (ABM) como la base operativa del sistema, para luego trascender hacia el diseño estructurado mediante Clases de Equivalencia. Esta transición permite diferenciar la simple gestión de flujos de datos de la lógica de particiones estratégicas, garantizando que el testing no sea una ejecución mecánica, sino una disciplina que descompone las entradas para maximizar la cobertura de riesgos con el mínimo esfuerzo operativo.
> 
> ## ABM (Alta, Baja, Modificación)
> 
> **Definición** Representa las operaciones fundamentales de persistencia de datos necesarias para gestionar el ciclo de vida de cualquier entidad dentro de un sistema informático. **Explicación ampliada** Este concepto constituye el equivalente funcional del patrón técnico CRUD. Se centra en las acciones que permiten que un objeto (como un legajo de empleado o un vehículo) sea creado, alterado en sus atributos o removido de la visibilidad operativa. Es fundamental destacar que, desde una perspectiva académica y técnica, la "Baja" suele implementarse como una eliminación lógica y no física; esto permite preservar la integridad histórica y los registros de auditoría del sistema mientras la entidad deja de figurar en los procesos activos. **Ejemplo** El proceso de dar de alta un nuevo legajo de empleado en el sistema de viáticos, modificar su categoría o darlo de baja lógica cuando cesa su contrato.
> 
> ## Acciones de entrada (Pasos)
> 
> **Definición** Secuencia procedimental y lógica que describe las interacciones específicas que el tester debe realizar sobre la interfaz para ejecutar una validación. **Explicación ampliada** La claridad en la redacción de estos pasos es imperativa para garantizar la reproducibilidad de la prueba, permitiendo que cualquier miembro del equipo ejecute el caso con exactitud incluso meses después de su creación. Estas acciones transforman la estrategia abstracta en una ejecución operativa concreta, constituyendo el núcleo de la evidencia documental necesaria para el proceso de QA. **Ejemplo** En un formulario de viáticos, la secuencia de completar el campo "Legajo", ingresar el "Monto" solicitado, seleccionar el "Vehículo" y presionar el botón "Siguiente".
> 
> ## Boundary Value Testing (Pruebas de Valores Límite)
> 
> **Definición** Técnica de diseño de pruebas de caja negra que se enfoca en los extremos o fronteras de los rangos de datos permitidos. **Explicación ampliada** Esta técnica es estratégicamente superior a la selección aleatoria de datos porque se fundamenta en la alta propensión al error humano durante la programación. Los desarrolladores suelen "pifiar" o cometer errores en la implementación de operadores relacionales (como utilizar `<` en lugar de `<=` o `>=` en lugar de `>`). Al testear valores inmediatamente menores, iguales y mayores al límite, se axiomatiza la validación de la lógica de fronteras donde suelen residir los defectos. **Ejemplo** Si una categoría de viáticos cambia su lógica de aprobación a partir de un monto de 1,00, el tester debe probar específicamente 1,01 para verificar que el sistema procese correctamente el cambio de rango.
> 
> ## Caso de Prueba (Test Case)
> 
> **Definición** Entidad documental que sistematiza las precondiciones, pasos, datos y resultados esperados necesarios para validar una funcionalidad específica. **Explicación ampliada** El caso de prueba funciona como una herramienta de auditoría y gestión que descompone el proceso en dos etapas: el diseño intelectual (estrategia y lógica del analista) y la ejecución operativa (validación frente al software). Su estructura permite generar métricas de cobertura y calidad, sirviendo como registro oficial de que el comportamiento del sistema ha sido verificado bajo condiciones controladas. **Ejemplo** Un registro que incluye el ID "TC-VIAT-01", descripción de "Validación de solicitud", precondiciones de logueo y el resultado esperado de "Solicitud enviada con éxito".
> 
> ## Clases de Equivalencia (Partición de Equivalencia)
> 
> **Definición** Técnica de diseño que divide los datos de entrada en grupos que el sistema debería procesar de manera idéntica. **Explicación ampliada** Su justificación reside en la eficiencia operativa: permite reducir drásticamente el número de ejecuciones al seleccionar un solo "representante" por cada rango. El axioma técnico establece que si el sistema funciona correctamente para un representante de la clase, funcionará para todos los demás valores del mismo grupo, manteniendo la cobertura de riesgo sin incurrir en pruebas masivas redundantes. **Ejemplo** Si el sistema acepta legajos numéricos entre 200 y 500, se selecciona un único valor (ej. 350) para representar a toda la clase de legajos válidos.
> 
> ## Criticidad (de un error)
> 
> **Definición** Escala de importancia o urgencia asignada a un defecto detectado, basada en su impacto sobre la funcionalidad de negocio. **Explicación ampliada** Esta métrica categoriza los fallos para dictar la prioridad en el ciclo de corrección. Los errores se dividen generalmente entre cosméticos (estética o etiquetas) y funcionales (lógica de negocio). Un error de alta criticidad impide la operación del sistema, mientras que uno de baja criticidad puede ser una simple desviación visual que no invalida el proceso. **Ejemplo** Un error de ortografía en la etiqueta "Vehículo" (cosmético) frente a un fallo en el cálculo del monto total del viático (crítico).
> 
> ## CRUD (Create, Read, Update, Delete)
> 
> **Definición** Acrónimo técnico que describe las cuatro funciones básicas de la gestión de persistencia de datos. **Explicación ampliada** Es el equivalente técnico del término ABM. Su relevancia en QA radica en la creación de la Matriz CRUD, una herramienta analítica que cruza las funciones del sistema con las entidades para asegurar que se ha testeado la creación, lectura, actualización y borrado de cada elemento, garantizando así la cobertura total del ciclo de vida de los datos. **Ejemplo** La capacidad del sistema para crear una solicitud de viático, leerla para revisión, actualizar sus montos o borrarla si fue ingresada por error.
> 
> ## 2. Bloque Alfabético D - P
> 
> La madurez de una metodología de testing se manifiesta en la precisión de la gestión de datos y la interpretación analítica de los estados del sistema. El paso de una actividad mecánica a una disciplina científica ocurre cuando el tester es capaz de modelar la evolución de una entidad mediante el Diagrama de Estados y optimizar la combinatoria de variables mediante técnicas de Pairwise. Esta sección profundiza en la importancia de validar no solo lo que es visible en la interfaz, sino la integridad de la persistencia interna y las transiciones lógicas que gobiernan el sistema.
> 
> ## Datos de entrada (Test Data)
> 
> **Definición** Valores específicos utilizados para alimentar las variables del sistema durante la ejecución de una prueba. **Explicación ampliada** La selección rigurosa de datos (tanto válidos como inválidos) constituye el núcleo de las pruebas dirigidas por datos. Sin una definición previa de estos valores, la prueba carece de rigor y reproducibilidad. El objetivo es verificar que el sistema procese la información correcta y gestione adecuadamente los ingresos erróneos mediante mensajes de error apropiados. **Ejemplo** Ingresar el valor "A100" para el legajo y "5000" para el monto en una solicitud de viáticos.
> 
> ## Defecto (Bug)
> 
> **Definición** Discrepancia documentada entre el comportamiento observado del software y el comportamiento esperado definido en los requisitos. **Explicación ampliada** Cuando un caso de prueba resulta en "Fail", se inicia el Ciclo de Corrección. Es fundamental documentar el defecto con evidencia técnica (capturas, logs) para que el desarrollador pueda reproducirlo. La interacción entre el tester y el desarrollador, mediada por la evidencia del defecto, es lo que garantiza la evolución hacia un software libre de fallos críticos. **Ejemplo** Un sistema que permite guardar una solicitud de viáticos a pesar de que el número de legajo ingresado no existe en la base de datos de empleados.
> 
> ## Diagrama de Estados (State Transition Testing)
> 
> **Definición** Técnica de diseño que valida los cambios en el ciclo de vida de una entidad ante diversos eventos. **Explicación ampliada** Existen dos niveles de rigor: la "prueba de estados" (forma débil), que solo asegura que el objeto puede existir en cada estado, y la "prueba de transiciones" (forma fuerte), que valida todos los caminos y eventos posibles. Por estándares de calidad, se recomienda siempre la prueba de transiciones para asegurar que el flujo de negocio sea infranqueable ante estímulos incorrectos. **Ejemplo** Validar que una solicitud de viáticos pase de "Registrada" a "Aprobada" tras la firma del gerente, o a "Rechazada" si el monto excede el límite.
> 
> ## Estado Final (del sistema)
> 
> **Definición** Situación técnica y persistente en la que queda el sistema y sus bases de datos tras la ejecución de los pasos de una prueba. **Explicación ampliada** Debe diferenciarse el "resultado visible" (un mensaje en pantalla) de la "comprobación real". El estado final exige una validación técnica profunda, generalmente mediante una consulta a la base de datos (query), para confirmar que la información fue persistida o alterada correctamente de acuerdo con las reglas de negocio, más allá de lo que la interfaz gráfica indique. **Ejemplo** Verificar mediante SQL que la solicitud de viáticos figura efectivamente con el estado "Cancelada por no pago" en la tabla correspondiente tras expirar el tiempo de espera.
> 
> ## Estado Inicial (Precondiciones)
> 
> **Definición** Requisitos previos o escenario lógico necesario que debe existir antes de iniciar la ejecución de un caso de prueba. **Explicación ampliada** Las precondiciones axiomatizan el punto de partida y evitan la redundancia operativa (como repetir el logueo en cada caso). Aseguran que el sistema se encuentre en la situación correcta para que la validación sea legítima, como poseer permisos específicos o tener datos previamente cargados. **Ejemplo** Contar con un usuario logueado que posea el rol de "Administrador de Recursos Humanos" antes de intentar aprobar un viático.
> 
> ## Matriz CRUD
> 
> **Definición** Herramienta analítica que mapea las funcionalidades del sistema contra las entidades de datos para verificar la cobertura de pruebas. **Explicación ampliada** Esta matriz permite identificar qué funciones (ej. "Nueva Ciudad") realizan operaciones de creación o lectura en múltiples entidades simultáneamente. Su valor reside en la optimización: permite al analista ver qué procesos son críticos y asegurar que cada entidad sea testeada en sus cuatro estados fundamentales con el mínimo número de casos de prueba posibles. **Ejemplo** Una matriz que muestra que la función "Solicitar Viático" realiza un 'Create' en la entidad Solicitud y un 'Read' en la entidad Legajo.
> 
> ## Pairwise Testing
> 
> **Definición** Técnica de diseño combinatoria que prueba todos los pares posibles de variables de entrada. **Explicación ampliada** Su justificación técnica se basa en la teoría de que la gran mayoría de los defectos se revelan mediante la interacción de, al menos, dos variables. Cuando la combinatoria total es inmanejable, el Pairwise permite reducir drásticamente la cantidad de casos manteniendo una altísima probabilidad de detección de errores, enfocándose en la interacción dual de los datos. **Ejemplo** Probar combinaciones de Legajo, Monto y Vehículo reduciendo miles de posibilidades a un subconjunto representativo que valide todos los pares de estos tres campos.
> 
> ## 3. Bloque Alfabético R - V
> 
> La fase final de la arquitectura de pruebas se centra en la validación objetiva y la estandarización mediante artefactos documentales. La comparación entre lo esperado y lo obtenido constituye el único criterio de éxito, eliminando la subjetividad del proceso. El uso de plantillas (Templates) no es meramente administrativo, sino una herramienta de auditoría y estadística que permite a la organización medir el rendimiento del equipo y la estabilidad de las áreas funcionales, garantizando la mejora continua del ciclo de desarrollo.
> 
> ## Resultado Esperado
> 
> **Definición** Respuesta teórica y correcta que el sistema debe manifestar ante un estímulo o dato de entrada específico. **Explicación ampliada** Funciona como el "oráculo" de la prueba. Sin un resultado esperado definido con precisión, el tester carece de un criterio objetivo para determinar el éxito o fallo del software. Es el estándar contra el cual se mide la realidad operativa del sistema durante la ejecución. **Ejemplo** Visualización del mensaje "Viático aprobado con éxito" tras ingresar un legajo válido y un monto dentro del límite permitido.
> 
> ## Resultado Real (Obtenido)
> 
> **Definición** Comportamiento o respuesta que el software manifiesta efectivamente durante la ejecución de la prueba. **Explicación ampliada** Es el dato empírico recolectado en el entorno de testing. Cuando este resultado no coincide con el esperado, se documenta la desviación (falla) adjuntando evidencias como logs o capturas de pantalla. La comparación dialéctica entre el resultado real y el esperado define el estado de "Pass" o "Fail" del caso de prueba. **Ejemplo** El sistema muestra un error de "Formato inválido" a pesar de haber ingresado un número de legajo que cumple con todas las reglas de negocio.
> 
> ## Tabla de Decisión
> 
> **Definición** Técnica de diseño utilizada para sistematizar pruebas en sistemas con lógica de negocio compleja gobernada por múltiples condiciones. **Explicación ampliada** Esta herramienta permite visualizar de forma tabular todas las combinaciones de reglas de negocio y las acciones resultantes. Su uso garantiza que ninguna combinación crítica de condiciones (ej. tipo de vehículo + rango de monto + permisos de usuario) quede fuera del alcance de la validación, axiomatizando la cobertura de reglas lógicas. **Ejemplo** Una tabla que define que si el "Monto > 1000" Y el "Vehículo es Avión", la acción requerida es "Solicitar Autorización Gerencial".
> 
> ## Template (Plantilla de Caso de Prueba)
> 
> **Definición** Estructura documental estandarizada que garantiza la uniformidad y calidad en la documentación de pruebas de una organización. **Explicación ampliada** Más allá de la prolijidad visual, las plantillas poseen un alto valor estadístico y de auditoría. Permiten a la gestión de QA extraer métricas críticas: quién diseñó cuántos casos, cuál es el rendimiento de cada tester y cuántos fallos se concentran por área funcional. El uso de un formato uniforme facilita el trabajo colaborativo y la trazabilidad del proceso de calidad. **Ejemplo** Un archivo Excel corporativo con columnas obligatorias para ID, Revisor, Versión, Pasos, Resultado Esperado y Estado Final (Check de base de datos).
> 
> ## Versión (del Caso de Prueba)
> 
> **Definición** Indicador del estado evolutivo de un documento de prueba que refleja actualizaciones o correcciones. **Explicación ampliada** El control de versiones es indispensable debido a la naturaleza volátil del desarrollo de software. Cuando cambian las normativas legales (ej. nuevos montos máximos de viáticos) o cuando un revisor identifica una mejora en el diseño de la prueba, el documento debe incrementar su versión para asegurar que el equipo siempre ejecute la validación más reciente y ajustada a la realidad del sistema. **Ejemplo** Incrementar un caso de prueba de la Versión 1.0 a la 2.0 tras una actualización en la política de gastos que modifica los tipos de vehículos permitidos.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 6 (22 05 26) - Metodología de pruebas de sistemas" src="https://www.youtube.com/embed/la_ifTmrDRU?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1ND54cLbt16Jcmu4rVvuDBWFvjkDNLqTX/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1uQTQh_RhfmeCoYfSMn18CbxKqJl5G0vt/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>