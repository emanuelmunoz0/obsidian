---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/5-modelado-y-diseno-de-software/clase-4-viernes-12-de-septiembre-de-2025-12-09-25-modelado-y-diseno-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio Completa: Diagramas de Objetos y Modelado Estático
> 
> Este documento constituye un apunte universitario integral sobre el **Diagrama de Objetos** en el contexto del diseño de software, basado en el análisis técnico de la sesión académica correspondiente a la materia de Modelado y Diseño de Software.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> El modelado de software requiere diferentes perspectivas para representar un sistema. Mientras que los diagramas de clases ofrecen una visión abstracta y general de las reglas de negocio, los **diagramas de objetos** (también conocidos como diagramas de instancias) proporcionan una visión concreta y específica del sistema en un momento determinado.
> 
> Este documento profundiza en la definición, notación y aplicación de estos diagramas, estableciendo paralelismos críticos con los diagramas de clases para facilitar su comprensión y diseño.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual y Definiciones
> 
> Para entender los diagramas de objetos, es fundamental definir sus componentes básicos desde cero.
> 
> ### Definición de Conceptos Clave
> 
> - **Objeto:** Es una instancia específica de una clase. Representa una entidad real o abstracta con identidad propia.
> - **Enlace (Link):** Es una relación física o conceptual entre objetos. En los diagramas de objetos, el enlace es la instancia de una asociación definida en un diagrama de clases.
> - **Estructura Estática:** A pesar de representar instancias, estos diagramas se consideran estructuras estáticas porque muestran una "fotografía" fija del estado del sistema en un punto del tiempo.
> 
> ### Notación Técnica Obligatoria
> 
> La distinción visual entre un diagrama de clases y uno de objetos es crítica. La notación estándar de UML para objetos incluye:
> 
> 1. **Subrayado:** El nombre del objeto y su clase **deben ir subrayados**. Esta es la marca distintiva fundamental.
> 2. **Sintaxis de Identificación:** Se utiliza el formato `nombreDelObjeto : Clase`.
> 3. **Objetos Anónimos:** Es posible representar objetos sin un nombre específico si la aplicación no lo requiere, utilizando la sintaxis `: Clase`.
> 4. **Caminos Completos:** En aplicaciones complejas, se puede incluir el paquete de origen usando la notación de doble punto (ej. `Botón : Controles`).
> 5. **Atributos:** Se pueden incluir valores específicos de los atributos dentro del bloque del objeto (ej. `color = rojo`). En este caso, los atributos no se subrayan, pero el encabezado del objeto sí.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: El Diagrama de Objetos
> 
> ### Relación entre Clase y Objeto
> 
> El diagrama de clase actúa como un "plano" o plantilla, mientras que el diagrama de objeto es la ejecución de dicho plano.
> 
> |   |   |
> |---|---|
> |Diagrama de Clase|Diagrama de Objeto|
> |Representa la estructura general.|Representa casos específicos (instancias).|
> |Define multiplicidad (ej. 1 a N).|Muestra la cantidad exacta de instancias (ej. 4 ruedas).|
> |Es un concepto abstracto.|Es una representación concreta de datos.|
> 
> ### Transformación de Diagramas
> 
> Es posible pasar de un diagrama de clase a uno de objeto y viceversa. Un ejemplo clásico es el de un **Coche**:
> 
> - **En el diagrama de clases:** Se define una clase `Coche` relacionada con una clase `Motor` (1 a 1) y una clase `Rueda` (1 a 4).
> - **En el diagrama de objetos:** Se graficaría un bloque para el objeto coche específico y, por separado, los cuatro bloques correspondientes a cada una de las ruedas y el bloque del motor, todos unidos por enlaces.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Relaciones Avanzadas entre Conceptos
> 
> ### Instancias Reflexivas
> 
> Ocurren cuando un objeto tiene un enlace consigo mismo. Esto sucede cuando un objeto cumple múltiples roles dentro de un sistema.
> 
> - **Ejemplo:** Una persona que trabaja con un familiar. El objeto `Persona` puede tener una relación reflexiva donde actúa simultáneamente como "Familiar" y como "Patrón/Empleado".
> 
> ### Objetos Compuestos
> 
> Se utilizan para simplificar el diagrama cuando un sistema tiene múltiples partes internas. En lugar de dibujar múltiples bloques dispersos, se utiliza un bloque "compuesto" que contiene las partes en su interior.
> 
> - **Simplificación:** Si una casa tiene siete puertas, en lugar de repetir el bloque de objeto siete veces, se puede agrupar en un paquete o bloque compuesto para mejorar la legibilidad.
> 
> ### Jerarquías y Subclases
> 
> En la notación de objetos, cuando se encuentra una relación de `Clase :: Clase` (dos puntos dobles), se está indicando una relación de herencia o una subclase, donde una entidad depende directamente de la otra en una estructura jerárquica.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Ejemplos Prácticos y Aplicados
> 
> ### Caso 1: Distribución Automotriz
> 
> - **Clase:** Un `Distribuidor` vende `Automóviles` a un `Comprador`.
> - **Objeto:** La compradora "Susana" (instancia de `Comprador`) compra un "Onix" (instancia de `Automóvil`). El diagrama muestra el enlace directo entre el objeto Susana y el objeto Onix, reflejando la acción de venta.
> 
> ### Caso 2: Reserva de Hotel
> 
> En un sistema de reservas, el diagrama de clases define que un `Pago` tiene un `Método` y un `Estado`.
> 
> - **Instancia de objeto:** Se mostraría un pago con el atributo `importe = 5000`, `método = efectivo` y `estado = pagado`, vinculado a una `Reserva` específica y a una `Habitación` con número e ID determinado.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores Comunes y Aclaraciones
> 
> - **Confusión de Notación:** El error más frecuente es no subrayar el nombre del objeto, lo que lo hace indistinguible de una clase.
> - **Multiplicidad Errónea:** En el diagrama de objetos no se usan rangos (como 1..*). Se debe mostrar la cantidad exacta de objetos existentes en ese escenario particular.
> - **Sobrecarga del Gráfico:** Intentar graficar todos los objetos posibles de un sistema. El diagrama de objetos debe buscar la **simplicidad y el camino más corto** para explicar un caso de uso.
> - **Uso de Herramientas:** Se recomienda el uso de software especializado (como Visio) para realizar los gráficos y luego exportarlos a procesadores de texto (como Word), dado que las herramientas de dibujo básicas suelen dificultar la creación de conectores y bloques precisos.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Síntesis y Conclusiones
> 
> El diagrama de objetos es una herramienta esencial para validar que el diagrama de clases sea funcional y lógico. Permite visualizar datos concretos y relaciones específicas que a veces se pierden en la abstracción de las clases. Su valor reside en la capacidad de representar situaciones complejas, como objetos compuestos o relaciones reflexivas, de manera clara y directa.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia visual principal en la notación de un objeto frente a una clase?
> 2. ¿Qué significa que un objeto sea "anónimo"?
> 3. ¿Cómo se representan los atributos en un diagrama de objetos?
> 
> ### Nivel Intermedio
> 
> 4. Explique el concepto de "instancia reflexiva" con un ejemplo que no sea el laboral.
> 5. ¿Cuándo es conveniente utilizar un "objeto compuesto" en lugar de objetos individuales?
> 6. ¿Por qué se dice que el diagrama de objetos es una estructura estática?
> 
> ### Nivel Avanzado
> 
> 7. Describa el proceso de transformación de un diagrama de clase con multiplicidad 1..N a un diagrama de objetos.
> 8. En un sistema de comunicaciones, ¿cómo influye la dirección de la asociación en la interpretación de un enlace entre objetos?
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de la sesión, se establecen las siguientes pautas y recordatorios:
> 
> - **Próxima Clase (Viernes siguiente):**
>     - **Evento:** Presentación de Trabajos Prácticos (TP).
>     - **Tarea:** Cada grupo debe presentar ejemplos de **Diagramas de Objetos** basados en su tema de interés (puede ser un tema nuevo o el mismo del diagrama de clases anterior).
>     - **Condición Crítica:** El diagrama debe ser explicado por un **integrante del grupo distinto** al que expuso anteriormente. Esto es una condición del profesor para respetar la constitución de los grupos.
> - **Estado de Entregas:**
>     - Los diagramas de clases presentados hasta la fecha están aprobados (incluyendo Grupo 1 y Grupo 2).
>     - El "borrador" del Grupo 2 fue aceptado positivamente tras la incorporación de métodos de pago y comunicaciones.
> - **Recordatorio de Contenido:**
>     - La próxima semana se profundizará en Diagramas de Objetos o se introducirá un diagrama nuevo (posiblemente Diagrama de Estado), dependiendo de la planificación.
>     - Se enfatiza la importancia de las "Comunicaciones" en los sistemas actuales, señalando que serán un tema de estudio posterior más detallado.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 4 - Modelado y diseño de software" src="https://www.youtube.com/embed/zg1ltuLowjQ?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1747Zx4aLDFcmT9Sc5PYC0hgZef2gxe21/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1GMJUP_mSb0qeII1m6rj8BVaGJSSf34ip/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>