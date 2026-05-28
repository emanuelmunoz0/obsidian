---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/5-metodologia-de-pruebas-de-sistemas/clase-4-viernes-08-de-mayo-de-2026-08-05-26-metodologia-de-pruebas-de-sistemas/","dg-note-properties":{}}
---


> [!quote]- Resumen
> # Metodología de Pruebas de Sistemas: Guía Integral de Casos de Prueba (Unidad 2)
> 
> Este documento constituye un material de estudio exhaustivo sobre la segunda parte de la asignatura de Metodología de Pruebas. Se centra en la transición de los conceptos teóricos hacia la práctica de generación de casos de prueba, el análisis de requerimientos funcionales y las técnicas de selección de datos.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción al Diseño de Pruebas
> 
> La segunda parte de la formación se enfoca en el aspecto práctico y creativo del testing: el uso del intelecto para generar los mejores **casos de prueba**. Mientras que la primera parte de la materia se centró en definiciones, esta etapa busca que el profesional aprenda a diseñar escenarios que aseguren la calidad del software de manera eficiente.
> 
> ### El rol del Tester en el ciclo de desarrollo
> 
> En una organización bien estructurada, el proceso de testing ocurre en paralelo al desarrollo:
> 
> 1. **Analista Funcional:** Genera los **Casos de Uso**.
> 2. **Desarrollador:** Comienza la programación basándose en dichos casos.
> 3. **Tester (Analista de Pruebas):** Recibe los Casos de Uso simultáneamente para realizar revisiones, inspecciones y, fundamentalmente, generar los **Casos de Prueba**.
> 
> Existen dos roles principales dentro del testing:
> 
> - **Tester Analista:** Es quien piensa y diseña las pruebas (el "guionista").
> - **Tester Ejecutor:** Es quien realiza las acciones en el software, ingresa datos y verifica resultados (el "actor").
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual: El Caso de Prueba
> 
> Un **Caso de Prueba** es un documento que plasma bajo qué parámetros, pasos y datos se evaluará una funcionalidad del sistema. Su objetivo primordial es permitir la revisión completa del software evitando la desprolijidad de las pruebas espontáneas.
> 
> ### La Eficiencia en el Testing
> 
> Un concepto fundamental es el equilibrio entre cantidad y cobertura:
> 
> **Regla de Oro:** Generar la **menor cantidad** de casos de prueba que cubran la **mayor cantidad** de funcionalidades posibles.
> 
> Dado que las combinaciones de datos pueden ser infinitas (ej. probar todos los nombres posibles, todas las edades, todos los caracteres), el tester debe usar herramientas lógicas para reducir ese infinito a un número razonable de casos ejecutables.
> 
> ### Los 5 Elementos Esenciales de un Caso de Prueba
> 
> Para que un caso de prueba sea considerado completo, debe contener obligatoriamente estos cinco elementos:
> 
> |   |   |
> |---|---|
> |Elemento|Descripción|
> |**Flujo o secuencia de pasos**|La lista ordenada de acciones que el ejecutor debe realizar en el sistema.|
> |**Datos de entrada**|Los valores específicos que se ingresarán en los campos (ej: "Juan", "25", "usuario@mail.com").|
> |**Estado inicial (Precondiciones)**|Las condiciones necesarias antes de iniciar la prueba (ej: el usuario debe estar logueado, el curso debe existir).|
> |**Valor de respuesta esperado**|Lo que el sistema muestra visualmente (ej: un mensaje de "Inscripción exitosa").|
> |**Estado final esperado**|Cómo queda realmente el sistema "por detrás" (ej: el registro nuevo existe en la base de datos).|
> 
> **Nota sobre la diferencia entre Respuesta y Estado Final:** El sistema puede mostrar un mensaje de éxito (valor de respuesta) pero no haber guardado los datos realmente por un error de programación en la base de datos (estado final). El tester debe verificar ambos.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Metodologías y Técnicas de Ejecución
> 
> ### Testing de Caja Negra vs. Caja Blanca
> 
> - **Caja Negra:** Se ignora el funcionamiento interno del código. El tester solo evalúa entradas y salidas. No requiere conocimientos técnicos profundos de programación.
> - **Caja Blanca:** El tester tiene conocimientos técnicos y acceso a la estructura interna. Por ejemplo, verifica el estado final haciendo un `SELECT` directamente en la base de datos para ver si el registro se insertó correctamente.
> 
> ### Pruebas Dirigidas por Datos (Data Driven Testing)
> 
> Esta metodología se focaliza en casos de uso donde la lógica de la prueba está guiada por la variación y combinación de los datos de entrada.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Tipología de Casos de Prueba: Abstractos y Específicos
> 
> - **Caso de Prueba Abstracto:** Es un "template" o plantilla que describe los pasos pero no incluye datos reales. Se utiliza para heredar la estructura y ahorrar tiempo de diseño. No se puede ejecutar.
> - **Caso de Prueba Específico:** Es la instancia real del caso abstracto con datos concretos (ej. Nombre: "María", Edad: "30"). Estos son los que el tester ejecutor utiliza frente a la pantalla.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Técnicas de Selección de Valores
> 
> Para evitar las "pruebas infinitas", se utilizan dos técnicas fundamentales que ayudan a seleccionar los datos de entrada de forma inteligente:
> 
> 1. **Clases de Equivalencia:** Se agrupan datos que el sistema debería tratar de la misma manera. Si el sistema acepta edades de 18 a 100, probar con 25 es equivalente a probar con 30; no es necesario probar cada número intermedio.
> 2. **Valores Límite:** Se prueban los extremos de las clases de equivalencia (ej: si el límite es 18, se prueba con 17, 18 y 19) para detectar errores en los operadores lógicos (como usar `<` en lugar de `<=`).
> 
> ### Ejemplo Práctico: Formulario de Alta de Cliente
> 
> Al analizar variables como la "Edad", el tester identifica:
> 
> - **Válidos:** Números entre 18 y 100.
> - **Inválidos por lógica de negocio:** Números menores a 18 (menores de edad) o mayores a 100 (longevidad extrema no permitida).
> - **Inválidos por formato:** Caracteres alfabéticos, símbolos, números negativos o dejar el campo vacío.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores Comunes y Confusiones
> 
> - **Confundir Caso de Uso con Caso de Prueba:** El Caso de Uso describe la intención del usuario y la respuesta del sistema a nivel funcional. El Caso de Prueba es el guion detallado con datos específicos para verificar que esa funcionalidad no falle.
> - **Asumir que el sistema funciona porque el mensaje es correcto:** Como se mencionó, el "mensaje de éxito" es solo la capa visual. Siempre se debe verificar el "estado final" (la persistencia del dato).
> - **Probar solo el "Caminito Feliz":** Muchos testers novatos solo prueban que el sistema funcione cuando todo se ingresa bien. Un buen tester debe probar "caminos infelices": datos duplicados, campos vacíos, formatos erróneos y caracteres especiales.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Síntesis y Conclusiones
> 
> - El diseño de pruebas es una actividad intelectual que precede a la ejecución.
> - Un caso de prueba debe ser autosuficiente, conteniendo pasos, datos, precondiciones y resultados esperados (visuales y lógicos).
> - La abstracción permite crear plantillas reutilizables, mientras que la especificación permite la ejecución real.
> - El objetivo es la eficiencia: probar lo máximo con el mínimo esfuerzo documental.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia principal entre un tester analista y un tester ejecutor?
> 2. ¿Qué elementos componen obligatoriamente un caso de prueba?
> 3. Defina "Caso de Prueba Abstracto".
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia entre "Valor de respuesta esperado" y "Estado final esperado" con un ejemplo.
> 5. ¿Qué es el Testing de Caja Negra y por qué un tester funcional lo utiliza primordialmente?
> 6. ¿Por qué se dice que el diseño de casos de prueba debe tender a la eficiencia?
> 
> ### Nivel Avanzado
> 
> 7. Dada una regla de negocio que dice "El nombre debe tener entre 2 y 30 caracteres", identifique tres clases de equivalencia y los valores límite para probarla.
> 8. ¿Cómo se relacionan los Casos de Uso del Analista Funcional con los Casos de Prueba del Tester?
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Fechas Importantes y Avisos Académicos
> 
> ### Evaluaciones y Notas del Primer Parcial
> 
> - Se han entregado las notas del primer parcial.
> - **Criterio de Aprobación:** El examen se aprobó con 4.
> - **Criterio de Promoción:** Requiere una nota de 7 o superior. Sin embargo, la promoción es una facultad del docente basada en:
>     - Participación activa en clase.
>     - **Cámara encendida obligatoriamente** durante todas las sesiones virtuales (se lleva registro y capturas de pantalla).
>     - Seguimiento constante de la materia.
> - Aquellos con nota menor a 4 deben replantear su método de estudio para el recuperatorio.
> - **Fecha de Recuperatorio:** Junio (consultar cronograma oficial en la plataforma).
> 
> ### Tarea Académica (Trabajo Grupal)
> 
> - **Formación de grupos:** 4 a 5 personas.
> - **Objetivo:** Recolectar material base para la práctica de la Unidad 2. No se debe entregar, sino tener disponible para trabajar en la próxima clase.
> - **Material requerido:**
>     1. **Un Caso de Uso:** Puede ser de una materia anterior o inventado (prohibido usar el caso de "Login").
>     2. **Un Formulario:** Captura de pantalla o diseño de un formulario con múltiples campos (ej: registro de cliente, alta de producto).
>     3. **Un Diagrama de Estados:** De cualquier funcionalidad o sistema.
> - **Nota:** No es obligatorio que los tres elementos pertenezcan al mismo sistema, aunque es preferible.
> 
> ### Bibliografía Obligatoria para la Unidad 2
> 
> - Guía del IFTS y material de ISTQB.
> - Pressman y Summerville (Capítulos de Calidad de Software).
> - **Libro Clave:** "Introducción a las pruebas de sistema" de **Federico Toledo**. El autor es uruguayo y ofrece el material de forma gratuita en internet. Se recomienda descargar el libro completo.

