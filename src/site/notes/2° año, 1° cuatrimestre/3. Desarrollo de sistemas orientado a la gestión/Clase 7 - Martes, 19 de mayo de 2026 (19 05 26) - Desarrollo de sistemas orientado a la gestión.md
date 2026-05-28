---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/3-desarrollo-de-sistemas-orientado-a-la-gestion/clase-7-martes-19-de-mayo-de-2026-19-05-26-desarrollo-de-sistemas-orientado-a-la-gestion/","dg-note-properties":{}}
---


> [!quote]- Resumen
> # Guía de Estudio: Implementación de ORM y Conexión Frontend-Backend
> 
> Este documento constituye un material de estudio integral sobre el desarrollo de sistemas orientado a la gestión, centrándose específicamente en la migración de datos estáticos (hardcoded) hacia una arquitectura persistente utilizando un **ORM (Object-Relational Mapping)** y su posterior integración con la interfaz de usuario.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> El desarrollo moderno de aplicaciones exige una separación clara entre la lógica de negocio y la persistencia de datos. En las etapas iniciales de un proyecto, es común utilizar datos "hardcodeados" (fijos en el código) para probar funcionalidades. Sin embargo, para escalar a una aplicación real, se requiere el uso de bases de datos. Esta transición se facilita mediante el uso de un ORM, que actúa como un puente entre la programación orientada a objetos y las bases de datos relacionales.
> 
> ## 2. Contexto del Tema
> 
> En el marco del desarrollo de sistemas de gestión, se ha progresado desde una estructura básica hacia una arquitectura **MVC (Modelo-Vista-Controlador)**. El punto de inflexión actual consiste en reemplazar los arreglos de datos temporales por una base de datos **SQLite** (para desarrollo) que sea fácilmente migrable a motores más potentes como **PostgreSQL** o **MySQL** mediante **Sequelize**, el ORM estándar para Node.js.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Marco Conceptual
> 
> ### Definición de Conceptos Clave
> 
> - **ORM (Object-Relational Mapping):** Es una capa de abstracción que permite interactuar con la base de datos utilizando funciones del lenguaje de programación (en este caso, JavaScript) en lugar de escribir consultas SQL manuales.
> - **Sequelize:** Es el ORM utilizado para Node.js. Su principal ventaja es la "filosofía de abstracción": el código escrito funciona independientemente del motor de base de datos (SQL Server, MariaDB, PostgreSQL, etc.).
> - **SQLite:** Un motor de base de datos relacional que no requiere un servidor independiente, ya que la base de datos es un simple archivo en el disco. Es ideal para entornos de desarrollo y pruebas.
> - **Dotenv (.env):** Herramienta para gestionar variables de entorno. Se utiliza para almacenar "secretos" o configuraciones sensibles (puertos, credenciales, rutas de archivos) que no deben subirse a repositorios públicos como GitHub.
> - **Sincronización (Sync):** Proceso mediante el cual el ORM compara los modelos definidos en el código con la estructura real de la base de datos y realiza las modificaciones necesarias (creación de tablas o columnas) automáticamente.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Desarrollo del Tema
> 
> ### A. Configuración y Prerrequisitos
> 
> Para implementar esta arquitectura, es necesario instalar tres dependencias fundamentales:
> 
> 1. `sequelize`: El motor del ORM.
> 2. `sqlite3`: El driver para manejar la base de datos local.
> 3. `dotenv`: Para la gestión de configuraciones privadas.
> 
> ### B. Gestión de Secretos y Seguridad
> 
> Es fundamental el uso del archivo `.gitignore` para excluir el archivo `.env`.
> 
> - **Referencia:** Se recomienda crear un archivo `.env.example` con la estructura de las variables pero sin los datos reales, para que otros desarrolladores sepan qué configurar.
> - **Variables clave:** Dialecto (dialect), almacenamiento (storage) y opciones de logueo (logging).
> 
> ### C. Definición de Modelos
> 
> En lugar de clases tradicionales, Sequelize utiliza `sequelize.define` para estructurar las tablas. Al definir un modelo (por ejemplo, `Product`), se deben especificar:
> 
> - **Tipo de dato:** `STRING`, `FLOAT` (para precios), `INTEGER`.
> - **Restricciones:** `allowNull: false` (para campos obligatorios), `primaryKey`, `autoIncrement`.
> - **Validaciones:** Por ejemplo, establecer un `min: 0` para el stock o el precio para evitar valores negativos.
> 
> ### D. Refactorización de Controladores
> 
> Los controladores ya no acceden a un archivo JSON o un arreglo fijo. Ahora utilizan métodos asíncronos del ORM:
> 
> - `findAll()`: Recupera todos los registros (equivale a `SELECT *`).
> - `findByPk()`: Busca un registro por su clave primaria.
> - `create()`: Inserta un nuevo registro y devuelve un código de estado **201** (creado).
> - `update()` y `save()`: Para modificar registros existentes.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Relaciones entre Conceptos
> 
> La potencia del ORM reside en cómo gestiona las asociaciones sin necesidad de escribir complejos `JOIN` de SQL manualmente:
> 
> |   |   |   |   |
> |---|---|---|---|
> |Concepto A|Relación|Concepto B|Explicación|
> |**Categoría**|`hasMany`|**Producto**|Una categoría (ej. Electrónica) puede tener muchos productos asociados.|
> |**Producto**|`belongsTo`|**Categoría**|Cada producto pertenece a una única categoría específica.|
> |**Controller**|`include`|**Model**|Al buscar un producto, el controlador puede pedir que se "incluya" el modelo de categoría para obtener los datos relacionados automáticamente.|
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Ejemplos Prácticos
> 
> ### Definición de un Modelo de Producto
> 
> ```javascript
> // Ejemplo de sintaxis en Sequelize
> const Product = sequelize.define('Product', {
>     name: {
>         type: DataTypes.STRING,
>         allowNull: false,
>         validate: { notEmpty: true }
>     },
>     price: {
>         type: DataTypes.FLOAT,
>         validate: { min: 0 }
>     },
>     stock: {
>         type: DataTypes.INTEGER,
>         defaultValue: 0
>     }
> });
> ```
> 
> ### Uso de Sync para Modificaciones
> 
> Si se desea agregar un campo nuevo, como `imagenURL`, simplemente se añade al modelo en el código JavaScript. Al ejecutar la función `sync()`, Sequelize detecta el cambio y genera internamente la sentencia `ALTER TABLE` en la base de datos sin que el programador escriba SQL.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Errores Comunes y Confusiones
> 
> 1. **Hardcoding en el código principal:** Un error frecuente es poner el nombre de la base de datos o contraseñas directamente en el archivo de conexión. **Solución:** Centralizar todo en el archivo `.env`.
> 2. **Inconsistencia de nombres:** Al modificar un modelo (por ejemplo, cambiar `precio` por `price`), es común olvidar actualizar el controlador. Esto generará errores en las operaciones `create` o `update`.
> 3. **No sincronizar el Git Local con GitHub:** Se suele hacer `commit` (que guarda los cambios localmente) pero olvidar el `push` o `sync`, lo que impide que el resto del equipo vea las actualizaciones.
> 4. **Confusión con SQLite:** Creer que SQLite requiere una instalación de servidor como MySQL. **Aclaración:** Es solo un archivo dentro de la carpeta del proyecto.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Síntesis y Conclusiones
> 
> La implementación de un ORM como Sequelize transforma la gestión de datos de una tarea manual y propensa a errores (SQL puro) a una tarea programática y abstracta. Los puntos clave son:
> 
> - **Abstracción:** El código es independiente del motor de base de datos.
> - **Seguridad:** Uso de variables de entorno para proteger datos sensibles.
> - **Automatización:** Sincronización automática de modelos con la estructura de la base de datos.
> - **Integración:** La Clase 8 marca el inicio de la conexión real, donde el Frontend usa `fetch` para consumir estos datos dinámicos en lugar de tarjetas estáticas.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la función principal de un ORM en una aplicación?
> 2. ¿Por qué es importante incluir el archivo `.env` en el `.gitignore`?
> 3. ¿Qué motor de base de datos se utiliza para desarrollo por ser basado en archivos?
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia entre los métodos `findAll()` y `findByPk()`.
> 5. ¿Qué sucede internamente cuando ejecutamos la función `sync()` después de agregar un atributo a un modelo?
> 6. ¿Cómo se define una relación "Uno a Muchos" entre Categorías y Productos en Sequelize?
> 
> ### Nivel Avanzado
> 
> 7. Describa el flujo de datos desde que el Frontend realiza un `fetch` hasta que el ORM devuelve un registro de la base de datos.
> 8. ¿Por qué se recomienda devolver un código de estado HTTP 201 al crear un recurso y un 404 cuando no se encuentra un ID?
> 9. Analice las ventajas de usar `dotenv` frente a tener un archivo de configuración `.js` convencional.
> 
> --------------------------------------------------------------------------------
> 
> ## 10. Fechas Importantes y Avisos Académicos
> 
> A partir del análisis de la fuente, se identifican los siguientes puntos relevantes para el seguimiento de la materia:
> 
> - **Estado de Entregas (Clase 7):** Los alumnos deben tener actualizada la migración al ORM en sus repositorios de GitHub. No hay una plataforma de entrega aparte; el profesor revisará directamente los repositorios (Git/GitHub).
> - **Disponibilidad de Material:**
>     - **Clase 7:** Enfocada en la migración a Sequelize y SQL Lite (Ya disponible y explicada).
>     - **Clase 8:** Ya se encuentra habilitada en el aula virtual.
> - **Objetivo de la Clase 8:** Conectar el Backend (base de datos) con el Frontend. Los alumnos deben empezar a reemplazar las tarjetas hardcodeadas de la interfaz por datos obtenidos mediante `fetch`.
> - **Indicación Especial:** El profesor realizará rondas por los grupos para supervisar la reorganización del código y resolver trabas técnicas con la migración.
> - **Estructura de Carpetas:** Existe una propuesta de separar el proyecto en carpetas claras de `frontend` y `backend`. Si el grupo ya tiene una estructura ordenada y acordada, pueden mantenerla; de lo contrario, se sugiere seguir la guía de la Clase 8.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 7 (19 05 26) - Desarrollo de sistemas orientado a la gestión" src="https://www.youtube.com/embed/Nrqb92EGa9c?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1V97HY5XFJ1ZZgVD6RNhlNwKQ8A2Ap5I3/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1eq28DgXPNwx-nRK6cjWkVgIQzYUjjVcS/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>