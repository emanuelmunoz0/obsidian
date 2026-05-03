---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/5-metodologia-de-pruebas-de-sistemas/clase-2-viernes-10-de-abril-de-2026-10-04-26-metodologia-de-pruebas-de-sistemas/","dg-note-properties":{}}
---


> [!quote]- Resumen
> # Metodología y Fundamentos de las Pruebas de Software: Guía Integral de Estudio
> 
> Este documento constituye un compendio exhaustivo y detallado sobre la metodología de pruebas de sistemas, diseñado para funcionar como material de estudio principal. Aborda desde los conceptos básicos hasta las distinciones técnicas avanzadas necesarias para la gestión de la calidad en el desarrollo de software.
> 
> ## 1. Introducción y Contexto
> 
> La calidad en el desarrollo de software no es un elemento periférico, sino una fase esencial e intrínseca al ciclo de vida del sistema. Las pruebas (testing) se integran en todas las etapas, desde la especificación inicial hasta el mantenimiento posproducción.
> 
> ### La Importancia de la Curva de Costos
> 
> Un concepto fundamental en la disciplina es la relación entre el momento de detección de un problema y el costo de su resolución. La eficiencia económica del proyecto depende de la detección temprana:
> 
> - **Detección en Diseño/Especificación:** El costo es mínimo, ya que solo implica refactorizar documentos o modificar diagramas.
> - **Detección en Desarrollo:** El costo aumenta, pues requiere horas de reprogramación.
> - **Detección en Producción (Software en funcionamiento):** Es el escenario más costoso y crítico. Implica pérdida de visibilidad, posibles bajas de clientes, costos laborales de urgencia y la necesidad de dar de baja el sistema temporalmente para implementar correcciones.
> 
> ## 2. Marco Conceptual y Terminología Fundamental
> 
> Para dominar la materia, es imperativo distinguir con precisión términos que en el lenguaje cotidiano suelen utilizarse como sinónimos, pero que en la ingeniería de calidad tienen significados específicos.
> 
> ### Diccionario Técnico: Error, Defecto y Falla
> 
> |Término|Definición|Contexto|
> |---|---|---|
> |**Error**|Acción humana involuntaria que conduce a un problema potencial.|Humano (ej. carga incorrecta de datos).|
> |**Defecto (Bug)**|Problema real en el código o diseño del software.|Etapa de desarrollo o testing.|
> |**Falla (Failure)**|Problema observado por el usuario final cuando el sistema no se comporta como se espera.|Entorno productivo (usuario final).|
> 
> ### Verificación vs. Validación
> 
> Esta distinción es crítica para la gestión de requerimientos:
> 
> 1. **Validación:** Proceso de chequear si los requerimientos documentados (ERS) cumplen con las necesidades reales del usuario. Se responde a la pregunta: _¿Estamos construyendo el producto correcto?_ Se realiza idealmente al final de la etapa de especificación.
> 2. **Verificación:** Proceso de comprobar si el producto de software desarrollado coincide con lo que se especificó en los requerimientos. Se responde a la pregunta: _¿Estamos construyendo el producto correctamente?_
> 
> ## 3. Principios Fundamentales del Software Testing
> 
> El proceso de pruebas se rige por siete principios básicos que guían al profesional:
> 
> 1. **La detección temprana ahorra recursos:** Cuanto antes se encuentre un problema, más barata es su solución.
> 2. **La exhaustividad es imposible:** No se pueden probar todas las combinaciones posibles de datos y caminos. Se debe buscar la mayor cobertura con los recursos disponibles.
> 3. **Las pruebas muestran la presencia de errores, no su ausencia:** Una prueba exitosa confirma que hay un error; la ausencia de errores en una prueba no garantiza que el sistema sea perfecto.
> 4. **Agrupamiento de defectos:** Los errores suelen concentrarse en módulos específicos del sistema.
> 5. **Paradoja del Pesticida:** Si se repiten siempre las mismas pruebas, el sistema se vuelve "inmune" y no se encontrarán defectos nuevos. Es necesario renovar los casos de prueba.
> 6. **La ausencia de errores es una falacia:** Un software sin errores detectados puede ser inútil si no satisface las necesidades del usuario o no cumple con el propósito para el que fue creado.
> 7. **Dependencia del contexto:** El nivel y tipo de pruebas dependen de la criticidad del sistema (ej. un sistema bancario requiere más rigor que una agenda personal).
> 
> ## 4. Gestión de la Calidad: QA vs. QC
> 
> Es común confundir el aseguramiento de la calidad con el control de la calidad. Sus enfoques son distintos:
> 
> ### Quality Assurance (QA - Aseguramiento de la Calidad)
> 
> - **Enfoque:** Orientado al **proceso**.
> - **Naturaleza:** Preventivo.
> - **Objetivo:** Garantizar que los procedimientos de trabajo sean los correctos para evitar errores futuros.
> - **Ejemplo:** Manuales de buenas prácticas, estandarización de procesos, checklists de cumplimiento.
> 
> ### Quality Control (QC - Control de la Calidad / Testing)
> 
> - **Enfoque:** Orientado al **producto**.
> - **Naturaleza:** Correctivo.
> - **Objetivo:** Inspeccionar el sistema terminado para detectar defectos antes de la entrega.
> - **Ejemplo:** Ejecución de casos de prueba sobre el software ejecutable.
> 
> **Analogía del Colchón:** El QA asegura que la fábrica use siempre la misma tela y resortes siguiendo un manual (proceso estandarizado). El QC es la prueba final de resistencia de un colchón específico antes de salir al mercado.
> 
> ## 5. Estrategias y Tipos de Pruebas
> 
> ### Pruebas Estáticas: Inspecciones
> 
> No requieren la ejecución del código. Consisten en la revisión de documentos (ERS, arquitectura, diagramas UML, esquemas de bases de datos).
> 
> - **Inspección de Programa:** Un experto lee las líneas de código sin ejecutarlo para identificar mejoras en algoritmos o nombres de variables.
> - **Ventaja:** Permite encontrar errores antes de que el software exista físicamente.
> 
> ### Pruebas Dinámicas: Ofensivas y Defensivas
> 
> - **Testing Ofensivo:** El tester "ataca" el software con el objetivo deliberado de encontrar fallos y romper el sistema.
> - **Testing Defensivo:** Se busca demostrar que el software funciona correctamente según lo esperado.
> - **UAT (User Acceptance Test):** Pruebas de aceptación del usuario. Se realizan al final del ciclo. Es el punto donde el cliente valida que el producto cumple con lo pactado y habilita el pago y paso a producción.
> 
> ### Prototipado
> 
> Creación de maquetas (ej. con herramientas como Whimsical) que simulan la interfaz del sistema. Ayudan al cliente a visualizar el producto final y corregir ambigüedades en los requerimientos antes de iniciar la codificación costosa.
> 
> ## 6. El Nivel de Confianza y el Mercado
> 
> El testing no es infinito; tiene un costo y un tiempo. El nivel de confianza deseado depende de:
> 
> 1. **Propósito del sistema:** Un error en una historia clínica es más crítico que en una agenda digital.
> 2. **Expectativas del usuario:** Qué nivel de fallo está dispuesto a tolerar el cliente.
> 3. **Entorno del mercado:** A veces, salir primero al mercado es más importante que salir perfecto.
> 
> **Caso de Estudio: WhatsApp vs. Telegram** Telegram surgió con funciones superiores y mayor robustez técnica. Sin embargo, WhatsApp priorizó salir rápido al mercado con una base de usuarios masiva. Aunque inicialmente tenía más errores y menos funciones que Telegram, WhatsApp ganó la cuota de mercado por oportunidad y tiempo, mejorando su calidad progresivamente.
> 
> ## 7. Síntesis y Conclusiones
> 
> - **El testing es multidisciplinario:** Involucra desde la revisión de documentos hasta la ejecución de datos artificiales.
> - **Calidad es prevención:** Cuanto más esfuerzo se ponga en QA e inspecciones tempranas, menor será el riesgo de fallas costosas en producción.
> - **No existe el software perfecto:** El objetivo es alcanzar un nivel de confianza aceptable según el contexto y el riesgo del negocio.
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia entre un error, un defecto y una falla?
> 2. ¿Por qué es más económico corregir un error en la etapa de diseño que en la de producción?
> 3. Defina brevemente qué es el Testing Defensivo.
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia entre Validación y Verificación. ¿En qué momento del desarrollo se realiza cada una?
> 5. ¿Qué es la "Paradoja del Pesticida" y cómo afecta a la planificación de pruebas?
> 6. Compare QA y QC en términos de enfoque y objetivos.
> 
> ### Nivel Avanzado
> 
> 7. Analice cómo el contexto del mercado influye en la decisión de cuánto tiempo dedicar al testing, utilizando el ejemplo de WhatsApp y Telegram.
> 8. ¿Qué funciones cumplen las inspecciones estáticas y por qué se consideran pruebas de software si no se ejecuta el programa?
> 9. Explique la importancia de los UAT en la finalización de un proyecto de software.
> 
> ## 9. Fechas importantes y avisos académicos
> 
> Basado en la información proporcionada en la sesión, se destacan los siguientes puntos:
> 
> - **Fecha de Examen Parcial:** Estimada para el **24 de abril** (sujeto a confirmación por feriados, aunque se mencionó "en dos semanas" respecto al 10 de abril).
> - **Tipo de Evento:** Primer Examen Parcial.
> - **Descripción Detallada:** Será un examen **eminentemente teórico**. Se evaluará el dominio del "diccionario" de terminología técnica (QA, QC, validación, verificación, tipos de cajas, etc.). No habrá una modalidad fija de año a año, el docente la definirá más cerca de la fecha.
> - **Material de Estudio:** Se deben estudiar las diapositivas de la Unidad 1, el manual de la ISTQB (Nivel Básico), y documentos complementarios como "¿Qué es probar?", "Cómo ser un tester" y "Tendencias en testing".
> - **Aviso Académico:** La segunda parte del cuatrimestre será práctica (diseño de casos de prueba y datos artificiales), por lo que es fundamental tener la base teórica clara ahora.
> - **Horario de Clases:** Se establece el inicio puntual a las **19:00 horas** para optimizar el tiempo y evitar repeticiones por ingresos tardíos.

