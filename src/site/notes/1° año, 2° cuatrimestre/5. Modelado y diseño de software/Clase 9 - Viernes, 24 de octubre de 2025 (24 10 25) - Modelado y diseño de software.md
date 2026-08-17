---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/5-modelado-y-diseno-de-software/clase-9-viernes-24-de-octubre-de-2025-24-10-25-modelado-y-diseno-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio Completa: Diagramas de Secuencia y Modelado de Software
> 
> Este documento constituye un material de estudio integral basado en la clase de Modelado y Diseño de Software. Su propósito es proporcionar una comprensión profunda de los diagramas de secuencia, su integración con otros modelos de software y las mejores prácticas de documentación técnica exigidas en el ámbito académico y profesional.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción general
> 
> El modelado de software no es un proceso estático; es una evolución que parte de estructuras fundamentales (clases) para llegar a la representación de comportamientos dinámicos. Dentro de este proceso, el **diagrama de secuencia** se presenta como una herramienta crítica de interacción que permite visualizar cómo los componentes de un sistema trabajan en conjunto para cumplir una tarea específica.
> 
> ### Contexto e importancia
> 
> El diagrama de secuencia es un tipo de **diagrama de interacción** que describe el "cómo" y el "en qué orden" un grupo de objetos funciona en conjunto. Su relevancia radica en:
> 
> - **Jerarquización del trabajo:** Permite organizar las tareas asignando intervalos de tiempo específicos a cada objeto.
> - **Claridad operativa:** Muestra el flujo de un proceso desde su inicio por un usuario hasta su finalización o retorno al origen.
> - **Personalización del diseño:** No existe un orden preestablecido por terceros; el diseñador es quien administra la lógica de la secuencia según la necesidad del sistema.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco conceptual
> 
> Para comprender los diagramas de secuencia, es necesario definir sus componentes fundamentales y el lenguaje visual que los sustenta.
> 
> ### Conceptos clave
> 
> - **Interacción:** Es el diálogo o intercambio de información entre distintas interfaces u objetos del sistema.
> - **Línea de vida (Lifeline):** Representa la existencia de un objeto a lo largo del tiempo durante la interacción.
> - **Mensajes:** Son las acciones o comunicaciones enviadas entre objetos. Se representan mediante flechas:
>     - **Trazo grueso:** Mensajes de acción o envío.
>     - **Trazo discontinuo:** Mensajes de respuesta.
> - **Objeto:** Representado por un símbolo de rectángulo (a menudo sin relleno o casilla de verificación).
> - **Actor:** Entidad externa (generalmente un usuario) que inicia la secuencia.
> - **Interfaz:** Se representa mediante rectángulos y sirve como punto de diálogo en un lenguaje coloquial con otras interfaces.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del tema: El Diagrama de Secuencia
> 
> El diagrama de secuencia se apoya fuertemente en el **diagrama de clases** previo. Mientras que el de clases define la estructura, el de secuencia define la dinámica temporal.
> 
> ### Lógica y estructura de la secuencia
> 
> La secuencia no debe entenderse como una lista de prioridades rígidas (primero, segundo, tercero), sino como un flujo administrado por el diseñador.
> 
> 1. **Inicio:** Todo comienza con un disparador, usualmente un usuario o actor.
> 2. **Intervalos de tiempo:** A cada objeto se le asigna un tiempo entre una tarea y otra.
> 3. **Escenarios:** Se pueden crear múltiples escenarios (ida y vuelta) para prever funcionalidades presentes y futuras.
> 4. **Bifurcaciones y Decisiones:** Aunque el fuerte del diagrama no es el uso de rombos (típicos de diagramas de flujo), las decisiones están implícitas. Por ejemplo, en un proceso de pago, existen dos líneas de secuencia posibles: "pago aceptado" o "pago rechazado".
> 
> ### Elementos avanzados
> 
> - **Paquetes:** Se pueden agrupar elementos relacionados para organizar diagramas complejos.
> - **Lazos (Loops):** Representan operaciones repetitivas dentro de la secuencia.
> - **Time out:** Se puede especificar un tiempo límite para una respuesta.
> - **Auto-destrucción de mensajes:** Siguiendo la lógica de algunas redes sociales, el diagrama puede contemplar que un mensaje desaparezca tras ser visualizado o leído.
> - **Secuencias seriales y paralelas:** El diseñador tiene la libertad de utilizar técnicas de ejecución en serie o en paralelo según la arquitectura del software.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Relaciones entre conceptos
> 
> El modelado de software es un ecosistema de diagramas interconectados:
> 
> - **Diagrama de Clases** **\rightarrow** **Diagrama de Secuencia:** El diagrama de secuencia jerarquiza el trabajo iniciado en el de clases. No se puede construir una secuencia efectiva sin conocer los objetos y métodos definidos previamente.
> - **Diagrama de Colaboración:** Funciona en conjunto con el de secuencia para mostrar cómo los objetos se comunican, permitiendo mejoras continuas (iteraciones) sobre el diseño original.
> - **Documentación** **\rightarrow** **Diagrama:** El diagrama es la representación visual, pero la documentación es la "espalda" del trabajo; explica el contexto y la funcionalidad que el gráfico por sí solo podría no agotar.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Ejemplos prácticos y casos aplicados
> 
> ### Caso 1: Reserva de Hotel (Sistema de Gestión)
> 
> En un sistema de reservas, la secuencia incluiría:
> 
> 1. El usuario consulta disponibilidad.
> 2. La interfaz de reserva comunica con el objeto "Habitación".
> 3. Se procesa el pago.
> 4. La reserva vuelve a comunicarse con la habitación para confirmar el cupo y retirarla de la disponibilidad.
> 5. Se emite un voucher electrónico como respuesta.
> 
> ### Caso 2: Comunicación de Hardware (Impresoras Matriciales)
> 
> Un ejemplo histórico de secuencia es la comunicación entre una computadora y una impresora a través de un puerto paralelo:
> 
> 6. Envío de datos (8 líneas de datos).
> 7. Señales de control (Buffer lleno, Ok, Reintentar).
> 8. Manejo de errores: Si no hay papel (_Auto paper_), el sistema genera un mensaje en el display o mantiene la cola de impresión en el software hasta que se solucione el factor externo.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores comunes y confusiones
> 
> - **Rigidez en el orden:** Creer que alguien externo debe definir qué va primero o último. La secuencia es una decisión de diseño lógica del autor.
> - **Confusión con Diagramas de Estado:** A diferencia del diagrama de estado, el de secuencia no prioriza quién está primero, sino cómo es el diálogo y la interacción entre interfaces.
> - **Falta de Fin:** No todos los diagramas necesitan un nodo de "fin" explícito; muchos regresan al origen para reiniciar el ciclo.
> - **Omitir lo Transversal:** No considerar factores externos (como problemas de conexión o situaciones del entorno) que pueden condicionar la secuencia normal.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Protocolo de Documentación Técnica
> 
> Documentar no es describir cómo se hizo el dibujo, sino explicar qué hace el sistema. Se debe entregar un documento tipo **Brief** con las siguientes especificaciones:
> 
> |   |   |
> |---|---|
> |Elemento|Requisito de Formato|
> |**Herramienta**|Microsoft Word.|
> |**Encabezado**|Incluir: FTS1, Nombre de la materia (Modelado de Software), Lenguaje.|
> |**Pie de página**|Número de página.|
> |**Carátula**|Integrantes y datos institucionales.|
> |**Contenido**|Descripción del contexto, funcionalidad y escenarios.|
> 
> ### Control de Versiones
> 
> Es fundamental registrar las modificaciones:
> 
> - **Versión 1.0:** Versión inicial aprobada.
> - **Versión 1.1:** Modificaciones puntuales o menores.
> - **Versión 2.0:** Modificaciones estructurales o cambios de fondo.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas importantes y avisos académicos
> 
> A partir del análisis de la sesión, se establecen los siguientes hitos y obligaciones:
> 
> - **Fecha: 31 de octubre**
>     - **Evento:** Entrega de borrador.
>     - **Descripción:** Presentación de un borrador del **Diagrama de Secuencia**. El tema es de libre elección (pueden continuar con el proyecto actual o elegir uno nuevo).
> - **Fecha: Próxima clase (31 de octubre)**
>     - **Evento:** Entrega de documentación técnica.
>     - **Descripción:** Elegir un diagrama realizado previamente y entregar su documentación completa (manual/brief) en Word, siguiendo las normas de formato (encabezado, pie de página y carátula).
> - **Recordatorio General:**
>     - Se enfatiza la importancia de **documentar todo**. "La documentación es la espalda de su trabajo".
>     - Cualquier ausencia por motivos de salud o fuerza mayor debe ser comunicada a través del **grupo de mensajería**, no por privado, para mantener la transparencia académica.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Síntesis y conclusiones
> 
> El diagrama de secuencia es una herramienta esencial para definir la lógica operativa de un sistema. Su construcción requiere apoyarse en el diagrama de clases y permite una personalización total del flujo de mensajes. La calidad de un modelo de software no reside solo en el diagrama, sino en la documentación que lo acompaña, la cual debe ser tratada como un manual de usuario resumido que evolucione mediante un control de versiones riguroso.
> 
> --------------------------------------------------------------------------------
> 
> ## 10. Preguntas de repaso
> 
> ### Nivel Básico
> 
> 1. ¿Qué representa la "línea de vida" en un diagrama de secuencia?
> 2. ¿Cuál es la diferencia visual entre un mensaje de acción y uno de respuesta?
> 3. ¿Quién es el encargado de definir el orden de las tareas en la secuencia?
> 
> ### Nivel Intermedio
> 
> 4. ¿Por qué se dice que el diagrama de secuencia jerarquiza el trabajo del diagrama de clases?
> 5. Explique cómo se representaría una toma de decisiones (condicional) en este diagrama sin usar necesariamente un rombo.
> 6. ¿Qué función cumplen los "lazos" u operaciones repetitivas?
> 
> ### Nivel Avanzado
> 
> 7. Describa la importancia de la documentación técnica y el control de versiones (1.0 vs 2.0) en el desarrollo de software.
> 8. Analice cómo un factor externo transversal (ej. falta de papel en una impresora o inasistencia de usuarios) puede afectar el diseño de una secuencia automatizada.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 9 - Modelado y diseño de software" src="https://www.youtube.com/embed/pk2eK4hlc24?feature=oembed" height="150" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.33333 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/15sLwfKjxH3iEHRe6O8pbZte_2Rms9bgx/preview" height="150" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.33333 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/12u4h78jThyp085ICebGVa8UAj6QSrpz3/preview" height="150" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.33333 / 1; width: 100%; height: 100%;"></iframe>