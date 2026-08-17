---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/5-modelado-y-diseno-de-software/clase-3-viernes-05-de-septiembre-de-2025-05-09-25-modelado-y-diseno-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Modelado y Diseño de Software: Guía Integral de Diagramas de Clases
> 
> Este documento constituye una síntesis exhaustiva y técnica sobre los fundamentos del modelado de software, centrándose específicamente en la transición de ideas abstractas a representaciones reales mediante el uso de diagramas de clases.
> 
> ## 1. Introducción y Contexto Histórico
> 
> El modelado de software es el proceso de llevar una idea del mundo abstracto al mundo real. Históricamente, la programación ha evolucionado significativamente desde la década de 1940:
> 
> - **Década de 1940 en adelante:** La programación se basaba en códigos binarios, nemónicos y funciones básicas.
> - **Evolución Moderna:** Se han optimizado los tipos de datos abstractos y el paradigma de objetos. Actualmente, no se programa directamente en binario (salvo casos muy específicos), sino que el desarrollador se apoya en la **abstracción**.
> 
> La abstracción es una conducta humana fundamental que permite definir conceptos (como la verdad o conceptos teóricos) para crear modelos arbitrarios. En el diseño de software, estos modelos permiten agrupar elementos y definir ámbitos de trabajo para un conjunto de objetos.
> 
> ## 2. Marco Conceptual y Definiciones Clave
> 
> ### Clase vs. Objeto
> 
> Es fundamental no confundir estos dos conceptos:
> 
> - **Clase:** Es un esquema o modelo que define un ámbito y un conjunto de características comunes. Es el "molde" o la categoría (ejemplo: Clase Vehículo).
> - **Objeto:** Es la instancia real de una clase. Es el elemento concreto que existe en la realidad o en la ficción del sistema (ejemplo: Un auto específico).
> 
> ### Estructura de una Clase
> 
> Una clase se representa gráficamente mediante un bloque dividido en tres secciones principales:
> 
> 1. **Nombre:** Identifica la clase.
> 2. **Atributos:** Son las características o propiedades (ejemplo: color, cilindrada, velocidad máxima).
> 3. **Operaciones/Funciones:** Son las acciones que la clase puede realizar (ejemplo: arrancar, acelerar, frenar).
> 
> ### Niveles de Visibilidad (Encapsulamiento)
> 
> Los atributos y operaciones poseen niveles de precisión o ámbitos definidos por símbolos:
> 
> |   |   |   |
> |---|---|---|
> |Símbolo|Nivel de Acceso|Descripción|
> |`+`|Público|Acceso total desde cualquier punto.|
> |`#`|Protegido|Acceso restringido a la clase y sus derivadas.|
> |`-`|Privado|Acceso exclusivo dentro de la propia clase.|
> 
> ## 3. Lógica y Operadores en el Modelado
> 
> El diseño de clases a menudo requiere definir condiciones lógicas para las operaciones, especialmente en el filtrado de datos:
> 
> - **AND:** Produce una salida verdadera solo si ambas entradas son verdaderas.
> - **OR Inclusivo:** Devuelve falso solo si ambas entradas son falsas; si una es verdadera, la salida es verdadera. Es un filtro más amplio.
> - **OR Exclusivo (XOR):** Es un filtro estricto y excluyente. No permite que dos casos se den simultáneamente (ejemplo: un motor es a nafta o es diésel, pero no ambos al mismo tiempo).
> - **NOT:** El operador de negación, el más sencillo de aplicar.
> 
> ## 4. Relaciones entre Clases
> 
> Las clases no trabajan de forma aislada, sino que se comunican mediante vínculos definidos:
> 
> ### Asociación y Enlaces
> 
> - **Asociación:** Crea un vínculo estricto entre clases. Por ejemplo, en un sistema académico, si no hay estudiantes, no tiene sentido la existencia de la universidad. Puede ser dual o unidireccional.
> - **Multiplicidad:** Define cuántas instancias de una clase se relacionan con otra.
>     - 1 a 1 (Uno y solo uno).
>     - 0 a 1.
>     - 1 a varios (1..*).
>     - 0 a varios (0..*).
> 
> ### Jerarquía (Herencia)
> 
> Permite establecer una estructura de clases principales (superclases) y clases derivadas (subclases) que heredan sus características:
> 
> - **Ejemplo de Jerarquía de Vehículos:**
>     - Vehículo (Principal)
>         - Terrestre (Coche, Camión)
>         - Aéreo (Avión, Helicóptero)
>             - Avión a motor
>             - Planeador
> 
> ### Agregación y Composición
> 
> Define si una relación es compartida o estricta. Por ejemplo, la relación entre un "Coche" y un "Motor" es una asociación no compartida: el motor pertenece específicamente a ese coche.
> 
> ## 5. Ejemplos Prácticos de Aplicación
> 
> A continuación, se describen casos de estudio analizados para la construcción de diagramas:
> 
> ### Caso 1: Gestión Hotelera
> 
> - **Clases identificadas:** Cliente, Reserva, Habitación.
> - **Dinámica:** La reserva puede requerir una "seña" para asegurar la habitación. El sistema debe prever políticas de cancelación (ejemplo: 24 horas antes) para proteger al negocio frente a clientes que no se presentan.
> 
> ### Caso 2: Supermercado
> 
> - **Clases identificadas:** Sucursal, Proveedor, Empleado, Producto.
> - **Atributos de Empleado:** Legajo, nombre, DNI, teléfono, antigüedad, sector y cargo.
> - **Relación:** Los proveedores abastecen a las sucursales con productos (verduras, artículos de almacén, etc.).
> 
> ### Caso 3: E-commerce (Carrito de Compras)
> 
> - **Clases identificadas:** Cliente, Carrito, Ítem de Carrito, Producto.
> - **Lógica de Negocio:** Un ítem de carrito "hereda" o toma los datos de un producto. Se discute la posibilidad de que un cliente tenga más de un carrito (uno en proceso de envío y otro activo).
> - **Tipo de Datos:** Para precios, se recomienda el uso de "Entero Doble" si se trabaja con centavos para evitar errores de precisión, o flotantes según la implementación.
> 
> ## 6. Errores Comunes y Aclaraciones
> 
> - **Confusión entre Clase y Objeto:** No se debe modelar una instancia específica como si fuera una categoría general.
> - **Mezcla de Diagramas:** Es un error intentar incluir elementos de comunicación o de flujo de procesos dentro de un diagrama de clases estático. Cada diagrama tiene su propósito.
> - **Ambigüedad en los Límites:** Al definir rangos (ejemplo: mayor a 5 o menor a 5), el desarrollador debe decidir explícitamente dónde incluir el valor extremo (el 5), ya sea en un tercer caso ("igual a") o incluyéndolo en uno de los grupos.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Síntesis y Puntos Clave
> 
> - El modelado es **subjetivo y voluntario**: No existe un modelo único "perfecto", sino que depende de cómo el diseñador interprete la problemática.
> - La **jerarquización** es vital para organizar la complejidad.
> - Los diagramas deben ser **evolutivos**: Son objetos de evaluación permanente y pueden modificarse a medida que se profundiza en el problema.
> - El uso de **paquetes** ayuda a organizar diagramas extensos (ejemplo: agrupar clases de productos por un lado y clases de clientes por otro).
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia fundamental entre una clase y un objeto?
> 2. ¿Qué representan los símbolos `+`, `-` y `#` en un diagrama de clases?
> 3. Defina qué es la abstracción en el contexto del diseño de software.
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia entre un OR Inclusivo y un OR Exclusivo con un ejemplo aplicado al modelado.
> 5. ¿Qué es la multiplicidad y cuáles son sus variantes más comunes?
> 6. ¿Por qué se considera que la relación entre Universidad y Estudiante es una asociación estricta?
> 
> ### Nivel Avanzado
> 
> 7. Diseñe una jerarquía lógica para la clase "Cuenta Bancaria" incluyendo posibles operaciones privadas y públicas.
> 8. En un sistema de E-commerce, ¿por qué es preferible que el Ítem de Carrito sea una clase distinta a Producto? Analice la relación de herencia o dependencia.
> 9. ¿Cómo beneficia el uso de paquetes a un diagrama que contiene más de 15 clases?
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Fechas importantes y avisos académicos
> 
> A partir de las fuentes analizadas, se establecen las siguientes pautas de organización de la materia:
> 
> - **Presentación de Borradores:** Se realizó la entrega y revisión de borradores de trabajos prácticos por parte de los Grupos 2, 3 y 4.
> - **Grupo 1:** Tiene pendiente la entrega de su borrador para la próxima semana (debido a problemas técnicos reportados).
> - **Flexibilidad de Modificación:** Los grupos tienen libertad total para modificar, mejorar y agregar elementos a sus diagramas de clase hasta el cierre del cuatrimestre. No hay una fecha límite estricta para la versión final mientras el borrador haya sido presentado.
> - **Próxima Clase:** Se introducirá un tema nuevo y se espera que los grupos continúen profundizando en sus modelos (agregando funciones, jerarquías y revisando niveles de visibilidad).
> - **Indicación del Profesor:** No es obligatorio realizar las "tareas" que aparecen dentro de los archivos de lectura proporcionados, a menos que se indique explícitamente. Lo primordial es el avance del Trabajo Práctico grupal.
> - **Comunicación:** Todas las dudas técnicas deben canalizarse a través del grupo de comunicación general, evitando consultas por privado para que las respuestas sirvan a todos los estudiantes.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 3 - Modelado y diseño de software" src="https://www.youtube.com/embed/Hd4DRDHgXRE?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1ITQpqi5Ycg9YdXV9z7rJ-68DZU6ujuwt/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1WVBkPmWRgZv39WkRvnYco8OuRhNF2E7T/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>