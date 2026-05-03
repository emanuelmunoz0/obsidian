---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/5-metodologia-de-pruebas-de-sistemas/clase-3-viernes-17-de-abril-de-2026-17-04-26-metodologia-de-pruebas-de-sistemas/","dg-note-properties":{}}
---


> [!quote]-  Resumen
> # Guía Integral de Metodología de Pruebas de Sistemas
> 
> Este documento constituye un material de estudio exhaustivo sobre la metodología de pruebas de software, sintetizando los fundamentos teóricos, los niveles de ejecución, los tipos de testing y la gestión de la calidad desde una perspectiva académica y técnica.
> 
> ## 1. Introducción General
> 
> La metodología de pruebas de sistemas es una disciplina crítica dentro de la ingeniería de software que busca asegurar que el producto final cumpla con las expectativas del cliente y los estándares de calidad definidos. No se trata únicamente de encontrar errores al finalizar el desarrollo, sino de un proceso continuo que integra revisiones estáticas y ejecuciones dinámicas para mitigar riesgos y reducir costos.
> 
> ### Contexto e Importancia
> 
> - **Detección Temprana:** Cuanto antes se detecta un error, más económica es su reparación. Las pruebas iniciadas antes de que exista código ejecutable (inspecciones) son altamente eficientes.
> - **Perspectiva del Tester:** El analista de pruebas aporta una visión imparcial y profesional, diferenciándose de la mirada del desarrollador, quien suele realizar pruebas de forma menos creativa o limitada por su propia lógica de programación.
> - **Documentación como Base:** El éxito del testing depende directamente de la calidad de la documentación funcional (casos de uso, requerimientos). Si la base es errónea, el testing validará un comportamiento incorrecto.
> 
> ## 2. Marco Conceptual y Definiciones Clave
> 
> Para comprender la metodología de pruebas, es fundamental establecer un lenguaje técnico común basado en estándares internacionales como el **ISTQB (International Software Testing Qualifications Board)**.
> 
> ### Términos Fundamentales
> 
> - **Pruebas Estáticas (Inspecciones):** Revisiones de documentación o código realizadas por terceros. Su objetivo es prevenir errores mediante la lectura y análisis, sin ejecutar el software. Son consideradas "baratas" y altamente efectivas.
> - **Pruebas Dinámicas:** Aquellas que requieren la ejecución del código para observar el comportamiento del sistema frente a datos específicos.
> - **Caso de Prueba (Test Case):** Documento formal que detalla los pasos, datos de entrada y resultados esperados para validar una funcionalidad específica.
> - **Caso de Uso:** Descripción de la interacción del sistema desde la perspectiva del usuario. De cada caso de uso pueden derivarse múltiples casos de prueba.
> - **Script de Prueba:** Secuencia de instrucciones (manuales o automatizadas) para ejecutar un caso de prueba.
> 
> ## 3. Desarrollo del Tema: El Proceso de Pruebas de Software
> 
> El proceso de pruebas es un conjunto de tareas organizadas (secuenciales o en paralelo) destinadas a validar el software.
> 
> ### Fases del Proceso
> 
> 1. **Diseño de Casos de Prueba:** Generación del documento que indica qué y cómo probar según los requerimientos.
> 2. **Preparación de Datos:** Selección de los valores de entrada. Se busca la "cobertura" máxima con la cantidad mínima de datos para optimizar recursos.
> 3. **Ejecución de Pruebas:** Correr el programa con los datos definidos y observar la respuesta del sistema.
> 4. **Registro de Resultados:** Documentar si el caso pasó o falló.
> 5. **Comparación y Reporte:** Contrastar el comportamiento real contra la documentación formal. Se genera un reporte de avance (ej. "de 500 casos, 50 ejecutados, 4 fallidos").
> 
> ## 4. Niveles de Prueba de Desarrollo
> 
> Las pruebas no ocurren en un solo momento; se estructuran en niveles progresivos de menor a mayor complejidad.
> 
> |Nivel|Responsable|Objetivo|
> |---|---|---|
> |**Pruebas de Unidad**|Desarrollador|Validar pequeñas partes de código (objetos, clases, funciones) mientras se programa.|
> |**Pruebas de Componente / Módulo**|Desarrollador o Tester|Probar funcionalidades más complejas resultantes de la unión de varias unidades.|
> |**Pruebas de Sistema**|Tester|Validar el sistema completo de forma imparcial y profesional, verificando la integración de todos los módulos.|
> 
> ## 5. Tipos y Formatos de Pruebas de Usuario
> 
> Existen diversas situaciones en las que el usuario final o el cliente interviene en el proceso de testeo.
> 
> - **Pruebas Alfa:** Realizadas por el usuario en las oficinas del desarrollador. El usuario aporta lógica de negocio y datos reales para ayudar al programador a simular circuitos lógicos antes de terminar el software.
> - **Pruebas Beta:** Lanzamiento de una versión casi terminada a un nicho pequeño de usuarios reales en su entorno cotidiano. Los errores se capturan de forma espontánea y silenciosa.
> - **Pruebas de Aceptación (UAT - User Acceptance Testing):** Etapa final y formal donde el cliente valida que el software cumple con lo solicitado. Su aprobación suele estar vinculada a la firma de conformidad y al cobro de cuotas pendientes.
> 
> ## 6. Pruebas Manuales vs. Automatizadas
> 
> La elección entre una y otra depende de la eficiencia y el tipo de prueba.
> 
> ### Pruebas Manuales
> 
> - Ejecutadas por personas que siguen los pasos del caso de prueba.
> - Ideales para funcionalidades nuevas o complejas que requieren inteligencia y "juego" cerebral.
> - **Ventaja:** Capacidad crítica del tester humano.
> 
> ### Pruebas Automatizadas
> 
> - Utilizan herramientas (ej. Selenium) para simular las acciones del usuario mediante scripts.
> - Ideales para **Pruebas de Regresión**: volver a probar funcionalidades existentes cada vez que se agrega algo nuevo para asegurar que nada se "rompió".
> - **Ventaja:** Velocidad y repetitividad en procesos que no cambian.
> - **Desventaja:** Tiempo de programación inicial elevado.
> 
> ## 7. Atributos de Calidad (Requerimientos No Funcionales)
> 
> Las pruebas deben cubrir no solo "qué" hace el sistema (funcional), sino "cómo" lo hace (no funcional). Estos atributos deben ser **medibles**.
> 
> - **Rendimiento:** Velocidad de respuesta y transacciones por segundo.
> - **Disponibilidad:** Tiempo que el sistema permanece operativo sin caídas.
> - **Seguridad:** Protección de datos y accesos.
> - **Escalabilidad:** Facilidad del sistema para crecer en capacidad.
> - **Mantenibilidad:** Facilidad para corregir o actualizar el código (comentarios, modularización).
> - **Usabilidad (Amigabilidad):** Facilidad de uso, medida por ejemplo en horas de capacitación necesarias o cantidad de clics para completar una tarea.
> 
> ## 8. El Proceso de Aceptación y Clasificación de Errores
> 
> En las pruebas de aceptación (UAT), los errores encontrados se clasifican para negociar la implementación:
> 
> 1. **Bloqueantes:** Impiden continuar con las pruebas (ej. falla el login).
> 2. **Críticos:** Fallas graves en funciones principales.
> 3. **Medios/Menores:** Fallas que no impiden el uso pero deben corregirse.
> 4. **Cosméticos:** Errores estéticos o de etiquetas (ej. una palabra mal escrita).
> 
> **Criterios de Aceptación:** Se definen de antemano (ej. "se acepta el sistema con 0 errores críticos y hasta 5 cosméticos").
> 
> ## 9. Errores Comunes y Confusiones
> 
> - **Asumir conocimientos:** El tester no debe probar basándose en lo que "cree" que debería hacer el sistema, sino estrictamente según la documentación.
> - **Automatizar todo:** Es un error derrochar recursos automatizando pruebas que se ejecutarán una sola vez. La automatización es para lo repetitivo (regresión).
> - **Clasificación subjetiva:** Un usuario puede ver un error cosmético como "terrible". Es labor del equipo técnico negociar y explicar la dificultad real de corrección.
> 
> ## 10. Síntesis y Conclusiones
> 
> El testing es un proceso disciplinado que comienza con la inspección de documentos y termina con la aceptación del usuario. Una estrategia exitosa combina niveles (unidad, componente, sistema), tipos de ejecución (manual y automática) y una validación rigurosa tanto de los requerimientos funcionales como de los atributos de calidad (no funcionales).
> 
> ## 11. Preguntas de Repaso
> 
> ### Básicas
> 
> 1. ¿Cuál es la principal diferencia entre una prueba estática y una dinámica?
> 2. ¿Quién es el responsable de realizar las pruebas de unidad?
> 3. Defina "Caso de Prueba".
> 
> ### Intermedias
> 
> 4. Explique la diferencia entre Pruebas Alfa y Pruebas Beta.
> 5. ¿Qué es una prueba de regresión y por qué se asocia con la automatización?
> 6. ¿Por qué los requerimientos no funcionales deben ser medibles? Dé un ejemplo.
> 
> ### Avanzadas
> 
> 7. Describa el flujo completo del proceso de aceptación (UAT) desde la definición de criterios hasta la firma.
> 8. En un escenario donde se agrega una nueva funcionalidad de "Calendario" a un sistema existente, ¿qué se debería probar primero: la funcionalidad nueva o realizar una regresión? Justifique.
> 
> ## 12. Fechas importantes y avisos académicos
> 
> En base al análisis de la sesión, se han establecido las siguientes pautas para la evaluación:
> 
> - **Evento:** Primer Examen Parcial.
> - **Fecha:** Viernes 24 de mayo.
> - **Horario:** 19:00 hs.
> - **Modalidad:** Presencial y Escrito (Teórico).
> - **Lugar:** Instituto.
> 
> ### Material de estudio para el parcial:
> 
> 1. **Conceptos Iniciales:** Archivo base sobre los fundamentos.
> 2. **ISTQB - Fundamentos del proceso de pruebas:** (Documento de 6 hojas). Incluye: qué es probar, qué se necesita, aseguramiento de la calidad, errores, defectos y fallos, y los siete principios de la prueba.
> 3. **Tipos de Testing:** Incluye inspecciones, pruebas de desarrollo (unidad, componente, sistema).
> 4. **Bibliografía complementaria (Habilitada en el aula):**
>     - **ISTQB (Niveles y tipos de prueba):** Estudiar hasta el punto 2.3.3 (excluyendo desde la página 53 en adelante).
>     - **Libro de Summerville:** Capítulo 8 (Pruebas de software). Enfocarse en secciones 8.1, 8.3 (versión, requerimientos, escenario, rendimiento) y 8.4 (usuarios). No profundizar en la "letra chica" del 8.1.2.
>     - **Libro de Presman:** Capítulo 17 (Calidad). Enfocarse en validación, verificación, estrategia de prueba, pruebas alfa/beta (17.6) y requerimientos no funcionales (seguridad, rendimiento).
> 
> **Recordatorio:** Los textos narrativos "Cómo ser un tester" y "Tendencias en testing" son de lectura introductoria y no son materia de evaluación directa, sino para comprensión del contexto profesional.

