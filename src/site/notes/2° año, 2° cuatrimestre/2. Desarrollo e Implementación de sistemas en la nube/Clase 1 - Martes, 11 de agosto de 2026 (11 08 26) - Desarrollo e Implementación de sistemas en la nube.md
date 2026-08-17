---
{"dg-publish":true,"permalink":"/2-ano-2-cuatrimestre/2-desarrollo-e-implementacion-de-sistemas-en-la-nube/clase-1-martes-11-de-agosto-de-2026-11-08-26-desarrollo-e-implementacion-de-sistemas-en-la-nube/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Desarrollo e Implementación de Sistemas en la Nube: Guía Integral de Aprendizaje
> 
> Este documento constituye una síntesis exhaustiva de los fundamentos, metodologías y aspectos técnicos abordados en la materia de Desarrollo e Implementación de Sistemas en la Nube. Está diseñado para funcionar como un material de estudio autosuficiente que abarca desde la organización profesional del trabajo hasta la arquitectura técnica de las aplicaciones modernas.
> 
> ## 1. Introducción General
> 
> La materia se centra en la integración de conocimientos técnicos previos (Frontend y Backend) para simular un entorno de trabajo profesional real. El objetivo primordial no es meramente la codificación, sino la comprensión de cómo los sistemas conversan entre sí a través de Internet, cómo se estructuran bajo estándares profesionales y cómo se implementan en infraestructuras de nube.
> 
> ### Contexto del Tema
> 
> La materia se sitúa en la etapa final de la formación técnica, buscando que el estudiante actúe en un escenario de "práctica profesionalizante". Se busca que los alumnos dejen de ver las aplicaciones como entes aislados y comiencen a gestionarlas como servicios interconectados que deben ser hosteados, monitoreados y securizados.
> 
> ### Importancia y Relevancia
> 
> En el mercado laboral actual, un desarrollador no solo debe saber programar; debe comprender la arquitectura de la comunicación (Protocolo HTTP, REST), la gestión de entornos (Nube, servidores estáticos vs. dinámicos) y la dinámica de trabajo en equipo (liderazgo técnico, manejo de requerimientos).
> 
> ## 2. Marco Conceptual
> 
> ### Definición de Conceptos Clave
> 
> - **Sistemas en la Nube:** Aplicaciones alojadas en servidores remotos que interactúan entre sí a través de la red pública.
> - **Líder Técnico:** Rol que asume el docente, guiando a los grupos en la toma de decisiones arquitectónicas y validando los requerimientos frente a "clientes" (reales o simulados).
> - **Práctica Profesionalizante:** Metodología que busca replicar situaciones de campo, incluyendo el manejo de la frustración ante cambios de requerimientos o proyectos que no llegan a producción.
> - **Acoplamiento:** El error de diseño donde un servicio depende excesivamente de los datos o procesos internos de otro. Se busca evitar esto mediante la independencia de bases de datos por cada servicio.
> 
> ## 3. Desarrollo del Tema: Arquitectura y Comunicación
> 
> ### La Evolución de la Programación Web
> 
> Existe una distinción fundamental entre el paradigma de los años 90 y el actual:
> 
> |   |   |   |
> |---|---|---|
> |Característica|Programación de los 90 (HTML Dinámico)|Programación Actual (SPA / API-First)|
> |**Generación de Contenido**|El servidor procesa reglas de negocio y arma el HTML antes de enviarlo.|El servidor envía contenido estático (texto) y el cliente lo procesa.|
> |**Interacción**|Cada clic suele recargar la página completa.|Solo viajan los datos necesarios (JSON) a través de llamadas asíncronas.|
> |**Carga de Servidor**|Alta, el servidor debe renderizar para cada usuario.|Baja, el servidor solo sirve archivos estáticos o datos puros.|
> |**Experiencia de Usuario**|Más lenta y con interrupciones visuales.|Fluida, similar a una aplicación nativa.|
> 
> ### El Protocolo HTTP como Piedra Angular
> 
> Toda la comunicación en la nube se basa en el protocolo HTTP (Hypertext Transfer Protocol). Es el lenguaje que permite que un Frontend (cliente) le pida información a un Backend (servidor).
> 
> #### Anatomía de una URL (Uniform Resource Locator)
> 
> Una URL no es solo una dirección; es una instrucción jerárquica:
> 
> 1. **Protocolo:** `http://` o `https://` (la "s" indica seguridad/encriptación).
> 2. **Dominio:** Traduce un nombre (ej. `facebook.com`) a una dirección IP física mediante un sistema llamado DNS.
> 3. **Puerto:** El "punto de entrada" a la aplicación en el servidor. Por defecto, HTTP usa el puerto 80 y HTTPS el 443.
> 4. **Contexto/Ruta:** Identifica la aplicación o sección específica dentro del servidor (ej. `/api`).
> 5. **Recurso:** Sustantivo en plural que indica qué entidad queremos manipular (ej. `/usuarios`).
> 6. **Parámetros (Query Params):** Filtros adicionales que comienzan con `?` (ej. `?edad=15`).
> 
> ### Métodos HTTP y REST
> 
> El protocolo REST define cómo deben hablarse los sistemas. Se basa en el uso correcto de verbos o métodos:
> 
> - **GET:** Obtener recursos. No debe modificar nada en el servidor.
> - **POST:** Crear un nuevo recurso.
> - **PUT:** Actualizar un recurso existente de forma completa.
> - **PATCH:** Actualización parcial de un recurso.
> - **DELETE:** Eliminar un recurso.
> - **OPTIONS:** Consultar qué capacidades o métodos permite el servidor.
> 
> ## 4. Relaciones entre Conceptos y Estructura de Proyecto
> 
> ### Interconexión de Servicios
> 
> En un proyecto típico de esta materia, se espera una estructura de microservicios o servicios divididos:
> 
> - **Frontend:** Hosteado en servidores de contenido estático. Su función es renderizar la interfaz y llamar a las APIs.
> - **Backend A y Backend B:** Deben ser independientes. Cada uno debe tener su propia base de datos.
> - **Comunicación:** El Frontend puede llamar a ambos Backends. Un Backend puede llamar a otro Backend para pedir información, pero **nunca** debe acceder directamente a la base de datos ajena.
> 
> ### El Ciclo de Request y Response
> 
> Cada interacción consta de dos partes:
> 
> 1. **Request (Solicitud):** Contiene el método, la URL, los _Headers_ (metainformación como el formato JSON) y el _Body_ (los datos enviados).
> 2. **Response (Respuesta):** Contiene un Código de Estado, _Headers_ y un _Body_ (generalmente el JSON resultante).
> 
> #### Códigos de Estado HTTP
> 
> - **2xx (Éxito):** Todo salió bien (ej. 200 OK, 201 Created).
> - **3xx (Redirección):** El recurso se movió.
> - **4xx (Error del Cliente):** El cliente hizo algo mal (ej. 404 Not Found, 400 Bad Request).
> - **5xx (Error del Servidor):** El servidor falló (ej. 500 Internal Server Error).
> 
> ## 5. Ejemplos Prácticos
> 
> ### Caso 1: Kiosco 25 (Escaneo de productos)
> 
> Si un sistema de inventario escanea un código de barras para obtener un precio:
> 
> - **URL:** `https://kiosco25.com:443/api/productos?barcode=12345`
> - **Acción:** El Frontend hace un `GET`. El servidor busca en la base de datos de productos y devuelve un JSON con el precio.
> - **Navegación de Recursos:** Si quiero el historial de stock de un producto específico, la URL profesional sería `/productos/1/stock`.
> 
> ### Caso 2: Facebook y Usuarios
> 
> Para buscar usuarias de 15 años de género femenino:
> 
> - **URL:** `https://facebook.com/usuarios?edad=15&genero=femenino`
> - **Lógica:** Si no se encuentran resultados, el sistema **no** debe dar error 404, sino devolver un 200 con una lista vacía, ya que el recurso "usuarios" existe, pero el filtro no arrojó datos.
> 
> ## 6. Errores Comunes y Confusiones
> 
> - **URLs Verbos:** Es un error común poner verbos en la URL (ej. `/obtenerListaUsuarios`). Lo correcto es usar el método `GET` sobre el recurso `/usuarios`.
> - **Acoplamiento de DB:** Compartir la misma base de datos entre dos Backends diferentes es una mala práctica que impide el escalamiento independiente.
> - **Confusión de Errores:** Interpretar una búsqueda sin resultados como un error de sistema (500) en lugar de una regla de negocio exitosa con resultado vacío.
> - **Uso de Datos Locales:** El Frontend no debe tener bases de datos persistentes principales, pero puede usar almacenamiento local (cache) para mejorar la performance y no llamar al Backend innecesariamente por datos estáticos (como imágenes o listas que no cambian).
> 
> ## 7. Síntesis y Conclusiones
> 
> La materia propone un cambio de mentalidad: de "programador de código" a "arquitecto de soluciones en la nube". Los puntos clave a recordar son:
> 
> - La comunicación debe seguir los estándares **REST** y el protocolo **HTTP**.
> - Cada servicio debe ser **independiente** y dueño de sus datos.
> - La arquitectura moderna separa el **contenido estático** de la **lógica de datos (APIs)**.
> - El trabajo profesional requiere documentar (Diagramas de secuencia) antes de codificar.
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia principal entre el protocolo HTTP y HTTPS?
> 2. ¿Qué significa que un servidor sea de "contenido estático"?
> 3. Nombre los 4 métodos HTTP más utilizados y su función.
> 
> ### Nivel Intermedio
> 
> 4. Describa las partes que componen una URL profesional.
> 5. ¿Por qué es una mala práctica que un Backend consulte directamente la base de datos de otro Backend?
> 6. Explique la diferencia entre un error de la serie 400 y uno de la serie 500.
> 
> ### Nivel Avanzado
> 
> 7. Explique el concepto de "Path Variables" vs "Query Parameters" y cuándo usar cada uno según los estándares de navegación de recursos.
> 8. ¿Cómo influye el uso de un sistema de monitoreo empresarial en la decisión de programar siguiendo estrictamente los códigos de estado HTTP?
> 9. Describa el ciclo completo desde que un usuario ingresa una URL en el navegador hasta que visualiza los datos, mencionando DNS, IP, Puertos y Renderización.
> 
> ## 9. Fechas Importantes y Avisos Académicos
> 
> A continuación, se detallan las fechas y pautas organizativas extraídas de la sesión:
> 
> |   |   |   |
> |---|---|---|
> |Fecha|Evento / Tipo|Descripción|
> |**Martes 10 de Noviembre**|**Presentación Final**|Fecha límite principal para la entrega y exposición del proyecto.|
> |**17 y 24 de Noviembre**|**Instancias de Recuperación**|Semanas adicionales para grupos que necesiten completar detalles o no hayan llegado al 10/11.|
> |**Clase 15 (Final)**|**Presencialidad Obligatoria**|Segunda y última clase presencial del cuatrimestre para la entrega.|
> 
> ### Recordatorios e Indicaciones del Profesor:
> 
> - **Grupos:** El tamaño ideal es de **3 personas** (1 Frontend y 2 Backends). Se admiten grupos de 2 o 4 con previo aviso, pero esto incrementa la carga de trabajo individual.
> - **Metodología:** El profesor actuará como **Líder Técnico**. Las clases se basarán en resolver dudas de desarrollo y profundizar en teoría según las necesidades de los proyectos.
> - **Evaluación:** Se evalúa el proceso y la arquitectura (Diagramas de secuencia, correcto uso de REST) más que solo el código fuente.
> - **Integración de Materias:** Se recomienda fuertemente utilizar el mismo proyecto para las materias de Frontend y Backend, unificando esfuerzos para reducir la carga académica total.
> - **Recurse:** La materia se promociona o se recursa; no suele haber instancias de examen final tradicional debido a la naturaleza práctica del contenido.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 1 (11 08 26) - Desarrollo e Implementación de sistemas en la nube" src="https://www.youtube.com/embed/3irk_e898Ho?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1QcG4Y0ZD0B1lvZqGQ3mteDn4yYLDs2XN/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1QJopQMiEMLU5AhbnV-SwLr41Op4Iz546/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>