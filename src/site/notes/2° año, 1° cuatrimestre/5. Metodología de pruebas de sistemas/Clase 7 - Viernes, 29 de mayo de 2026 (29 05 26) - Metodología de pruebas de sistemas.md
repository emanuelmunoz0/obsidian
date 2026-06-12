---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/5-metodologia-de-pruebas-de-sistemas/clase-7-viernes-29-de-mayo-de-2026-29-05-26-metodologia-de-pruebas-de-sistemas/","dg-note-properties":{}}
---


> [!quote]- Resumen
> # Metodología y Técnicas Avanzadas de Pruebas de Software
> 
> Este documento constituye una guía integral de estudio sobre las metodologías avanzadas para el diseño y ejecución de pruebas de sistemas. Su propósito es proporcionar las herramientas conceptuales y prácticas necesarias para asegurar la calidad de un producto de software mediante la optimización de los casos de prueba, basándose en el análisis de reglas de negocio y flujos de procesos.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> El proceso de pruebas de software ha evolucionado de la simple validación de campos a un análisis estratégico orientado a la eficiencia. El objetivo fundamental no es simplemente encontrar errores —puesto que ningún software puede declararse 100% libre de fallos— sino diseñar la menor cantidad de casos de prueba que representen la mayor cobertura de funcionalidades posible. Esto asegura un producto de alta calidad y una entrega confiable.
> 
> ### Contexto e Importancia
> 
> Las técnicas presentadas en este documento permiten al tester "pensar" el sistema de forma desacoplada de la etapa de desarrollo. Un buen diseño de pruebas permite que un script escrito hoy pueda ser ejecutado meses después por cualquier integrante del equipo, garantizando la consistencia y permitiendo el análisis de datos históricos para identificar qué módulos presentan mayor recurrencia de problemas.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual
> 
> Para comprender las técnicas avanzadas, es necesario dominar los conceptos fundamentales que estructuran un caso de prueba profesional:
> 
> ### Componentes de un Caso de Prueba
> 
> Todo caso de prueba debe contener, de forma obligatoria, cinco elementos para ser funcional y ejecutable:
> 
> 1. **Pasos a seguir:** Instrucciones detalladas de la ejecución.
> 2. **Datos de entrada:** Valores específicos con los que se operará.
> 3. **Resultados esperados:** El comportamiento que el sistema debe mostrar según los datos ingresados.
> 4. **Precondiciones:** El estado inicial requerido del sistema antes de la prueba.
> 5. **Postcondiciones:** El estado en el que queda el sistema al finalizar la prueba.
> 
> ### Datos Administrativos
> 
> Además de los componentes de ejecución, se suelen incluir datos de gestión que permiten el análisis posterior (métricas):
> 
> - ID del caso de prueba y título descriptivo.
> - Autor y revisor.
> - Fecha de creación y de ejecución.
> - Caso de uso del que depende y justificación.
> - Módulo o entidad asociada (para identificar áreas críticas).
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema
> 
> ### 3.1 Pruebas Basadas en Tablas de Decisión (Tablas de Verdad)
> 
> Esta técnica se utiliza específicamente cuando el sistema debe validar **reglas de negocio**. A diferencia de las validaciones de campos (donde se usan Clases de Equivalencia), las tablas de decisión modelan comportamientos complejos basados en la combinación de múltiples condiciones.
> 
> - **Reglas de Negocio:** Son las normas que rigen el comportamiento del sistema ante situaciones específicas (ej. otorgamiento de créditos según perfil).
> - **Estructura de la Tabla:**
>     - **Condiciones:** Variables de entrada (ej. ¿Es jubilado?, ¿Monto > $50,000?).
>     - **Acciones:** Resultados o comportamientos del sistema (ej. Aprobar, Denegar, Solicitar revisión).
>     - **Reglas:** Cada columna representa una combinación lógica de condiciones (Verdadero/Falso) y su acción resultante.
> 
> ### 3.2 Derivación de Casos de Prueba desde Casos de Uso
> 
> Esta técnica utiliza el **Diagrama de Actividad (UML)** para modelar el flujo de un proceso y asegurar que se prueben todos los recorridos posibles.
> 
> - **Flujo Normal:** El camino ideal donde todo sale bien.
> - **Flujos Alternativos:** Desvíos previstos que no son errores (ej. "olvidé mi contraseña").
> - **Excepciones:** Situaciones de error que interrumpen el flujo o requieren acciones especiales (ej. cuenta bloqueada tras tres intentos fallidos).
> 
> #### El rol del Diagrama de Actividad
> 
> El diagrama permite visualizar de forma metódica:
> 
> - **Recorridos (Caminos):** Cada línea de principio a fin es un caso de prueba potencial.
> - **Bucles (Loops):** Situaciones donde el sistema regresa a un paso anterior (ej. reintento de login). Se deben probar los límites del bucle (primer intento, segundo intento, límite de bloqueo).
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Relaciones entre Conceptos
> 
> Es vital distinguir cuándo aplicar cada herramienta según la necesidad del proyecto:
> 
> |   |   |   |
> |---|---|---|
> |Técnica|Propósito Principal|Aplicación Clave|
> |**Clases de Equivalencia y Valores Límite**|Validar atributos, variables o campos individuales.|Formularios, fechas, montos.|
> |**Pairwise (PW)**|Ahorrar casos de prueba ante múltiples combinaciones de datos de distintos tipos.|Configuraciones de sistema, compatibilidad.|
> |**Matriz CRUD**|Asegurar que las entidades puedan ser Creadas, Leídas, Actualizadas y Borradas.|Gestión de bases de datos y entidades.|
> |**Tablas de Decisión**|Validar lógica compleja y cruzamiento de reglas.|Sistemas de seguros, créditos, impuestos.|
> |**Derivación (UML)**|Cubrir todos los caminos de un proceso.|Flujos de navegación, procesos de compra.|
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Ejemplos Prácticos
> 
> ### Ejemplo 1: Tabla de Decisión (Aprobación de Créditos)
> 
> **Enunciado:** Un sistema aprueba créditos automáticamente a empleados. A los jubilados solo si el monto es menor a $50,000. Los estudiantes siempre son denegados.
> 
> |   |   |   |   |   |
> |---|---|---|---|---|
> |Condición / Regla|R1 (Empleado)|R2 (Jubilado)|R3 (Jubilado)|R4 (Estudiante)|
> |**¿Es Empleado?**|V|F|F|F|
> |**¿Es Jubilado?**|F|V|V|F|
> |**¿Es Estudiante?**|F|F|F|V|
> |**¿Monto < $50,000?**|Indiferente|V|F|Indiferente|
> |**ACCIÓN: Aprobado**|**X**|**X**|||
> |**ACCIÓN: Denegado**|||**X**|**X**|
> 
> _Nota: Se eliminan redundancias. Si para el empleado el monto no importa, se consolida en un solo caso._
> 
> ### Ejemplo 2: Derivación desde Diagrama de Actividad (Sistema de Login)
> 
> Para un sistema de login con bloqueo al 3er intento, se derivan los siguientes recorridos:
> 
> 1. **Caso 1 (Éxito):** Ingreso de credenciales correctas al primer intento.
> 2. **Caso 2 (Recuperación):** El usuario olvida la contraseña y solicita mail de recuperación.
> 3. **Caso 3 (Error y Éxito):** Falla el 1er intento, acierta en el 2do.
> 4. **Caso 4 (Bloqueo):** Falla 1er, 2do y 3er intento -> Sistema bloquea la cuenta.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores Comunes y Confusiones
> 
> - **Confundir Pairwise con Tablas de Decisión:** Pairwise se usa para combinar datos diversos y ahorrar casos; las Tablas de Decisión se usan para validar que se cumplan las **reglas de negocio** impuestas por el cliente.
> - **Omitir los bucles en UML:** Un error frecuente es no probar qué pasa en el intermedio de un bucle (ej. probar el 1er y el 3er intento de login, pero no el 2do).
> - **Exceso de datos administrativos:** Poner demasiados campos obligatorios en la planilla de gestión puede hacer el proceso engorroso y quitar tiempo valioso a la ejecución de pruebas.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Síntesis y Conclusiones
> 
> - **Calidad sobre cantidad:** El éxito no es hacer miles de pruebas, sino las pruebas correctas.
> - **Metodología:** El uso de tablas de verdad y diagramas de actividad garantiza que no se olviden "caminos" o combinaciones críticas de reglas de negocio.
> - **Desacoplamiento:** Los casos de prueba deben ser autosuficientes para que cualquier persona pueda ejecutarlos basándose en los pasos y datos definidos.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuáles son los 5 elementos obligatorios de todo caso de prueba?
> 2. ¿Cuál es la diferencia principal entre un flujo alternativo y una excepción en un caso de uso?
> 3. ¿Para qué sirve una Matriz CRUD?
> 
> ### Nivel Intermedio
> 
> 4. ¿En qué situaciones es preferible usar una Tabla de Decisión en lugar de Clases de Equivalencia?
> 5. Si un sistema tiene un bucle de 3 reintentos, ¿cuántos casos de prueba como mínimo deberías diseñar para cubrir ese comportamiento?
> 6. ¿Por qué se dice que el Pairwise ayuda a la eficiencia del tester?
> 
> ### Nivel Avanzado
> 
> 7. Explique cómo los datos administrativos de un caso de prueba ayudan a la gestión de proyectos a largo plazo.
> 8. Analice la siguiente situación: Un sistema de seguros varía la prima según edad, historial de multas y tipo de vehículo. ¿Qué técnica aplicaría para organizar las pruebas y por qué?
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Fechas Importantes y Avisos Académicos
> 
> A continuación, se detallan las fechas y pautas organizativas proporcionadas para el cierre del cuatrimestre:
> 
> |   |   |   |
> |---|---|---|
> |Fecha|Tipo de Evento|Descripción Detallada|
> |**Viernes 12 de Junio**|**Segundo Parcial**|Evaluación de los temas teóricos de la segunda mitad del cuatrimestre. Incluye todas las técnicas de diseño de casos de prueba.|
> |**Viernes 26 de Junio**|**Recuperatorio**|Fecha única para recuperar el primer o segundo parcial (solo se permite recuperar uno).|
> |**Próxima Clase (Pre-parcial)**|**Taller de TP**|La clase se dividirá en grupos para revisión del Trabajo Práctico. El docente se reunirá 15 min con cada grupo.|
> 
> ### Recordatorios del Profesor:
> 
> - **Finalización de Teoría:** Con la explicación de Tablas de Decisión y Derivación desde Casos de Uso, se dan por terminados los temas teóricos del cuatrimestre.
> - **Material de Estudio:** Se debe estudiar de la presentación principal, complementada con la bibliografía obligatoria (Capítulos de Calidad de libros de Ingeniería de Software, Libro de testing de Federico Toledo y materiales del ISTQB).
> - **Pautas del Trabajo Práctico (TP):**
>     - Debe incluir: Formulario con variables, Diagrama de Estados, aplicación de Pairwise, Diagrama de Actividad (UML) con sus casos derivados y una Tabla de Verdad para reglas de negocio.
>     - Plazo de entrega: 3 semanas a partir de la fecha.
> - **Organización de la Próxima Clase (Revisión de TP):**
>     - Grupo 1: 19:00 hs.
>     - Grupo 2: 19:15 hs.
>     - Grupo 3: 19:30 hs.
>     - Grupo 4: 19:45 hs.
>     - Grupo 5: 20:00 hs.
>     - _Nota: Se realizará una segunda vuelta de consultas a partir de las 20:15 hs si es necesario._