> [!quote]- Glosario
> # Glosario Académico: Metodología de Pruebas y Ciclo de Vida del Software
> 
> ## 1. Conceptos Fundamentales de la Calidad
> 
> La calidad del software no es un estado accidental, sino el resultado de una estrategia deliberada que comienza con la unificación del lenguaje técnico. Establecer una base terminológica común permite al equipo prevenir la propagación de errores desde las etapas de concepción, transformando el testing en una actividad preventiva y no solo detectivesca. La detección precoz de fallos, especialmente mediante inspecciones, impacta directamente en la eficiencia del desarrollo: cuanto más temprano se identifica una inconsistencia, menor es el impacto económico, ya que el costo de reparación aumenta exponencialmente a medida que el software avanza en su ciclo de vida.
> 
> 1. **Inspecciones (Pruebas Estáticas)**
>     - **Definición:** Actividad de revisión técnica realizada sobre la documentación del proyecto o el código fuente sin ejecutar el programa.
>     - **Explicación ampliada:** Se denominan "estáticas" porque el objeto de análisis es tratado como un archivo de texto (especificaciones, diagramas o código). Su valor es preventivo: permiten que "otros ojos" detecten ambigüedades o errores lógicos antes de invertir horas en programación. Se consideran una inversión de alto impacto porque son extremadamente económicas (solo requieren horas de personal) y evitan el acarreo de defectos hacia fases donde el código ya es ejecutable.
>     - **Ejemplo:** Un equipo de testing revisa los diagramas de casos de uso para detectar que falta una regla de negocio antes de que el desarrollador comience a codificar.
> 2. **Caso de Uso**
>     - **Definición:** Documento que describe la interacción entre un actor (usuario) y el sistema para alcanzar un objetivo.
>     - **Explicación ampliada:** Es el insumo principal generado por el analista funcional para el diseño de pruebas. Actúa como el "contrato" de comportamiento que el tester utiliza para verificar si el sistema cumple con lo solicitado por el negocio.
> 3. **Happy Path (Camino Feliz)**
>     - **Definición:** Flujo de ejecución ideal de una funcionalidad donde no ocurren errores ni excepciones.
>     - **Explicación ampliada:** Valida que el objetivo principal del negocio se cumpla bajo condiciones normales de éxito. Se debe contrastar siempre con los escenarios negativos o de error para asegurar la robustez del sistema.
>     - **Ejemplo:** En una tienda virtual, el Happy Path es comprar dos zapatillas cuando hay stock disponible. El escenario negativo sería intentar comprar dos zapatillas cuando solo queda una en inventario.
> 
> _Estos conceptos teóricos establecen el marco de referencia indispensable para los actores que intervienen en el proceso técnico._
> 
> ## 2. Roles y Responsabilidades en el Ciclo de Pruebas
> 
> El éxito del testing radica en la imparcialidad. Existe una división estratégica de tareas entre desarrolladores, testers y usuarios para garantizar una visión crítica del sistema. Mientras el programador posee un sesgo constructivo sobre su obra, el tester profesional aporta una mirada externa y objetiva. Esta separación de roles asegura que el software no solo sea técnicamente funcional, sino que responda genuinamente a las necesidades del mundo real.
> 
> 4. **Tester (Analista de Pruebas)**
>     - **Definición:** Profesional responsable de diseñar, planificar y ejecutar las pruebas para validar el comportamiento del sistema.
>     - **Explicación ampliada:** Su función va más allá de encontrar fallos; actúa como un consultor de calidad desde el inicio. Para muchos estudiantes, este rol representa la "puerta de entrada" al mundo del desarrollo profesional, ya que permite comprender profundamente la lógica del negocio y la arquitectura técnica simultáneamente.
> 5. **Desarrollador (Programador)**
>     - **Definición:** Responsable de la construcción técnica del software y de las validaciones iniciales de su propio código.
>     - **Explicación ampliada:** Su intervención en el testing se concentra en las pruebas de unidad. Aunque colabora con el usuario en etapas específicas (como las pruebas Alfa), su enfoque principal es garantizar la integridad de los componentes que construye.
> 6. **Usuario / Cliente**
>     - **Definición:** Personas que interactúan con el sistema o financian su creación, aportando el conocimiento del dominio.
>     - **Explicación ampliada:** El usuario provee la lógica real del negocio (reglas impositivas, tipos de sangre, circuitos contables). El cliente valida si el producto final satisface la inversión realizada, siendo su juicio determinante en las fases finales de aceptación.
> 
> _La colaboración entre estos perfiles se materializa a través de métodos de trabajo que optimizan el tiempo y los recursos del proyecto._
> 
> ## 3. Técnicas, Metodologías y Tipos de Testing
> 
> El testing profesional equilibra la profundidad creativa con la velocidad operativa. La dicotomía entre lo manual y lo automatizado no es una competencia, sino una sinergia: mientras el cerebro humano aporta valor crítico para explorar escenarios nuevos, las herramientas aportan la rapidez necesaria para la repetición. La estrategia de calidad ideal es siempre una combinación de ambos enfoques.
> 
> 7. **Pruebas Manuales**
>     - **Definición:** Ejecución de casos de prueba por un tester humano que interactúa directamente con el sistema.
>     - **Explicación ampliada:** Su valor reside en el "costo cerebral": el tester tiene la capacidad de "jugar" con el sistema y aplicar su creatividad para descubrir fallos que no están en un guion rígido. Son ideales para funcionalidades nuevas o flujos complejos que requieren subjetividad humana.
> 8. **Pruebas Automatizadas**
>     - **Definición:** Uso de scripts y herramientas para ejecutar pasos de prueba de forma programada.
>     - **Explicación ampliada:** Son esenciales en contextos de alta repetición. Aunque tienen un costo inicial de programación, su capacidad para ejecutar cientos de acciones en segundos las hace indispensables para mantener la agilidad en proyectos que crecen constantemente.
> 9. **Pruebas de Regresión**
>     - **Definición:** Re-ejecución de pruebas sobre funcionalidades que ya funcionaban para asegurar que los nuevos cambios no introdujeron errores.
>     - **Explicación ampliada:** Su etimología se refiere a la capacidad de "regresar" a un punto estable del sistema si una nueva versión lo "pincha". Se realizan ante cada crecimiento o corrección para garantizar que el "corazón" del software no se haya roto por efectos colaterales.
> 10. **Pruebas Alfa**
>     - **Definición:** Pruebas realizadas por usuarios en las oficinas del desarrollador durante la construcción del software.
>     - **Explicación ampliada:** El objetivo es que el usuario se siente junto al programador y aporte datos y circuitos reales (ej. combinaciones impositivas o reglas de negocio complejas) antes de que el software esté terminado.
> 11. **Pruebas Beta**
>     - **Definición:** Lanzamiento de una versión casi final a un nicho de mercado o grupo selecto de usuarios en entornos reales.
>     - **Explicación ampliada:** Funcionan como una "captura silenciosa" de errores. El software está codificado para reportar fallos automáticamente mientras los usuarios lo usan espontáneamente en sus propios dispositivos.
> 12. **Pruebas de Aceptación (UAT)**
>     - **Definición:** Fase final de validación donde el cliente confirma que el sistema cumple con los criterios acordados.
>     - **Explicación ampliada:** Es el cierre formal del desarrollo y tiene un impacto directo en la facturación. Aquí se negocia la gravedad de los errores encontrados, clasificándolos en niveles: **Bloqueantes** (impiden continuar), **Críticos**, **Medios**, **Menores** y **Cosméticos** (ej. una etiqueta mal escrita como "alummno"). La aceptación puede darse incluso con errores cosméticos pendientes de corrección.
> 
> _Estas metodologías se organizan cronológicamente para asegurar una progresión lógica en el flujo técnico._
> 
> ## 4. Niveles y Proceso de Ejecución
> 
> El testing sigue una lógica ascendente de "abajo hacia arriba". Es fundamental verificar que las piezas individuales funcionen correctamente antes de validar el sistema completo. En este sentido, distinguimos entre **Verificación** (¿Estamos construyendo el producto correctamente?) en los niveles bajos, y **Validación** (¿Estamos construyendo el producto correcto para el usuario?) en los niveles altos.
> 
> 13. **Pruebas de Unidad:** El nivel más pequeño, ejecutado por el programador sobre funciones u objetos individuales durante la codificación.
> 14. **Pruebas de Componente (o Modulares):** Evalúan el ensamble de varias unidades. Aquí ya interviene el tester para aportar imparcialidad sobre la integración de módulos.
> 15. **Pruebas de Sistema:** Prueba integral del software completo realizada por el tester en un ambiente controlado, validando el producto de forma profesional.
> 16. **Diseño de Casos de Prueba:** Creación del documento formal con pasos, condiciones y resultados esperados. Requiere alta experiencia y capacidad analítica.
> 17. **Preparación de Datos de Prueba:** Selección prolija de datos para maximizar la cobertura del sistema con el menor número de pruebas posible.
> 18. **Ejecución y Reporte de Pruebas:** Es la acción de correr el sistema siguiendo el diseño previo. Como pedagogía técnica, solemos decir que "mientras el diseño lo hace un experto, la ejecución podría hacerla mi mamá" si el documento es claro. Por ello, la ejecución es el rol de inicio ideal para perfiles junior. El reporte final clasifica los errores detectados para facilitar la toma de decisiones.
> 
> _Más allá de la funcionalidad, el sistema debe responder a estándares de comportamiento profesional analizados en la sección final._
> 
> ## 5. Atributos de Calidad y Requerimientos No Funcionales
> 
> Para que un software sea profesional, no solo importa "qué hace" (funcional), sino "cómo se comporta" (no funcional). Estos atributos actúan como restricciones técnicas que definen si un sistema es operativo o realmente excelente. A diferencia de las pruebas funcionales, estas suelen validarse hacia el final del proceso, cuando el sistema ya está integrado como un todo.
> 
> 19. **Rendimiento (Performance):** Eficiencia en el uso de recursos y tiempos de respuesta ante transacciones.
> 20. **Disponibilidad:** Capacidad del sistema de estar accesible para el usuario cuando se lo necesita (crítico en banca, secundario en juegos).
> 21. **Escalabilidad:** Capacidad de manejar el aumento de demanda (usuarios/datos) sin degradar la calidad.
> 22. **Mantenibilidad:** Cualidad de un código prolijo, modular y bien comentado que facilita correcciones futuras sin "romper" otras partes.
> 23. **Usabilidad (Amigabilidad):** Facilidad de aprendizaje y uso. Se mide con métricas objetivas como **horas de capacitación requeridas** y **cantidad de clics** para completar una tarea.
> 24. **Pruebas de Estrés:** Ejecución del sistema bajo condiciones límite (volumen masivo de datos) para observar su comportamiento antes del fallo.
> 
> _La implementación exitosa de estos atributos requiere negociar criterios de aceptación medibles y claros con el cliente antes de la entrega final._

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 3 (17 04 26) - Metodología de pruebas de sistemas" src="https://www.youtube.com/embed/d9RzhMx-HY8?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1WfMkmYL0a9RcMVcRuDTFoMW1s9LUOZTz/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1_L5PzDQicutYYnQfeR5olJfzolHEj-aM/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>