> [!quote]- Glosario
> # Glosario Académico: Metodología de Pruebas y Ciclo de Vida del Software
> 
> Las pruebas de software han dejado de ser una etapa aislada al final del desarrollo para consolidarse como una actividad transversal y estratégica. Su importancia radica en la capacidad de garantizar la fiabilidad del sistema y reducir los riesgos operativos mediante la detección temprana de anomalías. En el ámbito del mantenimiento y desarrollo, el testing no solo busca fallos, sino que actúa como un mecanismo de control de calidad que protege la inversión del cliente y asegura la continuidad del servicio. Es fundamental destacar que la terminología y los procesos aquí descritos se alinean con los estándares internacionales de la **ISTQB (International Software Testing Qualifications Board)**, proporcionando un marco de trabajo profesional y certificado.
> 
> ## 1. Conceptos Fundamentales de Calidad y Testing
> 
> En esta sección se sientan las bases terminológicas necesarias para comprender el testing como un proceso integral de evaluación que abarca desde la especificación hasta la puesta en marcha, con un enfoque en la optimización de recursos.
> 
> 1. **Software Testing (Pruebas de Software):**
>     - **Definición:** Es un proceso esencial de evaluación de la calidad que se ejecuta durante el desarrollo y mantenimiento de los sistemas de software para reducir riesgos.
>     - **Explicación ampliada:** Su rol trasciende la simple búsqueda de errores; busca evaluar si el producto cumple con los objetivos para los que fue creado. Involucra un conjunto de actividades diseñadas para detectar defectos, verificar requisitos y validar necesidades, siendo crucial tanto en la fase productiva como en el mantenimiento posterior.
>     - **Ejemplo:** Verificar si un sistema de gestión académica permite inscribir alumnos correctamente o cargar historias clínicas en un entorno médico.
> 2. **Calidad de Software:**
>     - **Definición:** Es el grado en que un sistema satisface las necesidades del usuario y cumple con los requisitos especificados.
>     - **Explicación ampliada:** La calidad no se limita a la ausencia de errores en el código (una noción falsa), sino que se vincula con la utilidad del producto y la satisfacción de las expectativas de los interesados (_stakeholders_).
>     - **Ejemplo:** Un software que emite facturas con el IVA correctamente calculado según las especificaciones fiscales solicitadas por el cliente.
> 3. **Fiabilidad (Reliability):**
>     - **Definición:** Es la capacidad de un software para funcionar de acuerdo con lo esperado, generando confianza técnica y operativa en el usuario.
>     - **Explicación ampliada:** La fiabilidad es un activo crítico; es el nivel de confianza que el usuario deposita en la herramienta. Un sistema poco fiable no solo falla técnicamente, sino que destruye la reputación de la consultora y genera malestar en el cliente.
>     - **Ejemplo:** La seguridad de que, al realizar un depósito en un sistema bancario, los datos no se pierdan y el saldo se actualice correctamente en tiempo real.
> 4. **Costo de Errores (Curva de Costos):**
>     - **Definición:** Relación económica que demuestra cómo el costo de corregir un problema aumenta drásticamente a medida que avanza el ciclo de vida del software.
>     - **Explicación ampliada:** Detectar un error en la fase de diseño permite una refactorización estratégica y económica (solo se modifican documentos). Si el error llega a producción, el impacto es máximo: requiere dar de baja el sistema, genera pérdida de clientes y daña la visibilidad de la empresa.
>     - **Ejemplo:** Es significativamente más económico corregir una ambigüedad en el documento de requerimientos que arreglar un fallo en un sistema ya implementado que está haciendo perder transacciones comerciales.
> 
> La solidez de estos conceptos depende directamente de la colaboración estrecha entre los sujetos que interactúan en el proceso de construcción del software.
> 
> ## 2. Roles y Responsabilidades en el Ecosistema de Desarrollo
> 
> El éxito de la validación y verificación de los requerimientos depende de una interacción fluida entre los actores, donde la comunicación define la calidad final del producto.
> 
> 1. **Cliente:**
>     - **Definición:** Persona o entidad que solicita el desarrollo del software, define los requerimientos y financia el proyecto.
>     - **Explicación ampliada:** Su rol es fundamental en la etapa de especificación y en la validación final. Es quien debe dar el "visto bueno" basado en sus necesidades de negocio.
> 2. **Usuario:**
>     - **Definición:** Actor que interactuará directamente con el software en su entorno operativo cotidiano.
>     - **Explicación ampliada:** Su participación es clave para validar si el sistema realmente resuelve sus problemas operativos y si la interfaz es funcional para su día a día.
> 3. **Tester:**
>     - **Definición:** Profesional encargado de la detección de defectos y la ejecución de actividades de control de calidad.
>     - **Explicación ampliada:** Su función no es solo "romper" el código, sino ejecutar actividades complementarias para garantizar que el software sea robusto y cumpla con la documentación técnica antes de la entrega.
> 4. **Desarrollador:**
>     - **Definición:** Encargado de traducir los requerimientos y el diseño técnico en código ejecutable.
>     - **Explicación ampliada:** Interactúa constantemente con el equipo de pruebas para recibir reportes de defectos y realizar las correcciones necesarias, asegurando que el flujo de trabajo sea cíclico y eficiente.
> 
> La colaboración efectiva entre estos roles permite aplicar marcos de gestión que distinguen entre el aseguramiento del proceso y el control del producto final.
> 
> ## 3. Modelos y Procesos de Gestión de Calidad
> 
> Existe una distinción estratégica entre asegurar que el proceso de trabajo sea el adecuado (QA) y controlar que el producto final funcione correctamente (QC).
> 
> 1. **Validación:**
>     - **Definición:** Proceso de comparar los requerimientos documentados con las necesidades reales del usuario ("¿Estamos construyendo el producto correcto?").
>     - **Explicación ampliada:** Se enfoca en asegurar que lo que se planea desarrollar es lo que el cliente realmente necesita para solucionar su problema. Es una tarea previa al desarrollo profundo.
>     - **Ejemplo:** Revisar el cálculo del IVA en el documento de especificación junto al cliente para confirmar que la lógica de negocio es la esperada.
> 2. **Verificación:**
>     - **Definición:** Proceso de comprobar que el software desarrollado coincide con los requerimientos documentados ("¿Estamos construyendo el producto correctamente?").
>     - **Explicación ampliada:** Consiste en chequear que el ejecutable se comporte según lo establecido en las especificaciones técnicas. Se centra en la fidelidad del software respecto al plano original.
>     - **Ejemplo:** Ejecutar el módulo de inscripción de alumnos y constatar que el sistema procesa la matrícula según las reglas de correlatividad escritas en el manual de requerimientos.
> 3. **Quality Assurance (QA - Aseguramiento de la Calidad):**
>     - **Definición:** Enfoque preventivo orientado al proceso de desarrollo para asegurar el cumplimiento de estándares y buenas prácticas.
>     - **Explicación ampliada:** Se basa en la estandarización para que todos trabajen de la misma manera siguiendo normas (como ISO o IRAM). El objetivo es evitar que ocurran errores mediante la prolijidad procesal.
>     - **Ejemplo (Analogía de la Fábrica de Colchones):** Una fábrica asegura calidad no pasando un camión sobre cada colchón (lo cual sería destructivo y costoso), sino documentando y auditando que cada operario siga el mismo proceso de resortes y telas para que el resultado sea siempre óptimo.
> 4. **Quality Control (QC - Control de Calidad):**
>     - **Definición:** Enfoque correctivo orientado al producto final para detectar defectos mediante la inspección.
>     - **Explicación ampliada:** Es la actividad de testing propiamente dicha. Se centra en encontrar fallas una vez que el código ya ha sido producido, actuando como el filtro final de detección.
> 5. **UAT (User Acceptance Testing - Pruebas de Aceptación del Usuario):**
>     - **Definición:** Pruebas finales realizadas por el cliente para dar conformidad al software antes de su paso a producción.
>     - **Explicación ampliada:** Es el punto crítico que habilita la implementación productiva. Un UAT exitoso culmina en la firma de conformidad, lo que permite la facturación del proyecto y el cierre del ciclo de desarrollo.
> 
> Establecida la gestión, es fundamental comprender la naturaleza técnica de los problemas que surgen durante la ejecución de estas tareas.
> 
> ## 4. Taxonomía de Problemas en el Software
> 
> En el ámbito académico, es imperativo distinguir con precisión entre la causa humana, la manifestación en el código y el impacto percibido por el usuario.
> 
> 6. **Error:**
>     - **Definición:** Acción humana que produce un resultado incorrecto en el sistema.
>     - **Explicación ampliada:** Se origina en una equivocación del programador o analista. También puede ocurrir por una interacción errónea del usuario con la lógica del sistema.
>     - **Ejemplo:** Un usuario ingresa la fecha de hoy en el campo de "fecha de nacimiento" por error.
> 7. **Defecto (Bug / "Bags"):**
>     - **Definición:** Imperfección en el código o diseño detectada por el equipo de desarrollo o testing antes de la entrega final.
>     - **Explicación ampliada:** Es el problema real que reside en el sistema mientras está en manos de la consultora. Coloquialmente, en el entorno de clase, se bromea con la pronunciación "**bags**", pero representa la anomalía técnica que debe corregirse antes de que el cliente la vea.
> 8. **Falla (Fallo):**
>     - **Definición:** Mal funcionamiento del software observado por el usuario final en un entorno productivo.
>     - **Explicación ampliada:** Ocurre cuando un defecto no fue detectado y llega al cliente. Es el momento en que el sistema "pincha" o entrega un resultado erróneo en su uso real, lo cual impacta directamente en la fiabilidad.
>     - **Ejemplo:** Un sistema que, debido a un defecto de cálculo no detectado, indica que un alumno recién inscrito tiene 5 meses de edad en su ficha oficial de producción.
> 
> La comprensión de estos fallos se complementa con los principios rectores que limitan y guían la estrategia de mitigación.
> 
> ## 5. Principios y Paradojas del Testing
> 
> Comprender las limitaciones del testing es vital para gestionar las expectativas del cliente y diseñar sistemas bajo la filosofía **APB (A Prueba de Boludos)**, anticipando comportamientos irracionales.
> 
> 9. **Exhaustividad Imposible:**
>     - **Definición:** Principio que establece la imposibilidad de probar todas las combinaciones de datos y caminos del software.
>     - **Explicación ampliada:** Debido a la complejidad infinita de los datos, el objetivo es realizar pruebas inteligentes que cubran el mayor riesgo funcional posible con los recursos disponibles.
> 10. **Presencia vs. Ausencia de Errores:**
>     - **Definición:** Las pruebas demuestran que existen errores, pero no pueden demostrar su inexistencia absoluta.
>     - **Explicación ampliada:** Es una falacia afirmar que un software es "perfecto" tras el testing. Solo significa que las pruebas realizadas no detectaron anomalías, no que el sistema carezca de ellas.
> 11. **Paradoja del Pesticida:**
>     - **Definición:** Fenómeno donde la repetición constante de las mismas pruebas deja de encontrar nuevos errores.
>     - **Explicación ampliada:** Al igual que los insectos desarrollan resistencia, el software "se acostumbra" a los casos de prueba. Es obligatorio evolucionar y diversificar los escenarios para descubrir defectos ocultos.
> 12. **Detección Temprana:**
>     - **Definición:** Principio de iniciar las pruebas lo antes posible para mitigar la curva de costos.
>     - **Explicación ampliada:** Revisar requerimientos y diseños previene la propagación de errores al código, ahorrando tiempo y dinero significativos.
> 13. **Dependencia del Contexto:**
>     - **Definición:** La intensidad de las pruebas depende de la criticidad del sistema y las expectativas del mercado.
>     - **Explicación ampliada:** Se debe evaluar el propósito del sistema. No es lo mismo un software de la NASA o un banco que una app de mensajería.
>     - **Caso de Estudio (WhatsApp vs. Telegram):** WhatsApp salió al mercado con más errores pero ganó por rapidez (time-to-market). Telegram era técnicamente superior y más confiable, pero WhatsApp capturó la clientela porque la expectativa del usuario en ese momento era simplemente comunicarse, tolerando fallos que en un banco serían inaceptables.
> 
> Estos principios se materializan a través de técnicas específicas de inspección y ejecución.
> 
> ## 6. Técnicas y Metodologías de Prueba
> 
> El profesional de calidad utiliza enfoques estáticos y dinámicos para maximizar la cobertura y validar la visión del cliente.
> 
> 14. **Inspecciones (Pruebas Estáticas):**
>     - **Definición:** Revisión de documentos de software (ERS, arquitectura, código) sin ejecutar el sistema.
>     - **Explicación ampliada:** Es una revisión técnica realizada idealmente por un tercero para encontrar errores lógicos o de redacción en etapas tempranas.
>     - **Ejemplo (Analogía de la VTV):** Al igual que la Verificación Técnica Vehicular (BTV), donde se inspecciona el estado del auto sin necesariamente correr una carrera, aquí se revisan los planos del software para asegurar que todo esté en regla antes de "arrancar" el motor del código.
> 15. **Testing Ofensivo vs. Defensivo:**
>     - **Definición:** Mentalidades opuestas de ejecución de pruebas.
>     - **Explicación ampliada:** El testing **ofensivo** busca "atacar" el sistema para encontrar errores mientras está en desarrollo. El **defensivo** busca "demostrar" que el software funciona correctamente, usualmente frente al cliente para asegurar el cobro y la conformidad.
> 16. **Prototipado (Maquetado):**
>     - **Definición:** Creación de versiones visuales simplificadas para validar la visión del cliente antes de codificar.
>     - **Explicación ampliada:** Permite que el usuario vea pantallas y flujos sin funcionalidad real. Ayuda a corregir malentendidos de diseño de manera económica.
>     - **Ejemplo:** El uso de herramientas como **Whimsical** para simular que un botón lleva a otra pantalla, validando el flujo con el usuario sin haber programado la base de datos.
> 17. **Datos Artificiales:**
>     - **Definición:** Escenarios inventados para forzar el comportamiento del sistema bajo condiciones extremas o poco comunes.
>     - **Explicación ampliada:** Se usan para probar los límites lógicos del software que no ocurrirían frecuentemente pero que deben estar controlados.
>     - **Ejemplo:** Intentar inscribir a un alumno en 47 materias simultáneamente para verificar que el sistema lance la alerta de restricción correspondiente.
> 
> Este glosario constituye la base terminológica fundamental para el profesional de calidad, permitiendo una comunicación alineada con estándares globales y una ejecución estratégica en el ciclo de vida del software.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 2 (10 04 26) - Metodología de pruebas de sistemas" src="https://www.youtube.com/embed/MnKZB_m_xRE?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1l9Op_Kd4ATpruv-OJr0CvPYTcWZNM-pn/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1QuqZWKRGCyuKUAaIulRZvQIP6KUmwZ9V/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>