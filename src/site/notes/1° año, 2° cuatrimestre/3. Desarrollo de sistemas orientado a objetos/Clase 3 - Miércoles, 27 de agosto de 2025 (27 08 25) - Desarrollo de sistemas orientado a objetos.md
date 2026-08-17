---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/3-desarrollo-de-sistemas-orientado-a-objetos/clase-3-miercoles-27-de-agosto-de-2025-27-08-25-desarrollo-de-sistemas-orientado-a-objetos/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía Integral de Desarrollo de Sistemas Orientado a Objetos: Fundamentos y Aplicación en JavaScript
> 
> Este documento constituye un material de estudio exhaustivo sobre el paradigma de Programación Orientada a Objetos (POO), su implementación técnica en JavaScript y las directrices para el desarrollo de proyectos avanzados. Ha sido sintetizado a partir de sesiones académicas especializadas para servir como fuente única de consulta.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> El desarrollo de sistemas orientado a objetos representó una revolución en la ingeniería de software, permitiendo la creación y el mantenimiento de sistemas significativamente más complejos que los permitidos por paradigmas anteriores. En la actualidad, este paradigma no se encuentra aislado, sino que está integrado en lenguajes modernos como JavaScript y Python. La POO facilita la reutilización de código y la organización lógica mediante la representación de entidades de la realidad en estructuras digitales.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual: Definición de Conceptos Clave
> 
> Para comprender la POO desde cero, es fundamental distinguir entre los elementos que componen su estructura:
> 
> ### Clases vs. Objetos
> 
> - **Clase:** Es el diseño, molde o definición abstracta que codificamos. En ella se especifican qué atributos (datos) y métodos (comportamientos) tendrán los elementos de ese tipo.
> - **Objeto:** Es una **instancia** concreta de una clase. Mientras la clase es el plano, el objeto es la realización específica que procesa datos reales e interactúa con otros objetos.
> 
> ### Componentes de una Clase
> 
> 1. **Atributos:** Son las características o datos que almacena el objeto (ej. nombre, kilometraje, sonido).
> 2. **Métodos:** Son las funciones o acciones que el objeto puede realizar (ej. encender, mostrar información, realizar sonido).
> 3. **Constructor:** Es un método especial que se ejecuta automáticamente al instanciar un objeto. Su función principal es establecer o definir los valores iniciales de los atributos.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Los Cuatro Pilares de la POO
> 
> El paradigma se sustenta en cuatro principios fundamentales que guían el diseño de software:
> 
> ### A. Abstracción
> 
> Consiste en realizar un "recorte de la realidad". No se busca representar todos los datos posibles de una entidad, sino únicamente aquellos que son relevantes para el objetivo del sistema.
> 
> - _Ejemplo:_ En una clase `Persona`, se puede incluir el DNI y la edad, pero omitir el color de ojos o datos de salud si no son necesarios para la aplicación, evitando así una complejidad innecesaria.
> 
> ### B. Encapsulamiento
> 
> Se refiere a la capacidad de ocultar la lógica interna del procesamiento de datos. Los objetos funcionan como una "caja negra": los usuarios u otros objetos interactúan con ellos a través de métodos públicos sin necesidad de conocer cómo se procesa la información internamente.
> 
> ### C. Herencia
> 
> Permite que una clase (subclase) adopte los atributos y métodos de otra clase superior (superclase o clase abstracta). Esto promueve la reutilización de código y facilita el mantenimiento, ya que los cambios en la clase superior impactan automáticamente en todas las que heredan de ella.
> 
> ### D. Polimorfismo
> 
> Es la capacidad de que métodos con el mismo nombre se comporten de manera distinta según la clase que los ejecute.
> 
> - _Ejemplo:_ El método `encender()` puede existir en la clase `Vehículo`, pero su implementación será distinta en una `Moto` (electrónico) que en un `Auto` (manual).
> 
> **Resumen parcial:** La POO utiliza clases para crear objetos, basándose en la abstracción para simplificar la realidad, el encapsulamiento para proteger la lógica, la herencia para reutilizar código y el polimorfismo para dar flexibilidad a los métodos.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Implementación Técnica en JavaScript
> 
> JavaScript presenta particularidades en su interpretación del estándar de objetos:
> 
> ### Sintaxis de Herencia y Jerarquía
> 
> - `**extends**`**:** Palabra clave utilizada para declarar que una clase es subclase de otra (ej. `class Leon extends Animal`).
> - `**super()**`**:** Se utiliza dentro del constructor de la subclase para invocar al constructor de la clase superior y heredar sus atributos inicializados.
> - `**this**`**:** Referencia a la instancia actual del objeto.
> 
> ### Visibilidad y Alcance
> 
> |   |   |   |
> |---|---|---|
> |Tipo de Atributo/Método|Notación|Descripción|
> |**Público**|Sin marca|Accesible directamente desde fuera de la clase al instanciar el objeto.|
> |**Privado**|`#` (numeral)|Solo accesible internamente. Se requiere un método público (getter/setter) para interactuar con él.|
> |**Estático**|`static`|Pertenece a la clase, no al objeto. Se invoca usando el nombre de la clase (ej. `Animal.metodo()`).|
> 
> ### Manejo de Variables y Constantes
> 
> - `**const**` **en Objetos:** Definir un objeto como `const` impide que la variable sea reasignada a otro valor, pero **permite modificar los atributos** internos del objeto mediante métodos o acceso directo.
> - `**let**`**:** Se utiliza si se prevé que la variable que contiene el objeto deberá cambiar de asignación completamente en el futuro.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Relaciones entre Conceptos: Estructuras de Datos Complejas
> 
> Una práctica común es la creación de **clases de gestión o administración**, que no representan una entidad física simple, sino una estructura que agrupa a otros objetos.
> 
> - **Arrays de Objetos:** Una clase (ej. `Manada`) puede tener un atributo que sea una lista (array) de objetos de otra clase (ej. `Leon`).
> - **Métodos de Gestión:** Estas clases suelen incluir métodos como `agregarElemento(objeto)` que utilizan funciones como `.push()` para alimentar la colección interna.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Ejemplo Práctico: Sistema de Gestión de Zoológico
> 
> A continuación, se detalla la implementación de un sistema basado en herencia y polimorfismo:
> 
> ### Estructura de Clases
> 
> 1. **Clase Animal (Padre):** Define atributos como `nombre` y `sonido`, y métodos como `hacerSonido()` y `mostrarInfo()`.
> 2. **Clase León (Hijo):**
>     - Usa `extends Animal`.
>     - En su constructor, utiliza `super(nombre)` para pasar el nombre a la clase padre.
>     - Define un sonido por defecto (`roar`).
>     - Añade un atributo específico: `manada`.
>     - Sobrescribe el método `mostrarInfo()` para incluir el dato de la manada.
> 3. **Clases Elefante y Mono (Hijos):** Heredan directamente de `Animal` sin añadir atributos complejos, demostrando cómo la herencia simplifica la creación de nuevas especies.
> 
> ### Flujo de Ejecución (Paso a Paso)
> 
> 4. Se instancia un objeto: `const leon1 = new Leon("Simba")`.
> 5. El constructor de `Leon` se activa, llama a `super()` para el nombre y asigna el sonido `roar`.
> 6. Se invoca un método específico: `leon1.unirseAManada("Manada Norte")`.
> 7. Se solicita información: `leon1.mostrarInfo()`, lo cual devuelve un string con el nombre, el sonido y la manada.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Errores Comunes y Aclaraciones Importantes
> 
> - **Rigurosidad de JavaScript:** A diferencia de otros lenguajes, los intérpretes de JavaScript pueden variar levemente. Por ejemplo, algunos desarrolladores usan guion bajo `_` para denotar privacidad por convención, aunque el estándar oficial es el numeral `#`.
> - **Constructores en otros lenguajes:** Mientras que en Java el constructor lleva el nombre de la clase, en JavaScript se utiliza explícitamente la palabra `constructor`.
> - **Tipado:** JavaScript no es un lenguaje tipado. Una variable puede almacenar cualquier tipo de dato (string, número, objeto) sin declaración previa del tipo, lo que exige mayor cuidado del programador para evitar errores en tiempo de ejecución.
> - **Setters y Validación:** No todos los atributos privados requieren un método `set`. Estos métodos se utilizan principalmente para validar los datos antes de asignarlos a un atributo.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Síntesis y Puntos Clave
> 
> - **POO** es un modelo para organizar código basado en entidades de la vida real.
> - **Herencia (**`**extends**`**)** ahorra código al compartir lógica entre clases padre e hijos.
> - **Encapsulamiento** protege la integridad de los datos usando métodos de acceso.
> - **JavaScript** es flexible (no tipado), por lo que el uso de constructores y métodos de validación es vital.
> - **Relaciones:** Es posible y común tener objetos que contienen colecciones (arrays) de otros objetos para gestionar sistemas complejos.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso (Tipo Examen)
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia fundamental entre una clase y un objeto?
> 2. ¿Qué función cumple el método `constructor` en JavaScript?
> 3. ¿Cómo se define un atributo privado en una clase de JavaScript?
> 
> ### Nivel Intermedio
> 
> 4. Explique el concepto de Herencia y cómo se implementa mediante la palabra clave `extends`.
> 5. Si un objeto se instancia usando `const`, ¿es posible cambiar el valor de uno de sus atributos? Justifique su respuesta.
> 6. ¿Para qué sirve la instrucción `super()` dentro de una subclase?
> 
> ### Nivel Avanzado
> 
> 7. Describa una situación donde el principio de Abstracción obligue a omitir ciertos datos de una entidad real.
> 8. ¿Qué ventaja ofrece un método estático (`static`) sobre un método de instancia y en qué casos se recomienda su uso?
> 9. Explique cómo se podría implementar una clase "Gestora" que administre una colección de objetos de otra clase distinta.
> 
> --------------------------------------------------------------------------------
> 
> ## 10. Fechas Importantes y Avisos Académicos
> 
> A partir del análisis de las fuentes, se han identificado las siguientes fechas y requerimientos para la materia:
> 
> ### Cronograma de Proyecto
> 
> - **10 de Septiembre (Fecha Original):** Inicio oficial de la fase de planificación y documentación del proyecto.
> - **17 de Septiembre (Fecha Estimada/Tentativa):** Inicio efectivo de los avances del proyecto (debido a posibles extensiones de trabajos prácticos previos).
> - **Presencialidad:** Se indica que habrá sesiones presenciales opcionales para consultas; quienes no asistan pueden aprovechar el tiempo para estudio u otras actividades online.
> 
> ### Requerimientos del Proyecto Grupal
> 
> El proyecto debe cumplir con los siguientes fundamentos técnicos:
> 
> 1. **Entorno:** Debe estar desarrollado sobre **Node.js**.
> 2. **Framework:** Es obligatorio el uso de **Express** (servidor web/API).
> 3. **Módulo de Inteligencia Artificial:** La aplicación debe realizar consultas a una API de IA (se sugieren **Gemini** de Google o **Quen**).
> 4. **Versionado:** El repositorio debe estar alojado en **GitHub** y utilizar Git para el control de versiones (permitiendo rollbacks).
> 5. **Base de Datos:** Debe incluir al menos una base de datos simple (se sugiere **MariaDB** para relacionales o **MongoDB** para no relacionales).
> 6. **Planificación:** Se deben utilizar o tener en el radar herramientas como **Diagramas de Gantt, Notion o Jira**.
> 7. **Interfaz (Front-end):** Se permite un desarrollo básico con **HTML y CSS**. El uso de frameworks como React o Angular es opcional.
> 
> ### Advertencias Académicas
> 
> - El profesor enfatiza que el proyecto no busca una complejidad extrema, sino que los alumnos se familiaricen con el "ecosistema" completo (Full Stack) y las herramientas que utilizarán en materias superiores.
> - Se recomienda vincular el proyecto con otras materias para optimizar el tiempo de trabajo.
> - **Próxima Clase:** Se resolverá en conjunto el **Ejercicio 6** del Trabajo Práctico, el cual involucra arrays de objetos. Se sugiere a los alumnos intentar resolverlo previamente.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 3 - Desarrollo de sistemas orientado a objetos" src="https://www.youtube.com/embed/6ISc_E2c2wg?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1uuC9gr2slu66lOfVhZD38r6u_Qryf1uD/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1PsetRxp9gO95QiSNjlxBHiQCBYbjYlFj/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>