> [!quote]- Glosario
> # Glosario Técnico de Metodología de Pruebas de Sistemas
> 
> ## I. FUNDAMENTOS, ROLES Y ENTRADAS DEL PROCESO
> 
> El testing no es una actividad espontánea ni improvisada; es una disciplina que comienza con la inspección y revisión de los casos de uso por parte del analista antes de que el código siquiera exista. Entender esta fase de transición es vital para garantizar que el proceso de calidad sea un activo estratégico y no un gasto descontrolado. La definición clara de roles y el análisis riguroso de los insumos permiten al equipo anticipar fallos desde el diseño, optimizando los recursos y asegurando la trazabilidad de cada requerimiento.
> 
> ### Analista de Testing (Tester que piensa)
> 
> - **Definición:** Rol senior responsable del diseño lógico y estratégico de las pruebas, cuya labor principal es la inspección y revisión técnica de los requerimientos.
> - **Explicación ampliada:** Este perfil toma los casos de uso del analista funcional y realiza un proceso de revisión crítica para identificar variables y escenarios de riesgo. Su objetivo es redactar los guiones o scripts de prueba antes de la fase de construcción del software, actuando como un puente entre la necesidad del negocio y la verificación técnica.
> - _¿Por qué es importante?: Su intervención garantiza la trazabilidad del proceso y mitiga el alto costo de corregir errores en etapas tardías. Al "pensar" la prueba antes de que el software exista, previene la desprolijidad y asegura que ningún escenario crítico quede fuera del plan de calidad._
> - _Ejemplo: Identificar qué variables de validación (longitud, tipo de carácter) requiere un formulario de "Alta de Cliente" mientras el desarrollador aún está diagramando la lógica del código._
> 
> ### Caso de Uso
> 
> - **Definición:** Insumo fundamental proporcionado por el analista funcional que describe el comportamiento esperado del sistema desde la perspectiva del usuario.
> - **Explicación ampliada:** Es la "fuente de la verdad" y el input primario para el testing funcional. Existe una dependencia directa: el analista de testing descompone el caso de uso en múltiples escenarios de prueba para verificar que el software final cumpla fielmente con lo pactado.
> - _¿Por qué es importante?: Sin un caso de uso claro, la prueba carece de criterio de aceptación. Actúa como el ancla que evita que el equipo de QA invierta tiempo en funcionalidades no solicitadas o malinterpretadas._
> - _Ejemplo: El documento descriptivo del flujo de registro de un nuevo usuario en una plataforma educativa._
> 
> ### Pruebas Funcionales
> 
> - **Definición:** Evaluaciones centradas en el comportamiento externo del software, analizando específicamente la relación entre entradas, procesamiento y salidas.
> - **Explicación ampliada:** Se enfocan en el "qué hace" el sistema basándose en reglas de negocio y requerimientos funcionales. No requieren acceso al código fuente, sino que validan si el flujo de información y las respuestas del sistema respetan la lógica funcional esperada.
> - _¿Por qué es importante?: Permiten validar directamente la utilidad del software para el usuario final, asegurando que las funciones críticas operen correctamente bajo las reglas operativas de la organización._
> - _Ejemplo: Verificar si el sistema permite la inscripción de un alumno a un curso solo si hay cupo disponible y el alumno está habilitado._
> 
> ### Pruebas No Funcionales
> 
> - **Definición:** Pruebas que evalúan atributos de calidad del sistema como el rendimiento, la seguridad, la usabilidad o la escalabilidad.
> - **Explicación ampliada:** Complementan a las funcionales analizando "cómo" se comporta el sistema bajo ciertas condiciones de estrés o vulnerabilidad, siguiendo estándares bibliográficos como los de Pressman o Sommerville.
> - _¿Por qué es importante?: Un sistema puede ser funcionalmente correcto pero fallar estratégicamente si es lento o inseguro. Estas pruebas aseguran la estabilidad y confiabilidad de la infraestructura tecnológica._
> - _Ejemplo: Medir el tiempo de respuesta del servidor cuando 1,000 alumnos intentan inscribirse simultáneamente al inicio del cuatrimestre._
> 
> ### Tester Ejecutor
> 
> - **Definición:** Rol técnico encargado de la ejecución física de los casos de prueba sobre el software, siguiendo estrictamente la documentación generada por el analista.
> - **Explicación ampliada:** Su función es "correr" los guiones de prueba, interactuar con la interfaz, ingresar datos específicos y comparar meticulosamente los resultados obtenidos contra los resultados esperados.
> - _¿Por qué es importante?: Es el filtro final que detecta defectos en la práctica. Su rigor asegura que el diseño del analista se traduzca en una validación real y repetible sobre el producto terminado._
> - _Ejemplo: Un técnico ingresando a la URL de pre-producción para completar un formulario de acceso siguiendo un guion de "Login exitoso"._
> 
> --------------------------------------------------------------------------------
> 
> _La correcta ejecución de estos roles y la calidad de los insumos iniciales son los pilares que permiten construir la anatomía técnica del caso de prueba._
> 
> ## II. ANATOMÍA Y DINÁMICA DEL CASO DE PRUEBA
> 
> La documentación de pruebas es un activo organizacional de alto valor que previene la "fuga de errores" (bug leakage) hacia producción. Una estructura sistemática en el diseño de casos de prueba elimina la subjetividad del tester y asegura una cobertura total de la funcionalidad. En esta fase, es crucial diferenciar entre las respuestas visibles de la interfaz y los estados internos del sistema, permitiendo detectar fallos profundos que una respuesta visual engañosa podría ocultar.
> 
> ### Caminito Feliz (Happy Path)
> 
> - **Definición:** Flujo de ejecución ideal donde el usuario realiza las acciones correctas y el sistema responde satisfactoriamente sin errores ni excepciones.
> - **Explicación ampliada:** Valida el éxito de la funcionalidad básica. Es la línea base de cualquier plan de pruebas; si el "caminito feliz" falla, el software no posee la estabilidad mínima para ser testeado en escenarios más complejos.
> - _¿Por qué es importante?: Establece la prueba de concepto de que el requerimiento principal fue comprendido y desarrollado correctamente en su escenario más frecuente._
> - _Ejemplo: Un alumno con todos sus datos en regla se inscribe a un curso con cupo disponible y recibe su confirmación al primer intento._
> 
> ### Caminito Infeliz (Caminos alternativos/negativos)
> 
> - **Definición:** Flujos de ejecución que contemplan excepciones, errores de datos, o situaciones fuera de la norma.
> - **Explicación ampliada:** Estas pruebas buscan desafiar la robustez del sistema ingresando datos inválidos, duplicados o excesivos para observar cómo gestiona el error sin colapsar.
> - _¿Por qué es importante?: Es donde suelen esconderse los defectos más críticos. Permiten verificar que el sistema "no pinche" (no colapse) ante situaciones inesperadas, protegiendo la integridad de los recursos y la experiencia del usuario._
> - _Ejemplo: Intentar inscribir a un alumno con un "DNI de extranjero" (numeración muy alta que el sistema podría no soportar) o con "apellidos dobles/largos" que excedan el límite de caracteres en la base de datos._
> 
> ### Caso de Prueba (Test Case)
> 
> - **Definición:** Documento formal que detalla la secuencia de pasos, datos de entrada y resultados esperados para validar un escenario particular.
> - **Explicación ampliada:** El objetivo del diseño es el equilibrio: lograr la mayor cobertura funcional con la menor cantidad de pruebas posible. Debe ser lo suficientemente claro para que cualquier miembro del equipo pueda reproducir un fallo de forma exacta.
> - _¿Por qué es importante?: Asegura la prolijidad y evita la redundancia, transformando el testing en una actividad científica y medible en lugar de una búsqueda errática de errores._
> - _Ejemplo: Documento técnico para validar que el sistema rechaza una factura con fecha 31/02._
> 
> ### Caso de Prueba Abstracto
> 
> - **Definición:** Modelo o plantilla de prueba que define la lógica y los pasos a seguir, pero carece de datos reales de entrada (no está instanciado).
> - **Explicación ampliada:** Funciona como una estructura de "herencia" técnica. Permite ahorrar tiempo de diseño al definir una secuencia de pasos que se reutilizará para múltiples combinaciones de datos en casos específicos.
> - _¿Por qué es importante?: Optimiza la fase de diseño y facilita el mantenimiento de la documentación ante cambios en el flujo de los procesos._
> - _Ejemplo: Un guion que indica "Ingresar [Usuario] y [Contraseña]" sin especificar valores concretos._
> 
> ### Caso de Prueba Específico (Instanciado)
> 
> - **Definición:** Versión del caso de prueba que incluye datos de entrada reales y valores de respuesta concretos.
> - **Explicación ampliada:** Es el documento que el tester ejecutor utiliza frente a la pantalla. Contiene la información exacta que debe ser tipeada y el resultado puntual que se debe observar.
> - _¿Por qué es importante?: Elimina la ambigüedad en la ejecución y permite una comparación binaria (pasa/falla) entre la realidad del software y el diseño del analista._
> - _Ejemplo: Ingresar usuario "admin_qa" y contraseña "Pass_2024" para verificar el acceso al panel administrativo._
> 
> ### Condiciones de Ejecución (Precondiciones)
> 
> - **Definición:** Estado previo indispensable en el que debe hallarse el sistema para que la prueba sea válida.
> - **Explicación ampliada:** Describe requisitos como el rol del usuario logueado, la existencia previa de datos en la base o configuraciones de entorno específicas.
> - _¿Por qué es importante?: Previene "falsos negativos". Si las precondiciones no se cumplen, cualquier error detectado podría ser producto del entorno y no del software, malgastando el tiempo del equipo de desarrollo._
> - _Ejemplo: "El alumno debe estar previamente creado en el sistema y no tener deudas pendientes"._
> 
> ### Estado Final Esperado
> 
> - **Definición:** Condición interna en la que debe quedar el sistema tras la ejecución (persistencia de datos).
> - **Explicación ampliada:** Se enfoca en lo que sucede "por detrás" de la interfaz. Mientras que el Valor de Respuesta es visual, el Estado Final valida la integridad de la base de datos o el cambio de estado en un proceso.
> - _¿Por qué es importante?: Detecta fallos donde la interfaz miente. Un sistema puede mostrar un cartel de "Éxito" mientras que internamente no guardó nada o lo hizo de forma errónea._
> - _Ejemplo: En una prueba de Caja Blanca, realizar un_ _**SQL Select**_ _para verificar que el registro existe; en Caja Negra, verificar que el alumno aparece en un_ _**Listado de Inscriptos**_ _funcional._
> 
> ### Valor de Respuesta Esperado
> 
> - **Definición:** Respuesta observable y visible que el sistema entrega al usuario a través de la interfaz.
> - **Explicación ampliada:** Comprende mensajes de éxito, alertas de validación, cambios de pantalla o envíos de correos electrónicos confirmados visualmente.
> - _¿Por qué es importante?: Es la forma en que el software se comunica con el usuario. Una respuesta clara guía el flujo operativo y reduce la incertidumbre._
> - _Ejemplo: Mensaje emergente en pantalla: "Inscripción realizada con éxito. Se envió un comprobante a su mail"._
> 
> --------------------------------------------------------------------------------
> 
> _Una vez estructurada la anatomía del caso, el especialista debe aplicar criterios lógicos para seleccionar qué datos utilizar entre un universo de posibilidades infinitas._
> 
> ## III. ESTRATEGIAS DE DISEÑO, SELECCIÓN DE DATOS Y TIPOLOGÍAS
> 
> El mayor desafío del testing es la "infinitud de las pruebas": es imposible testear cada combinación posible de datos. El especialista debe actuar con precisión quirúrgica, utilizando técnicas lógicas para reducir ese universo a un número eficiente de casos. El objetivo estratégico es encontrar la mayor cantidad de defectos con el menor esfuerzo, garantizando la estabilidad del sistema dentro de los plazos finitos del proyecto.
> 
> ### Clases de Equivalencia
> 
> - **Definición:** Técnica que agrupa datos que el sistema debería procesar de la misma manera, asumiendo que si funciona para un representante del grupo, funcionará para todos.
> - **Explicación ampliada:** Se dividen los inputs en conjuntos válidos e inválidos. En lugar de probar 100 números, se elige uno de cada clase para validar el comportamiento del grupo completo.
> - _¿Por qué es importante?: Reduce drásticamente la redundancia y el tiempo de ejecución sin sacrificar la cobertura de la prueba._
> - _Ejemplo: Para un rango de edad de 18-100, probar con "25" (Válido), "-5" (Inválido negativo), "abc" (Inválido carácter) y "255" (Inválido excedente)._
> 
> ### Data Driven Test (Pruebas dirigidas por datos)
> 
> - **Definición:** Metodología donde la ejecución de la prueba está guiada por combinaciones masivas de datos sobre un mismo flujo de pasos.
> - **Explicación ampliada:** Es ideal cuando la lógica de negocio varía sustancialmente según el dato ingresado pero los pasos operativos son idénticos. Se suele utilizar una tabla de datos (dataset) para alimentar el test case.
> - _¿Por qué es importante?: Permite validar reglas de negocio complejas de forma masiva, asegurando que combinaciones raras de datos no rompan el sistema._
> - _Ejemplo: Un "Formulario de Alta" probado con 20 filas de datos que incluyen nombres con tildes, apellidos muy largos, caracteres especiales y campos vacíos._
> 
> ### Pruebas de Caja Blanca
> 
> - **Definición:** Pruebas realizadas con conocimiento total de la estructura interna, el código fuente y la arquitectura del sistema.
> - **Explicación ampliada:** Requieren habilidades de programación para verificar rutas lógicas, ciclos de control y condiciones internas. El tester "mira dentro de la caja" para asegurar que cada camino del código se ejecute como fue diseñado.
> - _¿Por qué es importante?: Detecta errores de lógica pura y problemas de persistencia que son invisibles desde la interfaz de usuario._
> - _Ejemplo: Consultar la base de datos mediante un script SQL para verificar que el ID de una factura se generó correlativamente._
> 
> ### Pruebas de Caja Negra
> 
> - **Definición:** Pruebas que ignoran la estructura interna del software y se centran exclusivamente en las entradas y salidas desde la perspectiva del usuario.
> - **Explicación ampliada:** El tester trata al sistema como una "caja cerrada". No necesita saber en qué lenguaje está programado; solo valida si el resultado coincide con el requerimiento funcional y las reglas de negocio.
> - _¿Por qué es importante?: Es la validación más fiel de la experiencia del usuario final y asegura que el producto cumple con su propósito comercial._
> - _Ejemplo: Probar un botón de "Recuperar contraseña" verificando solo si llega el mail, sin saber qué función de servidor se activó._
> 
> ### Pruebas de Humo (Smoke Test)
> 
> - **Definición:** Conjunto de pruebas básicas y rápidas destinadas a verificar que las funciones vitales del sistema operan mínimamente después de una nueva versión o build.
> - **Explicación ampliada:** Funciona como un "filtro de estabilidad". Si el Smoke Test falla (por ejemplo, si el sistema no abre o el login no funciona), se rechaza la entrega y no se procede con pruebas profundas.
> - _¿Por qué es importante?: Evita que el equipo de QA malgaste horas intentando testear detalles en un sistema que tiene fallos estructurales o de instalación graves._
> - _Ejemplo: Verificar que tras una actualización de base de datos el sistema permite ingresar y navegar por el menú principal._
> 
> ### Pruebas Beta
> 
> - **Definición:** Fase de prueba realizada por usuarios reales en un entorno externo al de desarrollo, previo al lanzamiento oficial.
> - **Explicación ampliada:** Es la última etapa del ciclo de vida donde se busca feedback sobre usabilidad y se detectan errores en escenarios del "mundo real" que no fueron previstos en el laboratorio controlado de QA.
> - _¿Por qué es importante?: Proporciona una validación final de mercado y ayuda a identificar problemas de compatibilidad en dispositivos o redes que el equipo interno no posee._
> - _Ejemplo: Entregar una versión preliminar de la plataforma de inscripciones a un grupo de 50 alumnos seleccionados para que la utilicen desde sus casas._
> 
> ### Reglas de Negocio
> 
> - **Definición:** Restricciones o directrices lógicas que dictan cómo debe comportarse el sistema según las necesidades del cliente o normativas legales.
> - **Explicación ampliada:** Determinan la validez de los datos más allá de su formato técnico. Son definiciones "vivas" del negocio (ej. "el cliente debe ser mayor de edad para operar").
> - _¿Por qué es importante?: Son el corazón del software. Un sistema puede ser técnicamente perfecto pero un fracaso si no respeta los límites operativos del cliente._
> - _Ejemplo: La restricción lógica que dicta: "No se pueden generar facturas con fecha de hace más de 10 días"._
> 
> ### Valores Límites
> 
> - **Definición:** Técnica de diseño que se centra en probar los extremos o fronteras de las clases de equivalencia.
> - **Explicación ampliada:** La mayoría de los errores de programación ocurren en los límites debido a confusiones lógicas (por ejemplo, usar un `<` en lugar de un `<=`). Se prueban los valores justo antes, en, y justo después de la frontera.
> - _¿Por qué es importante?: Ofrece una eficiencia altísima para detectar defectos de lógica en validaciones numéricas o de fechas con un mínimo de casos de prueba._
> - _Ejemplo: Si el sistema acepta edades de 18 a 100 años, el tester DEBE probar 17, 18, 100 y 101 para asegurar que el límite fue programado correctamente._

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 4 (08 05 26) - Metodología de pruebas de sistemas" src="https://www.youtube.com/embed/dfV3JZL68BU?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1vUGcZTMdL6LUrqCzL2P1pqCBQRMNR3pk/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1fKF15Ydu3nM7rc5qeCLzwC3Vcrrij8kV/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>