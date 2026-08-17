---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/3-desarrollo-de-sistemas-orientado-a-objetos/clase-9-miercoles-08-de-octubre-de-2025-08-10-25-desarrollo-de-sistemas-orientado-a-objetos/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio: Desarrollo de Sistemas Orientado a Objetos y Modelado Ético
> 
> Este documento constituye un material de estudio integral basado en las sesiones académicas sobre el desarrollo de sistemas orientado a objetos (POO). El enfoque principal reside en la transición de la teoría a la práctica, la resolución de problemas mediante la abstracción y la implementación de sistemas complejos utilizando herencia y composición.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> El desarrollo orientado a objetos no es solo una técnica de programación, sino un proceso de **abstracción**. Consiste en observar situaciones complejas de la realidad y reducirlas a rasgos estructurales simples. El objetivo fundamental es identificar entidades (objetos), agruparlas por características comunes (clases) y definir su comportamiento (métodos).
> 
> La práctica constante es el único camino para superar la confusión inicial que genera la identificación de clases y la relación entre ellas. El desarrollo exitoso requiere aprender a realizar suposiciones lógicas para avanzar, en lugar de paralizarse ante la complejidad de un enunciado.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual: Definición de Conceptos Clave
> 
> Para dominar el desarrollo orientado a objetos, es imperativo comprender los pilares que estructuran cualquier sistema:
> 
> ### Clases y Objetos
> 
> - **Clase:** Es una plantilla o "molde" que define los atributos (datos) y métodos (comportamientos) comunes a un grupo de objetos. Por ejemplo, la clase `Persona`.
> - **Objeto:** Es una instancia específica de una clase. Si `Persona` es la clase, "Juan" con un DNI específico es el objeto.
> 
> ### Herencia
> 
> Es la capacidad de crear nuevas clases (subclases) a partir de clases existentes (superclases).
> 
> - **Superclase:** Contiene los atributos y métodos generales (ej. `Persona` tiene nombre y DNI).
> - **Subclase:** Hereda lo general y añade atributos propios (ej. `Doctor` hereda de `Persona` pero añade `Matrícula`).
> 
> ### Encapsulamiento
> 
> Principio que asegura que los datos de un objeto solo puedan ser accedidos o modificados a través de los métodos de su propia clase (usualmente mediante _getters_ y _setters_). Esto protege la integridad de la información y evita que clases externas gestionen datos que no les corresponden (como el DNI gestionado fuera de la clase `Persona`).
> 
> ### Composición
> 
> Se produce cuando una clase se compone de objetos de otras clases. Es el nivel más avanzado de relación. Por ejemplo, una `Historia Clínica` no es solo texto, sino que contiene un objeto `Paciente` y una lista de objetos `Diagnóstico`.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: El Sistema de Gestión Hospitalaria
> 
> A través del análisis de un sistema hospitalario, se observa cómo se estructuran estos conceptos en un entorno real.
> 
> ### Jerarquía de Clases y Atributos
> 
> |   |   |   |   |
> |---|---|---|---|
> |Clase|Tipo|Atributos Heredados|Atributos Propios|
> |**Persona**|Superclase|N/A|DNI, Nombre, Apellido, Edad|
> |**Doctor**|Subclase|DNI, Nombre, Apellido, Edad|Especialidad, Matrícula|
> |**Paciente**|Subclase|DNI, Nombre, Apellido, Edad|Nro. Historia Clínica, Obra Social|
> |**Enfermero**|Subclase|DNI, Nombre, Apellido, Edad|Turno, Sector|
> 
> ### Implementación de Métodos
> 
> Los métodos definen la funcionalidad. En un sistema de este tipo, se identifican tres niveles de métodos:
> 
> 1. **Getters y Setters:** Para acceder y validar datos básicos.
> 2. **Informativos (**`**getInfo**`**):** Devuelven un resumen del estado del objeto.
> 3. **Operacionales:** Realizan acciones específicas (ej. `atenderPaciente` en la clase `Doctor` o `tomarSignosVitales` en la clase `Enfermero`).
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Relaciones entre Conceptos y Flujo de Trabajo
> 
> El proceso de construcción de un sistema sigue un orden lógico de menor a mayor complejidad:
> 
> 4. **Modelado y Abstracción:** Identificar qué clases son necesarias y cómo se relacionan mediante herencia.
> 5. **Implementación de Clases Base:** Crear la superclase y las subclases con sus constructores y métodos básicos.
> 6. **Instanciación:** Crear objetos reales (objetos "hardcodeados" o de prueba) para verificar que la estructura funciona.
> 7. **Composición y Lógica Compleja:** Vincular objetos de distintas clases. Por ejemplo, un método de la clase `Doctor` recibe un objeto de la clase `HistoriaClínica` para modificarlo.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Ejemplos Prácticos de Implementación
> 
> ### Estructura de la Historia Clínica
> 
> La clase `Historia Clínica` es un ejemplo clave de composición. No debe verse como un simple campo de texto, sino como una estructura que almacena múltiples registros:
> 
> - **Atributo Paciente:** Almacena el objeto paciente al que pertenece.
> - **Array de Diagnósticos:** Una lista (pueden ser objetos o formato JSON) que contiene:
>     - Fecha.
>     - Descripción de la consulta.
>     - Objeto Doctor (quien realizó la atención).
>     - Tratamiento indicado.
> 
> ### El Método `atenderPaciente` (Clase Doctor)
> 
> Este método demuestra la interacción entre entidades:
> 
> 1. El Doctor recibe la `Historia Clínica` del paciente.
> 2. El Doctor genera un nuevo registro de diagnóstico.
> 3. Se añade la fecha actual, sus observaciones y el tratamiento.
> 4. Se guarda el registro en el historial y se devuelve el objeto actualizado.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores Comunes y Clarificaciones
> 
> - **Parálisis por Análisis:** No es necesario tener el 100% de la lógica clara para empezar a codificar. Se recomienda realizar suposiciones (ej. "voy a asumir que el tratamiento es un string por ahora") para avanzar y luego refinar.
> - **Confusión en Encapsulamiento:** Un error frecuente es permitir que una clase gestione datos que pertenecen a otra (ej. que la clase `Historia Clínica` intente modificar directamente el DNI del paciente). Siempre se debe acceder a través de la clase dueña del dato.
> - **Complejidad en Composición:** No se debe intentar implementar la composición (vincular varias clases) hasta que las clases individuales funcionen correctamente por separado.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Síntesis y Conclusiones
> 
> El éxito en el desarrollo orientado a objetos depende de una **abstracción sólida**. Un sistema bien diseñado permite que la información fluya entre objetos (como un Doctor modificando una Historia Clínica) manteniendo la integridad de los datos mediante el encapsulamiento. La herencia facilita la reutilización de código (evitando repetir campos como DNI o Nombre en cada clase), mientras que la composición permite modelar la complejidad real de un hospital o cualquier otra organización.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de la sesión, se establecen las siguientes pautas para la evaluación:
> 
> - **Fecha del Parcial:** Próximo miércoles.
> - **Estructura del Examen:**
>     - Se compone de **dos partes diferenciadas**: una de **Modelado** (teórico/diagrama) y una de **Codificación** (práctica).
>     - **Importante:** El modelado y la codificación estarán separados. Si un estudiante tiene dificultades modelando la jerarquía, esto no le impedirá realizar la parte de codificación, ya que para esta última el profesor entregará las clases ya definidas con métodos vacíos para completar.
> - **Contenido:** El examen podría incluir dos ejercicios (uno corto de modelado y uno largo de código) o uno solo integral. Se evaluará la capacidad de priorizar y resolver lo esencial en el tiempo estipulado (aprox. 2 horas).
> - **Recomendación del Profesor:** Practicar los ejercicios del Trabajo Práctico 2 (TP2), especialmente aquellos que involucran composición.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia entre una clase y un objeto?
> 2. ¿Para qué sirven los métodos `get` y `set` en el contexto del encapsulamiento?
> 3. En una jerarquía de herencia, ¿qué palabra clave se utiliza para invocar al constructor de la superclase? (Referencia: `super`).
> 
> ### Nivel Intermedio
> 
> 4. Si tengo las clases `Persona`, `Doctor` y `Paciente`, ¿cómo debería estructurarse la herencia y qué atributos quedarían en la clase base?
> 5. ¿Por qué es útil que un método como `atenderPaciente` reciba un objeto como parámetro en lugar de solo datos sueltos?
> 
> ### Nivel Avanzado
> 
> 6. Explique cómo se implementa la composición en el caso de la `Historia Clínica` y su relación con la clase `Doctor`.
> 7. Describa una estrategia para abordar un examen de programación cuando el tiempo es insuficiente para completar todas las funcionalidades.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 9 - Desarrollo de sistemas orientado a objetos" src="https://www.youtube.com/embed/bbqGbp-ot2Y?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/17Z-uR3BmTcaG1Ej8ptozUnE9Mk9ml6O2/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1jzHFdEgfP1TI8Xixcq7--Nq_YZwgibwM/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>