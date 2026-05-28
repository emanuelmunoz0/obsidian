---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/4-desarrollo-de-aplicaciones-para-dispositivos-moviles/clase-8-jueves-28-de-mayo-de-2026-28-05-26-desarrollo-de-aplicaciones-para-dispositivos-moviles/","dg-note-properties":{}}
---


> [!quote]- Resumen
> # Metodología y Desarrollo de Aplicaciones Móviles: Guía Integral de Implementación y Mejora
> 
> Este documento constituye una síntesis exhaustiva de los conocimientos técnicos y metodológicos abordados en la sesión académica sobre el desarrollo de aplicaciones móviles. Se centra en la resolución de problemas de diseño, la gestión de la persistencia de datos y la integración de componentes de interfaz de usuario (UI), proporcionando un marco teórico-práctico para la culminación de proyectos de software.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción y Contexto del Desarrollo
> 
> El desarrollo de aplicaciones móviles atraviesa una fase crítica donde la teoría se traduce en implementación práctica. En este estadio del ciclo de aprendizaje, el enfoque principal se desplaza de la adquisición de conceptos a la **iteración sobre dudas específicas** y la creación de una aplicación funcional para la entrega final.
> 
> ### Importancia y Relevancia
> 
> El dominio de los componentes de interfaz y la lógica de negocio es fundamental para crear productos que no solo funcionen, sino que ofrezcan una experiencia de usuario (UX) profesional. La capacidad de diagnosticar errores de visualización en diferentes plataformas (Web vs. Mobile) y de gestionar datos de forma local o remota define la calidad de un desarrollador senior en el mercado actual.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual y Definiciones Clave
> 
> Para abordar el desarrollo con precisión, es necesario clarificar términos fundamentales que suelen generar confusión:
> 
> - **Responsividad (Layout):** Capacidad de la interfaz para adaptarse a distintos tamaños de pantalla. En entornos como React Native, esto se logra mediante el uso de _Flexbox_ y dimensiones porcentuales.
> - **Alert (Alerta de Sistema):** Componente nativo del sistema operativo que interrumpe la ejecución del código para mostrar un mensaje. Es funcional pero ofrece nula personalización.
> - **Modal:** Componente de interfaz que se superpone a la pantalla actual. A diferencia del Alert, es altamente personalizable en forma, color, tamaño y animación.
> - **SQLite:** Motor de base de datos relacional ligero que se almacena en un archivo local dentro del dispositivo. Es el estándar para persistencia de datos en aplicaciones móviles sin dependencia constante de internet.
> - **Prompting (en Programación):** Instrucción dada a una Inteligencia Artificial para generar código. Requiere supervisión técnica constante ("delegar la tarea, no la responsabilidad").
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: Interfaz de Usuario y Estilos
> 
> ### Optimización de Layouts y Visualización
> 
> Uno de los problemas recurrentes es la discrepancia visual entre la versión Web y la versión Mobile de una aplicación.
> 
> #### Caso de Estudio: Fondos y Contenedores
> 
> Si una imagen de fondo se corta o no ocupa el espacio deseado en la versión Web, el problema suele radicar en la definición del contenedor.
> 
> - **Solución Técnica:** Se debe aplicar `width: 100%` y `height: 100%` al estilo del contenedor de la imagen (`ImageBackground`). Esto asegura que la imagen se estire para ocupar todo el espacio disponible que el _flex_ le asigna, independientemente de la resolución original de la imagen.
> - **Ajustes de UX:** En dispositivos con pantallas curvas, es vital evitar colocar botones en los extremos absolutos. Se recomienda el uso de **Padding** (relleno interno) o **Margin** (margen externo) para dar "aire" a los elementos y asegurar su accesibilidad.
> 
> ### Interacción Avanzada: Alerts vs. Modals
> 
> |   |   |   |
> |---|---|---|
> |Característica|Alert (Nativo)|Modal (Personalizado)|
> |**Origen**|Sistema Operativo|Definido por el Desarrollador|
> |**Bloqueo**|Sincrónico (frena la ejecución)|Asincrónico (el hilo sigue)|
> |**Personalización**|Nula|Total (color, forma, tamaño)|
> |**Uso Ideal**|Notificaciones críticas simples|Formularios, Pop-ups de marca|
> 
> #### Animaciones en Modals
> 
> Los modales permiten definir el tipo de transición al aparecer:
> 
> 1. **Fade:** Desvanecimiento gradual (el más utilizado por su elegancia).
> 2. **Slide:** Desplazamiento (desde arriba, abajo o laterales).
> 3. **None:** Aparición instantánea sin transición.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Persistencia de Datos: SQLite y Gestión Local
> 
> La integración de una base de datos local es un paso avanzado que mejora la robustez de la aplicación.
> 
> ### Implementación de SQLite con Expo
> 
> Para utilizar bases de datos locales, se emplea la librería `expo-sqlite`.
> 
> 4. **Apertura/Creación:** Se define un archivo `.db` que residirá en el almacenamiento del teléfono.
> 5. **Inicialización:** Es crucial ejecutar un comando `CREATE TABLE IF NOT EXISTS` al inicio de la aplicación para asegurar que la estructura de datos exista antes de cualquier consulta.
> 6. **Operaciones SQL:** Se utilizan sentencias estándar (`SELECT`, `INSERT`, `UPDATE`) para manipular los datos.
> 
> **Nota Crítica:** SQLite es una solución para dispositivos móviles. En entornos de previsualización Web, estas funciones generalmente no se ejecutan o fallan, por lo que las pruebas finales deben realizarse obligatoriamente en un dispositivo físico o emulador móvil.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. El Rol de la Inteligencia Artificial en el Código
> 
> El mercado laboral está virando hacia un modelo donde la IA genera el código base y el humano supervisa.
> 
> - **Supervisión Senior:** Empresas como Amazon o Google requieren que, aunque la IA escriba el código, ingenieros experimentados den el visto bueno.
> - **Riesgo de Delegación:** No entender el código que genera la IA puede llevar a desastres en producción (ej. borrado accidental de bases de datos).
> - **Aprendizaje:** El estudiante debe "aprender a gatear" (escribir código manualmente) para poder "correr" (supervisar IAs). En la materia, se permite el uso de IA, pero es obligatorio que el alumno pueda explicar cada línea de su funcionamiento.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores Comunes y Aclaraciones
> 
> 1. **Confusión entre Local y Web:** Muchos desarrolladores asumen que si algo funciona en el navegador, funcionará en el móvil. Esto es falso para componentes como SQLite o permisos de cámara.
> 2. **Manejo de Errores de Conexión:** Al conectar con bases de datos externas (como Supabase o backends locales), un error frecuente es no manejar el `404` o errores de red, dejando al usuario sin feedback visual.
> 3. **Cierre de Sesión (Login):** El login no es solo por seguridad; su propósito pedagógico es aprender a **pasar parámetros entre pantallas** (ej. pasar el ID del usuario logueado para mostrar sus datos específicos en la siguiente vista).
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Síntesis y Conclusiones
> 
> - **Diseño:** Priorizar dimensiones porcentuales y márgenes de seguridad para pantallas curvas.
> - **Funcionalidad:** Elegir Modales sobre Alerts si se requiere una estética coherente con la marca.
> - **Datos:** SQLite es la herramienta preferida para persistencia local en móviles, requiriendo inicialización programática.
> - **Responsabilidad:** El uso de IA es una herramienta de productividad, pero la responsabilidad técnica del código recae exclusivamente en el desarrollador.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> - **Próxima Clase (Próximo jueves):** **No habrá sesión sincrónica.** Se otorga el tiempo para trabajo autónomo y avance del proyecto.
> - **Siguiente Encuentro (En 15 días):** Clase de consulta obligatoria con avances tangibles.
> - **Entrega Final:** Se debe realizar la presentación mediante un **Código QR**. El profesor escaneará el código y probará la aplicación en su propio dispositivo.
> - **Excepción Especial:** Solo aquellos alumnos con restricciones de seguridad extremas en sus equipos (previamente autorizados) podrán presentar en formato Web.
> - **Requisito de Login:** La aplicación debe contar con un login funcional para evaluar la administración de parámetros entre pantallas.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia principal entre el uso de `Padding` y `Margin` en una interfaz móvil?
> 2. ¿Por qué una imagen de fondo podría verse correctamente en un celular pero cortada en una web?
> 3. ¿Qué comando SQL es esencial ejecutar al iniciar una aplicación que usa SQLite?
> 
> ### Nivel Intermedio
> 
> 4. Explique por qué un `Alert` nativo puede detener la ejecución de otras funciones visuales (como cambiar el color de fondo).
> 5. Describa el proceso para hacer que un modal sea transparente y tenga una animación de "Fade".
> 6. ¿Cuál es el objetivo académico de incluir un Login en el proyecto, más allá de la seguridad?
> 
> ### Nivel Avanzado
> 
> 7. Analice el impacto de la Inteligencia Artificial en el flujo de trabajo de un desarrollador según las tendencias de empresas líderes (Amazon/Google). ¿Qué significa "delegar la tarea pero no la responsabilidad"?
> 8. Si SQLite no funciona en entorno Web, ¿qué estrategias de prueba debería adoptar un desarrollador para asegurar que su lógica de base de datos es correcta antes de compilar para móvil?

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 8 (28 05 26) - Desarrollo de aplicaciones para dispositivos móviles" src="https://www.youtube.com/embed/lMLK2OiphXE?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1pqPQvuuc-5OhbefKQnymRMOJhFD0eXRe/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1Xio0AxiPz88mV_aUlAp-IAoCvvHLUoUI/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>