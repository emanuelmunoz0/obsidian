---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/4-administracion-de-base-de-datos/clase-4-viernes-11-de-abril-de-2025-11-04-25-administracion-de-base-de-datos/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio Integral: Administración de Bases de Datos - Del Modelo Conceptual al Relacional
> 
> Este documento constituye una síntesis exhaustiva de los conceptos fundamentales abordados en la materia, integrando el análisis de modelos conceptuales (DER) y la transición hacia el modelo relacional lógico.
> 
> ## 1. Introducción General
> 
> La administración de bases de datos requiere una transición fluida entre la interpretación de requerimientos del mundo real y su representación técnica. El proceso inicia con el **Modelo Entidad-Relación (DER)**, de carácter conceptual, y progresa hacia el **Modelo Relacional**, donde los datos se organizan en estructuras lógicas de tablas y columnas. La correcta interpretación inicial es crítica; una falla en la comprensión del problema deriva inevitablemente en un modelo técnico deficiente.
> 
> ## 2. Marco Conceptual y Definiciones Clave
> 
> Para entender las bases de datos desde cero, es imperativo dominar la terminología técnica que vincula el álgebra relacional con la práctica informática:
> 
> ### Términos Fundamentales
> 
> - **Relación:** En el contexto relacional, una relación es equivalente a una **Tabla**. Proviene de la teoría matemática de conjuntos.
> - **Tupla:** Representa una fila o un **Registro** dentro de la tabla. Cada tupla es una instancia única de la entidad.
> - **Atributo:** Representa una columna o **Campo**. Define una característica específica de la entidad.
> - **Dominio:** Es el conjunto de todos los valores posibles que puede tomar un atributo en las tuplas de una relación.
> - **Grado:** Se refiere al número total de atributos (columnas) de una relación.
> - **Cardinalidad:** En el modelo relacional, indica el número de tuplas (filas) de la relación.
> 
> ## 3. El Modelo Relacional: Propiedades y Reglas
> 
> El modelo relacional organiza los datos en tablas con propiedades específicas que garantizan la integridad de la información:
> 
> 1. **Independencia del Orden:** Las tuplas (filas) y los atributos (columnas) no poseen un orden definido. La disposición en la que se ingresan los datos no afecta su validez técnica, aunque culturalmente se suela seguir un orden lógico para facilitar la lectura humana.
> 2. **No Existencia de Tuplas Repetidas:** Cada registro debe ser único. No puede haber dos filas idénticas dentro de una misma tabla.
> 3. **Atomicidad de Atributos:** Todos los atributos deben ser atómicos (simples). No se deben guardar listas de valores en un solo campo (por ejemplo, no poner múltiples nombres separados por comas en una sola celda).
> 
> ## 4. Gestión de Claves y Relaciones
> 
> ### Claves Candidatas y Primarias
> 
> La identificación unívoca de cada registro se logra mediante claves:
> 
> - **Clave Candidata:** Cualquier atributo o conjunto de atributos que identifique a la tupla sin ambigüedad.
> - **Clave Primaria (PK):** Es la clave elegida entre las candidatas.
> 
> **Criterios de selección de PK:**
> 
> - **Preferencia Numérica:** Es mejor usar atributos numéricos enteros antes que cadenas de caracteres para optimizar la velocidad de procesamiento.
> - **Longitud Mínima:** Entre dos atributos del mismo tipo, se elige el de menor longitud.
> - **Estabilidad Temporal:** La clave no debe modificarse en el tiempo. Cambiar una clave primaria puede generar la pérdida de históricos y rupturas en las relaciones de la base de datos (ejemplo: usar un apellido como parte de una clave compuesta es riesgoso ante cambios legales o civiles).
> - **Uso de IDs Autoincrementales:** Como buena práctica moderna, se recomienda el uso de un campo "ID" autoincremental que garantice unicidad y estabilidad.
> 
> ### Claves Foráneas (FK) y Tablas Intermedias
> 
> Para conectar tablas, se utilizan las **Claves Foráneas**.
> 
> - En relaciones **Muchos a Muchos (N:N)**, no es posible realizar una conexión directa. Se requiere una **Tabla Intermedia** que contenga las claves foráneas de ambas tablas relacionadas (ejemplo: una tabla `Materias_por_Alumno` para conectar `Alumnos` y `Materias`).
> 
> ## 5. Análisis de Casos Prácticos y Modelado
> 
> ### Caso 1: Torneo de Ciclismo
> 
> - **Entidades vs. Atributos:** El "Director" no debe ser un simple atributo del equipo. Si se desea mantener un registro histórico ante renuncias o cambios, debe ser una **Entidad** separada.
> - **Contratos:** El contrato es una entidad que vincula al ciclista con el equipo. Debe tener fechas de inicio y fin.
> - **Atributos Derivados:** Los "Kilómetros Totales" de una prueba son un atributo derivado que surge de la sumatoria de los kilómetros de cada "Etapa" (que debe ser una entidad, posiblemente débil, vinculada a la prueba).
> 
> ### Caso 2: Sistema de Acceso a Club (Molinetes)
> 
> - **Entidad Molinete:** Es una entidad (frecuentemente débil de la Sede) que verifica el acceso.
> - **Apto Médico:** No debe ser solo un atributo booleano (sí/no). Al tener fechas de vencimiento y requerir renovaciones anuales, funciona mejor como una **Entidad** para registrar el historial de presentaciones.
> - **Cálculo de Ingreso:** Para decidir si un socio entra, el sistema compara la **Fecha Actual** (capturada por el sistema en el momento del acceso) con la **Fecha de Vencimiento** de la cuota y del apto físico.
> 
> ## 6. Errores Comunes y Aclaraciones Importantes
> 
> |   |   |
> |---|---|
> |Error Común|Explicación Correcta|
> |**Duplicar IDs**|No se deben poner dos IDs de diferentes entidades en un DER conceptual; eso corresponde al modelo lógico (FK).|
> |**Confundir Atributo con Entidad**|Un dato es entidad si tiene sus propias características (atributos) y vida propia en el sistema.|
> |**Atributos Derivados Guardados**|Datos como la "Edad" no se guardan como tales, sino que se derivan de la "Fecha de Nacimiento".|
> |**Uso de Caracteres Especiales**|Evitar acentos y la letra "ñ" en nombres de tablas y campos para evitar errores de codificación.|
> |**Nomenclatura Plural/Singular**|No hay una regla única, pero debe haber consistencia en el equipo de trabajo (ej. todo en singular por ser objetos, o todo en plural por ser conjuntos).|
> 
> ## 7. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de las fuentes, se establecen las siguientes directrices y cronograma:
> 
> - **Viernes (Semana Santa):** Feriado. No hay actividad académica ni clases.
> - **Próximo Martes:** No habrá entrega de tareas, ya que se requiere completar la Unidad 4 (Normalización) para poder transformar correctamente los modelos DER a tablas.
> - **Unidad 4 y 5:** Se verán de forma conjunta. La Unidad 4 trata sobre Normalización (evitar redundancia) y la Unidad 5 sobre SQL (lenguaje de consulta).
> - **Evaluación Parcial:** Se definirá próximamente (estimado para el mes de mayo). El examen incluirá la creación de bases de datos y consultas SQL.
> - **Material Adicional:** Se recomienda revisar videos de cuatrimestres anteriores sobre código SQL, ya que el tiempo en clase es limitado para la amplitud del tema.
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia entre una "Tupla" y un "Atributo"?
> 2. ¿Por qué se prefiere un tipo de dato entero para una Clave Primaria?
> 3. ¿Qué significa que un atributo sea "atómico"?
> 
> ### Nivel Intermedio
> 
> 4. Explique por qué el "Apto Médico" en un club deportivo debería ser una entidad y no un simple atributo de texto.
> 5. ¿Cuándo es estrictamente necesario crear una tabla intermedia? Dé un ejemplo distinto al de las fuentes.
> 6. ¿Cuál es la diferencia entre el tipo de dato `DATETIME` y `TIMESTAMP`?
> 
> ### Nivel Avanzado
> 
> 7. Analice las consecuencias de utilizar un atributo que cambia con el tiempo (como el estado civil o un apellido) como clave primaria.
> 8. En un sistema de molinetes, describa el flujo de datos necesario (comparación de atributos) para permitir o denegar el acceso a un socio.
> 9. ¿Por qué el orden de las columnas en una tabla de base de datos es irrelevante desde el punto de vista técnico pero importante desde el punto de vista del desarrollador?

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 4 - Administración de base de datos" src="https://www.youtube.com/embed/HRSQMruU0l4?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1u7eEnzuVqEMTKq3f34ku1iAIAggsGamk/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1h4P4GQe_6w5yxUeOx_fAYli9BPxiMPjC/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>