---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/4-administracion-de-base-de-datos/clase-3-viernes-04-de-abril-de-2025-04-04-25-administracion-de-base-de-datos/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio Completa: Administración de Bases de Datos - Modelo Entidad-Relación
> 
> Este documento constituye un material de estudio exhaustivo sobre la Unidad 2 de la asignatura, centrándose en el **Modelo Entidad-Relación (MER)**. Provee las bases teóricas, simbología técnica, aplicaciones prácticas y pautas administrativas necesarias para el dominio del diseño conceptual de bases de datos.
> 
> ## 1. Introducción al Modelado de Datos
> 
> El diseño de una base de datos comienza con la **abstracción**. Los modelos son elementos que permiten una aproximación inicial al diseño, funcionando como una representación conceptual antes de avanzar hacia el esquema lógico y la implementación física en un motor de base de datos.
> 
> ### Contexto e Importancia
> 
> El Modelo Entidad-Relación (MER), o _Entity Relationship Model_, fue desarrollado por **Peter Chen en 1976**. Es clasificado como un **modelo semántico**, ya que su objetivo principal es capturar el significado de los datos y las interrelaciones dentro de un "universo de realidad observada". Un diagrama conceptual bien construido es la base fundamental para el éxito de las etapas posteriores (diagrama lógico y base de datos física).
> 
> ## 2. Marco Conceptual: Componentes del Modelo
> 
> El MER se basa en la identificación de entidades y las conexiones (relaciones) entre ellas, describiendo sus características mediante atributos.
> 
> ### A. Entidades
> 
> Se definen como elementos claramente identificables dentro del contexto (ej. Alumno, Profesor, Materia).
> 
> - **Regla de Oro:** Las entidades siempre se nombran en **singular**.
> - **Entidad Fuerte:** Existe por sí misma dentro del universo observado.
> - **Entidad Débil:** Su existencia depende de otra entidad. No puede existir de forma aislada en el contexto dado.
>     - _Ejemplos:_ Un "Departamento" es una entidad débil que depende de un "Edificio" (fuerte). Un "Tipo de Usuario" depende de la existencia de un "Usuario".
> 
> ### B. Atributos (Propiedades)
> 
> Son las características que describen a una entidad.
> 
> - **Simple:** Un valor atómico e indivisible.
> - **Compuesto:** Se puede desglosar en propiedades más simples (ej. "Nombre Completo" compuesto por "Nombre" y "Apellido").
> - **Clave (Atributo Principal):** Es un valor único que identifica unívocamente a cada ejemplar de la entidad (ej. DNI, Legajo, ID). En el diagrama, el nombre del atributo va **subrayado**.
> - **Multivaluado:** Puede tener múltiples valores para una misma entidad (ej. las materias que dicta un profesor). Se representa con doble línea.
> - **Univaluado:** Posee un único valor (ej. un profesor en una comisión específica).
> - **Nulo:** Atributo que puede o no tener un valor asignado (ej. un proyecto de investigación opcional).
> - **Derivado:** No se almacena físicamente en la base de datos; se calcula a partir de un **Atributo Base**.
>     - _Ejemplo clásico:_ La "Fecha de Nacimiento" es el atributo base (se guarda), mientras que la "Edad" es el atributo derivado (se calcula y no se persiste porque cambia con el tiempo).
> 
> ### C. Relaciones
> 
> Es el vínculo que une a dos o más entidades. Se representa con un rombo y debe contener un **verbo** que describa la acción. Es recomendable utilizar dos verbos para indicar la dirección de la relación (ida y vuelta).
> 
> ## 3. Simbología Técnica del MER
> 
> Para la construcción de diagramas (utilizando herramientas como _Draw.io_), se debe respetar la siguiente convención gráfica:
> 
> |   |   |
> |---|---|
> |Elemento|Representación Gráfica|
> |**Entidad Fuerte**|Rectángulo simple|
> |**Entidad Débil**|Doble rectángulo|
> |**Relación**|Rombo simple (con verbo)|
> |**Relación Débil**|Doble rombo (vínculo entre entidades débiles)|
> |**Atributo Común**|Óvalo simple|
> |**Atributo Clave**|Óvalo con texto subrayado|
> |**Atributo Multivaluado**|Óvalo con doble línea|
> |**Atributo Derivado**|Óvalo con línea punteada|
> |**Atributo Compuesto**|Óvalo conectado a otros óvalos simples|
> 
> ## 4. Cardinalidades
> 
> La cardinalidad define cuántas instancias de una entidad se asocian con cuántas instancias de otra.
> 
> 1. **Uno a Uno (1:1):** Un individuo se relaciona con un solo elemento (ej. un inquilino vive en un solo departamento).
> 2. **Uno a Muchos (1:N):** Una entidad se relaciona con varias (ej. un propietario posee varios departamentos).
> 3. **Muchos a Uno (N:1):** Muchos elementos se relacionan con uno solo (ej. muchos alumnos asisten a un mismo curso; muchos alumnos realizan un único Trabajo Práctico).
> 4. **Muchos a Muchos (N:M):** Múltiples instancias se relacionan con múltiples instancias (ej. muchos profesores dictan muchas materias).
> 
> ## 5. Casos Prácticos y Aplicación
> 
> ### Ejemplo: Sistema de Préstamos
> 
> - **Entidades:** Prestador (Fuerte), Deudor (Fuerte).
> - **Atributos:** El Prestador tiene un ID (Clave) y Nombre Completo (Compuesto). El préstamo tiene un "Importe a devolver" (Derivado del interés y plazo).
> - **Relación:** El Prestador _otorga_ un Préstamo al Deudor.
> - **Nota de Diseño:** Cuando una entidad surge de una relación (como "Préstamo"), en el diagrama lógico posterior suele convertirse en una **tabla intermedia**.
> 
> ### Ejemplo: Torneo de Ciclismo (Análisis de Requerimientos)
> 
> - **Entidades identificadas:** Ciclista, Equipo, Prueba.
> - **Atributos Clave:** ID de ciclista, Nombre de equipo.
> - **Atributos Derivados:** El "Ganador de la prueba" es un dato que se deriva de los resultados de la competencia.
> - **Sugerencia de Diseño:** La "Nacionalidad" puede tratarse como una entidad débil para evitar redundancia entre ciclistas y equipos de un mismo país.
> 
> ## 6. Errores Comunes y Aclaraciones Didácticas
> 
> - **Confusión entre Datos y Atributos:** Un error frecuente es incluir los datos (ej. "Pizza de Muzarella") como si fueran entidades o atributos. El atributo es "Sabor", el dato es "Muzarella". Los datos no se grafican en el MER.
> - **Pluralización:** No se debe nombrar entidades como "Profesores" o "Alumnos". El estándar académico exige el singular: **Profesor**, **Alumno**.
> - **Omisión de Verbos:** Es un error grave no incluir el verbo dentro del rombo de relación. El verbo define la semántica del modelo.
> - **Atributos Derivados Persistidos:** No se debe marcar como atributo base algo que cambia constantemente o es calculable (como la edad).
> 
> ## 7. Fechas Importantes y Avisos Académicos
> 
> Basado en el análisis de las fuentes, se establecen los siguientes hitos y recordatorios:
> 
> |   |   |   |
> |---|---|---|
> |Evento|Fecha / Plazo|Descripción Detallada|
> |**Entrega TP 1**|Próximo Martes (23:50 hs)|Diagramas de Entidad-Relación grupales.|
> |**Entrega TP 2**|Siguiente Martes (23:50 hs)|Continuación del modelado de datos.|
> |**Parcial Individual**|A confirmar (post TP2)|Examen teórico-práctico presencial. Incluye temas de las unidades vistas y ejercicios de diagramación (MER o DLR).|
> |**TP Integrador**|Final de cuatrimestre|Trabajo grupal (mismo grupo del TP1). Incluye MER, DLR y consultas SQL. **Recupera el parcial**.|
> 
> **Avisos Académicos Importantes:**
> 
> 1. **Metodología de Evaluación:** La nota final será la más alta entre el promedio de la cursada y la nota del TP Integrador.
> 2. **Asistencia:** Se lleva un registro estricto (0.77 puntos por presente). La asistencia perfecta suma 10 puntos a la nota conceptual.
> 3. **Grupos:** Los grupos formados para el TP1 se mantienen fijos hasta el final del cuatrimestre para el TP Integrador.
> 4. **Entrega de Trabajos:** Se deben subir a la plataforma en formato PDF. Se recomienda incluir el **link de editor de Draw.io** (configurado como "Cualquier persona con el enlace - Editor") y nombrar el archivo con el **Número de Grupo**.
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia principal entre una entidad fuerte y una débil?
> 2. ¿Por qué las entidades deben nombrarse en singular?
> 3. ¿Qué símbolo representa un atributo clave y qué característica visual tiene su texto?
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia entre un atributo base y uno derivado mediante un ejemplo original.
> 5. En una relación 1:N entre "Instituto" y "Sucursal", ¿dónde se ubica el "1" y dónde la "N"?
> 6. ¿Cuándo se utiliza un doble rombo en un diagrama?
> 
> ### Nivel Avanzado
> 
> 7. Dado un contexto donde un profesor solo puede dar clases si tiene un turno asignado y pertenece a una sucursal, ¿cómo modelaría la relación entre Profesor, Curso y Turno para evitar inconsistencias?
> 8. ¿Por qué el MER se considera un modelo semántico y en qué se diferencia del diseño físico de la base de datos?

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 3 - Administración de base de datos" src="https://www.youtube.com/embed/ZdvMI2wBamA?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1RN0D4ygE6I_35glCwkm4N0k2bXz3drRK/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1GA-C80FCrmeP8TwjNctsz-xVCAA5HWAq/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>