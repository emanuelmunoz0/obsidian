---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/5-modelado-y-diseno-de-software/clase-2-viernes-29-de-agosto-de-2025-29-08-25-modelado-y-diseno-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio: Modelado y Diseño de Software - Diagramas de Clases y Estructura de Datos
> 
> Este documento constituye un material de estudio integral basado en la clase de Modelado y Diseño de Software. Explica desde los fundamentos del diseño orientado a objetos hasta la implementación técnica de diagramas de clases, tipos de datos y relaciones sistémicas.
> 
> ## 1. Introducción General
> 
> El modelado de software es una etapa crítica que permite traducir los requerimientos de un sistema en una estructura visual y lógica comprensible. A través del uso de herramientas de diseño (como Microsoft Visio), se busca representar la arquitectura de un sistema antes de su implementación técnica. El enfoque principal se centra en el **Diagrama de Clases**, que sirve como mapa para entender cómo se agrupa la información y cómo interactúan los diferentes componentes de un software.
> 
> ## 2. Contexto del Tema
> 
> El estudio del modelado se sitúa en la intersección entre el análisis de datos (base de datos) y la programación. Se utiliza software especializado para crear plantillas prediseñadas o diagramas desde cero, permitiendo la manipulación de elementos (agregado, modificación o eliminación) según las necesidades del proyecto. El diseño no es estático; se fomenta la mejora continua y la simplificación de estructuras complejas mediante el uso de conceptos avanzados como el empaquetamiento de clases.
> 
> ## 3. Importancia y Relevancia
> 
> La importancia del modelado radica en:
> 
> - **Claridad Organizativa:** Permite a los desarrolladores y analistas visualizar la jerarquía y las responsabilidades de cada parte del software.
> - **Precisión de Datos:** Define qué tipo de información puede procesar el sistema, evitando errores de cálculo o de almacenamiento.
> - **Comunicación:** Actúa como un lenguaje común entre los miembros de un equipo de trabajo.
> - **Eficiencia:** Detecta redundancias o falta de relaciones antes de escribir código.
> 
> ## 4. Marco Conceptual y Definición de Conceptos Clave
> 
> Para entender el modelado de software, es necesario dominar los siguientes términos fundamentales:
> 
> ### A. Objetos y Clases
> 
> - **Objeto:** Es un referente específico que se analiza por sus atributos (características).
> - **Clase:** Es un agrupamiento de objetos. Se utiliza para facilitar el estudio y la organización del sistema. Cada clase debe tener un nombre único y representativo.
> 
> ### B. Atributos y Operaciones
> 
> - **Atributos:** Son las características o datos que definen a la clase (ej. nombre, teléfono, ID).
> - **Operaciones (o Métodos):** Son las acciones o funciones que la clase puede ejecutar. A menudo se representan en una sección separada del diagrama, a veces diferenciada por colores para mayor claridad estética.
> 
> ### C. Visibilidad
> 
> Define quién puede acceder a la información dentro de una clase:
> 
> - **Público (+):** Acceso libre.
> - **Privado (-):** Acceso restringido a la clase.
> - **Protegido (#):** Acceso limitado a la clase y sus derivadas.
> - **Derivado / Paquete:** Otras formas de organización de visibilidad según el entorno.
> 
> ## 5. Desarrollo del Tema: Tipos de Datos y Relaciones
> 
> ### Clasificación de Tipos de Datos
> 
> El procesamiento de información requiere clasificar los datos para que la computadora sepa cómo manejarlos:
> 
> |   |   |   |
> |---|---|---|
> |Tipo de Dato|Descripción|Ejemplo|
> |**Entero sin signo**|Números positivos sin decimales.|Edad (0 a 150 años).|
> |**Entero con signo**|Números positivos y negativos.|Operaciones matemáticas (ej. -127 a +128).|
> |**Flotante (Float)**|Números con decimales y notación científica.|Divisiones (1/3 = 0.33) o exponentes (e+3).|
> |**Cadena (String)**|Símbolos y caracteres alfanuméricos.|Nombres, DNI, números de transferencia bancaria.|
> |**Booleano**|Datos lógicos binarios.|Verdadero/Falso (Sí/No).|
> 
> **Nota sobre Cadenas (Strings):** Aunque un dato parezca numérico (como el DNI o una cuenta bancaria), si no se realizarán operaciones algebraicas con él (sumar, promediar), debe tratarse como una **cadena**.
> 
> ### Relaciones y Asociaciones en Diagramas
> 
> Las líneas entre bloques indican cómo se comunican las clases:
> 
> 1. **Asociación:** Una línea recta simple que indica una relación general.
> 2. **Injerencia / Herencia:** Línea recta de trazo continuo.
> 3. **Realización:** Línea de trazo discontinuo.
> 4. **Dependencia:** Línea con una flecha abierta; indica que una clase depende de otra superior.
> 5. **Composición:** Una relación donde una clase es parte esencial de otra (forma integrada).
> 6. **Multiplicidad:** Indica cuántos objetos de una clase se relacionan con otra:
>     - `1`: Uno y solo uno.
>     - `0..1`: Cero o uno.
>     - `*` o `0..*`: Cero o muchos.
>     - `1..*`: Uno o muchos.
> 
> ## 6. Relaciones entre Conceptos
> 
> El diseño de software hereda conceptos de las **Bases de Datos**, específicamente en la lógica de las relaciones (uno a uno, uno a muchos, muchos a muchos). Sin embargo, en el modelado de clases, se añade la capa de **comportamiento** (operaciones) y **visibilidad**. Las ideas se conectan de forma que una clase puede comunicarse con otra directamente o de forma indirecta a través de una red de asociaciones, formando una estructura global cerrada.
> 
> ## 7. Ejemplos Prácticos: Sistema de Alquiler de Autos
> 
> Un modelo de referencia para un servicio de alquiler de autos incluiría las siguientes clases y atributos:
> 
> - **Clase Empresa:** Atributos como Nombre, Teléfono, Número de cuenta bancaria.
> - **Clase Cliente:** Atributos como ID de cliente, Datos bancarios, Dirección, Teléfono.
> - **Clase Reservación:** Atributos como Modelo, Marca, Color, Matrícula, Disponibilidad.
> - **Clase Pago:** Métodos para pago prepago o electrónico.
> - **Relación de Acción:** Entre la clase "Pedido" y "Libro", la acción sería "necesita" o "solicita". Es vital colocar texto en las relaciones para describir la operación principal.
> 
> ## 8. Errores Comunes y Confusiones
> 
> - **Exceso de Complejidad:** Intentar crear diagramas de 8 o más clases desde el inicio. Se recomienda empezar con un máximo de 5 clases y luego simplificar usando "paquetes".
> - **Confusión de Tipos de Datos:** Tratar documentos de identidad (DNI) como números en lugar de cadenas. Solo es número si se opera algebraicamente con él.
> - **Trabajo Individual:** El modelado de software es una tarea colaborativa. No se recomienda trabajar solo, ya que el intercambio de ideas entre compañeros ayuda a detectar necesidades de nuevas clases o relaciones.
> - **Falta de Texto:** No describir qué hace la relación entre dos clases. La "acción" debe estar explícita.
> 
> ## 9. Síntesis y Conclusiones
> 
> El modelado y diseño de software es un proceso progresivo que va de lo simple a lo complejo. Se basa en la definición clara de clases (objetos agrupados), sus atributos (datos) y sus operaciones (acciones). La correcta elección del tipo de dato y la definición precisa de las relaciones y su multiplicidad son fundamentales para que el sistema funcione lógicamente. El objetivo no es la perfección inicial, sino la construcción de borradores que evolucionen mediante la revisión y la colaboración grupal.
> 
> ## 10. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia fundamental entre un objeto y una clase?
> 2. ¿Qué herramienta de software se mencionó para realizar estos diagramas?
> 3. ¿Cuáles son los tres tipos de visibilidad más comunes en una clase?
> 
> ### Nivel Intermedio
> 
> 4. ¿Por qué un número de transferencia bancaria de 16 dígitos debe clasificarse como "cadena" y no como "numérico"?
> 5. Explique qué indica una multiplicidad de `1..*` en una relación entre clases.
> 6. ¿En qué se diferencia una relación de "asociación" de una de "dependencia" visualmente?
> 
> ### Nivel Avanzado
> 
> 7. Describa cómo se puede reducir la complejidad de un diagrama que tiene demasiadas clases relacionadas.
> 8. En un sistema de alquiler, ¿por qué la relación entre "Agencia" y "Auto" podría considerarse una composición?
> 9. ¿Cómo influye el tipo de dato "booleano" en la eficiencia del procesamiento de una máquina?
> 
> --------------------------------------------------------------------------------
> 
> ## Fechas Importantes y Avisos Académicos
> 
> A continuación, se detallan las fechas y pautas organizativas extraídas de la sesión:
> 
> ### Calendario de Evaluaciones y Entregas
> 
> - **04/09 o 05/09 (Próxima Clase):** Existe una breve discrepancia en la fecha mencionada; el profesor mencionó el 4 de septiembre, pero tras la aclaración de que el viernes es 5, se establece como la fecha de la próxima sesión.
>     - **Evento:** Presentación de borradores.
>     - **Descripción:** Los grupos deben traer un borrador del primer diagrama de clases para revisión. No se exige perfección, sino un avance funcional.
> - **Fecha Límite Flexible:** Se menciona que, aunque el 4 de septiembre (o 5) es para borradores, se podrían recibir borradores incluso el 11 de septiembre. Los diagramas finales se explicarán el último día de clase.
> 
> ### Indicaciones del Profesor
> 
> - **Temática del Proyecto:** Libertad total para elegir el tema del trabajo práctico. Se debe consensuar dentro del grupo.
> - **Complejidad del Trabajo:** Se recomienda un máximo de **5 clases** para el primer diagrama. Evitar excederse a 8 o más clases en esta etapa inicial.
> - **Metodología de Exposición:** Todos los miembros del grupo deben estar preparados para explicar. Si un alumno explica un ejercicio, el resto debe explicar los demás; no puede una sola persona exponer todo.
> - **Dinámica de Grupo:** Se asignaron números de grupo internos para el control administrativo de la materia "Modelado de Software" (Segundo Cuatrimestre).
> 
> ### Organización de Grupos (Listado Interno)
> 
> |   |   |
> |---|---|
> |Grupo|Integrantes|
> |**G1**|Ignacio Vidal, Lucía Corral, Carla Guisande, Ignacio Hernández, Pablo De Martini.|
> |**G2**|María Pía, Ludmila Sánchez Rufanaj, Tatiana Peralta, Rodrigo Gómez Muñoz.|
> |**G3**|Victoria Gómez Coria, Mariano Loreto, Julián Niegovic, Matías Sosa.|
> |**G4**|Pablo Cau, Nicolás Beco, Tatiana Brepe, Paloma Madrid.|
> 
> _Nota: Se enfatiza la importancia de utilizar los nombres y apellidos tal cual aparecen en el DNI para la carga de notas._

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 2 - Modelado y diseño de software" src="https://www.youtube.com/embed/c-o415Znvxo?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1j1LBUAaoGmmDfT5mqGb8cDDb6S_dpLXR/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1dbSmTouWlC3Rsd-zXTcyngfmxtev_cGl/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>