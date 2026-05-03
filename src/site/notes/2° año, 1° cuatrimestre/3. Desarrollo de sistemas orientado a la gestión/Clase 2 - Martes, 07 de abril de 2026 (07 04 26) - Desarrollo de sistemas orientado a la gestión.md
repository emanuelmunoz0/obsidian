---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/3-desarrollo-de-sistemas-orientado-a-la-gestion/clase-2-martes-07-de-abril-de-2026-07-04-26-desarrollo-de-sistemas-orientado-a-la-gestion/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Desarrollo de Sistemas Orientado a la Gestión: Del Análisis de Procesos al Modelado de Datos
> 
> Este documento constituye una guía exhaustiva de estudio basada en el análisis de flujos de trabajo, reglas de negocio y la transición hacia estructuras de datos complejas. Se centra en la aplicación práctica de conceptos de ingeniería de software para la resolución de problemas en entornos de gestión, tales como el comercio electrónico y la administración de bibliotecas.
> 
> ## 1. Introducción General
> 
> En el desarrollo de sistemas orientados a la gestión, el proceso no comienza con el código, sino con el entendimiento profundo de la lógica del negocio. Este documento detalla la progresión desde la representación visual de procesos (flujogramas) hasta la estructuración de la información (Diagramas de Entidad-Relación - DER). Se enfatiza la importancia de la validación de requisitos con el cliente y la resolución de ambigüedades lógicas antes de proceder a la implementación técnica.
> 
> ### Contexto del Tema
> 
> El análisis de sistemas requiere una transición fluida entre lo que el usuario necesita y cómo el sistema almacena y procesa esa información. A través de casos prácticos como un sistema de descuentos en un e-commerce, se examina cómo las decisiones administrativas impactan directamente en el diseño técnico.
> 
> ## 2. Marco Conceptual
> 
> Para comprender el desarrollo de sistemas de gestión, es fundamental dominar los siguientes conceptos:
> 
> ### Definición de Conceptos Clave
> 
> - **Flujograma (Diagrama de Flujo):** Herramienta gráfica que representa la secuencia de pasos, decisiones y procesos de un sistema. Permite identificar cuellos de botella y errores lógicos en la etapa de diseño.
> - **Reglas de Negocio:** Son las directrices y restricciones que rigen las operaciones de una organización. Por ejemplo: "Un descuento corporativo no es acumulable con un cupón".
> - **Diagrama Entidad-Relación (DER):** Un modelo de datos que describe las estructuras de información y las relaciones entre diferentes entidades (objetos) dentro de un sistema.
> - **Validación de Requisitos:** El proceso de confirmar con el cliente o usuario final que las interpretaciones del analista son correctas y cubren todas las posibilidades del negocio.
> 
> ### Términos Fundamentales
> 
> 1. **Entidad:** Un objeto del mundo real con existencia propia sobre el cual se desea guardar información (ej. Socio, Libro, Cliente).
> 2. **Atributo:** Característica que describe a una entidad (ej. el nombre de un socio o el porcentaje de un cupón).
> 3. **Vigencia:** Propiedad de un dato o regla que determina si es aplicable en un momento determinado (crucial para cupones y promociones).
> 
> ## 3. Desarrollo del Tema: La Evolución del Análisis
> 
> ### El Flujo de Decisiones en E-Commerce
> 
> El análisis comienza identificando los caminos lógicos que toma un proceso. En un sistema de ventas con descuentos, el sistema debe evaluar condiciones sucesivas:
> 
> - **Identificación del tipo de cliente:** ¿Es un cliente corporativo?
> - **Aplicación de beneficios:** Si es corporativo, se aplica un descuento específico.
> - **Gestión de cupones:** Si no es corporativo (o incluso si lo es, dependiendo de la regla), se evalúa la existencia de un cupón.
> 
> ### La Transición de la Lógica a los Datos
> 
> Una vez definido el flujo, surge la pregunta crítica: **¿De dónde salen los datos?** Para que un sistema valide si un cupón es vigente o qué porcentaje representa un código, no basta con la lógica del flujograma. Se requiere una estructura de datos (DER) que soporte esa información. Por ejemplo, la entidad "Cupón" debe tener atributos como `fecha_inicio`, `fecha_fin`, `estado` (activo/inactivo) y `valor_descuento`.
> 
> ### Relaciones entre Conceptos
> 
> La conexión entre las ideas se establece de la siguiente manera:
> 
> 1. El **Flujograma** define _cómo_ se procesa la información.
> 2. Las **Reglas de Negocio** definen los _límites_ de ese proceso.
> 3. El **DER** define _dónde_ reside la información necesaria para ejecutar dicho proceso.
> 
> **Resumen Parcial:** El diseño de un sistema es un proceso iterativo. Un flujograma incompleto o con ambigüedades (como no saber si los descuentos son acumulables) impide la creación de un modelo de datos robusto.
> 
> ## 4. Ejemplos Prácticos
> 
> ### Caso 1: Reglas de Descuento en E-Commerce
> 
> Imaginemos un escenario donde un cliente puede tener un descuento por ser "Corporativo" y, además, poseer un "Cupón de Descuento".
> 
> - **Problema:** El requerimiento inicial no define qué hacer si se cumplen ambas condiciones.
> - **Solución Propuesta:** Aplicar el descuento mayor (no acumulativo).
> - **Lógica en el Sistema:**
>     1. Validar si es corporativo.
>     2. Validar si el cupón está vigente.
>     3. Comparar ambos valores de descuento.
>     4. Aplicar el valor máximo al precio final.
> 
> ### Caso 2: Sistema de Biblioteca
> 
> Para modelar los datos de una biblioteca, se identifican tres entidades base:
> 
> 1. **Socio:** Personas que acceden al préstamo (pueden ser alumnos o profesores).
> 2. **Libro:** El inventario disponible para préstamo.
> 3. **Reserva/Préstamo:** La entidad que vincula al socio con el libro, registrando fechas de entrega y devolución.
> 
> ## 5. Errores Comunes y Confusiones
> 
> - **Asumir Reglas de Negocio:** Uno de los errores más graves es definir una solución técnica (como la acumulación de descuentos) sin haber consultado al cliente. Siempre se debe documentar la duda y resolverla en una segunda entrevista.
> - **Omitir Validaciones de Vigencia:** En el diseño de flujogramas, a menudo se olvida preguntar si un cupón ha expirado o si hay stock suficiente. Estas son "trampas" comunes en el análisis inicial.
> - **Confundir Flujo con Datos:** Creer que el flujograma es suficiente para empezar a programar. Sin un DER bien definido, el programador no sabrá en qué tabla de la base de datos buscar el porcentaje del cupón.
> 
> ## 6. Síntesis y Conclusiones
> 
> - **Análisis Exhaustivo:** Antes de realizar el diagrama final, todas las preguntas de negocio (reglas) deben estar respondidas por el cliente.
> - **Modelado Estructurado:** El paso del flujograma al DER es esencial para dar soporte a la lógica de programación.
> - **Flexibilidad:** Las soluciones pueden variar según el negocio; no hay un único diagrama "correcto", sino soluciones que se adaptan mejor o peor a las necesidades del cliente.
> 
> ## 7. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la función principal de un flujograma en el análisis de sistemas?
> 2. ¿Qué es una regla de negocio y por qué es importante antes de diseñar el DER?
> 
> ### Nivel Intermedio
> 
> 1. En un sistema de descuentos, ¿por qué es necesario validar la vigencia de un cupón antes de obtener su porcentaje?
> 2. Si un cliente no define si dos descuentos son acumulables, ¿cuál debe ser el proceder del analista?
> 
> ### Nivel Avanzado
> 
> 1. Explique cómo la pregunta "¿De dónde salen los datos?" facilita la transición de un diagrama de flujo a un diagrama de entidad-relación.
> 2. Diseñe una estructura de atributos mínima para una entidad "Reserva" en un sistema de biblioteca para asegurar que se pueda rastrear la devolución de un libro.
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> A continuación, se detallan las indicaciones administrativas y organizativas relevantes para el curso, derivadas de las comunicaciones actuales:
> 
>
>
> |Evento / Aviso|Fecha|Descripción Detallada|
> |---|---|---|
> |**Entrega de Actividad 1**|Pendiente (Reapertura)|Debido a problemas técnicos en la plataforma (bloqueos y links caídos), la entrega se habilitará nuevamente sin penalidad por mora.|
> |**Organización de Grupos**|Inmediata|Los estudiantes deben completar la planilla de Excel compartida con Apellido, Nombre y el número de grupo elegido (1, 2, 3 o 4).|
> |**Formato Institucional**|Próximamente|Se entregará un archivo modelo con la marca de la institución para que todas las entregas futuras cumplan con el marco institucional.|
> |**Práctica Actual (DER)**|En curso|Cada grupo debe utilizar herramientas como **[Draw.io](http://Draw.io)** para elaborar el DER del flujo de e-commerce y descuentos analizado en clase.|
> 
> **Advertencia Académica:**
> 
> - **Plataforma Virtual:** Se han detectado fallos recurrentes en el acceso y descarga de materiales. Existe flexibilidad por parte de la cátedra respecto a los plazos de entrega mientras duren estos inconvenientes.
> - **Registro de Entregas:** Es obligatorio subir los trabajos a la plataforma una vez se regularice el acceso, ya que esto constituye el registro oficial requerido al finalizar la cursada.
> - **Contenido Desactualizado:** El profesor aclaró que algunos materiales visualizados inicialmente en la "Clase 1" pertenecían al curso anterior por un error de copia; no deben ser tomados en cuenta si generan contradicción.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 2 (07 04 26) - Desarrollo de sistemas orientado a la gestión" src="https://www.youtube.com/embed/D0no7YAVpl8?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1ppZZm16uyDtOOqOkaZk0D74e0bqZ4CoX/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1N7wh4Sb-DE_5gVrgE2cOwZ5JTDCq7QpS/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>