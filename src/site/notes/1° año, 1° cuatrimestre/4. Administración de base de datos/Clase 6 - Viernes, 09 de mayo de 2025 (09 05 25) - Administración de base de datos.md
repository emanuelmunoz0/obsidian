---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/4-administracion-de-base-de-datos/clase-6-viernes-09-de-mayo-de-2025-09-05-25-administracion-de-base-de-datos/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio: Administración de Bases de Datos y Lenguaje SQL
> 
> Este documento constituye un material de estudio integral basado en la sesión académica sobre administración de bases de datos. Explora desde los fundamentos de los sublenguajes SQL hasta la implementación práctica de bases de datos relacionales, manejo de relaciones y manipulación de datos.
> 
> ## 1. Introducción y Contexto
> 
> La administración de bases de datos se fundamenta en el uso del lenguaje SQL (_Structured Query Language_), el cual permite tanto la definición de estructuras como la manipulación de la información contenida en ellas. En el ámbito académico y profesional, es esencial diferenciar entre la creación de objetos y el manejo de los datos para garantizar la integridad y eficiencia del sistema.
> 
> ## 2. Marco Conceptual: DDL y DML
> 
> Para comprender SQL, es imperativo dividir sus funciones en dos grupos principales de lenguajes:
> 
> ### Data Definition Language (DDL)
> 
> Es el lenguaje de definición de datos. Se utiliza para crear, modificar o eliminar la estructura de los objetos en la base de datos (tablas, índices, bases de datos).
> 
> - **CREATE DATABASE:** Crea una nueva base de datos.
> - **DROP DATABASE:** Elimina una base de datos existente.
> - **CREATE TABLE:** Crea una nueva tabla dentro de una base de datos.
> - **ALTER TABLE:** Modifica la estructura de una tabla ya existente (agregar campos, cambiar tipos de datos).
> - **DROP TABLE:** Elimina una tabla.
> 
> ### Data Manipulation Language (DML)
> 
> Es el lenguaje de manipulación de datos. Permite realizar las operaciones conocidas históricamente como ABM (Altas, Bajas y Modificaciones) o modernamente como **CRUD** (_Create, Read, Update, Delete_).
> 
> |   |   |   |
> |---|---|---|
> |Operación CRUD|Comando SQL|Descripción|
> |**C**reate|`INSERT`|Agrega nuevos registros a una tabla.|
> |**R**ead|`SELECT`|Consulta y recupera datos.|
> |**U**pdate|`UPDATE`|Modifica registros existentes.|
> |**D**elete|`DELETE`|Elimina registros de forma física.|
> 
> ## 3. Desarrollo del Tema: Operaciones y Lógica de Datos
> 
> ### El Concepto de Borrado Lógico
> 
> A diferencia del borrado físico (`DELETE`), el borrado lógico permite "desactivar" un registro sin eliminarlo físicamente de la base de datos, lo cual es vital para auditorías y recuperación de información.
> 
> Existen dos métodos comunes explicados:
> 
> 1. **Campos de Auditoría (Timestamps):** Se añaden campos como `created_at`, `updated_at` y `deleted_at`.
>     - Si `deleted_at` es `NULL`, el registro está vigente.
>     - Si tiene una fecha, el sistema interpreta que el registro fue "borrado" en ese momento.
> 2. **Campo Booleano (Flag de Estado):** Se utiliza un campo llamado `activo` (tipo _boolean_).
>     - `true`: Registro vigente.
>     - `false`: Registro dado de baja.
> 
> ### Creación de Bases de Datos y Tablas
> 
> En entornos como PHPMyAdmin, la creación sigue un flujo lógico:
> 
> - **Cotejamiento:** Se recomienda el uso de `UTF8MB4_GENERAL_CI` para asegurar la compatibilidad con caracteres internacionales y símbolos modernos.
> - **Orden de Creación:** Es fundamental crear primero las tablas que contienen las **Claves Primarias (PK)** antes que las tablas que contienen las **Claves Foráneas (FK)**. Si se intenta crear una relación hacia una tabla que no existe, el sistema devolverá un error.
> 
> ### Relaciones entre Tablas
> 
> Las relaciones permiten conectar entidades (ej. Empleado y Departamento).
> 
> - **Clave Foránea (FK):** Es el campo en una tabla que hace referencia a la Clave Primaria de otra.
> - **Implementación:** Se puede realizar mediante código SQL con `ALTER TABLE` o mediante la interfaz gráfica en la sección "Vista de relaciones" de la estructura de la tabla.
> 
> ## 4. Ejemplos Prácticos y Sintaxis
> 
> ### Inserción de Datos (`INSERT`)
> 
> Para insertar datos, el número de campos debe coincidir con el número de valores proporcionados.
> 
> ```sql
> INSERT INTO empleado (id_empleado, nombre, apellido, email, departamento_id) 
> VALUES (NULL, 'Martín', 'Castro', 'pirulo@gmail.com', 1);
> ```
> 
> _Nota: Si el ID es autoincremental, se puede pasar_ `_NULL_` _o simplemente omitir el campo si se especifican los demás._
> 
> ### Actualización de Datos (`UPDATE`)
> 
> Es crítico utilizar la cláusula `WHERE` para evitar modificar todos los registros de la tabla.
> 
> ```sql
> UPDATE empleado 
> SET departamento_id = 2 
> WHERE id_empleado BETWEEN 3 AND 4;
> ```
> 
> ### Consultas con Filtros y Ordenamiento
> 
> Para encontrar datos específicos, como el empleado con el DNI más alto (o más joven, según la lógica aplicada):
> 
> ```sql
> SELECT nombre, apellido, DNI 
> FROM empleado 
> ORDER BY DNI DESC 
> LIMIT 1;
> ```
> 
> - `ORDER BY ... DESC`: Ordena de mayor a menor.
> - `LIMIT 1`: Devuelve únicamente el primer resultado de la lista ordenada.
> 
> ## 5. Errores Comunes y Aclaraciones
> 
> - **Omisión del WHERE:** Olvidar el `WHERE` en un `UPDATE` o `DELETE` afectará a toda la base de datos de forma irreversible.
> - **Confusión en Alias (AS):** El uso de alias para tablas puede variar según la versión del motor de base de datos. Se recomienda prioridad en alias para nombres de campos en lugar de nombres de tablas si la versión genera errores.
> - **Atributos Derivados:** La **Edad** no debe guardarse en la base de datos; es un atributo derivado que se calcula mediante una consulta SQL a partir de la fecha de nacimiento para mantenerse siempre actualizada.
> - **Cardinalidad:** La cardinalidad (1:1, 1:N, N:N) es una cuestión lógica del diseño (DER/DLR) y no siempre se refleja gráficamente de forma explícita en todas las herramientas de administración, que suelen usar representaciones estándar.
> 
> ## 6. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de las fuentes, se identifican los siguientes hitos académicos:
> 
> - **Examen Parcial:**
>     - **Fecha:** Próximo viernes (reprogramado del viernes actual).
>     - **Descripción:** Evaluación de los contenidos vistos hasta la fecha.
> - **Trabajo Práctico (TP):**
>     - **Indicación:** Se debe entregar el trabajo que incluye el uso de Joins y Alias.
> - **Trabajo Integrador:**
>     - **Estado:** Mencionado como proyecto futuro basado en los modelos que los estudiantes están desarrollando.
> - **Próximas Clases (Estimaciones):**
>     - Tras el parcial, se retomarán los temas de bases de datos relacionales y se dedicará una sesión extensa a **NoSQL**.
> 
> ## 7. Síntesis de Conceptos Clave
> 
> - **DDL:** Crea el "contenedor" (Tablas, Bases de Datos).
> - **DML:** Manipula el "contenido" (Registros, Datos).
> - **Borrado Lógico:** Seguridad de datos mediante estados o fechas de baja.
> - **Integridad Referencial:** Las tablas deben crearse en orden lógico para permitir el enlace de Claves Foráneas.
> - **Consultas Avanzadas:** El uso de `ORDER BY` y `LIMIT` permite emular funciones de búsqueda de máximos y mínimos de forma eficiente.
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia principal entre los comandos DDL y DML?
> 2. ¿Qué comando SQL se utiliza para eliminar una tabla completa?
> 3. ¿Por qué es importante el uso de `UTF8MB4` al crear una base de datos?
> 
> ### Nivel Intermedio
> 
> 4. Explique el concepto de borrado lógico y mencione una ventaja sobre el borrado físico.
> 5. ¿Qué sucede si se ejecuta un comando `DELETE` sin la cláusula `WHERE`?
> 6. ¿Cómo se define una relación entre dos tablas en SQL?
> 
> ### Nivel Avanzado
> 
> 7. Si necesita obtener el registro con la fecha de creación más reciente, ¿cómo combinaría `ORDER BY` y `LIMIT`?
> 8. ¿Por qué la "Edad" se considera un atributo derivado y cómo debería manejarse en una base de datos profesional?
> 9. Describa el impacto de la integridad referencial al intentar insertar una Clave Foránea que no existe en la tabla de referencia.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 6 - Administración de base de datos" src="https://www.youtube.com/embed/i3LJKXsMlJI?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1P2tkmYHvKCTlxIVOToUY9Ga29gIX7YTv/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1O9r_bxXeYBGWwz8yl47P6njRudzaiH88/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>