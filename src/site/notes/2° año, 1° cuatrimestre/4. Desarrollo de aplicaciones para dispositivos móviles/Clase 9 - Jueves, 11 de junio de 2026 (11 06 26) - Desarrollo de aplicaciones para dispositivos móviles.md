---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/4-desarrollo-de-aplicaciones-para-dispositivos-moviles/clase-9-jueves-11-de-junio-de-2026-11-06-26-desarrollo-de-aplicaciones-para-dispositivos-moviles/","dg-note-properties":{}}
---


> [!quote]- Resumen
> # Guía de Estudio: Desarrollo de Aplicaciones para Dispositivos Móviles y Gestión de Proyectos Académicos
> 
> Este documento constituye un material de estudio integral basado en las sesiones de revisión de proyectos de la asignatura. Cubre desde conceptos técnicos fundamentales en React Native y Expo hasta directrices estratégicas para la evaluación final.
> 
> ## 1. Introducción General
> 
> El desarrollo de aplicaciones móviles modernas exige no solo el conocimiento de lenguajes de programación, sino la comprensión profunda del ecosistema móvil. Esto incluye la gestión de persistencia de datos, el acceso a funciones nativas del hardware y la capacidad de supervisar herramientas de Inteligencia Artificial para la generación de código. El objetivo primordial es que el desarrollador entienda la mecánica del desarrollo y la arquitectura de la aplicación, más allá de la escritura mecánica de funciones.
> 
> ## 2. Marco Conceptual: Definición de Conceptos Clave
> 
> Para el desarrollo de aplicaciones robustas en el entorno de la asignatura, se deben dominar los siguientes términos:
> 
> ### A. Persistencia de Datos
> 
> - **AsyncStorage:** Es un sistema de almacenamiento de datos de tipo "clave-valor", persistente y asincrónico. Es análogo al _LocalStorage_ del entorno web. Se utiliza principalmente para datos simples, como tokens de sesión o IDs de usuario.
> - **SQLite:** Una base de datos relacional ligera que reside en el dispositivo. A diferencia de AsyncStorage, permite realizar consultas complejas (SQL), manejar múltiples tablas y relaciones de datos, siendo ideal para aplicaciones que gestionan catálogos o registros extensos.
> - **Migraciones de Base de Datos:** Proceso para actualizar la estructura (esquema) de la base de datos en los dispositivos de los usuarios cuando se lanza una nueva versión de la aplicación, asegurando que no se pierdan los datos existentes.
> 
> ### B. Funcionalidades Nativas
> 
> Son capacidades de hardware a las que la aplicación accede mediante librerías específicas:
> 
> - **Haptics (Vibración):** Uso de vibraciones con diferentes intensidades (Light, Medium, High) para dar feedback al usuario (ej. al finalizar un temporizador).
> - **Sensores:** Incluye el GPS (localización), podómetro (cuenta de pasos) y la cámara/galería.
> - **Permissions (Permisos):** Lógica necesaria para solicitar al usuario acceso a funciones sensibles (cámara, galería, ubicación) antes de su uso.
> 
> ### C. Seguridad en Interfaz (UI)
> 
> - **SecureTextEntry:** Propiedad de los campos de entrada de texto (`TextInput`) que enmascara los caracteres, esencial para contraseñas.
> - **Toggle de Visibilidad:** Lógica que permite alternar entre ver el texto plano o enmascarado mediante un estado booleano.
> 
> ## 3. Desarrollo del Tema: Arquitectura y Lógica de Aplicación
> 
> ### Gestión de Usuarios y Parámetros
> 
> Un aspecto crítico en la evaluación es la capacidad de la aplicación para diferenciar datos por usuario.
> 
> 1. **Pasaje de Parámetros:** El `userID` debe viajar entre pantallas o ser recuperado de un estado global/almacenamiento local para filtrar la información.
> 2. **Diferenciación de Contenido:** Un usuario "A" no debe ver los mismos datos (ej. favoritos, rutinas) que un usuario "B". Esto se logra filtrando las consultas a la base de datos o al backend mediante el ID del usuario logueado.
> 
> ### Manejo de Versiones y Datos Iniciales
> 
> Un error común es reiniciar la base de datos cada vez que la aplicación se inicia. El flujo correcto debe ser:
> 
> - **Verificación de Existencia:** Antes de insertar datos de prueba, realizar un `SELECT COUNT` para verificar si la tabla ya tiene registros.
> - **Control de Versión de App:** Si se detecta una actualización de la aplicación, ejecutar scripts de migración para alterar tablas sin borrar la información del usuario.
> 
> ### Integración de Inteligencia Artificial
> 
> Se permite y fomenta el uso de herramientas como ChatGPT, Claude o GitHub Copilot para la generación de código. Sin embargo, el desarrollador tiene la **responsabilidad** de entender qué hace cada función. En una evaluación, el conocimiento del código propio es mandatorio; delegar la tarea no implica delegar la comprensión.
> 
> ## 4. Ejemplos Prácticos y Casos de Estudio
> 
> |   |   |   |
> |---|---|---|
> |Proyecto|Funcionalidad Clave|Tecnología Destacada|
> |**Control de Activos**|Escaneo de QR para movimientos de equipos.|SQLite e inserción de datos de prueba.|
> |**Recetario**|Temporizadores con alertas de vibración y favoritos.|Librería de Haptics y estados booleanos.|
> |**Lista de Medios**|Registro de libros y series con cámara.|`AsyncStorage` con claves compuestas.|
> |**App de Gimnasio**|Rutinas personalizadas y seguimiento de progreso.|Integración con Backend (Spring Boot/Java) y `ngrok`.|
> 
> ### Ejemplo: Lógica del botón de visibilidad de contraseña
> 
> Para implementar el "ojo" que muestra/oculta la contraseña, se utiliza un estado booleano:
> 
> ```javascript
> // Pseudocódigo de lógica
> const [verPassword, setVerPassword] = useState(false);
> 
> // En el componente TextInput
> secureTextEntry={!verPassword}
> 
> // En el botón (Toggle)
> onPress={() => setVerPassword(!verPassword)}
> ```
> 
> ## 5. Errores Comunes y Aclaraciones Importantes
> 
> - **El Botón "Atrás":** No todos los teléfonos tienen botones físicos o gestos de navegación estandarizados. Es vital incluir botones de navegación ("Back") dentro de la interfaz de la aplicación para evitar que el usuario quede atrapado en una pantalla.
> - **Recreación de Tablas:** Evitar que el script de inicio borre o sobrescriba datos cada vez que se abre la aplicación. Se debe usar `INSERT OR IGNORE` o validaciones previas.
> - **Aparición de Datos en Web vs. Mobile:** Ciertas funcionalidades (como la cámara o modales específicos) pueden comportarse distinto en el emulador web de Expo que en un dispositivo físico real. Siempre validar en hardware real.
> 
> ## 6. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de las fuentes, se establecen las siguientes fechas y recordatorios:
> 
> |   |   |   |
> |---|---|---|
> |Fecha|Evento|Descripción / Detalle|
> |**Martes 2 de julio**|**Examen Final / Presentación**|Fecha estipulada para la entrega definitiva y evaluación presencial.|
> |**Próxima clase**|**Evaluaciones Anticipadas**|El profesor ofrece la posibilidad de evaluar a quienes se sientan listos para setear la nota antes del final.|
> |**Continuo**|**Feedback Temprano**|Se recomienda mostrar avances (aunque estén incompletos o "rotos") para validar el rumbo del proyecto.|
> 
> **Recordatorios Críticos:**
> 
> - **Orden de Examen:** Los primeros en pasar al examen suelen enfrentar preguntas de menor complejidad. A medida que pasan los alumnos, el nivel de las preguntas aumenta para evitar la repetición de respuestas memorizadas.
> - **Conocimiento del Código:** El profesor advierte que revisará el código y hará preguntas técnicas. No saber explicar el funcionamiento de una parte de la app (aunque haya sido hecha por IA) es motivo de baja nota.
> - **Requisito de Aprobación:** La aplicación debe funcionar, permitir alta de usuario/login, usar al menos una función nativa del teléfono y demostrar pasaje de parámetros entre pantallas.
> 
> ## 7. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia principal entre usar `AsyncStorage` y `SQLite`?
> 2. ¿Para qué sirve la propiedad `secureTextEntry` en un `TextInput`?
> 3. ¿Por qué es importante incluir un botón de "Volver" en la UI?
> 
> ### Nivel Intermedio
> 
> 4. Explique cómo implementaría un filtro para que el usuario solo vea sus propios "favoritos".
> 5. ¿Qué sucede con los datos de una base de datos local si no se gestionan correctamente las migraciones al actualizar la app?
> 6. Describa el proceso para solicitar permisos de uso de la cámara en Expo.
> 
> ### Nivel Avanzado
> 
> 7. Si decidiera utilizar un Backend (ej. Spring Boot) en lugar de persistencia local, ¿cómo gestionaría la sesión del usuario en el dispositivo móvil?
> 8. Analice la ventaja estratégica de presentarse a los primeros turnos de un examen oral según la metodología del profesor.
> 
> **Resumen Final:** El éxito en la materia depende de la **funcionalidad** y el **entendimiento**. La estética es secundaria; lo primordial es que los datos persistan correctamente, se utilicen funciones nativas y el desarrollador sea capaz de explicar la arquitectura de su solución.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 9 (11 06 26) - Desarrollo de aplicaciones para dispositivos móviles" src="https://www.youtube.com/embed/7zOqMb8oIzs?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1_D8NBIOnRXbbkbjxxZOdYdISs7VjWjJa/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1Thx6tGBiSLIBsujLJTYr74fNgTBu6Czf/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>