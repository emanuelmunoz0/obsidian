---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/5-modelado-y-diseno-de-software/clase-10-viernes-31-de-octubre-de-2025-31-10-25-modelado-y-diseno-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Modelado y Diseño de Software: Diagramas de Secuencia, Estados y Documentación Técnica
> 
> Este documento constituye un material de estudio integral basado en el análisis de procesos de reserva y sistemas de comercio electrónico. Explora la importancia de la representación visual de sistemas mediante diagramas y la necesidad crítica de una documentación técnica que respalde el desarrollo de software.
> 
> ## 1. Introducción General
> 
> El modelado y diseño de software es una etapa fundamental en el desarrollo de sistemas complejos. Su propósito es permitir que los desarrolladores y las partes interesadas visualicen, especifiquen y documenten la estructura y el comportamiento de un sistema antes de su construcción. A través de diagramas de secuencia y de estados, se pueden prever errores, definir flujos lógicos y establecer prioridades en la ejecución de tareas.
> 
> ### Contexto del tema
> 
> En el entorno académico y profesional, el diseño no se limita a la creación de gráficos; implica la creación de un "Kernel" o núcleo del sistema. Este esquema principal se considera fijo y versátil, y cualquier modificación sobre él conlleva una gran responsabilidad, ya que es el cimiento sobre el cual se construye toda la funcionalidad operativa.
> 
> ### Importancia y relevancia
> 
> - **Claridad Operativa:** Permite entender el inicio y el fin de una secuencia de eventos.
> - **Prevención de Errores:** Identifica fallos potenciales en la comunicación entre sistemas (ej. pagos rechazados o falta de stock).
> - **Seguridad y Registro:** Facilita el seguimiento de acciones (fecha y hora), lo cual es crítico para la seguridad y el control de usuarios.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual
> 
> Para comprender el modelado de software, es necesario dominar ciertos términos fundamentales que estructuran la lógica del diseño.
> 
> ### Definición de conceptos clave
> 
> - **Diagrama de Secuencia:** Representación que detalla cómo los objetos o componentes de un sistema interactúan entre sí en un orden cronológico para completar un proceso.
> - **Diagrama de Estados:** Gráfico que describe el comportamiento de un sistema o de un objeto según los eventos que ocurren, mostrando las transiciones de un estado a otro (ej. de "vuelo reservado" a "pago efectuado").
> - **Líneas de Vida (Lifelines):** Elementos en un diagrama que representan la existencia de un objeto o sistema a lo largo del tiempo durante una interacción.
> - **Kernel (Núcleo):** El esquema principal y fijo de un sistema que no debe ser modificado a la ligera una vez que es funcional.
> - **Documentación Técnica:** Manual o guía descriptiva que explica detalladamente cada acción, estado y atributo de los diagramas para que cualquier consultor externo pueda entender el sistema.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: Modelado de Procesos Específicos
> 
> A continuación, se analizan tres aplicaciones prácticas de modelado de software basadas en casos de estudio reales.
> 
> ### A. Sistema de Reserva de Hotel (Flujo de Secuencia)
> 
> El proceso se divide en pasos numerados para establecer una prioridad clara:
> 
> 1. **Solicitud:** El cliente solicita la reserva.
> 2. **Validación:** El hotel verifica la disponibilidad de la habitación.
>     - _Flujo Alternativo:_ Si no hay disponibilidad, se ofrece otra opción; el cliente puede aceptar o rechazar.
> 3. **Pago:** Se valida el pago por parte del sistema financiero.
> 4. **Confirmación:** El hotel confirma la reserva y el pago al cliente.
> 
> ### B. Sistema de Reserva de Vuelos (Diagrama de Estados y Soporte)
> 
> Este modelo introduce la interacción entre múltiples líneas de vida: **Sistema, Soporte y Check-in**.
> 
> - **Parámetros de búsqueda:** Se definen argumentos específicos como fecha, origen, destino y horario. Estos datos son obligatorios para que el sistema chequee la disponibilidad.
> - **Gestión de Errores (Canal de Soporte):** Si un pago es rechazado o el usuario no sabe operar el sistema, se deriva a un canal de soporte personalizado. Esto es crucial porque el 90% de efectividad es aceptable, pero siempre existirán imprevistos o errores de usuario.
> - **Salidas del Sistema:** El usuario puede optar por un código QR o una tarjeta de embarque física (vía Check-in).
> 
> ### C. Sistema de E-commerce (Logística e Inventario)
> 
> Este modelo conecta la interfaz de usuario con la logística física.
> 
> - **Flujo:** Usuario -> Interfaz -> Carrito -> Pago -> Inventario -> Logística.
> - **Sincronización:** Una vez que logística envía el pedido, es imperativo disminuir el stock en el sistema. Sin esta actualización, el inventario mostraría datos incorrectos, afectando ventas futuras.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Relaciones entre Conceptos y Documentación
> 
> El diseño de software no es un elemento aislado; existe una dependencia directa entre la visualización y la descripción textual.
> 
> - **Versatilidad y Modificación:** Se recomienda no empezar de cero si ya existe un esquema principal funcional. Las modificaciones deben respetar el "Kernel".
> - **Integración de la Documentación:** Cada diagrama debe estar respaldado por un documento (en formatos como Word o PDF) que incluya:
>     - Descripción de clases y atributos.
>     - Roles de los actores.
>     - Ejemplos prácticos y versiones (v1.0, etc.).
> - **Jerarquía de Secuencia:** La prioridad de los eventos se determina visualmente de arriba hacia abajo o mediante numeración explícita.
> 
> |   |   |
> |---|---|
> |Elemento|Función en el Diseño|
> |**Actor (Tipito)**|Representa al usuario que inicia la acción.|
> |**Interfaz**|Punto de contacto entre el usuario y la lógica del sistema.|
> |**Base de Datos/Sistema**|Donde se procesan y validan los datos.|
> |**Notificaciones**|Cierran el ciclo informando al usuario sobre el éxito del proceso.|
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Ejemplos Prácticos y Casos Reales
> 
> ### Caso: Seguridad en Entornos Hostiles
> 
> El diseño de sistemas también debe considerar el contexto geográfico. Por ejemplo, en ciudades con altos índices de criminalidad (como se mencionó en los casos de Río de Janeiro o San Pablo), los sistemas de seguimiento y transporte de hoteles funcionan como una extensión de la seguridad del cliente. Registrar el ingreso y salida de un cliente (con fecha y hora) no es solo una cuestión administrativa, sino un protocolo de seguridad y tranquilidad para el destinatario.
> 
> ### Paso a paso de una validación de pago:
> 
> 1. La interfaz solicita el pago al sistema de pagos.
> 2. El sistema de pagos procesa la transacción con la entidad bancaria.
> 3. El sistema devuelve una confirmación o rechazo a la interfaz.
> 4. La interfaz comunica el resultado al sistema de reservas para finalizar o cancelar el proceso.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores Comunes y Confusiones
> 
> 1. **Omitir al Actor:** Un error frecuente es no incluir la figura del usuario (el "tipito") a la izquierda del diagrama, quien es el que dispara la secuencia.
> 2. **No actualizar el Stock:** En sistemas de comercio, olvidar la conexión entre la entrega logística y la actualización del inventario.
> 3. **Documentación Insuficiente:** Creer que el diagrama se explica por sí solo. La documentación es vital para que otros desarrolladores o auditores entiendan el "porqué" de cada decisión.
> 4. **Modificar el Kernel sin Previsión:** Tocar el núcleo del sistema de manera impulsiva en lugar de realizar modificaciones controladas que mantengan la estabilidad de lo que ya funciona.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Síntesis y Conclusiones
> 
> El modelado y diseño de software es un proceso disciplinado que requiere tanto precisión visual como rigor documental. Los diagramas de secuencia y estados permiten estructurar la lógica del negocio (reservas, pagos, logística), mientras que la documentación técnica garantiza la escalabilidad y el entendimiento a largo plazo del sistema. Un diseño exitoso siempre contempla la seguridad de los datos (fechas y horas de registro) y la gestión de excepciones (canales de soporte para errores de usuario).
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> A partir de las indicaciones proporcionadas en la sesión, se establecen los siguientes compromisos académicos:
> 
> - **Fecha de Examen Final / Entrega Presencial:** **Jueves 20 de junio** (o viernes 21, según la comisión correspondiente).
> - **Requisito de Entrega:** Se deben presentar todos los trabajos prácticos realizados durante el curso en **formato papel (impreso)**.
> - **Contenido de la Entrega:**
>     - Todos los diagramas diseñados (Secuencia, Estados, Clases, etc.).
>     - Una única documentación consolidada por grupo que explique todos los diagramas presentados.
> - **Procedimiento de Firma:** El profesor firmará los trabajos el día 20/21. Es suficiente con que un representante del grupo asista para la entrega y firma de los trabajos de todos los integrantes.
> - **Aviso sobre Documentación:** El grupo 2 tiene pendiente la entrega de la documentación de sus últimos diagramas para completar su validación en el registro del profesor.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Qué representa el "tipito" en un diagrama de secuencia?
> 2. ¿Por qué es importante registrar la fecha y hora en un sistema de reservas?
> 3. ¿Qué es el "Kernel" en el contexto del diseño de software?
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia entre un diagrama de secuencia y un diagrama de estados.
> 5. ¿Qué sucede en un sistema de reserva de vuelos si el pago es rechazado? Describa el flujo hacia el soporte.
> 6. ¿Cuál es la importancia de la numeración en las acciones de un diagrama de secuencia?
> 
> ### Nivel Avanzado
> 
> 7. Analice la importancia de la sincronización entre el sistema de logística y el de inventario en un e-commerce. ¿Qué problemas surgen si no están conectados?
> 8. ¿Por qué se considera que la documentación técnica debe ser "legible y entendible" por sí misma, sin necesidad de consultar al diseñador original?
> 9. En un entorno de producción real, ¿cuántas documentaciones deberían presentarse por cada diagrama y por qué se diferencia del entorno académico?

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 10 - Modelado y diseño de software" src="https://www.youtube.com/embed/XjscqFEi_mg?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/19i3aUSz4CPFNcGdfOvqu4ZI1ddXpYONW/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1RxDgdT8UiNvR3Nu0Ssm0ExVvs8cGj2oG/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>