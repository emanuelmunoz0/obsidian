---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/1-tecnicas-de-programacion/clase-12-lunes-23-de-junio-de-2025-23-06-25-tecnicas-de-programacion/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio Avanzada: Estructuras de Datos, Objetos JSON y Combinatoria
> 
> Este documento constituye un material de estudio integral para la asignatura de Técnicas de Programación. Cubre de manera exhaustiva los conceptos de estructuras de datos compuestas, la implementación de objetos JSON en JavaScript y la lógica de algoritmos combinatorios, proporcionando las bases necesarias para abordar evaluaciones avanzadas.
> 
> ## 1. Contexto e Importancia
> 
> El estudio de las técnicas de programación en esta etapa se centra en la transición de datos simples a **estructuras de datos compuestas**. La capacidad de organizar información en bases de datos simuladas (arrays de objetos) y de generar lógicas de combinación de elementos es fundamental para el desarrollo de aplicaciones de gestión, reportes y análisis de datos.
> 
> A diferencia del primer tramo de la materia, donde se trabajaron conceptos básicos, en este nivel se introduce una complejidad mayor basada en la **extensión y organización** de los algoritmos, más que en la aparición de teorías radicalmente nuevas.
> 
> ## 2. Marco Conceptual: Objetos JSON
> 
> ### Definición y Estructura
> 
> En el contexto de JavaScript, un objeto **JSON** (_JavaScript Object Notation_) es una estructura de datos "composite" o compuesta que permite agrupar múltiples valores bajo una sola entidad semántica.
> 
> - **Composición:** Se define mediante pares de **clave-valor** (o campo-valor).
> - **Sintaxis:** El objeto se encierra entre llaves `{ }`. Cada par clave-valor se separa por dos puntos `:`, y los distintos elementos del objeto se separan por comas `,`.
> - **Fidelidad Sintáctica:** Aunque JavaScript permite cierta flexibilidad, la norma general establece que las claves (campos) deben ir entre comillas. Los valores tipo cadena (_string_) también llevan comillas, mientras que los valores numéricos y lógicos no.
> 
> ### Diferencia con la Programación Orientada a Objetos (POO)
> 
> Es crucial no confundir los objetos JSON con el paradigma de **Programación Orientada a Objetos (POO)**.
> 
> - **Objetos JSON:** Son simplemente estructuras de datos para almacenar información. No requieren la definición de clases ni instancias mediante constructores en este nivel.
> - **POO:** Involucra conceptos de clases, herencia, métodos (funciones internas) y atributos privados. JavaScript es un lenguaje híbrido que permite POO, pero el uso de JSON aquí se limita a la organización de datos.
> 
> ### Acceso a la Información
> 
> Para acceder al valor de un campo dentro de un objeto, se utiliza la **notación de punto**: `nombre_del_objeto.nombre_del_campo`
> 
> Ejemplo:
> 
> ```javascript
> let alumno = { "nombre": "Juan", "edad": 22 };
> console.log(alumno.nombre); // Resultado: Juan
> ```
> 
> ## 3. Desarrollo del Tema: Estructuras Complejas
> 
> ### Arrays de Objetos
> 
> La forma más común de representar una base de datos en memoria es mediante un **array de objetos**. Cada elemento del array representa un "registro" (por ejemplo, un cliente o un producto), y cada objeto contiene los detalles de ese registro.
> 
> |   |   |
> |---|---|
> |Concepto|Descripción|
> |**Registro**|Un objeto individual con múltiples campos.|
> |**Base de Datos**|Un array que contiene múltiples objetos.|
> |**Anidamiento**|Un campo de un objeto puede ser, a su vez, otro array u otro objeto.|
> 
> ### Acceso Profundo (Anidado)
> 
> Cuando las estructuras se ramifican, el acceso sigue una lógica jerárquica:
> 
> 1. Nombre de la variable base.
> 2. Nombre del campo (punto).
> 3. Índice del array si corresponde (corchetes `[ ]`).
> 4. Nombre del sub-campo (punto).
> 
> **Ejemplo de flujo de acceso:** Para obtener la categoría del primer producto de una base de datos: `de_base.productos[0].categoria`
> 
> ## 4. Combinatoria en Programación
> 
> La combinatoria se enfoca en la generación de agrupaciones de elementos siguiendo reglas lógicas específicas. En programación, esto se resuelve generalmente mediante **bucles anidados** (`for`).
> 
> ### Tipos de Agrupaciones
> 
> 1. **Combinaciones entre conjuntos distintos:** Se vinculan elementos de un Conjunto A con elementos de un Conjunto B (ej. Nombres y Apellidos).
>     - Si hay 3 nombres y 3 apellidos, el resultado total es de 3 \times 3 = 9 combinaciones.
> 2. **Duplas o Tripletas en un mismo conjunto:** Se agrupan elementos de un solo array (ej. números `{1, 4, 7}`).
>     - **Con repetición:** Se permite que un elemento se agrupe consigo mismo (1-1, 4-4). Se logra con dos bucles `for` que recorren el mismo índice.
>     - **Sin repetición:** Se excluyen los casos donde el elemento se repite. Lógicamente, esto se controla con una condición: `if (i != j)`.
> 3. **Permutaciones y Orden:** En ciertos casos, el orden importa (no es lo mismo 1-4 que 4-1). En otros, solo interesa la presencia de los elementos en el grupo.
> 
> ## 5. Ejemplos Prácticos Paso a Paso
> 
> ### Caso A: Filtrado de Datos Complejos
> 
> Supongamos una base de datos de productos donde cada producto tiene un objeto de "talles" con un rango menor y mayor. El objetivo es buscar productos que cumplan con un talle solicitado por el usuario.
> 
> **Lógica del algoritmo:**
> 
> 4. Recorrer el array de productos con un bucle `for`.
> 5. Acceder al campo anidado: `productos[i].talles.talle_menor`.
> 6. Comparar con el valor buscado.
> 7. Si se cumple, mostrar la marca y modelo.
> 
> ### Caso B: Generación de Combinaciones
> 
> Para generar todas las combinaciones posibles entre un array de nombres y uno de apellidos:
> 
> ```javascript
> for (i = 0; i < nombres.length; i++) {
>     for (j = 0; j < apellidos.length; j++) {
>         // Se crea el par (nombres[i], apellidos[j])
>         // Se puede almacenar en un nuevo array de objetos
>     }
> }
> ```
> 
> ## 6. Errores Comunes y Aclaraciones
> 
> - **Confusión de Terminología:** No existe una convención universal estricta para llamar a los "componentes" de un array vs "elementos" de un objeto. Lo importante es distinguir que el array usa índices numéricos y el objeto usa claves semánticas.
> - **Errores de Sintaxis en Anidamiento:** Al crear objetos complejos, es frecuente olvidar cerrar una llave `}` o un corchete `]`, o bien omitir comas entre campos.
> - **Scope de Variables:** Se recomienda definir los índices de los bucles (`i`, `j`) fuera de las estructuras para evitar problemas de alcance (_scope_), permitiendo referenciarlas en cualquier parte del código.
> - **JSON vs String:** Para visualizar un objeto completo de forma legible en un `alert`, se debe convertir a cadena de texto usando funciones como `JSON.stringify()`.
> 
> ## 7. Síntesis y Conclusiones
> 
> - Los objetos **JSON** son agrupaciones de clave-valor fundamentales para manejar datos semánticos.
> - La dificultad de los programas actuales no radica en nuevos conceptos, sino en la **organización lógica** para resolver múltiples sub-tareas (reportes, cálculos de promedio, máximos y mínimos).
> - La **combinatoria** se implementa mediante bucles anidados; la cantidad de bucles determina si se trata de duplas, tripletas o grupos mayores.
> - El acceso a datos en estructuras complejas requiere precisión en el uso de puntos para campos y corchetes para índices.
> 
> ## 8. Fechas importantes y avisos académicos
> 
> Tras el análisis de las fuentes, se identifican las siguientes indicaciones para el cierre del ciclo evaluativo:
> 
> |   |   |   |
> |---|---|---|
> |Evento|Fecha|Descripción Detallada|
> |**Segundo Parcial**|Próxima clase (Fecha exacta no especificada)|Se evaluará Arrays, Objetos JSON y Combinatoria. No se incluyen funciones recursivas.|
> |**Entrega de TP 6**|No especificada|Trabajo práctico que incluye ejercicios de tiendas, combinatoria y gestión de bases de datos.|
> |**Recuperatorios**|Posterior al parcial|Se menciona que temas como ordenamiento y búsqueda podrían tener mayor peso en esta instancia si no se evaluaron profundamente en el parcial.|
> 
> **Advertencia Académica:** El profesor señala que los ejercicios del parcial no son difíciles individualmente, pero la complicación reside en que son **más largos** y requieren buena organización bajo el límite de tiempo. Se recomienda practicar la resolución de reportes (máximos, mínimos, promedios) sobre arrays de objetos.
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la sintaxis correcta para definir un objeto JSON con los campos "marca" y "precio"?
> 2. ¿Cómo se accede al tercer elemento de un array que está dentro de un objeto llamado `tienda`?
> 
> ### Nivel Intermedio
> 
> 1. Explique la diferencia técnica entre un objeto JSON y una clase en programación orientada a objetos.
> 2. ¿Qué lógica debe aplicarse en un bucle anidado para evitar que un número se combine consigo mismo en una dupla?
> 
> ### Nivel Avanzado (Tipo Examen)
> 
> 1. Dada una estructura de "ventas" (array de objetos), describa los pasos necesarios para encontrar al vendedor que realizó la venta más alta.
> 2. Si se requiere realizar combinaciones de 3 elementos de un mismo conjunto, ¿cuántos bucles `for` se necesitan y cuál sería la condición para obtener combinaciones sin repetición total?

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 12 - Técnicas de programación" src="https://www.youtube.com/embed/BpoZqAPV1q0?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1namMQHYV6YQuApANgnJINvkwVNYx5IZb/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1FHnvAuZ73PvObY1klp55jbcuHfqLnr-U/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>