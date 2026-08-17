---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/5-modelado-y-diseno-de-software/clase-5-viernes-19-de-septiembre-de-2025-19-09-25-modelado-y-diseno-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía Integral de Modelado y Diseño de Software: Diagramas de Colaboración y Objetos
> 
> Esta guía constituye un material de estudio exhaustivo diseñado para abordar los conceptos fundamentales y avanzados del modelado de software, centrándose específicamente en los **Diagramas de Colaboración** y su relación con los **Diagramas de Objetos**. El objetivo es proporcionar al estudiante una comprensión profunda que le permita diseñar sistemas robustos, lógicos y bien documentados.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> En el diseño de software, la representación visual de cómo interactúan los componentes de un sistema es crucial. Este documento explora la transición desde el modelado estático hacia un enfoque que integra las interacciones dinámicas. Se profundiza en la estructura, sintaxis y aplicación de los diagramas de colaboración, entendiéndolos no como entidades aisladas, sino como una extensión y mejora de los diagramas de objetos ya existentes.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual y Definición de Conceptos Clave
> 
> Para comprender el modelado de software desde cero, es necesario definir los pilares que sustentan estas representaciones gráficas:
> 
> ### Conceptos Fundamentales
> 
> - **Objeto:** Es una instancia de una clase que posee estado y comportamiento. En los diagramas, se representan como los entes que interactúan entre sí.
> - **Diagrama de Colaboración:** Es una estructura espacial estática que describe cómo colabora un grupo de objetos para realizar una tarea específica. Su característica distintiva es la **simultaneidad**: muestra al mismo tiempo las interacciones entre objetos y las relaciones estructurales que las permiten.
> - **Mensaje:** Es la comunicación enviada entre objetos. En el modelado, el mensaje indica la acción que el objeto receptor debe ejecutar. Se representa mediante flechas y texto descriptivo.
> - **Enlace (Link):** Es el camino de comunicación entre dos objetos, representado generalmente por una línea que los une.
> - **Secuencia:** El orden cronológico en el que ocurren los mensajes, indicado mediante una numeración (ej. 1, 2, 3).
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: El Diagrama de Colaboración
> 
> El diagrama de colaboración permite visualizar la interacción de los objetos en un formato que destaca la organización del sistema.
> 
> ### Estructura y Funcionamiento
> 
> A diferencia de otros diagramas que se centran exclusivamente en el tiempo, el diagrama de colaboración se organiza en el espacio. Las características principales incluyen:
> 
> 1. **Identificación de Objetos y Clases:** Se definen los objetos participantes y sus clases correspondientes.
> 2. **Definición de Acciones:** Representadas por flechas orientadas hacia el destinatario del mensaje.
> 3. **Priorización y Orden:** Se utiliza una sintaxis numérica para establecer la secuencia de las acciones.
> 
> ### Objetos Activos
> 
> Un concepto avanzado en estos diagramas es el **Objeto Activo**.
> 
> - **Definición:** Es un objeto que controla el flujo de ejecución o que tiene la capacidad de realizar multitareas.
> - **Representación Visual:** Se distinguen por tener **bordes reforzados o líneas más gruesas**.
> - **Función:** Actúan como iniciadores o controladores principales de una secuencia de acciones compleja (ej. un escáner o un procesador de texto en un flujo de impresión).
> 
> ### El Rol del Actor (Ente Concreto)
> 
> Todo sistema requiere un punto de partida. Basándose en principios similares a la termodinámica (donde nada se mueve por sí mismo sin un agente externo), el diagrama debe incluir un **Actor**.
> 
> - **Naturaleza:** Representa a un ser humano o un ente físico concreto.
> - **Importancia:** Es quien desencadena las interacciones. Sin un actor que inicie la acción (como insertar una moneda en una máquina de café), el sistema permanece estático.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Relaciones entre Conceptos y Estructuras
> 
> ### Sinergia entre Diagramas de Objetos y Colaboración
> 
> Existe una dependencia directa entre estos dos modelos:
> 
> - El Diagrama de Colaboración es, esencialmente, una **extensión del Diagrama de Objetos**.
> - **Mejora incremental:** No es necesario crear un diagrama nuevo desde cero. El proceso consiste en tomar la estructura del diagrama de objetos y "embellecerla" o completarla añadiendo la sintaxis de colaboración (mensajes, flechas de acción y actores).
> - **Complementariedad:** Lo que falta en el diagrama de objetos (la dinámica de interacción) lo aporta el de colaboración.
> 
> ### Sintaxis de Mensajes Complejos
> 
> Los mensajes pueden tener estructuras sintácticas avanzadas para representar condiciones de satisfacción. Por ejemplo, un mensaje puede enviarse solo cuando otros procesos previos han terminado (ej. `A.1` y `B.3`). También se pueden representar envíos múltiples o comunicaciones masivas (como en un sistema de _mailing_).
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Ejemplos Prácticos y Aplicaciones Reales
> 
> ### Caso A: El Sistema de Ascensor
> 
> 1. **Actor:** Una persona presiona el botón.
> 2. **Objeto Cabina:** Recibe la orden.
> 3. **Secuencia de Acciones:**
>     - 1: Encender la luz de la cabina.
>     - 2: Cerrar la puerta.
>     - 3: Iniciar movimiento.
> 4. **Interacción:** La cabina solicita a la puerta que se cierre (Mensaje orientado).
> 
> ### Caso B: Operación de Supermercado (Grupo 3)
> 
> - Se modela la compra en una sucursal.
> - **Clase:** Cliente / **Objeto:** Compra.
> - Se integra el ente concreto (Persona) arriba de la estructura para iniciar el circuito.
> 
> ### Caso C: Reserva de Hotel (Grupo 2)
> 
> - **Flujo:** Comienza con el Pago -> Generación de Reserva -> Asignación de Cliente -> Asignación de Habitación.
> - El hotel actúa como ente central que recibe la visita del cliente y contrata al personal.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores Comunes y Aclaraciones Importantes
> 
> |   |   |
> |---|---|
> |Error Común|Aclaración Correcta|
> |**Omitir el Actor**|El diagrama parece incompleto si no hay un ente concreto que inicie la acción. Siempre se recomienda incluir al ser humano.|
> |**No realizar copias de seguridad**|En el diseño de software, al destruir un objeto (Acción de destrucción), es una política fundamental crear previamente una copia de seguridad (_backup_) para permitir la anulación de acciones o recuperación de datos.|
> |**Confundir la simultaneidad con caos**|La simultaneidad en el diagrama de colaboración no significa que todo ocurra al azar; la numeración secuencial es la que mantiene el orden lógico.|
> |**Pensar que son diagramas aislados**|El diagrama de colaboración debe "vivir" dentro de la estructura que ya se definió para el diagrama de objetos.|
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Síntesis y Conclusiones
> 
> - **Integración:** El modelado efectivo requiere combinar la estructura estática (objetos) con la dinámica de interacción (colaboración).
> - **Secuencialidad:** El uso de números para ordenar mensajes es vital para la claridad del flujo.
> - **Actores:** La presencia de un ente concreto (humano) es lo que otorga realismo y punto de partida al modelo.
> - **Mejora Continua:** Los diagramas son documentos vivos; se pueden y deben refinar agregando flechas, textos de acción y bordes reforzados para objetos activos.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de las directrices docentes, se establecen los siguientes puntos clave para la organización de la materia:
> 
> - **Próxima Clase (Viernes siguiente):** Será una **Actividad Asincrónica**. El profesor no estará presente de forma sincrónica debido a su participación en una jornada por el Día del Estudiante en Cañuelas.
> - **Plataforma:** La actividad será subida al Aula Virtual.
> - **Tema de la Actividad:** **Diagramas de Estado**. Se enfocará en la investigación de estados y diagramas de computadoras.
> - **Fecha de Entrega:** **3 de octubre**.
> - **Metodología:** Se recomienda el trabajo en equipo. La tarea consistirá en buscar un diagrama sencillo de una computadora y responder pautas escritas o preguntas.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Qué diferencia principal existe entre un diagrama de objetos y uno de colaboración?
> 2. ¿Cómo se representa visualmente un mensaje en un diagrama de colaboración?
> 3. ¿Por qué es fundamental incluir un "Actor" en el diagrama?
> 
> ### Nivel Intermedio
> 
> 4. Explique la función de la numeración en las secuencias de mensajes.
> 5. ¿Qué representa un objeto con bordes reforzados y qué nombre recibe?
> 6. En un sistema de software, ¿cuál es la importancia de la acción de "copia" antes de eliminar un objeto B?
> 
> ### Nivel Avanzado
> 
> 7. Analice la frase: "El diagrama de colaboración muestra simultáneamente interacciones y relaciones estructurales". ¿Cómo se logra esto gráficamente?
> 8. Describa cómo se aplicaría la sintaxis de mensajes múltiples en un sistema de combinación de correspondencia (_mailing_).

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 5 - Modelado y diseño de software" src="https://www.youtube.com/embed/8RNbO7jO29c?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/179Y_q2Be8A8gE8siZSUlJR3uzNdwZJ_6/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1-XhI-qnTswulWawUXy79-r5gRNG7LNTV/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>