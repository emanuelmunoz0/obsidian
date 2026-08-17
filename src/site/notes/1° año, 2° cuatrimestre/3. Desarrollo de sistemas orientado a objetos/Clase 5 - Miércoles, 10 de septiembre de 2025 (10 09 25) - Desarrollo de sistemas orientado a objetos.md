---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/3-desarrollo-de-sistemas-orientado-a-objetos/clase-5-miercoles-10-de-septiembre-de-2025-10-09-25-desarrollo-de-sistemas-orientado-a-objetos/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía Avanzada de Estudio: Desarrollo de Sistemas Orientado a Objetos
> 
> Este documento constituye un material de estudio exhaustivo y técnico sobre el paradigma de Programación Orientada a Objetos (POO), basado en el análisis de la arquitectura de sistemas y la implementación práctica en JavaScript. Abarca desde los conceptos fundamentales de herencia y abstracción hasta la integración compleja de la composición y el manejo de excepciones.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> El desarrollo de sistemas orientado a objetos no es solo una técnica de codificación, sino un modelo de pensamiento que permite representar la realidad mediante estructuras lógicas llamadas **clases**. A través de esta metodología, los desarrolladores pueden crear sistemas escalables, reutilizables y fáciles de mantener. El presente documento profundiza en cómo estas estructuras se interconectan para formar sistemas complejos, utilizando como base ejercicios prácticos de gestión de zoológicos y sistemas hoteleros.
> 
> ## 2. Contexto del Tema
> 
> En el marco del aprendizaje técnico, la transición de ejercicios simples a sistemas integrales requiere comprender que las clases no existen de forma aislada. La importancia de este tema radica en la capacidad de organizar la lógica de negocio de manera que refleje fielmente las necesidades del mundo real, minimizando la redundancia de datos y asegurando la integridad del sistema a través de relaciones bien definidas entre objetos.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Marco Conceptual y Definiciones
> 
> ### Conceptos Clave
> 
> |   |   |
> |---|---|
> |Término|Definición Académica|
> |**Clase**|Molde o plantilla que define los atributos y métodos de un objeto.|
> |**Objeto / Instancia**|La materialización concreta de una clase con valores específicos.|
> |**Herencia**|Mecanismo por el cual una subclase adquiere atributos y métodos de una clase padre.|
> |**Abstracción**|Proceso de omitir detalles de la realidad para centrarse en las características esenciales del sistema.|
> |**Composición**|Relación donde una clase está integrada por objetos de otras clases como componentes.|
> |**Polimorfismo**|Capacidad de diferentes clases de responder al mismo mensaje o método de manera distinta.|
> |**Clase Funcional**|Clase que no tiene un correlato físico directo, sino que organiza lógica o procesos (ej. una Reserva).|
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Desarrollo del Tema: Estructura y Relaciones
> 
> ### 4.1. La Herencia: Relación "Es un"
> 
> La herencia se define por la expresión semántica **"es un"**. Una subclase es una versión especializada de su clase padre.
> 
> - **Implementación:** Se utiliza la palabra clave `extends`.
> - **Constructor:** La subclase debe invocar a `super()` para ejecutar el constructor de la clase padre y heredar sus propiedades.
> - **Ejemplo:** Un `León` _es un_ `Animal`. Una `HabitaciónSimple` _es una_ `Habitación`.
> 
> ### 4.2. La Composición: Relación "Tiene un"
> 
> A menudo considerada por algunos autores como un "quinto pilar" de la POO, la composición explica cómo las clases se integran entre sí.
> 
> - **Naturaleza:** A diferencia de la herencia, que es ontológica (del ser), la composición es funcional.
> - **Uso de Arrays:** Es común modelar la composición mediante un array de objetos dentro de un atributo de otra clase.
> - **Ejemplo:** Una `Manada` _tiene_ leones. Una `Habitación` _tiene_ camas (objetos de la clase `Cama`).
> 
> ### 4.3. Clases de Mayor Especificidad y Granularidad
> 
> El diseño puede seguir niveles de abstracción crecientes:
> 
> 1. **Clase Abstracta:** `Animal de Manada` (Concepto que no se instancia, no existe un "animal de manada" genérico en la realidad).
> 2. **Subclase Específica:** `León` (Se instancia en objetos reales).
> 
> - **Nota sobre Abstracción:** No es necesario crear infinitas subclases; el límite lo define la utilidad para el sistema que se está construyendo.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Profundización en la Implementación Técnica
> 
> ### Manejo de Excepciones (Try-Catch)
> 
> Para evitar que un programa se detenga ante un error (como intentar crear un registro que ya existe en una base de datos), se implementa la estructura `try-catch`.
> 
> - **Try:** Bloque donde se intenta ejecutar una instrucción que podría fallar (ej. instanciar una manada con un nombre duplicado).
> - **Catch:** Bloque que captura el error y permite manejarlo (ej. imprimir un mensaje informativo) sin romper el flujo del programa.
> - **Integridad de Datos:** En sistemas reales, el constructor debería validar si un ID o nombre único ya existe antes de proceder.
> 
> ### Estructura de un Sistema Hotelero (Caso de Estudio)
> 
> El sistema analizado presenta una jerarquía compleja:
> 
> 1. **Clase Cama:** Atributos como tipo, tamaño y peso máximo.
> 2. **Clase Habitación:** Contiene un array de objetos `Cama` (Composición).
> 3. **Subclases de Habitación:** `HabitaciónSimple`, `HabitaciónDoble`, `Suite`. Utilizan el método `super()` para definir valores base y añaden atributos propios (ej. `serviciosExtra` en la Suite).
> 4. **Clase Reserva:** Vincula un Huésped con una Habitación y fechas. Es una **Clase Funcional**.
> 5. **Clase Hotel:** La entidad superior que gestiona los arrays de habitaciones y reservas.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Ejemplos Prácticos Explicados
> 
> ### Caso 1: El Método `reservar` en la Clase Habitación
> 
> Este método demuestra la importancia del estado interno de un objeto.
> 
> 6. **Validación de Disponibilidad:** El método consulta un atributo privado `disponible`.
> 7. **Cambio de Estado:** Si está libre, cambia `disponible` a `false`.
> 8. **Manejo de Errores:** Si ya está ocupada, puede devolver una excepción o un valor booleano para informar al sistema.
> 
> ### Caso 2: Composición en la Suite
> 
> Al instanciar una `Suite`, el sistema automáticamente agrega una cama de tipo "Matrimonial King" al array de camas heredado de la clase `Habitación`. Esto muestra cómo la herencia y la composición trabajan juntas: la Suite _hereda_ la estructura de habitación pero _se compone_ de camas específicas.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Errores Comunes y Clarificaciones
> 
> - **Confundir Herencia con Composición:** Pensar que `Habitación` debe extender de `Cama`. Error: Una habitación no _es_ una cama, sino que _contiene_ camas.
> - **Omitir** `**super()**`**:** Intentar usar `this` en una subclase antes de llamar al constructor padre resultará en un error de referencia.
> - **Falta de Validación:** En ejercicios académicos se suele omitir la validación de tipos de datos (asegurarse de que lo que se recibe es un objeto y no un texto), pero es obligatorio en entornos productivos.
> - **Abuso de Clases:** Crear clases para cada pequeño detalle. Si una clase tiene muy poca funcionalidad, podría ser mejor integrar sus atributos en otra clase relacionada.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Síntesis y Conclusiones
> 
> - **Modularidad:** La POO permite separar la lógica en unidades autónomas (clases).
> - **Reutilización:** Mediante la herencia, evitamos escribir el mismo código para diferentes tipos de habitaciones o animales.
> - **Relaciones Lógicas:** La clave de un buen diseño es identificar correctamente si la relación es "Es un" (Herencia) o "Tiene un" (Composición).
> - **Persistencia:** En sistemas reales, estas clases interactúan con bases de datos donde cada objeto suele estar vinculado a un ID único para evitar redundancias e inconsistencias.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso
> 
> **Básicas:**
> 
> 1. ¿Cuál es la diferencia semántica entre herencia y composición?
> 2. ¿Para qué sirve la palabra clave `extends` en JavaScript?
> 3. ¿Qué sucede si no se incluye el bloque `catch` en una estructura de manejo de errores?
> 
> **Intermedias:** 4. Explique el concepto de "Clase Funcional" y dé un ejemplo basado en el sistema hotelero. 5. ¿Cómo ayuda la abstracción a simplificar un sistema de gestión de zoológicos? 6. ¿Qué función cumple el método `super()` dentro del constructor de una subclase?
> 
> **Avanzadas:** 7. Analice cómo el polimorfismo se manifiesta cuando el método `getInfo()` es redefinido en una `Suite` para incluir servicios extra. 8. En un entorno con base de datos, ¿por qué el manejo de excepciones debería ocurrir preferentemente en el método que interactúa con el Query y no propagarse por todas las clases?
> 
> --------------------------------------------------------------------------------
> 
> ## 10. Fechas Importantes y Avisos Académicos
> 
> A partir del análisis de las fuentes, se han identificado las siguientes fechas y recordatorios clave para el desarrollo de la materia:
> 
> - **Fecha de Examen Parcial:** **10 de septiembre**. (Confirmado según el cronograma del Drive; se descartaron las dudas sobre el 24 o el 1 de octubre).
> - **Trabajo Práctico (TP1):** Consta de **15 ejercicios** en total. Actualmente se está trabajando sobre los ejercicios 14 y 15 para finalizar el TP.
> - **Clase de Repaso:** La clase previa al parcial (posterior a la finalización del TP1) será de carácter presencial para resolver dudas.
> - **Trabajo Grupal:** Los proyectos finales en grupo deben comenzar a definirse y ejecutarse próximamente. Se recomienda tener seleccionados los temas para la siguiente semana.
> - **Recordatorio Académico:** Es fundamental la organización en el Drive para la entrega del TP. No se realizarán más modificaciones al enunciado del TP que ya está publicado.
> - **Asistencia:** Se recuerda a los alumnos manejar la planilla de asistencias de forma regular. El profesor destaca la importancia de asistir a las clases presenciales, especialmente para firmar las actas correspondientes.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 5 - Desarrollo de sistemas orientado a objetos" src="https://www.youtube.com/embed/SFaCNZJ-zj8?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1kanQyUqiAaWfahMC59suD0GERLmFRNAy/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1zhLMc9uupx2thA5Sh6jBVlmNWAY05GY6/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>