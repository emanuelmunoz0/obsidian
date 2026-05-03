---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/3-desarrollo-de-sistemas-orientado-a-la-gestion/clase-3-martes-14-de-abril-de-2026-14-04-26-desarrollo-de-sistemas-orientado-a-la-gestion/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Desarrollo de Sistemas Orientado a la Gestión: De la Planificación al Código y Control de Versiones
> 
> Este documento constituye una guía académica integral basada en los contenidos de la Clase 3 del curso. El objetivo es proporcionar una base sólida para la transición entre el diseño conceptual de un negocio y su implementación técnica mediante programación orientada a objetos y herramientas de colaboración profesional.
> 
> ## 1. Introducción General
> 
> El desarrollo de un sistema de gestión sigue un proceso evolutivo y lógico. Tras haber definido las reglas de negocio y los procesos principales (flujograma) y haber estructurado los datos mediante un Diagrama Entidad-Relación (DER), el siguiente paso crítico es la **traducción a código**.
> 
> Este proceso implica transformar entidades abstractas en componentes funcionales (clases en JavaScript) que no solo almacenen información, sino que también ejecuten la lógica financiera y operativa del negocio, como el cálculo de impuestos, la aplicación de descuentos y la validación de inventarios.
> 
> ## 2. Marco Conceptual y Definición de Conceptos Clave
> 
> Para abordar la codificación de sistemas de gestión, es fundamental dominar los siguientes términos:
> 
> - **Entidad:** Representación de un objeto del mundo real (como una "Orden" o un "Producto") que se traduce en una tabla en la base de datos y en una clase en el código.
> - **Mapeo de Componentes:** El proceso de transformar las tablas y relaciones del DER en esqueletos de clases de programación.
> - **Clase (JavaScript):** Plantilla para crear objetos que encapsulan datos (propiedades) y comportamientos (métodos).
> - **Constructor:** Función especial dentro de una clase que se encarga de inicializar los atributos de un objeto al momento de su creación.
> - `this`**:** Palabra clave que hace referencia a la instancia específica de la clase sobre la cual se está trabajando.
> - **Clave Primaria (PK):** Identificador único de un registro o instancia.
> - **Clave Foránea (FK):** Referencia a la clave primaria de otra entidad para establecer una relación.
> - **Instancia:** Un objeto específico creado a partir de una clase (ej. la "Orden #105" es una instancia de la clase "Orden").
> 
> ## 3. Desarrollo del Tema: Traducción del DER a Código
> 
> La construcción de las clases debe seguir un orden jerárquico y de mejores prácticas para garantizar la integridad de los datos.
> 
> ### Estructura Sugerida de una Entidad en Código
> 
> Al definir una clase, los atributos deben organizarse de la siguiente manera:
> 
> 1. **Claves Primarias (PK):** Definidas generalmente como parámetros en el constructor.
> 2. **Claves Foráneas (FK):** Referencias a otras entidades.
> 3. **Datos Propios:** Nombres, montos, descripciones.
> 4. **Estados de Control:** Banderas que indican la situación del objeto (ej. Orden: "emitida", "procesada", "rechazada").
> 5. **Datos de Auditoría:** Información sobre cuándo y quién creó o modificó el registro (fecha de creación, usuario, etc.).
> 
> ### El Patrón Cabecera-Detalle
> 
> Este es el núcleo de la mayoría de las transacciones comerciales (como tickets o facturas). Se entiende como una **unidad transaccional única** dividida en dos niveles:
> 
> - **Cabecera (Maestro):** Contiene datos globales de la transacción. Ejemplo: folio, ID del cliente, fecha, subtotal global, impuestos y descuentos totales.
> - **Detalle (Líneas):** Contiene la información específica de cada artículo comprado. Ejemplo: ID del producto, cantidad y precio unitario.
> 
> ### La Importancia del "Precio Histórico" (La Foto del Precio)
> 
> Un error crítico es no registrar el precio en el detalle de la orden. Los precios de los productos son volátiles (debido a inflación o cambios de política).
> 
> - **Regla de Oro:** En el momento de la venta, se debe guardar una "foto" del precio vigente. Si un producto vale $1000 hoy y sube a $1500 la próxima semana, la factura de hoy debe mantener los $1000 para reflejar la realidad financiera de la transacción original.
> 
> ## 4. Relaciones entre Conceptos y Modelado
> 
> En JavaScript, las relaciones definidas en el DER se modelan mediante la asignación de objetos o arreglos:
> 
> |Tipo de Relación|Implementación en Código|Ejemplo|
> |---|---|---|
> |**1 a N (Uno a Muchos)**|Se utiliza un **Arreglo (Array)**.|`this.lineasDetalle = []` (Una orden tiene muchas líneas).|
> |**N a 1 (Muchos a Uno)**|Se hace una **referencia directa al objeto**.|`this.cliente = objetoCliente` (Muchas órdenes pertenecen a un cliente).|
> 
> ### Lógica de Negocio y Reglas Mutuamente Excluyentes
> 
> El código debe validar el flujo definido. Por ejemplo, si una regla de negocio establece que los descuentos por "Cliente Corporativo" y por "Cupón" son **mutuamente excluyentes**, el sistema no debe evaluar el cupón si ya detectó que el cliente es corporativo. Esto optimiza el procesamiento y evita errores en el cálculo final.
> 
> ## 5. Ejemplos Prácticos: Flujo de Ejecución de Cálculos
> 
> Para cerrar una orden de venta, el sistema sigue este orden lógico paso a paso:
> 
> 1. **Instanciación:** Se crean los objetos de cliente y productos.
> 2. **Carga de Detalle:** Se agregan productos al arreglo de líneas (instancias de `OrdenDetalle`).
> 3. **Sumatoria:** Se calcula el total sumando cada línea del detalle.
> 4. **Validación de Reglas:**
>     - ¿Hay stock suficiente? (Si no, se detiene o marca error).
>     - ¿El cupón es válido y vigente?
> 5. **Aplicación de Descuentos/Impuestos:** Se aplican de forma global sobre la sumatoria si las condiciones se cumplen.
> 6. **Cierre:** Se muestra en consola el precio base, el descuento aplicado, el IVA y el total final.
> 
> ## 6. Errores Comunes y Confusiones
> 
> - **Descuentos mal aplicados:** Aplicar descuentos ítem por ítem cuando la regla de negocio define que el descuento es global (sobre la cabecera).
> - **Uso de Visual Studio vs. Visual Studio Code:**
>     - _Visual Studio:_ Es un IDE pesado, propietario de Microsoft, orientado principalmente al framework .NET.
>     - _Visual Studio Code (VSC):_ Es un editor de texto "vitaminizado", liviano, de código abierto (open source) y extensible mediante plugins. Es el estándar para desarrollo basado en componentes y JavaScript.
> - **No usar Git para control de versiones:** Intentar gestionar cambios mediante copias manuales de archivos ("final", "final_v2"), lo cual genera caos y pérdida de información.
> 
> ## 7. Sistemas de Control de Versiones: Git y GitHub
> 
> Para el trabajo colaborativo, es indispensable separar la herramienta del servicio:
> 
> - **Git:** Es el motor de control de versiones que se instala localmente. Rastrea cambios en los archivos.
> - **GitHub:** Es una plataforma en la nube (propiedad de Microsoft) donde se alojan los repositorios para que el equipo pueda sincronizarlos. (Alternativa libre: GitLab).
> 
> ### Comandos Esenciales de Git
> 
> |Comando|Función|
> |---|---|
> |`git add .`|Agrega los cambios de la carpeta al área de preparación (stage).|
> |`git commit -m "mensaje"`|Confirma los cambios en el repositorio local con un comentario descriptivo.|
> |`git push`|Sube los cambios confirmados desde el local a la nube (GitHub).|
> |`git pull`|Descarga y sincroniza los cambios de la nube al equipo local.|
> 
> ## 8. Síntesis y Conclusiones
> 
> El desarrollo profesional de sistemas requiere una transición ordenada del diagrama al código. La clave del éxito reside en:
> 
> 1. **Fidelidad al DER:** Respetar las claves primarias y foráneas en los constructores de las clases.
> 2. **Integridad de Datos:** Capturar "fotos" de precios y estados en el momento de la transacción.
> 3. **Colaboración:** Utilizar Git y GitHub siguiendo convenciones de nombres para que todo el equipo trabaje sobre la misma base de código de forma sincronizada.
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 4. ¿Cuál es la diferencia principal entre Visual Studio y Visual Studio Code?
> 5. ¿Qué función cumple el constructor en una clase de JavaScript?
> 6. ¿Para qué sirve el comando `git add`?
> 
> ### Nivel Intermedio
> 
> 7. Explique por qué es necesario registrar el precio del producto en la entidad "Detalle de Orden" y no solo referenciarlo desde la entidad "Producto".
> 8. ¿Cómo se modela una relación de 1 a N en JavaScript?
> 
> ### Nivel Avanzado
> 
> 9. En un sistema donde los descuentos corporativos y los cupones son mutuamente excluyentes, ¿cómo debería estructurarse la lógica de validación para optimizar el código?
> 10. Describa el ciclo de vida completo de un cambio en el código, desde que se edita en el directorio de trabajo hasta que está disponible para el resto del equipo en GitHub.
> 
> ## 10. Fechas importantes y avisos académicos
> 
> Basado en las instrucciones del docente durante la sesión:
> 
> - **Entrega de Clase 3 (Vigente):**
>     - **Contenido:** Traducción del DER corregido a clases de JavaScript y configuración del repositorio.
>     - **Formato de entrega:** No pegar el código en el documento; se debe incluir únicamente el **link al repositorio público de GitHub**.
>     - **Requisito de Grupo:** Solo una persona por grupo realiza la entrega, pero todos deben tener acceso y sincronización con el repositorio.
> - **Correcciones Pendientes:**
>     - Aquellos grupos que recibieron devoluciones sobre el flujograma (Clase 1) o el DER (Clase 2) deben aplicar las correcciones directamente en la entrega de la Clase 3. La evaluación es incremental.
> - **Plazos:**
>     - Se han "corrido" las fechas de entregas anteriores para aquellos alumnos que tuvieron problemas de carga o vencimiento en la plataforma.
>     - Se recomienda tener Git instalado y configurado para la próxima semana (aunque no es obligatorio finalizar toda la carga de código el mismo día de la clase).
> - **Material de Apoyo:** El docente subió al aula virtual el PowerPoint de la clase y un anexo específico sobre el uso de Git y GitHub.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 3 (14 04 26) - Desarrollo de sistemas orientado a la gestión" src="https://www.youtube.com/embed/scucxAf4NYo?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1zcQcd73zdNMvI5ZuQCRVMzOuKG7SNuTL/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1uSn1DsbFCxytSEJXmCoJgZSTuukGEbpG/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>