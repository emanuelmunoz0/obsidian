---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/4-desarrollo-de-aplicaciones-para-dispositivos-moviles/clase-7-jueves-21-de-mayo-de-2026-21-05-26-desarrollo-de-aplicaciones-para-dispositivos-moviles/","dg-note-properties":{}}
---


> [!quote]- Resumen
> # Guía de Estudio: Desarrollo de Aplicaciones Móviles con React Native y Expo
> 
> Este documento constituye un compendio exhaustivo y detallado sobre los conceptos, técnicas y requisitos discutidos en el ámbito del desarrollo de aplicaciones móviles, con un enfoque particular en el uso de React Native y la plataforma Expo. Funciona como material de estudio principal para comprender la arquitectura de dispositivos móviles, el diseño de interfaces y los criterios de evaluación académica.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> El desarrollo de aplicaciones móviles contemporáneo se apoya en marcos de trabajo (frameworks) que permiten la creación de interfaces ricas y la interacción con el hardware del dispositivo. La arquitectura de estos sistemas es multicapa, lo que exige que el desarrollador comprenda no solo la lógica de programación, sino también cómo su código se comunica con el sistema operativo y los componentes físicos (sensores, cámara, GPS). El objetivo primordial es transitar de un conocimiento teórico hacia la implementación de una aplicación funcional que interactúe de manera nativa con el entorno del dispositivo.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual y Definiciones Clave
> 
> Para abordar el desarrollo móvil, es fundamental desglosar términos que suelen utilizarse de manera indistinta pero que poseen significados técnicos específicos.
> 
> ### 2.1 El Concepto de "Android"
> 
> El término "Android" está sobrecargado y se refiere a tres entidades diferentes:
> 
> - **Sistema Operativo:** El software base que gestiona el hardware.
> - **Lenguaje de Programación:** El conjunto de reglas y sintaxis (históricamente asociado a Java y ahora Kotlin).
> - **Runtime:** El entorno de ejecución donde corren las aplicaciones.
> 
> ### 2.2 Arquitectura del Teléfono (Modelo de Capas)
> 
> Un dispositivo móvil funciona mediante un sistema de "pasamanos" entre diferentes capas:
> 
> 1. **Kernel (Linux en Android):** Contiene los _drivers_ o controladores de hardware (pantalla, cámara, memoria).
> 2. **Librerías y Frameworks:** Capas intermedias que gestionan datos y medios (SQLite para bases de datos, WebKit para navegación web, Media Framework para videos y fotos).
> 3. **Framework de Aplicaciones Nativas:** Administradores de alto nivel como el _Activity Manager_ (gestiona las pantallas), el _Notification Manager_ y el _Location Manager_ (GPS).
> 4. **Aplicaciones:** La capa superior donde residen las apps de usuario y las del sistema (Contactos, Navegador, Home).
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: Diseño e Interactividad
> 
> ### 3.1 Estilos y Posicionamiento de Elementos
> 
> En React Native, el diseño de la interfaz de usuario (UI) implica decidir entre flexibilidad y precisión absoluta.
> 
> - **Posicionamiento Absoluto:** Permite superponer elementos (como iconos o tildes en las esquinas de un botón) usando coordenadas en píxeles (`top`, `left`, `bottom`).
>     - _Riesgo:_ No siempre se ajustan bien al cambiar entre dispositivos de diferentes tamaños de pantalla.
> - **Layout Flexbox:** Es la forma recomendada de organizar componentes. Utiliza contenedores (`View`) con propiedades de alineación y justificación para asegurar que la app sea responsiva.
> 
> ### 3.2 Funcionalidad Nativa: El Núcleo del Proyecto
> 
> Un requisito crítico en el desarrollo avanzado es la comunicación con funciones nativas. Una función es nativa cuando la aplicación interactúa con:
> 
> - **Hardware físico:** Cámara, micrófono, giroscopio, GPS, parlantes.
> - **Aplicaciones del sistema:** Llamar a un número de teléfono, abrir el navegador del sistema, conectarse con la agenda de contactos o enviar un mensaje vía WhatsApp.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Diferencia Crítica: API Externa vs. Aplicación Nativa
> 
> Existe una distinción vital entre consumir datos de una API y realizar una interacción nativa. El siguiente cuadro comparativo aclara esta confusión común:
> 
> |   |   |   |
> |---|---|---|
> |Acción|Tipo de Interacción|Descripción|
> |**Dibujar un mapa mediante API**|Consumo de Servicio|La app recibe datos de Google Maps y los dibuja dentro de un `View` propio. El control es de la app.|
> |**Saltar a Google Maps**|**Interacción Nativa**|La app delega el control al sistema operativo para que abra la aplicación oficial de mapas y realice una acción (como iniciar una ruta).|
> 
> **Nota Académica:** Para fines de evaluación, se prioriza que el estudiante logre que la aplicación "salga" de su entorno para usar una herramienta del teléfono o acceda a componentes físicos, demostrando la comprensión de los _intents_ o puentes de comunicación del dispositivo.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Errores Comunes y Aclaraciones
> 
> 1. **Confusión de Unidades:** Usar píxeles fijos para posiciones absolutas en lugar de unidades porcentuales o flexbox puede romper el diseño en pantallas grandes o pequeñas.
> 2. **Dependencia de la Red:** Intentar probar funcionalidades que requieren GPS o mapas en entornos sin conexión o con bloqueos de seguridad (como redes corporativas).
> 3. **Versiones de Expo Go:** Existe una incompatibilidad frecuente si la versión de la aplicación instalada en el dispositivo (ej. 54.0.8) no coincide con el SDK configurado en el proyecto (ej. 55). Es vital mantener sincronizadas estas versiones para que el código se ejecute correctamente a través del código QR.
> 4. **Uso de la Web como referencia final:** Si bien usar el navegador para previsualizar la app acelera el desarrollo, las funciones nativas (cámara, sensores) solo pueden validarse fehacientemente en un dispositivo físico.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Síntesis y Conclusión
> 
> El éxito en la creación de una aplicación móvil bajo este esquema radica en la capacidad de integrar una interfaz visualmente coherente (usando estilos avanzados y componentes como `FlatList`) con una lógica que aproveche las capacidades del dispositivo. No se trata solo de mostrar información, sino de que la aplicación sea un ciudadano activo dentro del ecosistema del teléfono, interactuando con otras apps y con el hardware disponible.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Fechas Importantes y Avisos Académicos
> 
> A partir del análisis de las fuentes, se establecen los siguientes lineamientos para la finalización de la materia:
> 
> ### Cronograma Estimado de Clases (Junio)
> 
> - **28 de mayo:** Clase de dudas y avance de proyecto.
> - **Junio (4, 11, 18, 25):** Clases destinadas a la construcción de la app, resolución de dudas técnicas y revisiones previas. No se impartirá nueva teoría salvo pedido explícito de los alumnos.
> - **02 de julio:** **Examen Final / Entrega Presencial.** Presentación de la aplicación en el instituto.
> 
> ### Requisitos Técnicos Obligatorios para la Aplicación
> 
> 1. **Framework:** React Native con Expo y TypeScript.
> 2. **Navegación:** Implementar _Stack_ o _Tabs_ para moverse entre pantallas.
> 3. **Listados:** Uso de un `FlatList` dinámico (con funciones de alta, edición y baja de elementos).
> 4. **Feedback Visual:** Uso de `Alert`, `ActivityIndicator` (loader) y validaciones de datos.
> 5. **Interacción Nativa:** Debe interactuar con al menos un componente nativo (Cámara, GPS, Contactos, etc.).
> 6. **Persistencia:** Los datos pueden trabajarse en memoria (no es obligatoria una base de datos externa, aunque suma puntos el uso de `AsyncStorage`).
> 
> ### Entregables
> 
> - **Repositorio en GitHub:** Con todo el código fuente.
> - **Archivo README.md:** Explicando el funcionamiento y alcance del proyecto.
> - **Defensa Oral:** El estudiante debe correr la app en su máquina y el docente la probará mediante Expo Go.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuáles son los tres significados que se le atribuyen a la palabra "Android"?
> 2. ¿Qué diferencia hay entre un posicionamiento absoluto y un layout basado en Flexbox?
> 3. ¿Para qué sirve el componente `ActivityIndicator`?
> 
> ### Nivel Intermedio
> 
> 4. Explique el sistema de "pasamanos" en la arquitectura de un teléfono cuando una aplicación solicita acceso a la cámara.
> 5. ¿Por qué es preferible evitar el posicionamiento en píxeles fijos al diseñar para múltiples dispositivos?
> 6. ¿Qué elementos debe contener obligatoriamente el archivo `README.md` del proyecto final?
> 
> ### Nivel Avanzado
> 
> 7. Un estudiante integra Google Maps en su app mediante una API y dibuja los puntos de interés dentro de su propia interfaz. ¿Cumple esto con el requisito de "interacción nativa"? Justifique su respuesta.
> 8. Describa el proceso y los posibles problemas al intentar generar una build APK cuando se trabaja en entornos con restricciones de red (USB o Wi-Fi bloqueados).

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 7 (21 05 26) - Desarrollo de aplicaciones para dispositivos móviles" src="https://www.youtube.com/embed/LMQioxWzmVM?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/12chw0jQTEZrwEdcqjOlG7hPSBSFqsKgT/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1IWq7rnqtmFVzBlHW_ggbTD6qcnUAtU-t/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>