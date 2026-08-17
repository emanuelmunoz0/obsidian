---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/3-desarrollo-de-sistemas-orientado-a-objetos/clase-4-miercoles-03-de-septiembre-de-2025-03-09-25-desarrollo-de-sistemas-orientado-a-objetos/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Desarrollo de Sistemas Orientado a Objetos: Conceptos Avanzados y Aplicación Práctica
> 
> Este documento constituye un material de estudio exhaustivo basado en la cuarta sesión sobre el desarrollo de sistemas orientado a objetos. El contenido profundiza en la arquitectura de clases, la implementación de herencia y polimorfismo, y la creación de clases funcionales para la gestión de colecciones de datos.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> El desarrollo orientado a objetos (POO) no es solo una técnica de codificación, sino un paradigma de diseño que busca modelar la realidad mediante entidades denominadas "objetos". Esta sesión se centra en cómo estructurar estas entidades de manera lógica, desde la identificación de objetos físicos (como un animal en un zoológico) hasta la creación de estructuras organizativas complejas que gestionan dichos objetos (como una manada o un linaje).
> 
> ## 2. Contexto del Tema
> 
> En el ámbito del desarrollo de software actual, la POO permite abordar problemas complejos mediante la **abstracción**. El reto principal para el desarrollador no radica únicamente en escribir código, sino en determinar la estructura de clases adecuada: qué clases crear, con qué nivel de detalle y cómo se relacionarán entre sí. La sesión enfatiza que, una vez definida la estructura, la codificación de funciones se vuelve una tarea de implementación lógica directa.
> 
> ### Importancia y Relevancia
> 
> - **Semántica sobre Estructura:** A diferencia de las bases de datos tradicionales, la POO es semántica; se basa en cómo percibimos y explicamos el funcionamiento de las cosas.
> - **Escalabilidad:** Un diseño de clases sólido permite que el sistema crezca sin volverse inmanejable.
> - **Mantenibilidad:** Mediante principios como el encapsulamiento, los cambios en una parte del sistema no afectan necesariamente al resto.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Marco Conceptual
> 
> ### Definición de Conceptos Clave
> 
> 1. **Abstracción:** Es el proceso de determinar qué características y comportamientos de un objeto son relevantes para el sistema y cuáles deben omitirse. Un biólogo puede necesitar un nivel de abstracción muy profundo (subespecies, ADN), mientras que un sistema de gestión de zoológicos solo requiere datos básicos (nombre, especie).
> 2. **Encapsulamiento:** Consiste en ocultar la lógica interna de procesamiento de un método. Las otras clases solo necesitan conocer qué respuesta obtendrán al invocar un método, no cómo se realiza internamente el proceso. Esto asegura que cualquier alteración en la lógica sea responsabilidad exclusiva del administrador de esa clase.
> 3. **Herencia:** Mecanismo por el cual una clase (subclase) adquiere los atributos y métodos de otra (clase padre o superclase). Esto evita la duplicación de código.
> 4. **Polimorfismo:** Capacidad de que diferentes clases tengan métodos con el mismo nombre pero que ejecuten códigos distintos. Por ejemplo, el método `mostrarInfo()` puede comportarse de forma diferente en una clase `León` que en una clase `Elefante`.
> 5. **Clases Funcionales o Intermedias:** Clases que no representan objetos físicos directos, sino que sirven para agrupar, organizar o realizar lógica sobre colecciones de objetos.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Desarrollo del Tema: Arquitectura y Herencia
> 
> ### El Uso del Constructor y la Palabra Clave `super`
> 
> En JavaScript (y otros lenguajes de POO), cuando una subclase hereda de una clase padre, el uso del método `super()` dentro del constructor es obligatorio si se desea acceder a los atributos de la clase superior.
> 
> - **¿Por qué** `**super**`**?** Invoca al constructor de la clase padre para inicializar los atributos heredados. Si la clase `Animal` tiene un atributo `nombre`, la subclase `León` no necesita definir `nombre` nuevamente; simplemente lo pasa a través de `super(nombre)`.
> - **Regla de Oro:** Un atributo definido en la clase padre no debe duplicarse en la subclase a menos que exista una motivación específica (como cambiar el tipo de dato). La normativa teórica dicta que se debe reutilizar lo heredado para minimizar el uso de recursos.
> 
> ### Clases Funcionales y Colecciones
> 
> Un sistema avanzado no solo vive de objetos individuales. Se requieren clases que gestionen estos objetos.
> 
> - **Ejemplo:** En lugar de tener leones dispersos, se crea una clase `Manada`.
> - **Atributos de Clase Funcional:** Generalmente incluyen un _Array_ o colección donde se almacenan las instancias de los objetos que gestiona.
> - **Propósito:** Permiten recorrer todo el "universo" de objetos (por ejemplo, todos los leones de una manada) para obtener datos agregados, como posiciones GPS o estados de salud.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Relaciones entre Conceptos
> 
> La conexión entre las ideas se estructura de forma jerárquica y funcional:
> 
> |   |   |   |
> |---|---|---|
> |Concepto|Relación|Dependencia|
> |**Atributos**|Definen el estado del objeto.|Heredados de la superclase mediante `super`.|
> |**Métodos**|Definen el comportamiento.|Pueden ser polimórficos (mismo nombre, distinta lógica).|
> |**Clases Funcionales**|Gestionan colecciones.|Contienen arrays de instancias de otras clases.|
> |**Abstracción**|Determina el límite del diseño.|Define qué clases y atributos existirán.|
> 
> ### Conexión con Bases de Datos
> 
> Es un error común equiparar directamente una clase con una tabla de base de datos.
> 
> - **Base de Datos Relacional:** Se rige por la normalización y formas normales; los datos de un "Empleado" pueden estar dispersos en cinco tablas.
> - **POO:** Es una capa superior intuitiva. Un objeto "Empleado" unifica todos esos datos dispersos en una sola entidad semántica para el programador.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Ejemplos Prácticos: El Sistema del Zoológico
> 
> ### Caso: Implementación de la Clase `Manada`
> 
> Se busca crear una estructura donde la clase `Manada` gestione objetos de la clase `León`.
> 
> **Paso 1: Definición de la Clase León (Subclase)**
> 
> ```javascript
> class Leon extends Animal {
>     constructor(nombre, sonido) {
>         super(nombre); // Hereda nombre de Animal
>         this.sonido = sonido;
>     }
> }
> ```
> 
> **Paso 2: Definición de la Clase Manada (Funcional)**
> 
> ```javascript
> class Manada {
>     constructor(nombreManada) {
>         this.nombre = nombreManada;
>         this.integrantes = []; // Array que almacenará objetos León
>     }
> 
>     adLeon(leon) {
>         this.integrantes.push(leon);
>     }
> 
>     getLocalizacionIntegrantes() {
>         // Retorna un objeto JSON con el estado de todos los leones
>         let respuesta = { mensaje: "ok", datosLeones: [] };
>         this.integrantes.forEach(leon => {
>             respuesta.datosLeones.push({
>                 nombre: leon.nombre,
>                 gps: "Lat: -34, Long: -58" // Dato simulado
>             });
>         });
>         return respuesta;
>     }
> }
> ```
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Errores Comunes y Confusiones
> 
> 1. **Duplicación de Atributos:** Intentar definir `this.nombre` en la subclase cuando ya existe en la superclase. **Aclaración:** Debe usarse `super(nombre)`. JavaScript es estricto en esto y arrojará error si no se utiliza correctamente en la herencia.
> 2. **Confusión entre Objeto de Clase y Objeto JSON:** Un objeto instanciado (ej. `new Leon()`) posee métodos y lógica; un objeto JSON (ej. `{"nombre": "Simba"}`) es solo una estructura de datos para transferencia de información. Se recomienda usar `JSON.stringify` para visualizar el contenido de objetos complejos en la consola.
> 3. **Escalabilidad Infinita:** Caer en el error de seguir creando clases hacia arriba o hacia abajo sin necesidad (ej. Linaje -> Manada -> León -> Subespecie). **Aclaración:** El pilar de la abstracción debe dictar el límite basado en lo que el sistema realmente necesita resolver.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Síntesis y Conclusiones
> 
> - **La POO se basa en la intuición:** El diseño debe reflejar cómo el usuario explica su negocio o realidad.
> - **La herencia optimiza:** Permite que las subclases se enfoquen solo en lo que las hace diferentes.
> - **Las clases funcionales son el motor:** Mientras que las clases básicas definen entidades, las funcionales (como `Manada` o `SistemaDeVentas`) ejecutan la lógica operativa y gestionan las colecciones de datos.
> - **Encapsulamiento es seguridad:** Permite cambiar la implementación interna sin romper las conexiones con otras partes del sistema.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la función principal del método `super()` en un constructor?
> 2. Defina brevemente el concepto de herencia.
> 3. ¿Para qué sirve `JSON.stringify` al trabajar con objetos en Node.js?
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia entre una clase que representa un objeto físico y una "clase funcional".
> 5. ¿Cómo se relaciona el polimorfismo con el uso de métodos que tienen el mismo nombre en distintas clases?
> 6. ¿Por qué se dice que el encapsulamiento protege al administrador de una clase?
> 
> ### Nivel Avanzado
> 
> 7. Describa el proceso de abstracción necesario para decidir si un atributo debe ir en una clase padre o en una subclase.
> 8. En un sistema de gran escala, ¿cómo asegurarías el acceso al "universo" completo de objetos de una clase específica utilizando clases funcionales?
> 
> --------------------------------------------------------------------------------
> 
> ## 10. Fechas Importantes y Avisos Académicos
> 
> A partir del análisis de las fuentes, se identifican las siguientes indicaciones del profesor:
> 
> - **Próxima Clase:** Se espera avanzar con la resolución de ejercicios y añadir mayores complicaciones funcionales a los mismos. Se enfatiza no dejar pasar mucho tiempo sin practicar.
> - **Entorno de Desarrollo:** Es obligatorio tener instalado **Node.js** y **npm**. Se recomienda la extensión **Code Runner** en Visual Studio Code para agilizar la ejecución de scripts.
> - **Organización de Proyectos (Próximamente):**
>     - **Definición de Grupos:** Los estudiantes deben tener definidos sus grupos y temas de proyecto.
>     - **Dinámica de Trabajo:** Una vez iniciados los proyectos, las clases serán por turnos (ej. 30 minutos por grupo), donde cada grupo se conectará en su horario asignado.
>     - **Fecha Estimada de Inicio de Proyectos:** Aproximadamente en dos semanas (cuando el profesor regrese de su viaje).
> - **Cambio de Horario del Profesor:** Se menciona que para la próxima semana el profesor tendrá una diferencia horaria de 5 horas (posiblemente en Italia/Europa), lo que podría afectar la duración o el inicio de las sesiones (estimación de clases de 1.5 horas).
> - **Advertencia:** Se requerirá el uso de _frameworks_ como **Express** y paquetes de conexión a bases de datos próximamente, por lo que el entorno de Node.js debe estar funcional.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 4 - Desarrollo de sistemas orientado a objetos" src="https://www.youtube.com/embed/yvD6TmGWU8g?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1X2qDOY1XBD9gBRPPOmrWdCzIEhA0OZnR/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1C0sFyhiNYzf2trgOqk41ra0e8c1hV_UD/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>