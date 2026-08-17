---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/5-modelado-y-diseno-de-software/clase-11-viernes-07-de-noviembre-de-2025-07-11-25-modelado-y-diseno-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía Completa de Estudio: Diagramas de Paquetes en el Modelado de Software
> 
> Este documento constituye un material de estudio integral sobre el modelado y diseño de software, centrándose específicamente en la estructura, funcionalidad y aplicación de los **diagramas de paquetes**. A través de este análisis, se busca proporcionar una comprensión profunda de cómo organizar sistemas complejos mediante una jerarquización lógica y visual.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> El diagrama de paquetes es una herramienta fundamental dentro de los diagramas estructurales de UML. Su función principal es mostrar la organización y disposición de los elementos de un sistema, permitiendo una visualización macro que facilita la comprensión de estructuras complejas. Se considera una continuación lógica de otros diagramas estructurales, donde cada uno está relacionado y depende del anterior para conformar la arquitectura total del software.
> 
> ## 2. Contexto del Tema
> 
> En el desarrollo de software, los diagramas de clases pueden volverse excesivamente extensos y difíciles de manejar a medida que el proyecto crece. El diagrama de paquetes surge como una solución para agrupar estas clases y otros elementos en unidades lógicas. Mientras que el diagrama de clases es minucioso y "fino", el de paquetes es "macro" y abarcativo, permitiendo resumir múltiples actividades y funciones en gráficos ordenados.
> 
> ### Importancia y Relevancia
> 
> - **Simplificación:** Permite reducir la complejidad visual de sistemas con numerosas clases.
> - **Organización Jerárquica:** Facilita la visualización de la estructura jerárquica dentro de un sistema.
> - **Flexibilidad:** Es aplicable a proyectos, sistemas y diversos escenarios de modelado.
> - **Visibilidad de Capas:** Permite identificar claramente las capas de presentación, lógica, física (hardware) y de datos.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Marco Conceptual
> 
> ### Definición de Conceptos Clave
> 
> - **Paquete:** Se representa gráficamente como un rectángulo con una solapa o "orejita" en la parte superior izquierda, similar a una carpeta de archivo físico. Es un contenedor que agrupa elementos como interfaces, subsistemas, funciones y clases.
> - **Capa:** Representa un nivel de abstracción dentro del sistema. Las capas comunes incluyen:
>     - **Capa de Presentación:** Interfaz de usuario y componentes de _frontend_.
>     - **Capa Lógica:** Donde residen las reglas de negocio y procesos.
>     - **Capa Física/Hardware:** Referente a la infraestructura.
>     - **Capa de Datos:** Modelos de bases de datos y persistencia.
> - **Subsistema:** Una agrupación de elementos que cumple una función específica dentro del sistema general (por ejemplo, un subsistema de comunicación).
> 
> ### Términos Fundamentales de Relación
> 
> |   |   |
> |---|---|
> |Término|Definición Académica según el Contexto|
> |**Dependencia**|Relación donde un paquete requiere de otro para su funcionamiento.|
> |**Generalización**|Relación de herencia entre paquetes.|
> |**Morfismo**|Concepto proveniente del álgebra de conjuntos que describe el tipo de relación entre bloques.|
> |**Polimorfismo**|En informática, se refiere a la capacidad de un método para realizar distintas acciones según el contexto o la clase donde se aplique (polifuncionalidad).|
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Desarrollo del Tema: El Diagrama de Paquetes
> 
> ### Estructura y Composición
> 
> Un paquete funciona como un "archivero". Así como en una oficina las carpetas con solapas organizan documentos por nombre (administrativos, profesores, alumnos), en el software los paquetes organizan el código y las responsabilidades.
> 
> Dentro de un paquete se pueden incluir:
> 
> 1. **Múltiples Clases:** Lo ideal es que un paquete englobe más de una clase para justificar su función de agrupamiento.
> 2. **Subpaquetes:** Estructuras anidadas (paquetes dentro de paquetes) para mayor desglose.
> 3. **Funciones y Condicionales:** Representaciones de toma de decisiones.
> 
> ### Relaciones entre Paquetes
> 
> Las comunicaciones entre paquetes no deben ser "islas". Deben reflejar las conexiones existentes en el diagrama de clases original. Aunque en algunos diagramas simplificados no se incluyan nombres en las flechas de relación, es altamente recomendable **nombrar las relaciones** para aumentar la descriptividad y facilitar la lectura por parte de terceros.
> 
> #### El Concepto de Morfismos en el Diseño
> 
> Para entender cómo se conectan las ideas, es útil distinguir los tipos de relaciones (morfismos):
> 
> - **Endomorfismo:** Una relación unidireccional (desde A hacia B). Ejemplo: "Pienso, luego existo" (la inversa no necesariamente aplica de la misma forma en lógica pura).
> - **Isomorfismo:** Una relación dual o bidireccional (de A hacia B y de B hacia A).
> - **Polimorfismo:** Situaciones múltiples que parten desde un origen. En el desarrollo de software, se asocia a la reutilización de nombres de métodos para diferentes aplicaciones.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Ejemplos Prácticos y Aplicaciones
> 
> ### Casos de Uso Comunes
> 
> 1. **Reserva de Hotel:** Agrupamiento de clases de clientes, habitaciones y fechas en un paquete de "Reservas".
> 2. **Pago con Tarjeta / Compra Online:** Paquetes que gestionan la pasarela de pagos y la validación de transacciones.
> 3. **Sistema de Televisión (Analogía):** Un televisor puede resumirse en dos grandes paquetes: **Video** y **Sonido**. Ambos deben confluir en sincronía hacia el display y el audio. Dentro de estos paquetes "macro" existen sub-elementos como osciladores, filtros y etapas de frecuencia que, vistos individualmente, serían inentendibles sin la estructura de bloques.
> 
> ### Aplicación en Proyectos de Software
> 
> Al diseñar el sistema, se recomienda:
> 
> - Identificar el _Frontend_ como un paquete de subsistema de comunicación.
> - Utilizar protocolos de internet para definir cómo se llevan a cabo las comunicaciones entre paquetes.
> - Incluir el modelo de base de datos dentro de su propio paquete descriptivo.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores Comunes y Confusiones
> 
> - **Paquetes Aislados:** Graficar paquetes sin flechas de comunicación. Si no hay relación, el paquete no cumple función dentro del flujo del sistema.
> - **Confusión entre Nodo y Nudo:**
>     - **Nudo:** Un caso particular de conexión.
>     - **Nodo:** Concepto más general en teoría de circuitos y diagramas de estado. Se considera un nodo cuando llegan más de dos flechas (flujos) a un punto.
> - **Omitir Documentación:** Creer que el diagrama se explica solo. Todo diagrama debe ir acompañado de una descripción detallada o un documento (PDF/DOC) que explique su lógica.
> - **Falta de nombres en relaciones:** No poner texto en las líneas de dependencia obliga al lector a "romperse la cabeza" para interpretar la función del vínculo.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Síntesis y Conclusiones
> 
> El diagrama de paquetes es una herramienta de **abstracción superior** que permite organizar el software en capas y bloques lógicos. Su éxito radica en:
> 
> - Mantener la **concordancia** con el diagrama de clases (el diagrama de clases sigue mandando en el detalle).
> - Utilizar una **nomenclatura descriptiva** en cada "orejita" o solapa.
> - Facilitar la **visualización macro** para ahorrar espacio y tiempo en la interpretación del sistema.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> Basado en las directrices del profesor, se establecen los siguientes hitos para el cierre de la materia:
> 
> |   |   |   |
> |---|---|---|
> |Fecha|Evento / Entrega|Descripción Detallada|
> |**14 de Junio**|Avance de Proyecto|Presentación del último proyecto (Diagrama de Paquetes basado en el de Clases).|
> |**20 de Junio**|**Examen Final / Cierre**|Rendida presencial del examen. Entrega del Trabajo Práctico (TP) **impreso**.|
> |**21 de Junio**|Feriado / Puente|Día no laborable. El profesor habilitará este día solo para correcciones o modificaciones mínimas.|
> |**Semana del 24 de Junio**|Carga de Notas|Fecha límite administrativa para la entrega de notas finales.|
> 
> ### Indicaciones Académicas Cruciales:
> 
> 1. **Formato de Entrega:** El Trabajo Práctico final debe ser **impreso** para ser firmado por el profesor. No se aceptan entregas exclusivamente digitales para el cierre.
> 2. **Organización del TP:** Se entrega **un solo trabajo por grupo**. Debe incluir una carátula con los nombres de todos los integrantes (máximo 5 personas mencionado en el ejemplo).
> 3. **Contenido del TP:** Debe ser una presentación de **todos los diagramas** realizados, incluyendo el de paquetes.
> 4. **Cierre Anticipado:** El profesor busca cerrar todo el día **20 de junio** durante el examen presencial. Se recomienda llevar las correcciones en una notebook o celular ese día para evitar conectarse el día 21 (feriado).
> 5. **Trabajo en Equipo:** Se enfatiza la importancia del diálogo y la cooperación grupal sobre el trabajo individual, promoviendo el aprendizaje compartido.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 6. ¿Cuál es la representación gráfica de un paquete en UML?
> 7. ¿Qué elementos pueden incluirse dentro de un paquete?
> 8. ¿Cuál es la diferencia principal entre un diagrama de clases y uno de paquetes?
> 
> ### Nivel Intermedio
> 
> 9. Explique la importancia de las "capas" en un diagrama de paquetes y mencione tres ejemplos.
> 10. ¿Por qué es recomendable nombrar las relaciones de dependencia entre paquetes si el estándar no lo exige estrictamente?
> 11. Describa la analogía del "archivero" aplicada a la organización de software.
> 
> ### Nivel Avanzado
> 
> 12. Analice la diferencia entre un **isomorfismo** y un **endomorfismo** aplicada a la comunicación entre bloques de sistema.
> 13. ¿En qué situación un punto de conexión en un diagrama de estado pasa de ser un "nudo" a ser considerado un "nodo"?
> 14. Justifique cómo un diagrama de paquetes puede ayudar a reducir la complejidad de un grafo que se ha vuelto "extensivo" en su nivel de clases.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 11 - Modelado y diseño de software" src="https://www.youtube.com/embed/mtZ1DfPxP3c?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1aouYuMtHaVZWNYZEoJJSlPx5QNFd4OiZ/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1jkO9wgMfmcLYJwqrfr_ipnQ75c8WdwcZ/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>