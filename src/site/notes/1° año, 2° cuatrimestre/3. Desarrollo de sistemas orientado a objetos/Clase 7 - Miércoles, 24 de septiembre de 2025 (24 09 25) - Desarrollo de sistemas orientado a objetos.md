---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/3-desarrollo-de-sistemas-orientado-a-objetos/clase-7-miercoles-24-de-septiembre-de-2025-24-09-25-desarrollo-de-sistemas-orientado-a-objetos/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio: Desarrollo de Sistemas Orientado a Objetos y Tecnologías de Integración
> 
> Este documento constituye un material de estudio exhaustivo basado en las sesiones académicas sobre el desarrollo de sistemas orientados a objetos (POO), con un enfoque especial en la integración de bases de datos, inteligencia artificial y la estructuración de proyectos en Node.js.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> El desarrollo de sistemas modernos requiere una transición de la codificación lineal y procedimental hacia una arquitectura organizada y escalable. El documento se centra en la aplicación práctica de la Programación Orientada a Objetos (POO) para resolver problemas complejos, como la gestión hotelera o la creación de chatbots inteligentes.
> 
> Un pilar fundamental de este enfoque es la integración de componentes externos —bases de datos y modelos de Inteligencia Artificial (IA)— mediante el uso de clases que encapsulan la lógica de conexión y operación, facilitando la reutilización del código y la claridad estructural.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual
> 
> Para comprender el desarrollo de sistemas orientado a objetos, es necesario definir los conceptos fundamentales discutidos:
> 
> ### Conceptos Clave de POO
> 
> - **Clase (Class):** Es la plantilla o molde para crear objetos. Define atributos (datos) y métodos (comportamientos).
> - **Constructor:** Método especial que se ejecuta al instanciar un objeto. Se utiliza para inicializar los datos básicos del sistema (por ejemplo, cargar la configuración de una base de datos).
> - **Herencia (Extends):** Mecanismo que permite a una clase (subclase) heredar propiedades y métodos de otra (clase padre). Esto evita la duplicación de código.
> - **Encapsulamiento:** Organización del código de manera que la complejidad interna esté oculta, permitiendo interactuar con el objeto a través de métodos definidos.
> - **Polimorfismo:** Capacidad de las subclases de reescribir métodos de la clase padre (como el método `generarRespuesta` en diferentes tipos de chatbots) para adaptarlos a necesidades específicas.
> 
> ### Terminología de Bases de Datos
> 
> - **Base de Datos Relacional (RDBMS):** Estructura de datos basada en tablas con filas y columnas, vinculadas mediante claves foráneas (ej. MariaDB, MySQL).
> - **Base de Datos de Grafos:** Representación del conocimiento mediante **Nodos** (entidades) y **Relaciones** (vínculos). Es más cercana al pensamiento humano.
> - **Pool de Conexiones:** Un conjunto de conexiones a la base de datos listas para ser usadas, lo que mejora la eficiencia al no tener que abrir y cerrar una conexión por cada consulta.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema
> 
> ### A. Integración de Bases de Datos en Node.js
> 
> La conexión con bases de datos relacionales como MariaDB requiere pasos específicos en un entorno de objetos:
> 
> 1. **Instalación:** Uso de `npm install mariadb`.
> 2. **Referenciación:** Uso de `require` o `import` al inicio del script.
> 3. **Configuración (Config):** Se define un objeto JSON con los parámetros de acceso:
>     - `host`: Dirección del servidor (ej. `localhost` o IP pública).
>     - `user`: Nombre de usuario.
>     - `password`: Contraseña de acceso.
>     - `database`: Nombre de la base de datos.
> 4. **Clase Database:** Se recomienda crear una clase genérica que maneje la conexión y el pool, y subclases específicas para cada motor (ej. `class MariaDB extends Database`).
> 
> ### B. Bases de Datos de Grafos (Neo4j)
> 
> A diferencia de las relacionales, las bases de datos de grafos utilizan una **unidad atómica de información** compuesta por una tríada: **Sujeto - Verbo - Predicado**.
> 
> |   |   |   |
> |---|---|---|
> |Componente|Descripción|Ejemplo en Grafos|
> |**Nodo**|Representa sustantivos (sujeto o predicado).|Empleado, Empresa, Párrafo.|
> |**Relación**|Representa los verbos que conectan nodos.|"Trabaja en", "Pertenece a".|
> |**Capa Ontológica**|Reglas de inferencia definidas.|Si X trabaja en Y, e Y está en Buenos Aires, X está en Buenos Aires.|
> 
> Este modelo es especialmente útil para alimentar modelos de IA, ya que los datos son precisos y permiten a la IA "recorrer" el grafo para inferir respuestas sin ambigüedades.
> 
> ### C. Integración de IA (Gemini API)
> 
> Para dotar a una aplicación de capacidades de lenguaje natural:
> 
> - Se requiere una conexión vía API (usando claves de acceso).
> - El flujo consiste en enviar un _prompt_ (pregunta o instrucción) y recibir una respuesta procesada.
> - La IA potencia los grafos al convertir los resultados de las consultas en respuestas conversacionales para el usuario.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Relaciones entre Conceptos y Estructura
> 
> El sistema se organiza de forma jerárquica para permitir la escalabilidad:
> 
> 1. **Clase Base (Chatbot):** Contiene métodos comunes como `guardarEnHistorial` y `mostrarHistorial`.
> 2. **Subclases (ChatbotClima, ChatbotSoporte):** Heredan de la base pero implementan su propia lógica de `generarRespuesta`.
> 3. **Dependencias de Datos:** Las subclases pueden consultar una base de datos (MariaDB) para obtener información en tiempo real o un grafo (Neo4j) para obtener conocimiento estructurado.
> 4. **Asincronismo:** Debido a que las conexiones a bases de datos y APIs de IA toman tiempo, se deben utilizar funciones **asíncronas** (`async` / `await`). No se puede pedir una conexión o un resultado sin esperar a que el proceso externo responda.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Ejemplos Prácticos
> 
> ### Ejemplo 1: Estructura de un Chatbot en Node.js
> 
> Para crear un chatbot que maneje opciones, se puede utilizar un array de objetos JSON:
> 
> ```javascript
> // Array de conocimiento (hardcoded para pruebas)
> const arrayCompleto = [
>   { opcion: 1, pregunta: "Temperatura actual", respuesta: "25 grados" },
>   { opcion: 2, pregunta: "Probabilidad de lluvia", respuesta: "70%" }
> ];
> 
> // Método para mostrar opciones recorriendo el array
> mostrarCuestionario() {
>   let rta = "";
>   for (let i = 0; i < this.arrayCompleto.length; i++) {
>     rta += `${this.arrayCompleto[i].opcion} - ${this.arrayCompleto[i].pregunta}\n`;
>   }
>   return rta;
> }
> ```
> 
> ### Ejemplo 2: Creación de Nodos en Grafos (Cypher/Neo4j)
> 
> La creación de conocimiento se codifica estableciendo el nodo y su relación:
> 
> - `Create (A:Termino {nombre: "Ética"})`
> - `Create (B:Obra {nombre: "Aristóteles"})`
> - `Create (A)-[:PERTENECE_A]->(B)`
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores Comunes y Aclaraciones
> 
> 1. **Enfoque en la Teoría vs. Práctica:** Un error común es intentar entender toda la teoría (herencia, encapsulamiento) antes de que el código funcione. Se recomienda **priorizar que el código funcione** y luego refinar la estructura teórica.
> 2. **Sintaxis de Arrays y Objetos:** Al usar `push` en un array para agregar nuevas entradas al chatbot, se debe asegurar de pasar un objeto JSON correctamente formado (`{ clave: valor }`).
> 3. **Visualización de Objetos:** Si se intenta imprimir un array de objetos directamente en la consola, se verá `[object Object]`. Es necesario usar `JSON.stringify(array)` para ver el contenido real.
> 4. **Barras en Strings:** Para saltos de línea, se debe usar la barra invertida `\n`, no la barra inclinada `/n`.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Síntesis y Conclusiones
> 
> - **Modularidad:** La POO permite separar la conexión a base de datos (clase `Database`) de la lógica de negocio (clase `Hotel` o `Chatbot`).
> - **Flexibilidad de Datos:** Mientras que las bases relacionales son estándar, las de grafos son superiores para representar conocimiento complejo y alimentar IAs.
> - **Pragmatismo Programático:** Una vez que se logra que un mecanismo funcione (como una conexión o un ciclo `for`), el resto del desarrollo consiste en replicar y adaptar ese patrón (copiar y pegar con ajustes).
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia entre una clase y un objeto?
> 2. ¿Para qué sirve el método `constructor` en una clase de Node.js?
> 3. ¿Cómo se instala el paquete necesario para usar MariaDB?
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia estructural entre una tabla relacional y un nodo de grafo.
> 5. ¿Por qué es necesario utilizar `async` y `await` al trabajar con bases de datos?
> 6. ¿Qué función cumple `JSON.stringify` en la depuración de código?
> 
> ### Nivel Avanzado
> 
> 7. Describa cómo se aplica el concepto de herencia en la creación de múltiples chatbots especializados.
> 8. ¿Cómo funciona una capa ontológica en una base de datos de grafos y qué ventaja ofrece para la inferencia de datos?
> 9. Diseñe la lógica de un método `procesarMensaje` que utilice `indexof` para identificar palabras clave en una entrada de usuario.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Fechas Importantes y Avisos Académicos
> 
> A partir del análisis de las fuentes, se detallan los siguientes compromisos académicos:
> 
> |   |   |   |
> |---|---|---|
> |Fecha|Tipo de Evento|Descripción Detallada|
> |**01 de Octubre** (estimado)|Clase de Integración|El profesor planea mostrar la integración conjunta de Base de Datos e IA en un solo ejercicio (módulo de Gemini).|
> |**08 de Octubre**|**Examen Parcial**|Fecha confirmada del parcial (postergado una semana). Será de modalidad virtual.|
> |**Post-Parcial**|Inicio de Proyectos|Tras el parcial, comenzará el trabajo en proyectos grupales.|
> 
> **Indicaciones Académicas Importantes:**
> 
> - **Metodología de Proyectos:** Las clases post-parcial se dividirán en bloques de **20 minutos por grupo** para seguimiento de avances. Los grupos pueden coordinar y rotar sus horarios entre sí.
> - **Enfoque del Parcial:** El profesor enfatiza que el foco debe estar en **hacer funcionar el código**, más que en la profundidad teórica extrema. Se sugiere estudiar el ejercicio del "Hotel" y el "Chatbot" como modelos base.
> - **Caso Especial:** Una alumna realizará el examen el **01 de Octubre** (una semana antes) debido a un viaje programado, previa coordinación con el docente.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 7 - Desarrollo de sistemas orientado a objetos" src="https://www.youtube.com/embed/EqsxLOp0jFU?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1D_UUJ9a-uOzLaTcfedUYPS_7X8c72Xbe/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1SbCKVzmsGl265dMllkdqt1M-0rZH5GAA/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>