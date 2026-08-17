---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/5-modelado-y-diseno-de-software/clase-1-viernes-22-de-agosto-de-2025-22-08-25-modelado-y-diseno-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio: Modelado y Diseño de Software
> 
> Este documento constituye un material de estudio integral para la asignatura de Modelado y Diseño de Software, basado en las directrices académicas y técnicas proporcionadas en el contexto institucional. Su objetivo es proporcionar una comprensión profunda del Lenguaje de Modelado Unificado (UML) y la metodología de trabajo requerida.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> El modelado de software se presenta como un paso fundamental en el ciclo de vida del desarrollo de sistemas. Se define como un "lenguaje de bienvenida" para los profesionales de la informática, ya que permite diseñar organizaciones, eventos y estructuras de manera estandarizada antes de proceder a la codificación.
> 
> ### Importancia y Relevancia
> 
> El uso de modelos permite:
> 
> - **Planificación Estructural:** Crear "planos" de software, similares a los de una construcción arquitectónica.
> - **Comunicación:** Facilitar el diálogo entre diseñadores, usuarios y desarrolladores.
> - **Documentación Evolutiva:** Mantener un registro de las versiones y modificaciones del sistema (ej. Versión 1.0, 1.1, 2.0).
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual: Fundamentos de UML
> 
> El **Lenguaje de Modelado Unificado (UML)** es el estándar de la industria para visualizar, especificar, construir y documentar los artefactos de un sistema de software.
> 
> ### Conceptos Clave
> 
> - **Diagrama:** Representación gráfica de un aspecto del sistema. UML posee entre 13 y 14 tipos de diagramas, aunque la práctica académica se centra en los más influyentes.
> - **Bloques de Construcción:** Los objetos y elementos que se arrastran y conectan para representar la lógica del negocio.
> - **Estereotipos:** Conductas o elementos conocidos de la vida diaria que se utilizan para clasificar elementos en el modelo. Pueden ser comunes o inventados por el diseñador según la problemática.
> - **Valores Etiquetados:** Extensiones de las propiedades de los bloques; permiten añadir información adicional a los elementos del modelo.
> - **Restricciones:** Limitaciones o impedimentos definidos por el diseñador (ej. quién tiene acceso a qué parte del software).
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: Tipos de Diagramas y Aplicación
> 
> UML se divide en diagramas estructurales y de comportamiento. A continuación se detallan los diagramas fundamentales:
> 
> ### Tabla de Diagramas Principales
> 
> |   |   |   |
> |---|---|---|
> |Categoría|Diagrama|Descripción|
> |**Estructural**|**Clase**|El más importante. Define clases, atributos y funciones.|
> |**Estructural**|**Objetos**|Muestra cómo se relacionan los objetos entre sí en un momento dado.|
> |**Estructural**|**Componentes**|Describe la organización de los componentes físicos (CPU, memoria, periféricos).|
> |**Estructural**|**Despliegue**|Representa la configuración de los nodos de procesamiento y redes.|
> |**Comportamiento**|**Caso de Uso**|Identifica a los actores y cómo se vinculan con las funciones del sistema.|
> |**Comportamiento**|**Secuencia**|Muestra la interacción temporal (ej. la secuencia de un cajero automático).|
> |**Comportamiento**|**Estado**|Describe los cambios de estado ante eventos (ej. una máquina de café).|
> |**Comportamiento**|**Actividad**|Detalla procesos internos o algoritmos (ej. un programa de autolimpieza).|
> |**Comportamiento**|**Colaboración**|Clarifica qué integrantes intervienen en un estudio o proceso específico.|
> 
> ### Profundización en Elementos Estructurales
> 
> 1. **Clases:** Representadas por rectángulos. Incluyen:
>     - Nombre de la clase.
>     - Atributos (características).
>     - Funciones (operaciones).
>     - **Visibilidad:** Determina si un atributo es público, privado, protegido o no visible (ej. el "ojo" en las claves de celulares).
> 2. **Paquetes:** Elementos de agrupación que engloban estructuras y clases para organizar el modelo.
> 3. **Notas:** Comentarios esenciales que sirven como "ayuda memoria" para explicar comportamientos o funciones.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Tipos de Datos y Relaciones
> 
> El diseño de diagramas requiere precisión en la definición de la información que se procesa.
> 
> ### Gestión de Datos
> 
> - **Cadenas (Strings):** Se utilizan para todo lo que no requiere operaciones numéricas (nombres, documentos, direcciones, emails). Es el tipo de dato más versátil.
> - **Tipos Numéricos:** Incluyen enteros (positivos o negativos) y números con decimales (flotantes/doble precisión). Es vital definir si llevan signo o no para optimizar la memoria (bytes).
> - **Validación:** Es responsabilidad del diseñador evitar valores imposibles (ej. edades negativas).
> 
> ### Relaciones y Dependencias
> 
> Inspiradas en el modelo de bases de datos, las conexiones entre bloques pueden ser:
> 
> - Uno a uno (1:1).
> - Uno a varios (1:N).
> - Varios a varios (N:N).
> - **Generalización:** Indica una jerarquía entre un origen y un final.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Ejemplos Prácticos
> 
> ### El Caso de la Máquina de Café (Diagrama de Estado)
> 
> Es el ejemplo por excelencia de una máquina de estados:
> 
> 1. **Estado Inicial:** Panel inactivo.
> 2. **Evento:** Ingreso de moneda/tarjeta.
> 3. **Cambio de Estado:** Se ilumina el teclado.
> 4. **Interacción:** El usuario selecciona bebida y azúcar.
> 5. **Actividad:** Proceso de generación y volcado de la bebida.
> 6. **Estado Final:** Retiro del producto y aviso de finalización.
> 
> ### El Caso de la Biblioteca (Conectividad)
> 
> Un sistema de biblioteca debe evitar ser una "isla". Se recomienda:
> 
> - Mostrar libros por categoría.
> - **Comunicaciones:** Incluir logos o funciones de WhatsApp/Email para que el usuario consulte disponibilidad.
> - **Opciones Flexibles:** Definir si el libro es digital (solo lectura) o físico (retiro presencial).
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Metodología de Trabajo y Herramientas
> 
> ### Filosofía del "Borrador Permanente"
> 
> En esta materia, ningún trabajo se considera "terminado" definitivamente. Cada diagrama es un borrador sujeto a revisión continua basado en el debate y la retroalimentación. Se enfatiza que el software es propenso a modificaciones constantes por necesidades del usuario o fallas detectadas.
> 
> ### Herramientas de Software Recomendadas
> 
> - **Microsoft Visio:** Excelente para diagramas de bloques; muy familiar para usuarios de Word.
> - **Wondershare EdrawMax:** Software especializado con cuadrículas y plantillas prediseñadas.
> - **Herramientas Portables/Online:** Se permite el uso de cualquier software que el grupo elija, priorizando la practicidad.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de las fuentes, se establecen los siguientes hitos y normas para el cuatrimestre:
> 
> |   |   |   |
> |---|---|---|
> |Fecha|Evento / Hito|Descripción Detallada|
> |**Inmediato**|Conformación de Grupos|Grupos de 3 a 5 integrantes. Deben informarse al profesor por WhatsApp o en clase.|
> |**Próximo Viernes**|Inicio de Temas Específicos|Comienza la explicación detallada de los diagramas, iniciando con el de **Clase**.|
> |**6 de Septiembre**|**Inicio de Presentaciones**|Fecha establecida para comenzar a presentar los diagramas de UML.|
> |**Semanal**|Rotación de Expositores|**Obligatorio:** Cada semana debe explicar un alumno distinto del grupo para asegurar que todos conozcan el trabajo.|
> |**Fin de Cuatrimestre**|Entrega Final|Revisión de todos los diagramas adeudados (formato virtual o presencial acordado).|
> 
> ### Advertencias Académicas:
> 
> - **Evaluación:** La nota surge de los trabajos prácticos (TPs) presentados clase a clase.
> - **Comunicación:** Es estrictamente obligatorio incluir elementos de comunicación (logos de redes sociales, chats) en los diagramas para evitar que los sistemas queden aislados.
> - **Documentación:** Se recomienda documentar cada cambio estructural con números de versión para mantener el control del proyecto.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Síntesis y Conclusiones
> 
> El modelado con UML no es solo un ejercicio técnico, sino un proceso creativo de diseño. Los puntos clave a recordar son:
> 
> - UML es un estándar global para "planos" de software.
> - La flexibilidad y la conectividad son los pilares de un buen diseño moderno.
> - El trabajo grupal y la rotación son fundamentales para el aprendizaje integral.
> - El modelado es iterativo: siempre se puede (y se debe) mejorar el borrador.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Qué es UML y para qué sirve en el desarrollo de software?
> 2. Mencione tres tipos de diagramas estructurales.
> 3. ¿Qué función cumplen las "Notas" en un diagrama?
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia entre visibilidad pública y privada en una clase.
> 5. ¿Por qué es importante definir correctamente el tipo de dato (ej. cadena vs. entero) en un modelo?
> 6. ¿Qué es un "Estereotipo" y cómo se aplica en un diagrama?
> 
> ### Nivel Avanzado
> 
> 7. Describa el funcionamiento de un Diagrama de Estado utilizando el ejemplo de la máquina de café.
> 8. ¿Cuál es la importancia de la "Generalización" en las relaciones entre objetos?
> 9. Analice por qué el profesor insiste en la inclusión de canales de comunicación externos en los diseños de software actuales.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 1 - Modelado y diseño de software" src="https://www.youtube.com/embed/VwsLEyXx_7g?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1cwXlp3GrMKFw2HVqImXaf5JENb5bSURr/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1-3JmtPs45RmqEXnabn5ik0kwT7rvoVci/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>