---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/4-administracion-de-base-de-datos/clase-5-viernes-25-de-abril-de-2025-25-04-25-administracion-de-base-de-datos/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía Integral de Normalización de Bases de Datos Relacionales
> 
> Este documento constituye un material de estudio exhaustivo sobre la metodología de normalización de bases de datos, basada en los principios de diseño relacional para garantizar la integridad, eficiencia y escalabilidad de los datos.
> 
> ## 1. Introducción y Contexto
> 
> La **normalización** es un término que deriva de la metodología utilizada para evitar la redundancia de datos y facilitar tanto el acceso como la actualización de la información. Esta metodología fue enunciada originalmente por E.F. Codd y consiste en un conjunto de reglas denominadas **Formas Normales (FN)**.
> 
> Aunque existen hasta cinco formas normales, además de la forma normal de Boyce-Codd, en la práctica profesional y técnica se suele llegar hasta la **Tercera Forma Normal (3FN)**, ya que las etapas posteriores suelen considerarse improcedentes o excesivamente complejas para la mayoría de los casos de uso reales.
> 
> ### Importancia y Relevancia
> 
> La aplicación de las formas normales permite cumplir con los fundamentos teóricos del manejo de bases de datos relacionales, asegurando que:
> 
> - Se elimine la redundancia innecesaria.
> - Se proteja la integridad de los datos.
> - Se optimice el rendimiento en las consultas y actualizaciones.
> 
> ## 2. Marco Conceptual y Definiciones Clave
> 
> Para comprender la normalización, es fundamental manejar los siguientes conceptos:
> 
> - **Atributo:** Cada una de las columnas de una tabla que representan características de una entidad.
> - **Clave Primaria (PK):** Un atributo (o conjunto de ellos) que identifica de forma única a una fila. Para que un atributo sea clave primaria, el resto de los atributos de la relación deben depender funcional y únicamente de él.
> - **Clave Compuesta:** Clave primaria formada por más de un atributo. Se utiliza cuando un solo dato no basta para garantizar la unicidad (por ejemplo, Número de Factura + Código de Producto).
> - **Dependencia Funcional:** Se dice que un atributo depende funcionalmente de otro cuando el valor del primero está determinado por el valor del segundo.
> - **Transitividad:** Propiedad por la cual, para que una relación alcance un nivel de normalización superior, debe haber cumplido necesariamente los niveles anteriores (ej. para estar en 3FN, debe estar antes en 2FN y 1FN).
> 
> ## 3. Desarrollo de las Formas Normales
> 
> La normalización se realiza de manera progresiva mediante el siguiente proceso:
> 
> ### Primera Forma Normal (1FN)
> 
> Establece que una tabla debe tener un **valor único en cada celda** y no debe haber grupos repetitivos de valores dentro de una sola fila.
> 
> - **Regla:** Cada celda debe contener un solo valor atómico.
> - **Problema habitual:** Tablas donde en una misma fila se repiten datos como número de factura, cliente y fecha para listar distintos productos.
> 
> ### Segunda Forma Normal (2FN)
> 
> Para alcanzar la 2FN, la tabla debe estar primero en 1FN y cumplir que **todos los atributos que no son clave dependan funcionalmente de la clave primaria completa**.
> 
> - **Aplicación en Claves Compuestas:** Si una tabla tiene una clave compuesta (Atributo A + Atributo B), un atributo no puede depender solo del Atributo A. Si eso ocurre, ese atributo debe trasladarse a una nueva tabla.
> - **Caso del Precio:** El precio unitario puede depender de la clave completa (Factura + Producto) si el negocio requiere registrar el precio al momento de la venta debido a la inflación o cambios frecuentes (reglas de negocio).
> 
> ### Tercera Forma Normal (3FN)
> 
> Una relación está en 3FN si está en 2FN y **todos los atributos no clave dependen de manera no transitiva de la clave primaria**.
> 
> - **Explicación:** Un atributo no clave no puede depender de otro atributo no clave.
> - **Ejemplo:** En una tabla de ventas, el "Nombre del Cliente" depende del "Código de Cliente", no directamente del "Número de Factura". Por lo tanto, los datos del cliente deben ir a una tabla independiente.
> 
> ## 4. Ejemplo Práctico: Caso "Ventas"
> 
> A continuación, se detalla el proceso de transformación de una tabla única (desnormalizada) hacia la 3FN.
> 
> ### Estado Inicial (Tabla de Ventas Única)
> 
> Atributos: `Nro_Factura`, `Cod_Producto`, `Desc_Producto`, `Precio_Unitario`, `Cantidad`, `Cod_Cliente`, `Nombre_Cliente`, `Fecha`, `Domicilio_Cliente`.
> 
> - **Problema:** Redundancia masiva de datos del cliente y la factura por cada producto vendido.
> 
> ### Paso 1: Hacia la 1FN
> 
> Se separan los grupos repetitivos. Se crea una tabla de **Detalle Venta**.
> 
> - **Tabla Venta:** `Nro_Factura` (PK), `Cod_Cliente`, `Nombre_Cliente`, `Fecha`, `Domicilio_Cliente`.
> - **Tabla Detalle Venta:** `Nro_Factura` (PK compuesta), `Cod_Producto` (PK compuesta), `Desc_Producto`, `Precio_Unitario`, `Cantidad`.
> 
> ### Paso 2: Hacia la 2FN
> 
> Se analiza la dependencia en el detalle. La descripción del producto depende del código de producto, no de la factura.
> 
> - **Nueva Tabla Producto:** `Cod_Producto` (PK), `Desc_Producto`.
> - En **Detalle Venta** solo quedan: `Nro_Factura`, `Cod_Producto`, `Precio_Unitario` y `Cantidad`.
> 
> ### Paso 3: Hacia la 3FN (Estado Final)
> 
> Se analiza la tabla Venta. El nombre y domicilio del cliente dependen del Código de Cliente, no del número de factura.
> 
> - **Nueva Tabla Cliente:** `Cod_Cliente` (PK), `Nombre_Cliente`, `Domicilio_Cliente`.
> - **Tabla Venta Final:** `Nro_Factura` (PK), `Cod_Cliente` (FK), `Fecha`.
> 
> |   |   |
> |---|---|
> |Tabla|Atributos Principales|
> |**Venta**|Nro_Factura (PK), Cod_Cliente (FK), Fecha|
> |**Detalle_Venta**|Nro_Factura (PK/FK), Cod_Producto (PK/FK), Cantidad, Precio|
> |**Producto**|Cod_Producto (PK), Desc_Producto|
> |**Cliente**|Cod_Cliente (PK), Nombre_Cliente, Domicilio|
> 
> ## 5. Integridad y Desnormalización
> 
> ### Integridad Referencial
> 
> Para que un modelo sea íntegro, debe cumplir:
> 
> 1. **No Nulidad:** Las claves primarias no pueden ser nulas.
> 2. **Coincidencia de Claves:** No pueden existir claves foráneas que no coincidan con una clave primaria existente. Por ejemplo, no se puede realizar una venta a un cliente que no ha sido dado de alta previamente.
> 3. **Consistencia de Tipos:** Los campos relacionados deben tener el mismo tipo de dato (ej. Varchar con Varchar, Integer con Integer).
> 
> ### Desnormalización
> 
> Existen casos excepcionales donde se decide, intencionalmente, no normalizar al 100% para ganar rendimiento (**performance**) o simplificar la lógica de negocio.
> 
> - **Ejemplo:** En un sitio web bilingüe, en lugar de crear tablas complejas de idiomas con múltiples relaciones, se puede optar por repetir campos (campo_español, campo_ingles) en la misma tabla para agilizar las consultas (Queries).
> 
> ## 6. Síntesis y Conclusiones
> 
> - La normalización es un proceso **reversible**; se puede volver atrás, pero si se pierden datos en el proceso, significa que la normalización original fue incorrecta.
> - El objetivo final es que **cada dato esté en su lugar correspondiente** y nada esté repetido innecesariamente.
> - La **regla de negocio** define aspectos críticos, como la ubicación del precio (en Producto si es fijo, o en Detalle de Venta si es variable).
> 
> ## 7. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es el objetivo principal de la normalización?
> 2. ¿Qué significa que un valor sea "atómico" en la 1FN?
> 3. ¿Qué sucede con la integridad si una clave primaria contiene un valor nulo?
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia entre una clave primaria simple y una compuesta.
> 5. ¿Por qué es necesario pasar por la 2FN antes de llegar a la 3FN?
> 6. ¿En qué casos el precio de un producto debería estar en la tabla "Detalle de Venta" y no en "Producto"?
> 
> ### Nivel Avanzado
> 
> 7. Defina el concepto de "Integridad Referencial" y dé un ejemplo de su incumplimiento.
> 8. Analice un escenario donde la desnormalización sea preferible sobre la normalización total.
> 9. Si un atributo no clave depende de otro atributo no clave, ¿qué forma normal se está violando y cómo se soluciona?
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> A partir del análisis de las fuentes, se identifican las siguientes indicaciones y compromisos académicos:
> 
> ### Calendario y Evaluaciones
> 
> - **Entrega de Trabajo Práctico (Unidad 4):**
>     - **Fecha:** Viernes 2 de mayo.
>     - **Hora:** 13:00 hs.
>     - **Nota:** Se extendió el plazo originalmente previsto (29 de abril) debido al feriado puente.
> - **Examen Parcial:**
>     - **Fecha:** Martes 30 de abril (según contexto de otras materias) / Próximo viernes de clase presencial.
>     - **Horario de inicio:** 18:30 hs (se recomienda puntualidad, ya que el edificio cierra a las 21:00 hs).
>     - **Contenido:** Unidades 1 a 4 inclusive. Incluye teoría y un ejercicio de normalización hasta 3FN.
> 
> ### Indicaciones del Profesor
> 
> - **Metodología del Parcial:** Será escrito. Se evaluará la capacidad de normalizar una tabla (llegar a la 3FN) y preguntas teóricas de desarrollo (no "escribir un libro", pero tampoco respuestas de una sola palabra).
> - **Herramientas para TP:** Se puede utilizar **draw.io** para el Diagrama Lógico Relacional (DLR) o la vista de diseñador de **PHPMyAdmin**. Es obligatorio incluir restricciones, tipos de datos y relaciones.
> - **Recuperatorio:** El examen parcial puede recuperarse mediante la aprobación del **Trabajo Integrador Final**.
> - **Recomendación:** Practicar la claridad de la letra para el examen escrito y revisar los videos de SQL disponibles en la plataforma para después del parcial.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 5 - Administración de base de datos" src="https://www.youtube.com/embed/NRHQJartdY0?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1Pb98N812GuIoQkBsf9PgXW5AGDb_IZBR/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1_2oiXcExHnP9-pObIswfqNHTEVL2vpI6/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>