---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/3-desarrollo-de-sistemas-orientado-a-objetos/clase-12-miercoles-12-de-noviembre-de-2025-12-11-25-desarrollo-de-sistemas-orientado-a-objetos/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio: Desarrollo de Sistemas Orientado a Objetos e Integración de Inteligencia Artificial
> 
> Este documento constituye un material de estudio exhaustivo basado en la duodécima clase de la materia, centrado en la finalización de proyectos de desarrollo de software, la integración técnica de servicios de Inteligencia Artificial (IA) y las pautas para la presentación final de aplicaciones.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción y Contexto
> 
> El desarrollo de sistemas orientado a objetos en su etapa final requiere no solo la consolidación de la lógica de negocio y la base de datos, sino también la capacidad de integrar servicios externos y preparar una comunicación efectiva de los resultados. En esta fase, los proyectos transitan desde la codificación de funcionalidades básicas (como el CRUD y la autenticación) hacia la implementación de características avanzadas, como el uso de modelos de lenguaje (LLM) y la optimización del cierre de recursos en el servidor.
> 
> La relevancia de esta etapa radica en convertir una aplicación funcional en un producto robusto y presentable, abordando aspectos de seguridad (manejo de claves), experiencia de usuario (respuestas en tiempo real) y estabilidad del sistema (gestión de conexiones).
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual: Definiciones Clave
> 
> Para comprender la integración de IA y el manejo de servidores en Node.js, es fundamental dominar los siguientes términos:
> 
> - **Endpoint:** Punto de terminación de un canal de comunicación. En una API, es la URL específica (por ejemplo, `/api/chat`) a la que el cliente envía solicitudes para obtener una respuesta.
> - **API (Application Programming Interface):** Conjunto de reglas que permiten que dos aplicaciones se comuniquen entre sí. En este contexto, se utiliza para conectar el frontend con el backend y el backend con el proveedor de IA.
> - **LLM (Large Language Model):** Modelos de inteligencia artificial entrenados para procesar y generar texto (ej. DeepSeek, Google Gemma, ChatGPT).
> - **Stream (Flujo de datos):** Método de transmisión de datos que permite enviar y recibir información en fragmentos (_chunks_) de manera progresiva, sin esperar a que el mensaje completo esté generado.
> - **Variables de Entorno (Environment Variables):** Valores configurables externos a la aplicación (almacenados en un archivo `.env`) que permiten guardar información sensible como claves de API o credenciales de base de datos de forma segura.
> - **CORS (Cross-Origin Resource Sharing):** Mecanismo de seguridad que permite o restringe el acceso a recursos de un servidor desde un dominio diferente al que originó la solicitud.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: Integración de IA y Arquitectura de Servidor
> 
> ### 3.1 Estructura de la Integración de IA
> 
> La implementación de un módulo de chat o consulta de IA sigue un flujo de cuatro pasos:
> 
> 1. **Frontend (HTML/JS):** El usuario escribe una pregunta y el navegador envía un `POST` al servidor propio.
> 2. **Backend (Node.js/Express):** Recibe la pregunta, recupera la clave de API desde las variables de entorno y realiza una nueva solicitud al servidor de IA (como Open Router).
> 3. **Servidor de IA:** Procesa el _prompt_ y devuelve la respuesta, preferiblemente de forma fragmentada (_streaming_).
> 4. **Backend a Frontend:** El servidor propio retransmite los fragmentos de respuesta al navegador del usuario en tiempo real.
> 
> ### 3.2 El Proveedor "Open Router"
> 
> Se destaca el uso de **Open Router** como una herramienta unificada que permite acceder a múltiples modelos (gratuitos y pagos) mediante una sola suscripción y una misma estructura de código. Esto facilita el intercambio de modelos (por ejemplo, pasar de un modelo de Google a uno de DeepSeek) simplemente cambiando una línea de configuración.
> 
> ### 3.3 Gestión Segura de Datos con `.env` y `.gitignore`
> 
> Es una práctica profesional obligatoria separar las credenciales del código fuente:
> 
> - **Archivo** `**.env**`**:** Almacena constantes como `API_KEY` o puertos de conexión.
> - **Archivo** `**.gitignore**`**:** Debe incluir la referencia al archivo `.env`. Esto evita que las contraseñas se suban a repositorios públicos (como GitHub), protegiendo la seguridad del desarrollador y el presupuesto de la API.
> 
> ### 3.4 Cierre Elegante del Servidor (_Graceful Shutdown_)
> 
> Un error común es cerrar la aplicación abruptamente, dejando conexiones a la base de datos abiertas. Se implementan funciones como `server.close()` y `process.exit()` para asegurar que:
> 
> - El "pool" de conexiones se cierre correctamente.
> - Se liberen los recursos de memoria del sistema operativo.
> - No se acumulen procesos huérfanos que degraden el rendimiento del servidor.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Relación entre Conceptos y Estructuras
> 
> La conexión entre el frontend, el backend y la base de datos se articula mediante el intercambio de objetos JSON.
> 
> - **Dependencia Tecnológica:** Para que el servidor Express pueda interpretar los mensajes entrantes, es necesario explicitar el uso de `express.json()` y configurar los encabezados de tipo `application/json`.
> - **Memoria de Conversación:** Para que la IA tenga "memoria", el backend debe mantener un historial (un _array_ de mensajes) que se envía en cada nueva consulta. Se recomienda limitar este historial (por ejemplo, a las últimas 10 interacciones) para no exceder los límites de tokens o memoria.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Ejemplos Prácticos y Aplicación Real
> 
> ### Caso: Implementación de Chat en un E-commerce de Mascotas
> 
> Si un grupo desarrolla una tienda para mascotas, puede integrar un chatbot que:
> 
> 1. Reciba una consulta sobre alimentación.
> 2. El backend procese la solicitud mediante un endpoint `/api/chat`.
> 3. El sistema devuelva una respuesta detallada formateada en texto plano que el navegador muestra progresivamente en un área de texto (_textarea_).
> 
> ### Paso a paso para configurar el entorno:
> 
> 4. Instalar dependencias: `npm install dotenv cors node-fetch`.
> 5. Crear el archivo `.env` con la clave de API.
> 6. Configurar `const.js` para exportar las variables de entorno.
> 7. Implementar el endpoint en el archivo principal de Express (ej. `express0.js`).
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores Comunes y Aclaraciones
> 
> - **Confusión con el Formato de Respuesta:** Los modelos de IA suelen devolver texto plano con marcas de formato (como asteriscos o numerales). Si no se utiliza un "parseador" en el frontend, el usuario verá estas marcas.
> - **No usar** `**.gitignore**`**:** Subir el archivo `.env` al repositorio es un riesgo de seguridad crítico.
> - **Ignorar la Latencia:** Algunos modelos de IA son lentos. El uso de `Stream: true` es vital para que el usuario no piense que la aplicación se ha colgado mientras espera la respuesta completa.
> - **No cerrar el "Pool":** Si el servidor se reinicia muchas veces durante el desarrollo y no se cierran las conexiones a la base de datos, eventualmente se agotará el límite de conexiones permitidas.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Fechas Importantes y Avisos Académicos
> 
> |   |   |   |
> |---|---|---|
> |Fecha|Evento / Hito|Descripción Detallada|
> |**12 de noviembre**|Clase Actual|Revisión de proyectos, introducción a integración de IA y cierre de recursos.|
> |**19 de noviembre**|Penúltima Clase|Clase de repaso conjunto y trabajo en grupos sobre las aplicaciones.|
> |**26 de noviembre**|**Presentación Final**|Exposición de los proyectos terminados (última clase presencial).|
> |**28 de noviembre**|Entrega de Notas|El profesor debe presentar las notas finales este viernes.|
> 
> **Indicaciones para la Presentación Final:**
> 
> - **Duración:** Máximo 15 minutos por grupo.
> - **Formato:** Preferentemente presencial en aula con TV/HDMI. Se recomienda llevar una notebook.
> - **Contenido:** Demostración del funcionamiento (no es necesario mostrar cada función), explicar aspectos técnicos interesantes, dificultades encontradas y posibles proyecciones futuras.
> - **Plan B:** Es obligatorio estar preparados para imprevistos (falta de internet, fallas en el proyector). Se sugiere tener capturas de pantalla o un video de respaldo.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Síntesis y Conclusiones
> 
> La clase 12 consolida el aprendizaje técnico enfocándose en la **interconectividad**. La integración de IA no es un proceso aislado, sino que depende de una configuración sólida de servidores Express, un manejo seguro de variables de entorno y una gestión eficiente de flujos de datos (_streams_). La arquitectura orientada a objetos permite que estas nuevas funcionalidades se integren como módulos adicionales (clases o rutas) sin desestabilizar el sistema preexistente.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Para qué sirve el archivo `.env` y por qué no debe subirse a Git?
> 2. ¿Qué es un endpoint y cuál es un ejemplo común en una aplicación de chat?
> 3. ¿Qué función cumple la librería `dotenv` en Node.js?
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia entre recibir una respuesta de IA completa vs. recibirla por _streams_.
> 5. ¿Por qué es necesario configurar CORS en el servidor si el frontend y el backend están en dominios o puertos distintos?
> 6. ¿Cómo se logra que una IA mantenga el contexto de una conversación previa?
> 
> ### Nivel Avanzado
> 
> 7. Describa el proceso de _Graceful Shutdown_ y por qué es crítico para la gestión del "pool" de conexiones de una base de datos.
> 8. Analice las ventajas de utilizar Open Router frente a conectarse directamente a la API de un proveedor único como OpenAI o Google.
> 9. En el código de servidor, ¿qué importancia tiene el comando `express.json()` al trabajar con solicitudes POST de IA?

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 12 - Desarrollo de sistemas orientado a objetos" src="https://www.youtube.com/embed/8H2NCm4iSns?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1pNkb9aHsPL7E4YwnTbRFfUXmaKuMcIbk/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1PiD-kyAlStaxYEfK-dvmGAa4eu7VpAEC/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>