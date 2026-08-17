---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/4-administracion-de-base-de-datos/clase-7-viernes-23-de-mayo-de-2025-23-05-25-administracion-de-base-de-datos/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio Completa: Administración de Bases de Datos y Modelado Relacional
> 
> Este documento constituye una síntesis exhaustiva de los contenidos académicos y técnicos abordados en la materia, integrando las explicaciones sobre modelado de datos, la gestión del Trabajo Práctico (TP) Integrador y los criterios de evaluación. Funciona como material de estudio principal para la comprensión del diseño de bases de datos relacionales y la transición hacia la culminación del cuatrimestre.
> 
> ## Introducción General
> 
> La administración de bases de datos requiere no solo el conocimiento de lenguajes de consulta como SQL, sino una capacidad analítica profunda para transformar requisitos del mundo real en estructuras lógicas eficientes. El foco de esta etapa de la cursada se centra en la consolidación del modelado relacional a través de diagramas (DER y DLR) y la implementación de consultas complejas, preparándose para el desarrollo de un proyecto integrador que aplique estos conceptos de forma sistémica.
> 
> ## Contexto del Tema
> 
> Debido a contingencias académicas (feriados y ajustes en la plataforma institucional), el programa de este cuatrimestre ha priorizado el dominio del modelo relacional y SQL sobre los temas de bases de datos NoSQL (Unidades 6 y 7), los cuales no serán evaluados en el parcial ni en el trabajo integrador. El objetivo es garantizar que los estudiantes posean una base sólida en el modelo SQL tradicional, que es fundamental para el desarrollo profesional en el área de IT.
> 
> ## Marco Conceptual
> 
> Para abordar el diseño de bases de datos desde cero, es imperativo comprender los siguientes términos y conceptos fundamentales:
> 
> ### Definición de Conceptos Clave
> 
> |   |   |
> |---|---|
> |Concepto|Descripción|
> |**DER (Diagrama Entidad-Relación)**|Representación gráfica conceptual que identifica las entidades (objetos), sus atributos (propiedades) y las relaciones entre ellos.|
> |**DLR (Diagrama Lógico Relacional)**|Evolución del DER donde se definen tablas, claves primarias, claves foráneas y tipos de datos, acercándose a la implementación física.|
> |**Clave Primaria (Primary Key - PK)**|Identificador único para cada registro en una tabla. Se recomienda que sea autoincremental para facilitar la gestión.|
> |**Clave Foránea (Foreign Key - FK)**|Campo en una tabla que se vincula con la clave primaria de otra tabla, permitiendo establecer relaciones.|
> |**Normalización**|Proceso de organizar los datos para reducir la redundancia y mejorar la integridad de la información.|
> |**Tabla Intermedia**|Estructura necesaria para resolver relaciones de "muchos a muchos" (N:N), permitiendo vincular dos entidades mediante sus respectivos IDs.|
> 
> ## Desarrollo del Tema: Modelado y Relaciones
> 
> El proceso de creación de una base de datos sigue un orden lógico: del entendimiento del problema al diagrama, y del diagrama a las tablas.
> 
> ### Relaciones entre Conceptos y Estructuras
> 
> 1. **Relaciones Muchos a Muchos (N:N):** Cuando múltiples registros de una entidad se relacionan con múltiples registros de otra (por ejemplo, muchos profesores pueden enseñar muchas especialidades), es obligatorio crear una **tabla intermedia**.
> 2. **Dependencias de la Tabla Intermedia:** Una tabla intermedia puede contener atributos propios de la relación, como una fecha o un horario.
> 3. **Jerarquía de Datos:** El diseño debe permitir "navegar" la información. Por ejemplo, en un sistema de natación, para saber qué profesor dicta una clase, se debe conectar:
>     - `Alumno` -> `Reserva` -> `Clase` -> `Profesor`.
> 
> ### Reglas Prácticas de Diseño (Buenas Prácticas)
> 
> - **Identificación Visual de Claves:** Una regla mnemotécnica sugerida es colocar el ID a la izquierda si es Clave Primaria (PK) y a la derecha si es Clave Foránea (FK) dentro del diseño, lo que agiliza la lectura de los _Joins_ en las consultas SQL.
> - **Redundancia:** Evitar la duplicación de datos innecesaria. Si un dato puede derivarse de una relación, no debe almacenarse dos veces.
> 
> ## Ejemplos Prácticos: El Caso de la Escuela de Natación
> 
> A través de un ejercicio de modelado para una escuela de natación, se ilustran los pasos de normalización:
> 
> 1. **Entidades Identificadas:** Alumno (Socio), Profesor, Clase, Especialidad y Nivel.
> 2. **Gestión de Reservas:** Se utiliza una tabla intermedia `Reserva` que conecta al `Alumno` con la `Clase`. El atributo clave de esta relación es `fecha_reserva`.
> 3. **Dictado de Clases:** Para evitar estructuras complejas, se puede crear una tabla de `Dictado de Clase` que englobe la relación entre la `Clase`, el `Profesor`, la `Especialidad` y el `Nivel`.
> 
> ### Ejemplo de Consulta SQL (Búsqueda por Fecha)
> 
> Para filtrar registros de un mes específico (ej. mayo de 2025), se utiliza el operador `LIKE` con comodines `%`:
> 
> ```sql
> SELECT * FROM reserva WHERE fecha_reserva LIKE '2025-05%';
> ```
> 
> _Aclaración:_ El orden de los factores (año-mes o mes-año) dependerá de la configuración regional de la base de datos (default es Año-Mes-Día).
> 
> ## Errores Comunes y Confusiones
> 
> - **Uso incorrecto de IDs en Tablas Intermedias:** Un error frecuente es relacionar una entidad con el ID de la tabla intermedia en lugar de hacerlo directamente con la entidad principal. Esto genera "caminos extra" innecesarios y complica las consultas (Inners Joins).
> - **Redundancia en Claves:** No siempre es obligatorio que una tabla intermedia tenga un ID propio (PK) si su única función es relacionar dos tablas mediante FKs, aunque se usa por costumbre para facilitar actualizaciones específicas.
> - **Confusión en la Normalización:** Al pasar de un DER a un DLR, es común olvidar atributos o no identificar correctamente cuándo una relación requiere una tabla nueva. No se debe volver atrás a corregir el DER si se detecta un error en el DLR; es mejor explicar la mejora durante la defensa del proyecto.
> 
> ## Síntesis y Conclusiones
> 
> El éxito en la administración de bases de datos radica en la práctica constante ("culo en silla"). El diseño relacional busca la eficiencia mediante la eliminación de datos redundantes y la correcta vinculación de entidades. El Trabajo Integrador es la instancia final donde se debe demostrar la capacidad de traducir un problema real (como el de ciclismo, natación o patinaje) en un modelo funcional que soporte consultas SQL precisas.
> 
> ## Fechas Importantes y Avisos Académicos
> 
> A continuación, se detallan los hitos críticos para el cierre del cuatrimestre:
> 
> |   |   |   |
> |---|---|---|
> |Fecha|Evento / Actividad|Descripción Detallada|
> |**Próximo Viernes**|Seguimiento Grupal|Revisión obligatoria del DER grupo por grupo. Se ajustarán errores de diseño.|
> |**20 de Junio**|**Feriado Nacional**|Día de la Bandera. No hay actividad académica.|
> |**Próximas Semanas**|Consultas en Crudo|Revisión de DLR y Queries SQL antes de la entrega final.|
> |**4, 5 y 6 de Julio**|**Presentación Final**|Defensa presencial del Trabajo Integrador (DER, DLR y 4+ Queries).|
> 
> **Advertencias Académicas Importantes:**
> 
> - **TP Integrador:** Es un trabajo grupal con defensa individual. Funciona como recuperatorio para quienes reprobaron el parcial (ej. Griselda) o estuvieron ausentes (ej. Lucía).
> - **Promoción:** Se requiere un promedio de 7 o más. La nota del TP Integrador puede reemplazar una nota baja del parcial si el desempeño es superior.
> - **Evaluación de Presentación:** Se valorará la fluidez, el manejo de grupo y la capacidad de "vender" el proyecto técnicamente al profesor (simulando una entrevista laboral/líder técnico).
> - **Asistencia:** Sigue sumando puntos para el promedio final y puede definir redondeos de nota (ej. de 6.60 a 7).
> 
> ## Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia principal entre un DER y un DLR?
> 2. ¿Para qué sirve una Clave Foránea (FK)?
> 3. ¿Cómo se representa una relación de muchos a muchos en una base de datos física?
> 
> ### Nivel Intermedio
> 
> 4. Explique por qué es recomendable que los IDs de las tablas sean autoincrementales.
> 5. En una consulta SQL, ¿cuál es la función del comando `INNER JOIN`?
> 6. Si un profesor da varias clases, ¿en qué tabla debería colocarse la clave foránea del profesor?
> 
> ### Nivel Avanzado (Tipo Examen)
> 
> 7. Dado un sistema donde un Alumno reserva una Clase impartida por un Profesor, diseñe el camino lógico para obtener el nombre del profesor desde el ID del alumno.
> 8. Analice la ventaja de separar la "Especialidad" en una tabla independiente en lugar de tenerla como un campo de texto en la tabla "Profesor".
> 9. ¿Cómo impacta una mala normalización en la performance de las consultas SQL a largo plazo?

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 7 - Administración de base de datos" src="https://www.youtube.com/embed/w8ovw5jN6sg?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/12Wti5Wmi3_PjeZwbx97qTcVbXUiTnAph/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1i0SBmhhs2b2QFiR0hBLjOu5SM7-SrfIl/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>