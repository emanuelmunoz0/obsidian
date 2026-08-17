---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/3-desarrollo-de-sistemas-orientado-a-objetos/clase-2-miercoles-20-de-agosto-de-2025-20-08-25-desarrollo-de-sistemas-orientado-a-objetos/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Fundamentos del Desarrollo de Sistemas Orientado a Objetos: Guía Académica Completa
> 
> Este documento constituye un material de estudio integral sobre el paradigma de Programación Orientada a Objetos (POO), basado en las sesiones académicas de desarrollo de sistemas. Su propósito es proporcionar una comprensión profunda de los conceptos, desde sus bases hasta su implementación técnica en JavaScript.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> La **Programación Orientada a Objetos (POO)** es un paradigma que permite representar situaciones, actividades o procesos del mundo real dentro de un sistema informático. En lugar de ver la programación como una simple secuencia de instrucciones, la POO organiza el software en "objetos" que interactúan entre sí para procesar datos y cumplir funciones específicas.
> 
> ### Contexto del tema
> 
> En el desarrollo de software profesional, especialmente en sistemas de mediana y alta complejidad, la POO es fundamental. Permite que el código sea reutilizable, organizado y fácil de mantener. Las empresas de desarrollo de software no suelen diseñar sistemas aislados, sino estructuras de clases que puedan ser aprovechadas en múltiples proyectos.
> 
> ### Importancia y relevancia
> 
> - **Modularidad:** Divide problemas complejos en partes más pequeñas y manejables (objetos).
> - **Reutilización:** Una clase diseñada para un sistema bancario puede adaptarse a otros contextos.
> - **Abstracción:** Permite enfocarse en lo que un objeto hace y no necesariamente en cómo lo hace internamente.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual: Conceptos Clave desde Cero
> 
> Para entender la POO, es necesario dominar la distinción entre clase y objeto, y cómo se estructuran internamente.
> 
> ### Definiciones Fundamentales
> 
> |   |   |
> |---|---|
> |Concepto|Definición|
> |**Clase**|Es el "molde", plano o lógica que codificamos. Define qué datos tendrá un objeto y qué acciones podrá realizar. No procesa datos por sí misma, es una definición abstracta.|
> |**Objeto**|Es una instancia concreta de una clase. Es el elemento real que ocupa memoria, procesa datos y realiza las funciones definidas en su clase.|
> |**Atributos**|Son las características o datos que definen a un objeto (ej. nombre, edad, saldo).|
> |**Métodos**|Son las funciones u operaciones que el objeto puede realizar (ej. retirar dinero, avanzar tiempo).|
> |**Instanciar**|El acto de crear un objeto a partir de una clase utilizando la palabra clave `new`.|
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: Estructura y Pilares de la POO
> 
> ### El Circuito de Desarrollo
> 
> El proceso de creación de un sistema sigue un orden lógico:
> 
> 1. **Identificación:** Se analiza una actividad (ej. un banco) y se identifican los objetos que interactúan (clientes, cuentas, tarjetas).
> 2. **Diseño de Clases:** Se crean los moldes (clases) con sus atributos y métodos.
> 3. **Codificación:** Se escribe la lógica en un lenguaje (en este caso, JavaScript).
> 4. **Instanciación:** Se crean los objetos reales que procesarán la información.
> 
> ### Los Atributos y su Visibilidad
> 
> En JavaScript, no todos los datos deben ser accesibles para todos. Existen diferentes niveles de acceso:
> 
> 1. **Públicos:** Accesibles desde cualquier parte del programa. Se definen usualmente dentro del constructor.
> 2. **Privados (**`**#**`**):** Solo pueden ser accedidos o modificados por métodos internos de la misma clase. Se definen anteponiendo el signo `#` al nombre del atributo. Esto protege la integridad de los datos.
> 3. **Estáticos (**`**static**`**):** Pertenecen a la **clase** en sí y no a un objeto específico. Todos los objetos comparten el mismo valor para un atributo estático.
> 4. **Dinámicos:** Variables que se añaden a una instancia específica después de haber sido creada, aunque no estuvieran en el diseño original de la clase.
> 
> ### El Método Constructor
> 
> Es un método especial llamado `constructor` que se ejecuta automáticamente al instanciar un objeto. Su función principal es inicializar los atributos del objeto con valores específicos.
> 
> ### Los Cuatro Pilares de la POO
> 
> |   |   |
> |---|---|
> |Pilar|Explicación|
> |**Abstracción**|Consiste en realizar un "doble recorte": primero, identificar qué objetos de la realidad nos interesan y, segundo, qué datos específicos de esos objetos necesitamos para nuestro sistema (ej. de un empleado solo nos interesa el CUIL y nombre, no su color favorito).|
> |**Encapsulación**|Oculta la lógica interna y la complejidad del procesamiento. El usuario del objeto solo necesita conocer los nombres de los métodos (la "interfaz") para obtener resultados, sin saber qué ocurre "bajo el capó".|
> |**Herencia**|Permite que una clase (subclase) herede atributos y métodos de otra clase superior. Ejemplo: Una clase `Producto` puede ser la madre de `TarjetaDeCrédito` y `Préstamo`.|
> |**Polimorfismo**|Capacidad de que diferentes clases tengan métodos con el mismo nombre pero que se comporten de forma distinta según quién los invoque o qué parámetros reciban.|
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Relaciones entre Conceptos y Sintaxis en JavaScript
> 
> La conexión entre los conceptos se manifiesta en la forma en que escribimos el código.
> 
> - `**this**`**:** Se utiliza dentro de la clase para hacer referencia al objeto que se está creando o utilizando en ese momento. Por ejemplo: `this.saldo = 0;` indica que el saldo de _este_ objeto específico es cero.
> - **Clase como Atributo:** Un atributo de una clase puede ser, a su vez, una colección u objeto de otra clase. Por ejemplo, la clase `Banco` puede tener un array de objetos de la clase `CuentaBancaria`.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Ejemplos Prácticos Paso a Paso
> 
> ### Caso 1: Sistema Bancario Simple
> 
> A continuación, se muestra cómo se define una clase con atributos privados y métodos públicos para acceder a ellos (Getters).
> 
> ```javascript
> class CuentaBancaria {
>   // Atributos privados (fuera del constructor)
>   #numeroCuenta;
>   #saldo;
> 
>   constructor(propietario, numero, banco) {
>     this.propietario = propietario; // Público
>     this.#numeroCuenta = numero;    // Privado
>     this.#saldo = 0;                // Privado
>     this.nombreBanco = banco;       // Público
>   }
> 
>   // Método público para acceder a un dato privado
>   getNumeroCuenta() {
>     return this.#numeroCuenta;
>   }
> }
> 
> // Instanciación
> const miCuenta = new CuentaBancaria("Juan Pérez", "12345", "Banco Central");
> console.log(miCuenta.propietario); // Funciona
> // console.log(miCuenta.#numeroCuenta); // Daría ERROR
> console.log(miCuenta.getNumeroCuenta()); // Funciona correctamente
> ```
> 
> ### Caso 2: Reloj Digital (Lógica de Avance)
> 
> Este ejemplo demuestra cómo un método (`avanzar`) puede gestionar la lógica interna de los atributos.
> 
> ```javascript
> class Reloj {
>   constructor() {
>     this.hora = 0;
>     this.minutos = 0;
>     this.segundos = 0;
>   }
> 
>   avanzar() {
>     if (this.segundos < 59) {
>       this.segundos++;
>     } else {
>       this.segundos = 0;
>       if (this.minutos < 59) {
>         this.minutos++;
>       } else {
>         this.minutos = 0;
>         this.hora++;
>       }
>     }
>   }
> }
> ```
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores Comunes y Confusiones
> 
> 1. **Confusión entre Clase y Objeto:** Intentar acceder a un atributo de instancia directamente desde la clase (ej. `CuentaBancaria.saldo` en lugar de `miCuenta.saldo`).
> 2. **Acceso a Privados:** Olvidar que los atributos con `#` no se pueden leer ni escribir desde fuera de la clase. Se requiere un método "getter" o "setter".
> 3. **El Prefijo "0" (Error de Octal):** En JavaScript, poner un cero delante de un número (como `00` o `07`) puede causar errores o interpretaciones inesperadas (base octal). Se recomienda usar un solo `0` para valores numéricos nulos.
> 4. **Uso de** `**static**`**:** Intentar acceder a un método o atributo estático desde un objeto (instancia). Los estáticos solo se acceden mediante el nombre de la Clase (`Clase.atributo`).
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Síntesis y Conclusiones
> 
> - La POO se basa en la creación de **clases** (diseño) para generar **objetos** (acción).
> - La **abstracción** selecciona lo importante; la **encapsulación** protege la lógica.
> - En JavaScript, usamos `#` para privacidad y `static` para datos compartidos por la clase.
> - El **constructor** es la puerta de entrada para definir un objeto con sus datos iniciales.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia fundamental entre una clase y un objeto?
> 2. ¿Para qué sirve el método `constructor`?
> 3. ¿Cómo se define un atributo privado en JavaScript?
> 
> ### Nivel Intermedio
> 
> 4. Explique el concepto de Abstracción con un ejemplo diferente al bancario.
> 5. ¿Qué sucede si intento acceder a un atributo estático desde un objeto instanciado?
> 6. ¿Por qué es importante la Encapsulación en un sistema que maneja datos sensibles?
> 
> ### Nivel Avanzado
> 
> 7. Describa un escenario donde el Polimorfismo sea necesario para simplificar un sistema de ventas.
> 8. En el ejemplo del reloj, ¿por qué la lógica de "avanzar" debe estar dentro de la clase y no fuera? Analice esto desde el pilar de la Encapsulación.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Fechas Importantes y Avisos Académicos
> 
> A partir del análisis de la fuente, se identifican las siguientes indicaciones:
> 
> - **Trabajo Práctico N° 1 (TP1):**
>     - Ya se encuentra disponible en el Drive/Aula Virtual.
>     - Contiene 15 ejercicios.
>     - **Indicación del profesor:** Se espera que los estudiantes comiencen a resolverlo a su propio ritmo para identificar dudas. Se recomienda completar al menos hasta el ejercicio 4 o 5 para la próxima clase, ya que a partir del 6 o 7 la complejidad aumenta.
>     - **Incentivo informal:** Existe el compromiso de una "docena de facturas" para aquellos que logren presentar hasta el ejercicio 7 completado en la próxima sesión.
> - **Requerimientos Técnicos:**
>     - Es obligatorio instalar **Node.js** y **npm** en las computadoras personales para ejecutar el código JavaScript (especialmente para trabajar con clases y atributos privados, que herramientas online como _Coding_ podrían no soportar adecuadamente).
> - **Sobre el Parcial:**
>     - La fecha exacta no ha sido definida, pero se estima que los temas actuales (POO básica, clases, atributos, métodos y los pilares) constituirán el núcleo de la evaluación. Posteriormente, la materia se enfocará en el desarrollo de aplicaciones en grupos.
> - **Material de consulta:**
>     - El archivo `.txt` de anotaciones y el enunciado del TP1 estarán centralizados en la carpeta de Drive compartida.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 2 - Desarrollo de sistemas orientado a objetos" src="https://www.youtube.com/embed/GX4F4IsbB7M?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/12M9_8xFmVVykHNOx3jfSwiGg-DdqGt1J/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1WvbRL9ZaPfWW5uRcSot_3cn72X3s8tSg/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>