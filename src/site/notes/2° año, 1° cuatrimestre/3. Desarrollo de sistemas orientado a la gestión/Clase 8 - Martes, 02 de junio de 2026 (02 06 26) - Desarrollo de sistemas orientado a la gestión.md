---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/3-desarrollo-de-sistemas-orientado-a-la-gestion/clase-8-martes-02-de-junio-de-2026-02-06-26-desarrollo-de-sistemas-orientado-a-la-gestion/","dg-note-properties":{}}
---


> [!quote]- Resumen
> # Desarrollo de Sistemas Orientado a la Gestión: Autenticación, Seguridad y Roles
> 
> Este documento constituye un apunte técnico detallado sobre la implementación de medidas de seguridad, autenticación de usuarios y protección de rutas en el desarrollo de aplicaciones de gestión. El contenido se basa en las directrices académicas para la finalización de proyectos de software, enfocándose en la transición de un sistema con rutas expuestas a uno protegido y jerarquizado.
> 
> ## 1. Introducción y Contexto
> 
> En el desarrollo de sistemas orientados a la gestión, la exposición de rutas en internet sin protecciones adecuadas representa un riesgo crítico de seguridad. Sin un sistema de autenticación, cualquier usuario con conocimientos básicos podría manipular datos sensibles, como modificar productos, agregar categorías o eliminar registros.
> 
> El objetivo central de esta etapa del desarrollo es implementar una **autenticación mínima de usuarios** y proteger las rutas sensibles (creación, edición y eliminación) para que solo sean accesibles por usuarios con roles específicos, como el de administrador.
> 
> ## 2. Marco Conceptual y Definiciones Clave
> 
> Para comprender la implementación de seguridad, es necesario definir los conceptos fundamentales que intervienen en el proceso:
> 
> ### 2.1. Cifrado de Contraseñas (BCRYPT)
> 
> Nunca se deben almacenar contraseñas en texto plano en una base de datos. Si un tercero accede a la base de datos, las credenciales quedarían comprometidas.
> 
> - **Hash:** Es el proceso de convertir el texto de la contraseña en una cadena de caracteres encriptada e irreversible.
> - **BCRYPT:** Biblioteca utilizada para el hashing de contraseñas. Incluye funciones para encriptar durante el registro y para comparar el texto plano ingresado en el login contra el hash almacenado.
> 
> ### 2.2. JSON Web Token (JWT)
> 
> El JWT es un estándar para la creación de tokens de acceso. Funciona como un identificador de sesión.
> 
> - **Token:** Es una "llave" generada tras un inicio de sesión exitoso. El servidor la entrega al cliente y este debe presentarla en cada petición subsiguiente para demostrar su identidad.
> - **Expiración:** Los tokens tienen una validez temporal. Si el tiempo de sesión expira, el token se invalida y el usuario debe loguearse nuevamente.
> 
> ### 2.3. Middleware
> 
> Un **Middleware** es un programa o bloque de código que se ejecuta de forma intermedia, justo antes de que la petición llegue al controlador final. Su función es interceptar la solicitud para validar condiciones (como si el token es válido o si el usuario tiene permisos) antes de permitir el acceso al recurso.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: Implementación de Seguridad
> 
> ### 3.1. Modificación de la Entidad Usuario
> 
> Para gestionar la autorización, la tabla o entidad de **Usuarios** debe ser modificada para incluir un campo de discriminación de permisos.
> 
> - **Atributo "Rol":** Se implementa generalmente como un tipo enumerado (Enum) que distingue entre `Admin` (Administrador) y `Cliente` (Usuario normal).
> - **Identificación:** Este campo permite que el sistema decida si habilita o no funcionalidades específicas, como el acceso al panel de administración.
> 
> ### 3.2. Proceso de Autenticación (Login)
> 
> El flujo de autenticación sigue los siguientes pasos:
> 
> 1. El usuario envía sus credenciales (email y password) al endpoint de login.
> 2. El sistema utiliza la biblioteca BCRYPT para comparar la contraseña ingresada con el hash de la base de datos.
> 3. Si la comparación es exitosa (`true`), el servidor genera un **JSON Web Token (JWT)**.
> 4. El servidor responde con el token y, opcionalmente, datos básicos del usuario y su rol.
> 
> ### 3.3. Protección de Rutas mediante Middleware
> 
> En lugar de repetir el código de validación en cada controlador (productos, categorías, usuarios), se utiliza un **Middleware de Autenticación**.
> 
> |   |   |
> |---|---|
> |Fase|Acción del Middleware|
> |**Intercepción**|Lee el encabezado de la petición buscando la autorización.|
> |**Extracción**|Obtiene el JWT del encabezado `Authorization`.|
> |**Decodificación**|Valida si el token es legítimo y si no ha expirado.|
> |**Validación de Rol**|Verifica si el usuario tiene el rol necesario (ej. Admin) para la ruta específica.|
> |**Resolución**|Si es válido, permite el paso al controlador; si no, devuelve un error (401 o 403).|
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Ejemplos Prácticos y Aplicación
> 
> ### 4.1. Uso de Encabezados (Headers)
> 
> Para acceder a una ruta protegida (por ejemplo, un método POST para crear un producto), el cliente debe configurar la petición de la siguiente manera:
> 
> - **Content-Type:** `application/json`
> - **Authorization:** Debe llevar el prefijo `Bearer` seguido del token generado en el login.
>     - _Ejemplo:_ `Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...`
> 
> ### 4.2. Flujo en la Interfaz de Usuario (Frontend)
> 
> El comportamiento de la aplicación web varía según el rol detectado:
> 
> - **Usuario Anónimo:** Puede ver productos y agregar al carrito. Al momento del _checkout_ (finalizar compra), el sistema dispara un popup de login.
> - **Usuario Cliente:** Identificado para finalizar la facturación.
> - **Usuario Administrador:** Al loguearse, el sistema detecta su rol y habilita visualmente el acceso al **Panel de Administración**, donde se encuentran los ABM (Alta, Baja y Modificación) de productos, categorías y clientes.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Errores Comunes y Aclaraciones
> 
> - **Token No Provisto:** Ocurre cuando se intenta acceder a una ruta sensible sin enviar el encabezado de autorización. El sistema debe responder con un mensaje de "Acceso denegado".
> - **Token Expirado:** Es un mecanismo de seguridad. Si el usuario deja la sesión abierta mucho tiempo, el middleware invalidará el token y forzará un nuevo login.
> - **Confusión entre Autenticación y Autorización:**
>     - _Autenticación:_ ¿Quién eres? (Validado con el login/token).
>     - _Autorización:_ ¿Qué tienes permiso de hacer? (Validado mediante el rol de administrador).
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Síntesis y Conclusiones
> 
> La seguridad en un sistema de gestión no es opcional. La implementación de **BCRYPT** asegura que las contraseñas no sean legibles, mientras que **JWT** permite mantener sesiones seguras en un entorno web. El uso de **Middlewares** es la mejor práctica para centralizar la lógica de seguridad, evitando la redundancia de código y asegurando que las banderas de rol (Admin/Cliente) se verifiquen de manera consistente en todas las rutas sensibles de la API.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Por qué no se deben guardar las contraseñas en texto plano?
> 2. ¿Cuál es la función principal de un JSON Web Token (JWT)?
> 3. ¿Qué campo debe añadirse a la entidad Usuario para manejar permisos?
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia entre el prefijo `Bearer` y el contenido del token en un encabezado de autorización.
> 5. ¿Cuál es la ventaja de utilizar un Middleware en lugar de validar el usuario dentro de cada controlador?
> 6. ¿Qué sucede si un usuario intenta acceder a una ruta de administrador con un token válido pero con rol de "Cliente"?
> 
> ### Nivel Avanzado
> 
> 7. Describa el flujo completo desde que un usuario ingresa sus credenciales en el frontend hasta que logra modificar un producto en la base de datos.
> 8. ¿Cómo afecta la expiración de un token a la experiencia del usuario y por qué es necesaria para la seguridad?
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> A partir del análisis de la comunicación docente, se detallan los siguientes puntos relevantes para la organización de la materia:
> 
> - **Estado de Materiales:** La **Clase 10** ya se encuentra disponible para su visualización y descarga en el aula virtual.
> - **Entregas en Plataforma:**
>     - **Link de GitHub:** No es necesario subir el link en cada clase individualmente, ya que se utiliza el mismo repositorio para el proyecto. El objetivo actual es avanzar en el desarrollo.
>     - **Obligatoriedad:** El docente ha configurado las últimas clases para que la entrega **no sea obligatoria** en la plataforma, con el fin de evitar confusiones mientras se completa el flujo mínimo del proyecto.
> - **Repositorio de Ejemplo:** El profesor ha comiteado un repositorio actualizado con el ejemplo de implementación de seguridad, autenticación y middlewares para que los alumnos lo usen como referencia y comparen con sus propios desarrollos.
> - **Metodología de Seguimiento:** El docente realizará rondas por las oficinas virtuales (BigBlueButton) para revisar dudas puntuales sobre la implementación del código de seguridad y el rol de administrador.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 8 (02 06 26) - Desarrollo de sistemas orientado a la gestión" src="https://www.youtube.com/embed/2dnOs4L-oIM?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1e4u5-F4dJDX98X2iOeLzsCggMH7sHR_l/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1dNgfaGNit0sUEeYKaO6hJmvkeTDlsd-g/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>