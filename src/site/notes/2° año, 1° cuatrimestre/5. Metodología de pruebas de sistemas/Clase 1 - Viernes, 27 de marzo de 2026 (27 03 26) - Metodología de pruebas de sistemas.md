---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/5-metodologia-de-pruebas-de-sistemas/clase-1-viernes-27-de-marzo-de-2026-27-03-26-metodologia-de-pruebas-de-sistemas/","dg-note-properties":{}}
---


> [!quote]- Resumen
> # Metodología de Pruebas de Sistemas: Fundamentos, Procesos y Calidad del Software
> 
> Este documento constituye un apunte integral de estudio que sintetiza los conceptos fundamentales de la ingeniería de software, el ciclo de vida de desarrollo y la importancia estratégica del testing y la calidad en la industria tecnológica.
> 
> ## 1. Introducción al Proceso de Desarrollo de Software
> 
> Todo proceso de creación de software, independientemente de su escala, debe atravesar etapas fundamentales para garantizar un producto funcional. El desarrollo no es un camino lineal de un solo sentido, sino un ciclo que puede retroalimentarse constantemente.
> 
> ### Etapas Fundamentales del Ciclo de Vida
> 
> 1. **Especificación:** Fase donde se define el problema a resolver y los requerimientos del cliente.
> 2. **Diseño y Desarrollo:** Creación de la arquitectura (modelado) y escritura del código propiamente dicha.
> 3. **Testing (Pruebas):** Verificación del software para asegurar que cumple con lo especificado.
> 4. **Mantenimiento Evolutivo / Producción:** Etapa donde el sistema está operativo. Cualquier mejora o cambio reinicia el ciclo (especificación -> desarrollo -> prueba).
> 
> ## 2. Marco Conceptual y Definiciones Clave
> 
> Para comprender la metodología de pruebas, es necesario establecer una base terminológica sólida desde la ingeniería de software.
> 
> ### Conceptos Fundamentales
> 
> - **Ingeniería de Software:** Disciplina que utiliza el ingenio, la lógica, herramientas y técnicas profesionales para crear software de calidad.
> - **Ingeniería de Requerimientos:** Rama que se encarga de entender la necesidad del cliente y plasmarla en especificaciones. Su producto principal es el **SRS** (_Software Requirement Specification_ o Especificación de Requerimientos de Software).
> - **UML (Unified Modeling Language):** Lenguaje de modelado unificado. Posee una **sintaxis** (reglas gráficas como flechas y recuadros) y una **semántica** (el significado funcional de esos gráficos).
> - **Sistema vs. Software:** Un _sistema_ es un conjunto de elementos interrelacionados (software, hardware, personas, datos, procedimientos y documentos) para cumplir una función. El _software_ es el componente lógico que hace que el sistema funcione.
> 
> ### Diferencia entre Cliente y Usuario
> 
> |Entidad|Definición|
> |---|---|
> |**Cliente**|Es quien financia el proyecto y toma las decisiones estratégicas sobre qué debe hacer el software.|
> |**Usuario**|Es toda persona que interactúa con el sistema (tiene usuario y contraseña). Incluye administradores, operadores y usuarios finales.|
> 
> ## 3. Desarrollo del Tema: El Rol del Testing y la Calidad
> 
> El testing no debe entenderse únicamente como la ejecución de pruebas al final del camino, sino como una filosofía de **Gestión de Calidad** presente en todo el proceso.
> 
> ### La Curva de Costo del Error
> 
> Un concepto central en la materia es la relación entre el tiempo y el costo de corregir fallos.
> 
> - **Fase de Especificación:** Detectar un error aquí cuesta "un retroceso" en el documento (costo mínimo).
> - **Fase de Producción:** Si el error se detecta cuando el sistema ya lo usa el cliente, el costo es altísimo (puede ser hasta 200 veces mayor), implicando pérdida de reputación, tiempo de caída del sistema y retrabajo complejo.
> 
> ### El Rol del Tester
> 
> Existen dos niveles de responsabilidad en el área de pruebas:
> 
> 1. **Tester Analista:** Utiliza el pensamiento crítico y el análisis para diseñar las pruebas. Su objetivo es optimizar: realizar la **menor cantidad de pruebas** que cubran la **mayor cantidad de software**.
> 2. **Tester Ejecutor:** Sigue los libretos o "scripts" de prueba diseñados por el analista.
> 
> ### Calidad vs. Testing
> 
> La calidad consiste en realizar pruebas en cada etapa donde sea posible, incluso antes de que exista código ejecutable. Esto incluye:
> 
> - Revisiones de la documentación (SRS).
> - Validación de diagramas de diseño.
> - Pruebas unitarias realizadas por desarrolladores.
> 
> ## 4. Metodologías de Desarrollo
> 
> La forma en que se organiza el trabajo impacta directamente en cómo se realizan las pruebas.
> 
> ### Modelo Tradicional (Cascada)
> 
> Es un enfoque lineal donde no se avanza a la siguiente etapa hasta terminar la anterior.
> 
> - **Ventajas:** Mayor seguridad en sistemas críticos (cohetes, medicina) donde los requerimientos deben ser definitivos.
> - **Desventajas:** Lento, costoso y genera "personal ocioso" (los testers esperan meses a que los desarrolladores terminen). El cliente solo ve el producto al final.
> 
> ### Metodologías Ágiles (Scrum)
> 
> Divide el trabajo en ciclos cortos llamados **Sprints** (ej. 2 semanas).
> 
> - **Dinámica:** Se especifican, desarrollan y testean pequeñas funcionalidades llamadas **Incrementos**.
> - **Roles en Scrum:**
>     - _Product Owner (PO):_ Representa la voz del cliente.
>     - _Scrum Master:_ Facilita el proceso del equipo.
>     - _Equipo de Desarrollo:_ Roles mixtos (desarrolladores, testers, analistas).
> - **Documentación:** Es más informal, basada en **Historias de Usuario**.
> 
> ## 5. Evolución de los Requerimientos y Casos de Uso
> 
> Un requerimiento atraviesa niveles de profundidad antes de ser programado o testeado.
> 
> 1. **Requerimientos de Usuario:** Expresiones macro de lo que el cliente necesita (ej. "Quiero saber quién llega tarde").
> 2. **Requerimientos de Sistema:** Especifican qué necesita el sistema para cumplir lo anterior (hardware, personal, datos).
> 3. **Requerimientos de Software:** Se dividen en:
>     - **Funcionales:** Comportamiento del sistema (qué hace).
>     - **No Funcionales:** Atributos de calidad (eficiencia, usabilidad, seguridad).
> 
> ### Casos de Uso
> 
> Es la descomposición de un requerimiento funcional en un nivel de detalle técnico pero comprensible. Se compone de:
> 
> - **Diagrama de Caso de Uso:** Gráfico que muestra actores y sus responsabilidades dentro del sistema.
> - **Caso de Uso Detallado:** Un documento que describe la "conversación" paso a paso entre el actor y el sistema (ej. 1. El actor busca un producto; 2. El sistema muestra resultados). Incluye **Precondiciones** (qué debe pasar antes) y **Postcondiciones** (resultado final).
> 
> ## 6. Ejemplos Prácticos y Analogías
> 
> - **Analogía del Tester Ejecutor:** Es como darle un libreto de pasos claros a una persona sin conocimientos técnicos para que pueda verificar un software simplemente siguiendo instrucciones.
> - **Caso del Taller Mecánico:** Un cliente pide un sistema para gestionar turnos y repuestos. El analista debe observar cómo trabaja el mecánico (observación directa) para decidir si, por ejemplo, le conviene un escáner de códigos de barras o si la computadora está demasiado lejos de su zona de trabajo.
> 
> ## 7. Errores Comunes y Confusiones
> 
> - **Confundir Testing con Calidad:** El testing es solo una parte; la calidad es el proceso global de mejora constante.
> - **Asumir que el software no tendrá errores:** Es imposible entregar un software con "cero fallos"; el objetivo es reducir el riesgo y entregar la mejor calidad posible.
> - **Falta de neutralidad del tester:** Un desarrollador no es el mejor tester de su propio código porque "pierde la validez del ojo externo". Siempre es preferible que otra persona revise el trabajo para detectar errores de lógica.
> 
> ## 8. Síntesis y Conclusiones
> 
> La metodología de pruebas es una disciplina basada en el pensamiento crítico y la optimización de recursos. El objetivo fundamental no es solo encontrar errores, sino prevenirlos actuando desde las etapas más tempranas (especificación). Comprender la diferencia entre modelos tradicionales y ágiles permite al profesional de IT adaptar su estrategia de pruebas según la criticidad y los tiempos del proyecto.
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuáles son las cuatro etapas fundamentales del proceso de desarrollo de software?
> 2. ¿Qué diferencia hay entre un requerimiento funcional y uno no funcional?
> 3. ¿Cuál es la diferencia entre un cliente y un usuario?
> 
> ### Nivel Intermedio
> 
> 4. ¿Por qué se dice que el costo de corregir un error aumenta a lo largo del tiempo?
> 5. Explique las diferencias principales entre el modelo de Cascada y la metodología Scrum.
> 6. ¿Qué elementos componen un "Sistema" según la definición técnica?
> 
> ### Nivel Avanzado
> 
> 7. Describa la estructura de un Caso de Uso Detallado y por qué es vital para el tester analista.
> 8. ¿En qué casos es preferible utilizar un modelo de desarrollo tradicional sobre uno ágil?
> 9. Analice el rol del "Tester Analista" frente al "Tester Ejecutor".
> 
> ## 10. Fechas Importantes y Avisos Académicos
> 
> A continuación se detallan las pautas establecidas para el cursado de la materia:
> 
> - **Horario de Clases:** 19:00 horas (puntual). Se recomienda conexión previa a las 18:30 para asegurar puntualidad.
> - **Requisitos de Asistencia y Promoción:**
>     - **75% de asistencia** obligatoria.
>     - **Cámaras encendidas** durante toda la clase virtual (requisito excluyente para computar asistencia y promoción).
> - **Evaluación:**
>     - Dos exámenes parciales.
>     - Un Trabajo Práctico (TP).
>     - Nota para promoción: 7 o más en todas las instancias (Parciales y TP). Existe instancia de recuperatorio.
> - **Tareas de Estudio Independiente (Repaso UML):** Es fundamental que el alumno repase por su cuenta los siguientes diagramas de modelado, ya que se darán por sabidos para la segunda etapa de la materia:
>     1. Diagrama de Clases.
>     2. Diagrama de Estado.
>     3. Diagrama de Actividad.
>     4. Diagrama de Caso de Uso.
> - **Uso de IA:** Se permite el uso de Inteligencia Artificial para complementar el estudio, pero el alumno debe ser capaz de defender y explicar oralmente cualquier contenido incluido en sus trabajos; de lo contrario, se considerará reprobado.