> [!quote]- Glosario
> # Glosario Crítico de Aseguramiento de Calidad y Metodologías de Prueba
> 
> **SECCIÓN A - D: FUNDAMENTOS Y TÉCNICAS ESTRUCTURALES**
> 
> El diseño estratégico de las pruebas de software comienza con lo que en cátedra denominamos la "hoja mágica": una organización metódica que actúa como el principal escudo del analista frente al caos. La importancia estratégica de estos términos iniciales radica en su capacidad para transformar requisitos amorfos en una estructura técnica que reduce redundancias y optimiza el esfuerzo. Al aplicar estas técnicas, no buscamos simplemente "probar", sino justificar científicamente por qué ciertos casos son representativos, permitiendo que la validación sea un proceso eficiente y no una repetición infinita de datos similares.
> 
> ## Atributos (Variables)
> 
> **Definición:** Representan los campos, elementos de entrada o variables específicas que componen un módulo del sistema, los cuales poseen características y validaciones propias que deben ser evaluadas.
> 
> **Explicación ampliada:** Para el analista de QA, identificar los atributos es el paso inicial para desglosar la complejidad. Sobre estos elementos se aplican las reglas de validación (tipo de dato, longitud, obligatoriedad) que determinan si una entrada es aceptada. Es la unidad mínima de análisis antes de pasar a la lógica de negocio.
> 
> **Ejemplo:** En un formulario de solicitud de créditos, los atributos incluyen la "Categoría del Solicitante" (un dropdown con opciones) y el "Monto Solicitado" (un campo numérico).
> 
> ## Casos de Prueba
> 
> **Definición:** Conjunto de condiciones, pasos e instrucciones documentadas, basadas en estándares como el ISTQB, diseñadas para que un evaluador determine si una funcionalidad cumple con los requisitos especificados.
> 
> **Explicación ampliada:** Su importancia fundamental reside en el "desacoplamiento" de la fase de escritura y la de ejecución. Un caso de prueba bien construido permite que el analista actual o "la Paula del futuro" pueda ejecutar la validación sin ambigüedades. Según los estándares de ingeniería, un caso de prueba profesional debe contener obligatoriamente cinco elementos: pasos a seguir, datos de entrada, resultados esperados, precondiciones y postcondiciones.
> 
> **Ejemplo:** Un documento detallado que indica cómo validar el acceso al sistema, especificando el ingreso a la URL, la carga de credenciales y la verificación del mensaje de bienvenida.
> 
> ## Casos de Uso
> 
> **Definición:** Descripciones narrativas extraídas de la bibliografía de ingeniería de software que detallan la interacción entre un actor y el sistema para alcanzar un objetivo.
> 
> **Explicación ampliada:** El analista utiliza el caso de uso como el "mapa de ruta" para derivar pruebas funcionales. La trazabilidad entre el caso de uso y el caso de prueba es vital para la gestión: permite identificar qué módulos son más complejos y han requerido mayor esfuerzo de revisión debido a la densidad de errores encontrados.
> 
> **Ejemplo:** El caso de uso "Registro de Usuario", que detalla si el usuario debe loguearse con credenciales existentes o crear una cuenta nueva si no posee una.
> 
> ## Clases de Equivalencia
> 
> **Definición:** Técnica de diseño de cajas negras que divide los datos de entrada en grupos de tal forma que el sistema los procese de manera idéntica.
> 
> **Explicación ampliada:** Es la herramienta de optimización por excelencia. Su justificación técnica reside en que, si un valor representativo de la clase funciona, asumimos que todos los demás valores de esa misma clase están "probados por proxy". Esto evita la ejecución de miles de pruebas redundantes, manteniendo la integridad del proceso.
> 
> **Ejemplo:** Para un campo de monto de crédito, se define una clase para "Montos < 50,000" y otra para "Montos ≥ 50,000", seleccionando un solo valor de cada rango para la prueba.
> 
> ## Cobertura de Funcionalidades
> 
> **Definición:** Indicador de gestión que mide el grado en que el plan de pruebas abarca el total de los requisitos funcionales del sistema.
> 
> **Explicación ampliada:** El objetivo máximo del analista es lograr la mayor cobertura posible con la menor cantidad de casos de prueba. Es un balance entre eficiencia y seguridad, asegurando que ningún rincón crítico del software quede sin validar antes de la entrega.
> 
> **Ejemplo:** Asegurarse de que el plan de pruebas incluya escenarios específicos para empleados, jubilados y estudiantes, cubriendo así todas las ramificaciones del sistema de créditos.
> 
> ## Datos Administrativos
> 
> **Definición:** Información complementaria registrada en la documentación de pruebas con fines de gestión, trazabilidad y análisis métrico.
> 
> **Explicación ampliada:** Aunque pueden parecer engorrosos, campos como el ID del caso, autor, revisor, fecha de ejecución y módulo asociado son críticos para el análisis posterior. Permiten al líder de QA detectar, por ejemplo, qué módulos presentan mayor recurrencia de fallos o cuánto tiempo transcurre entre la escritura y la ejecución de una prueba.
> 
> **Ejemplo:** Registrar en una planilla de control que el Caso #101 fue escrito por "Paula" y depende directamente del Caso de Uso de "Facturación".
> 
> ## Datos de Prueba
> 
> **Definición:** Valores específicos de entrada que se suministran al sistema durante la ejecución para obtener un resultado concreto.
> 
> **Explicación ampliada:** Es uno de los cinco elementos obligatorios de todo caso de prueba según la bibliografía técnica. Sin datos precisos (valores reales), la prueba carece de validez, ya que el resultado esperado está intrínsecamente atado a la naturaleza del dato ingresado.
> 
> **Ejemplo:** Ingresar el valor exacto de "45,000" en el campo de monto para validar que el sistema aplique la regla de aprobación automática para jubilados.
> 
> _La correcta estructuración de estos datos sienta las bases para el siguiente nivel de análisis: el modelado del comportamiento lógico y la persistencia de la información._
> 
> **SECCIÓN E - M: MODELADO DE COMPORTAMIENTO Y PERSISTENCIA**
> 
> El modelado visual y la gestión de entidades (CRUD) permiten una profundidad de cobertura que las pruebas de campo simples no alcanzan. Mientras que un test de campo valida una entrada aislada, el modelado del comportamiento permite detectar errores en la lógica de navegación y en la persistencia de datos. Evaluar las transiciones de estado y la integridad de las entidades asegura que el software no solo acepte datos, sino que los procese y conserve respetando el ciclo de vida de la información del negocio.
> 
> ## Diagrama de Actividad UML
> 
> **Definición:** Representación gráfica que modela el flujo de trabajo, las actividades, los bucles y las bifurcaciones de decisión dentro de un proceso.
> 
> **Explicación ampliada:** Omitir este modelado visual impide que el analista detecte "caminos ciegos" o bucles infinitos. Facilita la visualización de todos los recorridos posibles, permitiendo derivar casos de prueba que garanticen que el usuario puede navegar por el sistema sin quedar atrapado en errores lógicos.
> 
> **Ejemplo:** Modelar el flujo de login que incluye el acceso, el ingreso de credenciales y el bucle de reintento que se activa hasta el tercer intento fallido.
> 
> ## Eliminación Lógica vs. Física
> 
> **Definición:** La eliminación física borra permanentemente el registro de la base de datos; la eliminación lógica simplemente desactiva o marca el registro como inactivo (flag), ocultándolo de la vista del usuario pero preservándolo en el almacenamiento.
> 
> **Explicación ampliada:** En la ingeniería de software moderna, la eliminación física es inusual porque destruye el historial de negocio. El analista debe probar la eliminación lógica asegurándose de que la entidad "desaparezca" de las búsquedas activas, pero que su "ficha histórica" permanezca íntegra en la base de datos para futuras auditorías o reportes.
> 
> **Ejemplo:** Desactivar un registro de mascota en el sistema de una veterinaria para que no aparezca en la agenda del día, manteniendo sus datos médicos históricos accesibles.
> 
> ## Entidades
> 
> **Definición:** Objetos o conceptos centrales del dominio del negocio que el sistema debe gestionar, almacenar y manipular.
> 
> **Explicación ampliada:** Si el analista falla en identificar las entidades principales, dejará funcionalidades críticas sin probar. Cada entidad debe ser sometida a un ciclo completo de vida (CRUD) para asegurar que el sistema pueda manejarla correctamente desde su creación hasta su eventual baja.
> 
> **Ejemplo:** En un sistema de gestión hospitalaria, las entidades primordiales serían el "Paciente", el "Médico" y el "Turno".
> 
> ## Errores de Software (Naturaleza residual)
> 
> **Definición:** Concepto académico y profesional que establece que es imposible garantizar la ausencia total de defectos; los errores siempre están presentes, incluso si aún no han sido detectados.
> 
> **Explicación ampliada:** Como analistas, debemos aceptar que el software "cero errores" es una utopía. Siempre existe una "combinación esotérica" de datos o condiciones ambientales que, a futuro, manifestará un fallo residual. Nuestra misión no es encontrar "todos" los errores, sino minimizar el riesgo encontrando la mayor cantidad posible antes de la entrega final.
> 
> **Ejemplo:** Una falla que ocurre meses después de la implementación debido a una interacción imprevista entre el volumen de datos y una actualización de servidor no testeada.
> 
> ## Estados (Transiciones de)
> 
> **Definición:** Las diversas condiciones o etapas por las que atraviesa un proceso o entidad a medida que avanza en el circuito del sistema.
> 
> **Explicación ampliada:** Ignorar las transiciones puede generar un software que permita saltarse pasos obligatorios. El analista debe asegurar que el circuito funcione y que el elemento transite por todos los estados lógicos (ej. de "Pendiente" a "Aprobado") sin errores de secuencia.
> 
> **Ejemplo:** El seguimiento de un turno médico desde su solicitud, pasando por la confirmación, hasta su estado final de "Atendido" o "Cancelado".
> 
> ## Excepciones
> 
> **Definición:** Situaciones de error o comportamientos atípicos que el sistema debe identificar y gestionar de manera controlada para evitar un colapso.
> 
> **Explicación ampliada:** Las excepciones son el "manejo de crisis" del software. El analista debe verificar que, ante un fallo (como una caída de red o un dato inválido), el sistema informe al usuario adecuadamente en lugar de producir una terminación anormal del programa.
> 
> **Ejemplo:** El sistema notificando que "El email ingresado no existe" en un flujo de recuperación de contraseña, en lugar de mostrar una pantalla de error genérico.
> 
> ## Flujos (Normal y Alternativo)
> 
> **Definición:** El flujo normal (o "happy path") es el camino ideal donde el usuario cumple su objetivo sin inconvenientes; los flujos alternativos son desviaciones válidas que no constituyen errores, sino opciones distintas de navegación.
> 
> **Explicación ampliada:** Limitarse a probar el flujo normal deja al software vulnerable ante la realidad del uso. Los usuarios suelen tomar caminos alternativos, y el analista debe certificar que el sistema responde correctamente a estas variantes de decisión.
> 
> **Ejemplo:** En un login, el flujo normal es entrar con credenciales; un flujo alternativo es el usuario optando por "Crear una cuenta" porque se da cuenta de que no posee una.
> 
> ## Matriz CRUD
> 
> **Definición:** Herramienta técnica de control que verifica que para cada entidad del sistema se hayan implementado y probado las cuatro operaciones básicas: Crear (Create), Leer (Read), Actualizar (Update) y Borrar/Desactivar (Delete).
> 
> **Explicación ampliada:** Es una salvaguarda de integridad. Al utilizarla, el analista garantiza que ninguna entidad quede "huérfana" de funciones esenciales, asegurando la gestión completa del objeto de negocio durante todo su ciclo de vida.
> 
> **Ejemplo:** En una veterinaria, verificar que se pueda dar de alta a un paciente, visualizar su ficha, editar su peso y, de ser necesario, desactivar su registro si deja de asistir.
> 
> _Este modelado nos prepara para enfrentar la complejidad de las reglas de negocio mediante herramientas lógicas avanzadas diseñadas para optimizar la toma de decisiones._
> 
> **SECCIÓN P - Z: LÓGICA DE NEGOCIO Y HERRAMIENTAS DE DECISIÓN**
> 
> La complejidad de las reglas de negocio modernas exige herramientas que transformen requisitos ambiguos en escenarios de prueba exactos. Mientras que las técnicas combinatorias como Pairwise resuelven el problema del volumen de variables, las Tablas de Decisión abordan la lógica booleana profunda. Ambas permiten al analista diseccionar las condiciones del sistema, asegurando que la conjunción de múltiples factores no resulte en comportamientos inesperados, elevando la precisión técnica del proceso de QA.
> 
> ## Pairwise (PWS)
> 
> **Definición:** Técnica de diseño de pruebas combinatorias basada en la evidencia de que la mayoría de los defectos son causados por la interacción de, a lo sumo, dos parámetros.
> 
> **Explicación ampliada:** Se utiliza cuando el analista enfrenta una explosión combinatoria de variables que hace imposible probar todas las permutaciones. Su gran valor reside en la _justificación_: no probamos todo, pero garantizamos que todos los pares posibles han sido validados, reduciendo drásticamente la cantidad de casos sin sacrificar significativamente la detección de fallas.
> 
> **Ejemplo:** Combinar 3 canales de atención (presencial, teléfono, email) con 4 prioridades y 3 tipos de servicios bancarios; en lugar de 36 pruebas, Pairwise permite cubrir todas las interacciones de pares con una fracción de esos casos.
> 
> ## Postcondición
> 
> **Definición:** Estado final e inalterable en el que debe quedar el sistema y sus datos una vez finalizada la ejecución exitosa de una prueba.
> 
> **Explicación ampliada:** Es uno de los cinco elementos obligatorios de un caso de prueba profesional. Su validación confirma que la transacción no solo fue aceptada, sino que impactó correctamente en el ecosistema del software (ej. actualización de tablas, envío de correos).
> 
> **Ejemplo:** Tras un login exitoso, la postcondición es que el usuario tenga acceso a su panel y su ingreso conste en la tabla de "Actividad de Usuarios".
> 
> ## Precondición
> 
> **Definición:** Condición o estado previo que debe cumplirse obligatoriamente para que un caso de prueba pueda ser ejecutado y arroje resultados válidos.
> 
> **Explicación ampliada:** Al ser un dato obligatorio, su omisión invalida la prueba. Si el sistema no se encuentra en el estado inicial requerido, el analista no puede determinar si un fallo posterior se debe a la funcionalidad probada o a un entorno mal preparado.
> 
> **Ejemplo:** Para probar la "Reprogramación de Turno", la precondición obligatoria es que el turno ya exista y esté en estado "Confirmado" en la base de datos.
> 
> ## Reglas de Negocio
> 
> **Definición:** Conjunto de normas, restricciones y políticas que definen el comportamiento inteligente y la toma de decisiones del software.
> 
> **Explicación ampliada:** Son el corazón lógico del sistema. A diferencia de las validaciones de campo (como "solo números"), las reglas de negocio determinan flujos complejos en función de múltiples condiciones (ej. quién es elegible para un beneficio). Su correcta identificación es lo que diferencia a un tester de campo de un analista de calidad senior.
> 
> **Ejemplo:** La regla que determina que el sistema solo aprueba créditos automáticos para jubilados si el monto solicitado es estrictamente menor a 50,000 pesos.
> 
> ## Resultados Esperados
> 
> **Definición:** La respuesta, mensaje o comportamiento previsto que el software debe manifestar tras la ejecución de los pasos con los datos de prueba suministrados.
> 
> **Explicación ampliada:** Es el elemento obligatorio que define el éxito o fracaso de la prueba. Debe estar alineado perfectamente con los requisitos y las reglas de negocio para evitar interpretaciones subjetivas por parte del tester.
> 
> **Ejemplo:** El sistema debe mostrar el mensaje "Solicitud Denegada" si el solicitante es un estudiante.
> 
> ## Script de Pruebas
> 
> **Definición:** Documento técnico que materializa el Caso de Prueba en una secuencia detallada de pasos e instrucciones de ejecución.
> 
> **Explicación ampliada:** Su propósito es desacoplar la escritura de la ejecución. Un buen script permite que "la Paula del futuro" o cualquier otro integrante del equipo ejecute la prueba con exactitud meses después de haber sido escrita, garantizando la repetibilidad del proceso.
> 
> **Ejemplo:** Una secuencia numerada: 1. Ingresar a la URL, 2. Cargar usuario "test_user", 3. Presionar "Olvidé mi contraseña".
> 
> ## Tabla de Decisión (Tabla de Verdad)
> 
> **Definición:** Matriz lógica que organiza condiciones y acciones resultantes mediante combinaciones booleanas (Verdadero/Falso) para representar reglas de negocio complejas.
> 
> **Explicación ampliada:** A diferencia de Pairwise, que es una herramienta _combinatoria_ para ahorrar tiempo entre variables, la Tabla de Decisión es una herramienta _lógica_. Se utiliza cuando el resultado depende de la conjunción de múltiples reglas de negocio interrelacionadas, asegurando que no se pase por alto ninguna combinación de condiciones que deba arrojar un resultado específico (como "Aprobar", "Denegar" o "Reprogramar").
> 
> **Ejemplo:** Una tabla que cruza las condiciones "Es Empleado", "Es Jubilado" y "Monto < 50,000" para determinar de forma prolija la acción de aprobación del crédito.
> 
> ## Valores Límites
> 
> **Definición:** Técnica de prueba de caja negra que se centra en los extremos de las clases de equivalencia, donde la probabilidad de encontrar errores de programación es mayor.
> 
> **Explicación ampliada:** Complementa a las Clases de Equivalencia. El analista sabe que los desarrolladores suelen cometer errores en los bordes de los rangos (confundiendo un "menor" con un "menor o igual"). Probar el valor límite, el inmediatamente superior y el inmediatamente inferior maximiza la detección de fallas en la lógica de control.
> 
> **Ejemplo:** Si el límite para un crédito es 50,000, el analista debe probar con 49,999, 50,000 y 50,001 para validar que la restricción se aplique exactamente donde corresponde.
> 
> _El dominio de estas herramientas permite al profesional de QA cumplir con el axioma fundamental de nuestra disciplina: alcanzar la mayor cobertura funcional con el menor número de casos posibles._

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 7 (29 05 26) - Metodología de pruebas de sistemas" src="https://www.youtube.com/embed/PkFYCV9LvCw?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1mPz90nAS7mI-x3fUoiIQGHcO0UavNmik/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1CEulWA9SrUneP-ZzCAc9diUPTVhjWW7d/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 

> [!quote]- <a href="https://notebooklm.google.com/notebook/74ff5218-7c6c-4d94-9e3c-a8b0f7e388f4/artifact/b1497cbc-8359-42ed-be69-ca3ea08242df?utm_source=nlm_web_share&utm_medium=google_oo&utm_campaign=art_share_2&utm_content=&utm_smc=nlm_web_share_google_oo_art_share_2_" target="_blank" style="color: inherit; font-weight: bold;">Cuestionario de repaso</a>