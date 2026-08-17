---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/3-desarrollo-de-sistemas-orientado-a-objetos/clase-8-miercoles-01-de-octubre-de-2025-01-10-25-desarrollo-de-sistemas-orientado-a-objetos/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía Completa de Estudio: Desarrollo de Sistemas Orientado a Objetos
> 
> Este documento constituye un material de estudio integral basado en las sesiones académicas sobre programación orientada a objetos (POO) en JavaScript. Cubre desde los fundamentos de la encapsulación hasta la implementación práctica de sistemas de gestión de datos, proporcionando una base técnica sólida para la evaluación de la materia.
> 
> ## 1. Introducción General
> 
> El desarrollo de sistemas orientado a objetos es un paradigma que permite modelar problemas del mundo real mediante la creación de "objetos" que contienen tanto datos como funcionalidades. En el contexto de este curso, se ha priorizado el fortalecimiento de estos conceptos fundamentales antes de avanzar hacia entornos de desarrollo más complejos (como la configuración de servidores web o bases de datos), debido a que la comprensión profunda de la POO es un requisito indispensable para las materias de años superiores.
> 
> ## 2. Contexto del Tema
> 
> ### Importancia y Relevancia
> 
> La transición de una programación lineal o procedimental a una orientada a objetos permite una mejor organización del código, mayor reutilización y una seguridad incrementada a través de la protección de datos. El enfoque actual del curso se centra en tres pilares fundamentales:
> 
> 1. **Encapsulamiento:** Proteger la integridad de los datos internos de un objeto.
> 2. **Herencia:** Crear nuevas clases basadas en clases existentes (ej. una clase `Contacto` que hereda de una clase `Persona`).
> 3. **Composición:** Una estructura donde una clase contiene instancias de otras clases (ej. una `Agenda` compuesta por objetos de tipo `Contacto`).
> 
> ## 3. Marco Conceptual
> 
> ### Definición de Conceptos Clave
> 
> |   |   |
> |---|---|
> |Concepto|Definición|
> |**Clase**|La plantilla o "plano" que define las propiedades y comportamientos de un objeto.|
> |**Constructor**|Método especial que se ejecuta automáticamente al crear una instancia de una clase para inicializar sus atributos.|
> |**Atributo Privado**|Propiedad de una clase que no es accesible directamente desde fuera de la misma. En JavaScript, se denota con el prefijo `#`.|
> |**Método**|Función definida dentro de una clase que representa una acción que el objeto puede realizar.|
> |**Getter/Setter**|Métodos específicos diseñados para obtener (get) o modificar (set) los valores de los atributos de forma controlada.|
> 
> ## 4. Desarrollo del Tema: Encapsulación y Atributos Privados
> 
> ### El Uso del Numeral (#)
> 
> La encapsulación se logra principalmente mediante el uso de atributos privados. Un atributo definido con `#` (numeral) garantiza que la información sensible no pueda ser alterada o consultada sin pasar por la lógica interna de la clase.
> 
> - **Declaración:** Debe declararse fuera del constructor pero dentro de la clase.
> - **Acceso Interno:** Dentro de la clase, se debe referenciar siempre con el numeral (ej. `this.#calificacion`).
> - **Acceso Externo:** Si se intenta acceder desde fuera de la clase (ej. `pelicula1.#calificacion`), el sistema arrojará un error de "Private field", lo cual indica que la protección está funcionando correctamente.
> 
> ### Lógica de Acceso (Getters y Setters)
> 
> Aunque un atributo sea privado, a menudo necesitamos interactuar con él. Para ello se crean métodos públicos que actúan como intermediarios:
> 
> - **Validación:** El método `set` permite verificar si el valor que se intenta asignar es válido (ej. que una calificación esté entre 1 y 10).
> - **Seguridad:** El método `get` puede incluir lógica de autenticación para decidir si el usuario tiene permisos para ver ese dato específico.
> 
> ## 5. Relaciones entre Conceptos
> 
> ### Composición de Objetos
> 
> La relación de composición ocurre cuando una clase "maestra" gestiona una colección de otros objetos. Por ejemplo, en un sistema de agenda:
> 
> - La clase `Contacto` contiene datos individuales (nombre, teléfono, email).
> - La clase `Agenda` posee un array que almacena múltiples instancias de `Contacto`.
> - La `Agenda` es responsable de las funcionalidades lógicas: buscar, agregar o eliminar contactos dentro de su colección interna.
> 
> ### Interacción entre Clases
> 
> Las clases no suelen trabajar aisladas. Un método en la clase `Agenda` puede recibir como parámetro un objeto completo de la clase `Contacto`. Esto permite que la agenda interactúe con los métodos internos del contacto (como `getNombre()`) para realizar búsquedas o filtrados.
> 
> ## 6. Ejemplos Prácticos
> 
> ### Caso 1: Clase Película con Atributo Privado
> 
> Este ejemplo demuestra cómo proteger la calificación de una película.
> 
> ```javascript
> class Pelicula {
>   #calificacion; // Atributo privado
> 
>   constructor(titulo, director, calificacion) {
>     this.titulo = titulo;
>     this.director = director;
>     this.#calificacion = calificacion;
>   }
> 
>   // Método público para acceder al dato privado
>   obtenerCalificacion() {
>     return this.#calificacion;
>   }
> }
> 
> const matrix = new Pelicula("Matrix", "Wachovski", 9);
> console.log(matrix.obtenerCalificacion()); // Funciona: muestra 9
> // console.log(matrix.#calificacion); // Error: El campo es privado
> ```
> 
> ### Caso 2: Sistema de Agenda (Composición y Búsqueda)
> 
> Implementación de una agenda que gestiona objetos de tipo contacto.
> 
> 1. **Clase Contacto:** Define la estructura básica (nombre, email, etc.).
> 2. **Clase Agenda:** Utiliza un array para almacenar los contactos y un bucle `for` para buscarlos por nombre.
> 3. **Visualización:** Se utiliza `JSON.stringify(objeto)` para mostrar el contenido completo de los objetos en la consola, evitando el mensaje genérico `[object Object]`.
> 
> ## 7. Errores Comunes y Confusiones
> 
> - **Error de Declaración de Privados:** Intentar usar un atributo con `#` en el constructor sin haberlo declarado previamente al inicio de la clase.
> - **Confusión con el Error de Acceso:** Muchos estudiantes asumen que un error de "Private field must be declared in an enclosing class" significa que el código está mal escrito, cuando en realidad confirma que el atributo está correctamente protegido contra accesos externos no autorizados.
> - **Errores Sintácticos en Bucles:** Es frecuente el error de dedo en la propiedad `.length` (escribir `lenth` o `lenght`), lo que impide que los bucles `for` se ejecuten.
> - **Confusión entre Parámetro y Objeto:** Al agregar un contacto a una agenda, se debe pasar el objeto instanciado, no solo los datos sueltos, para mantener la integridad de la POO.
> 
> ## 8. Síntesis y Conclusiones
> 
> - La **POO** es la base de la arquitectura de software moderna en JavaScript.
> - Los **atributos privados (#)** son herramientas de seguridad que obligan a usar métodos intermediarios para gestionar datos.
> - La **composición** permite crear sistemas complejos mediante la agrupación de objetos simples dentro de colecciones (arrays).
> - Es fundamental **limpiar la terminal** y realizar **validaciones** constantes para asegurar que los métodos de búsqueda y eliminación funcionen sobre datos reales.
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Qué símbolo se utiliza en JavaScript para declarar un atributo como privado?
> 2. ¿Cuál es la función principal del método `constructor`?
> 3. ¿Para qué sirve el método `JSON.stringify()` al mostrar objetos en consola?
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia entre una clase y un objeto (instancia).
> 5. ¿Por qué es una buena práctica utilizar métodos `get` y `set` en lugar de acceder directamente a los atributos?
> 6. En una relación de composición, ¿qué clase debería contener el método para "buscar" un elemento?
> 
> ### Nivel Avanzado
> 
> 7. Describa qué sucede internamente cuando intentamos acceder a un atributo privado desde fuera de su clase y por qué esto es beneficioso para el sistema.
> 8. Si un método de búsqueda devuelve un objeto JSON con un mensaje y un objeto (o `null`), ¿qué ventajas ofrece esto al desarrollador que consume ese método?
> 
> --------------------------------------------------------------------------------
> 
> ## Fechas Importantes y Avisos Académicos
> 
> A continuación se detallan las fechas y avisos relevantes para la organización de la materia:
> 
> - **Martes 7 de Octubre:** El Instituto permanecerá **cerrado** debido a jornadas de nivel secundario. No habrá actividad académica presencial.
> - **Miércoles 8 de Octubre:** **Examen Parcial.**
>     - **Tipo de evento:** Evaluación presencial obligatoria.
>     - **Contenido:** El examen consistirá en la resolución de ejercicios "desde cero". Se recomienda practicar especialmente con los ejercicios del **TP2**, ya que el nivel de dificultad del parcial será similar a estos (más completos y extensos que los del TP1).
>     - **Temas clave:** Encapsulamiento (privados), Herencia y Composición.
> - **Trabajo Práctico 2 (TP2):** Ya disponible en el Drive. Se introdujo para reforzar la práctica de POO antes del parcial. Reemplaza temporalmente el avance del trabajo grupal.
> - **Trabajo Grupal:** Se pospone para después del parcial y de la clase de corrección. El objetivo es centrarse primero en los contenidos base de la materia.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 8 - Desarrollo de sistemas orientado a objetos" src="https://www.youtube.com/embed/nQ6X6AyEPwE?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1XUm9kDJlPPcy2Ad-6p2d4z0ALXve02N1/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1TRBtAPRPKJU69foSYHxLdcMvaL4H-q0F/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>