> [!quote]- Glosario
> # Glosario Académico: Metodología de Pruebas y Ciclo de Vida del Software
> 
> ## 1. Introducción al Marco de la Ingeniería de Software
> 
> La Ingeniería de Software trasciende el acto artesanal de la programación para consolidarse como una disciplina científica y profesional dedicada a la creación de productos digitales de alta complejidad. Su importancia estratégica radica en abordar el desarrollo no como un evento aislado de escritura de código, sino como un proceso lógico, estructurado y sistémico. El éxito de un proyecto no depende únicamente de las herramientas empleadas, sino de la capacidad analítica, el ingenio y la experiencia del profesional para gestionar la incertidumbre y la complejidad técnica.
> 
> ### Análisis de Conceptos Fundamentales
> 
> - **Ingeniería de Software:** Es la aplicación rigurosa del ingenio humano, la lógica y el conocimiento experto, apoyada en metodologías y herramientas profesionales, para el diseño y construcción de productos de software que resuelven problemas específicos de manera eficiente y escalable.
> - **Sistema:** Se define como un conjunto de elementos interrelacionados y organizados para cumplir una función determinada. Sus componentes esenciales son:
>     - **Software:** El componente lógico, los programas y algoritmos que permiten la operatividad.
>     - **Datos:** La información procesada y almacenada por el sistema.
>     - **Personas:** Los actores (usuarios, administradores, operarios) que interactúan con el sistema.
>     - **Procedimientos:** Las reglas de negocio, manuales y procesos que dictan el uso del sistema.
>     - **Documentos:** Toda la documentación técnica, de usuario e institucional que respalda el sistema.
>     - **Hardware:** La infraestructura física donde el software reside y se ejecuta.
> - **Software:** Mientras que el "Sistema" es el ecosistema integral, el software se refiere estrictamente al conjunto de instrucciones lógicas y programas que orquestan el comportamiento del hardware y procesan los datos.
> 
> La comprensión de la naturaleza sistémica del software nos obliga a establecer un ciclo de vida riguroso que permita gestionar el producto desde su concepción hasta su retiro.
> 
> ## 2. El Ciclo de Vida del Desarrollo de Software (SDLC) y sus Etapas
> 
> El Ciclo de Vida del Desarrollo de Software (SDLC) constituye el marco metodológico que divide el proceso de creación en etapas técnicas delimitadas. La adherencia a este ciclo es fundamental para mitigar riesgos, asegurar la estabilidad del producto y garantizar que el resultado final satisfaga los requerimientos originales del cliente bajo un enfoque atomizado y profesional.
> 
> ### Desglose del Ciclo Tradicional
> 
> - **Especificación**
>     - **Definición:** Fase inicial donde se relevan, analizan y documentan las necesidades del cliente.
>     - **Explicación ampliada:** Es el punto de partida crítico donde se aplica la ingeniería de requerimientos para entender el problema real. El resultado es un contrato técnico que evita interpretaciones subjetivas.
> - **Diseño**
>     - **Definición:** Transición de los requerimientos abstractos a un modelo técnico y funcional.
>     - **Explicación ampliada:** Se definen la arquitectura, las bases de datos y las interfaces. Es la creación de los planos técnicos antes de la construcción.
> - **Desarrollo / Implementación**
>     - **Definición:** Etapa de construcción propiamente dicha mediante la codificación.
>     - **Explicación ampliada:** Los desarrolladores traducen los modelos diseñados a código fuente ejecutable, siguiendo la "receta" establecida en la documentación técnica.
> - **Testing (Pruebas)**
>     - **Definición:** Fase de verificación y validación mediante la comparación sistemática.
>     - **Explicación ampliada:** Su función es contrastar el software desarrollado contra los documentos de especificación para detectar desvíos entre el resultado esperado y el obtenido.
> - **Mantenimiento Evolutivo**
>     - **Definición:** Fase operativa donde el sistema se encuentra en producción.
>     - **Explicación ampliada:** Lejos de ser una etapa final, se considera el reinicio del ciclo. Cualquier cambio, mejora o corrección dispara nuevamente las etapas de especificación, diseño, desarrollo y pruebas.
> 
> ### Análisis del Costo del Error: El Factor 200x
> 
> Desde una perspectiva financiera y estratégica, la prevención temprana es imperativa. Si un error de lógica se identifica en la etapa de **Especificación**, el costo de corrección es marginal (un simple ajuste documental). Sin embargo, según estudios de la industria, si ese mismo error llega a la etapa de **Producción**, el costo de reparación puede ser aproximadamente **200 veces mayor**. Este incremento exponencial se debe a la necesidad de retirar el sistema, reprogramar, realizar nuevas pruebas de regresión y gestionar el impacto negativo en la confianza del cliente.
> 
> Tras comprender las etapas del proceso, es necesario identificar los roles especializados que ejecutan estas responsabilidades de manera coordinada.
> 
> ## 3. Roles y Responsabilidades en el Ecosistema de Desarrollo
> 
> La optimización de recursos en una empresa de software depende de una distinción clara entre "roles" y "personas". Mientras que una persona puede asumir múltiples roles en proyectos pequeños, las responsabilidades de cada perfil son distintas y requieren competencias específicas para evitar conflictos de interés y fallos de calidad.
> 
> ### Glosario de Roles
> 
> - **Analista Funcional:** Actúa como el puente crítico entre el cliente y el equipo técnico; traduce necesidades de negocio a un lenguaje técnico comprensible para los desarrolladores.
> - **Desarrollador (Programador):** Es el ejecutor técnico encargado de transformar los requerimientos y modelos en código funcional y eficiente.
> - **Tester Analista vs. Tester Ejecutor:**
>     - El **Analista de Testing** ocupa una jerarquía superior, empleando **análisis y pensamiento crítico** para diseñar la estrategia, los escenarios y el "libreto" de pruebas.
>     - El **Tester Ejecutor** es un rol operativo que se limita a seguir paso a paso el libreto diseñado por el analista; su tarea es reproductiva y no requiere el mismo nivel de capacidad analítica.
> - **Project Manager (PM):** Responsable de la gestión integral y la logística (el "garage") del proyecto. Su misión es equilibrar la **Triple Restricción**: Alcance, Tiempo y Costo.
> - **Scrum Master y Product Owner:** Roles de metodologías ágiles. El **Product Owner** prioriza el valor para el negocio, mientras que el **Scrum Master** facilita el proceso y elimina impedimentos del equipo.
> - **Diseñador de Interfaces (UI/UX):** Encargado de la estética y la usabilidad. Aplica principios de psicología y diseño para asegurar que el software sea intuitivo y satisfactorio para el perfil de usuario específico.
> 
> Una vez definidos los actores, estos deben comunicarse mediante lenguajes estandarizados que aseguren la precisión técnica.
> 
> ## 4. Técnicas, Metodologías y Modelado de Sistemas
> 
> El uso de un lenguaje unificado permite que todos los actores de la industria compartan una sintaxis común, eliminando la ambigüedad y evitando fallos de interpretación que comprometan la integridad del producto.
> 
> ### Bloque de Modelado (UML)
> 
> El **UML (Unified Modeling Language)** es el estándar global para la visualización y documentación de sistemas de software.
> 
> - **Diagrama de Casos de Uso:** Modela la relación entre el sistema, los actores externos y las funcionalidades principales.
> - **Diagrama de Clases:** Representa la estructura estática, incluyendo atributos, métodos y relaciones entre objetos.
> - **Diagrama de Estado:** Describe las transiciones y los estados posibles de un elemento del sistema durante su ciclo de vida.
> - **Diagrama de Actividad:** Modela el flujo de trabajo o comportamiento lógico de un proceso de negocio.
> - **Diagrama de Secuencia:** Representa la interacción temporal entre objetos, detallando el orden en que se intercambian mensajes.
> 
> ### Bloque de Metodologías
> 
> - **Modelo de Cascada (Tradicional):** Enfoque lineal donde cada etapa debe concluir antes de iniciar la siguiente. Ofrece alta previsibilidad y seguridad para software crítico (como sistemas aeroespaciales), pero resulta rígido y costoso ante cambios.
> - **Metodologías Ágiles (Scrum):** Basadas en ciclos cortos de desarrollo llamados **Sprints** (típicamente de 2 semanas, frente a los 9 meses de un proyecto tradicional). Se centran en la entrega de **Incrementos** de valor constante y utilizan **Historias de Usuario (User Stories)** —documentación escueta y ágil— en lugar de extensos manuales iniciales.
> 
> La correcta aplicación de estas metodologías deriva en la creación de artefactos técnicos que sirven como base para la calidad.
> 
> ## 5. Artefactos y Documentación Técnica
> 
> La documentación técnica representa la "receta" indispensable que garantiza que el producto satisfaga al cliente, eliminando la dependencia de la interpretación subjetiva del programador y asegurando la transferibilidad del conocimiento.
> 
> - **ERS (Especificación de Requerimientos de Software):** El contrato técnico y legal del proyecto. Contiene requerimientos funcionales, no funcionales y modelos de diseño.
> - **Requerimientos Funcionales vs. No Funcionales:** Los **Funcionales** describen el "qué" hace el sistema (comportamiento). Los **No Funcionales** definen los **atributos de calidad** (eficiencia, seguridad, usabilidad, disponibilidad).
> - **Caso de Uso Detallado:** Narrativa técnica que desglosa la interacción sistema-usuario. Incluye: Actor, Precondiciones, Flujo de Conversación y Postcondiciones (resultado final).
> - **Caso de Prueba (Test Case):** Artefacto que funciona como "libreto" o plantilla para el tester. Detalla pasos, datos de entrada y el resultado esperado para verificar una funcionalidad específica.
> 
> El control de estos artefactos es el primer paso hacia el aseguramiento de la calidad integral del producto.
> 
> ## 6. Conceptos Avanzados de Calidad y Pruebas
> 
> El Aseguramiento de Calidad (QA) no es una etapa final de "detección de errores", sino una disciplina transversal y preventiva que busca la excelencia en todo el proceso de desarrollo, desde la primera entrevista con el cliente hasta el despliegue.
> 
> ### Definiciones Críticas de Calidad
> 
> - **Aseguramiento de Calidad (QA):** Proceso holístico y preventivo aplicado a todas las fases del SDLC, incluyendo auditorías de procesos y revisiones de documentación.
> - **Validación:** Proceso de chequear con el cliente si el producto satisface sus necesidades reales. Se define como **"Construir el producto correcto"**.
> - **Pruebas Estáticas:** Técnica de revisión de código o documentación sin necesidad de ejecutar el software, permitiendo detectar fallos lógicos prematuramente.
> - **Pruebas Unitarias:** Pruebas atómicas realizadas por el propio desarrollador sobre su código para verificar su funcionalidad antes de la integración.
> - **Testing de Caja Negra y Caja Blanca:**
>     - **Caja Negra:** Pruebas funcionales externas donde no se tiene visibilidad del código.
>     - **Caja Blanca:** Pruebas estructurales donde se analiza la lógica interna, el flujo y el código fuente.
> 
> En conclusión, aunque técnicamente es imposible garantizar un software "libre de fallos" debido a la complejidad inherente de los sistemas, el objetivo del profesional es la optimización técnica del proceso de pruebas y la aplicación rigurosa de estándares de calidad para minimizar riesgos y maximizar el valor entregado.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 1 (27 03 26) - Metodología de pruebas de sistemas" src="https://www.youtube.com/embed/zjajFUDjuvE?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1jXqxQhYOQTDpNnFVkhAd5pUDsgnPwlAf/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1Ie9hsQLcaAZAvQRFDUlJIPq-REZ55rpY/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>