---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/4-desarrollo-de-aplicaciones-para-dispositivos-moviles/clase-4-jueves-23-de-abril-de-2026-23-04-26-desarrollo-de-aplicaciones-para-dispositivos-moviles/","dg-note-properties":{}}
---


> [!quote]- Resumen
> # Guía de Estudio: Navegación y Arquitectura en Aplicaciones Móviles
> 
> Este documento constituye un material de estudio integral basado en la teoría y práctica sobre el desarrollo de aplicaciones móviles, centrándose específicamente en los mecanismos de navegación entre pantallas, el paso de parámetros y la configuración de interfaces mediante pilas y pestañas.
> 
> ## 1. Introducción General
> 
> En el desarrollo de aplicaciones móviles, la navegación no es simplemente un cambio de vista, sino la gestión de un flujo de estados y memoria. A diferencia de la web tradicional, donde cada URL recarga recursos, las aplicaciones móviles gestionan las pantallas mediante estructuras de datos específicas que permiten una experiencia fluida y coherente para el usuario.
> 
> ### Importancia y Relevancia
> 
> Comprender la navegación es crítico por dos razones:
> 
> 1. **Experiencia de Usuario (UX):** Define cómo el usuario se desplaza y regresa en la aplicación.
> 2. **Gestión de Memoria:** Cada pantalla en una "pila" consume recursos. Una mala gestión puede llevar a que el sistema operativo cierre la aplicación por falta de memoria.
> 
> ## 2. Marco Conceptual: Definiciones desde Cero
> 
> Para dominar la navegación en React Native, es fundamental entender los siguientes conceptos:
> 
> |Concepto|Definición|Analogía|
> |---|---|---|
> |**Stack (Pila)**|Estructura donde las pantallas se colocan una encima de otra. Solo la de arriba es visible.|Un mazo de cartas o una pila de platos.|
> |**Navigator Container**|El "cerebro" o contenedor principal que gestiona el estado de navegación de toda la aplicación.|El director de una orquesta.|
> |**Stack Navigator**|Mecanismo que permite apilar pantallas y proporciona automáticamente el botón "atrás".|El historial de navegación.|
> |**Tab Navigator**|Navegación mediante pestañas (usualmente inferiores) que permite cambiar entre secciones principales.|El menú de secciones de una revista.|
> |**Parámetros de Ruta**|Información que se envía de una pantalla a otra durante la navegación.|Una carta enviada de una oficina a otra.|
> 
> ## 3. Desarrollo del Tema: Sistemas de Navegación
> 
> ### 3.1. Navegación por Stack (Pila)
> 
> Es el método estándar en aplicaciones móviles. Cuando se abre una pantalla nueva, esta se coloca sobre la anterior. Al presionar "atrás", la pantalla actual se "desmonta" (se quita de la pila) y se revela la que estaba debajo.
> 
> **Características clave:**
> 
> - **Historial:** Mantiene el orden exacto de navegación.
> - **Memoria:** Si se navega infinitamente hacia adelante sin desapilar, el consumo de memoria aumenta. El sistema operativo puede "romper" la pila si se queda sin recursos.
> - **Comportamiento:** Si desde una pantalla "D" se llama a la pantalla "A" (que ya estaba en la base), se crea una _nueva instancia_ de "A" sobre "D", no se regresa a la base original, a menos que se use una función específica para retroceder.
> 
> ### 3.2. Navegación por Pestañas (Bottom Tabs)
> 
> A diferencia del Stack, las pestañas no suelen apilar pantallas en el sentido tradicional de "historial".
> 
> - Se utilizan para las secciones principales de la app.
> - Las pantallas suelen estar siempre disponibles y solo se ocultan o muestran.
> - No generan automáticamente un botón de "volver atrás" porque el usuario cambia de contexto lateralmente.
> 
> ### 3.3. Pasaje de Parámetros
> 
> La comunicación entre pantallas se realiza mediante dos objetos fundamentales que recibe cada componente de pantalla:
> 
> 1. **Navigation Prop:** Permite ejecutar acciones (ej: `navigate`, `goBack`).
> 2. **Route Prop:** Contiene la información de la ruta actual, incluyendo los `params` (parámetros).
> 
> **Punto Clave:** Para que TypeScript reconozca los parámetros, es necesario definirlos en un tipo (ej: `RootStackParamList`), especificando qué pantallas aceptan parámetros y de qué tipo son (ej: `undefined` si no recibe, o un objeto con los tipos de datos).
> 
> ## 4. Relación entre Conceptos y Estructura Técnica
> 
> El flujo lógico para implementar la navegación sigue esta jerarquía:
> 
> 1. **Definición de Tipos:** Se declaran todas las pantallas y sus parámetros permitidos.
> 2. **Creación del Stack/Tab:** Se utiliza una función (como `createStackNavigator`) para generar el objeto de navegación.
> 3. **Configuración del App.tsx:** Se envuelve la lógica en un `NavigationContainer`.
> 4. **Inyección en Pantallas:** Cada pantalla recibe las propiedades para poder navegar o leer datos.
> 
> ### Diferencia en el uso de Propiedades
> 
> - `navigation`: Se usa para **ir** a otro lugar.
> - `route`: Se usa para **leer** dónde estoy y qué me enviaron.
> 
> ## 5. Ejemplos Prácticos Paso a Paso
> 
> ### Caso: Del Home al Detalle con Parámetros
> 
> 1. **En el Home:** Se define un botón con una acción.
>     - _Código lógico:_ `navigation.navigate('Details', { productId: 123, username: 'John' })`
> 2. **En el Destino (Details):** Se recuperan los datos.
>     - _Código lógico:_ Se extrae de `route.params` los valores `productId` y `username` para mostrarlos en pantalla.
> 
> ### Caso: Configuración de Iconos en Tabs
> 
> Para personalizar la navegación por pestañas, se utiliza la propiedad `screenOptions` en el Navigator. Esto permite:
> 
> - Ocultar el encabezado superior (`headerShown: false`).
> - Asignar iconos dinámicos según el nombre de la ruta (ej: si es 'Home', mostrar icono de casa).
> - Definir colores para el estado activo e inactivo de la pestaña.
> 
> ## 6. Errores Comunes y Aclaraciones
> 
> - **Confusión de Componentes Web vs. Móviles:** Un error frecuente es usar elementos de HTML/JavaScript web (como `alert` tradicional o etiquetas `button` en minúscula). En React Native, se deben usar componentes nativos (como `Alert` de la librería o `Button` con mayúscula) para asegurar la compatibilidad con el dispositivo.
> - **Pila Infinita:** Navegar siempre hacia adelante hacia la misma pantalla puede saturar la memoria. Se debe evaluar cuándo usar `navigate` (crear nueva) y cuándo usar funciones de retroceso.
> - **Parámetros Obligatorios:** Si una pantalla está definida para recibir parámetros y se navega hacia ella sin enviarlos, la aplicación puede fallar (romperse). Para evitarlo, se pueden usar `initialParams` como valores por defecto.
> - **TypeScript y nombres de propiedades:** En la configuración de rutas, las propiedades como `navigation` y `route` deben mantener sus nombres literales para que React Native pueda inyectarlas correctamente; cambiarlas por nombres personalizados puede causar errores de compilación.
> 
> ## 7. Síntesis y Conclusiones
> 
> - La **navegación móvil** se basa en un **Stack (pila)** para profundidad y **Tabs (pestañas)** para lateralidad.
> - El `NavigationContainer` es esencial para envolver toda la lógica.
> - El paso de información se gestiona mediante **parámetros de ruta**, que deben estar tipados para evitar errores de ejecución.
> - Es vital distinguir entre componentes **web** y **nativos**; el uso de los primeros en entornos móviles impedirá el funcionamiento correcto de la aplicación.
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de las fuentes, se identifican las siguientes indicaciones y fechas clave:
> 
> |Fecha|Tipo de Evento|Descripción Detallada|
> |---|---|---|
> |**30 de abril**|Clase Asincrónica|No habrá conexión presencial/sincrónica. Se debe trabajar el material de la "Clase 5" de forma autónoma.|
> |**5 o 6 de mayo**|Entrega de Tarea|Fecha límite para entregar el ejercicio correspondiente a la clase asincrónica (Menú de Pestañas).|
> |**Fin de cuatrimestre**|Defensa Final|Evaluación principal. Consiste en la defensa presencial de la aplicación y una "venta" de la misma.|
> |**18 de mayo**|Referencia Externa|Un estudiante menciona un parcial en esta fecha, pero el profesor aclara que **la materia no tiene parciales tradicionales**, sino entregas y defensa final.|
> 
> **Recordatorios Importantes:**
> 
> - **Promoción vs. Final:** La materia es promocionable mediante el trabajo práctico final. El examen final es descrito como "imposible" debido a que requiere la defensa del código más una carga teórica profunda en una sola semana; se recomienda fuertemente buscar la promoción.
> - **Metodología de Entrega:** Las tareas se suben a la sección de "Trabajos Prácticos". Formatos válidos: link a repositorio GitHub (preferido), archivo ZIP con el código, o documento PDF con el código pegado.
> - **Calificaciones Parciales:** Las notas de las tareas asincrónicas funcionan como indicadores de progreso y pueden sumar puntos, pero lo fundamental es la defensa del proyecto final.
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Qué es un Stack Navigator y cuál es su analogía principal?
> 2. ¿Cuál es la función del `NavigationContainer`?
> 3. ¿En qué parte del proyecto se definen las pantallas disponibles?
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia entre la propiedad `navigation` y la propiedad `route`.
> 5. ¿Qué sucede con la memoria del dispositivo si la pila de pantallas crece indefinidamente?
> 6. ¿Cómo se pasan parámetros de una pantalla A a una pantalla B?
> 
> ### Nivel Avanzado
> 
> 7. Compare la navegación por Stack con la navegación por Pestañas (Tabs) en términos de historial y flujo de usuario.
> 8. ¿Para qué sirven los `initialParams` y en qué escenario evitarían que la app se cierre inesperadamente?
> 9. ¿Por qué es un error crítico usar componentes web en el desarrollo con React Native?

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 4 (23 04 26) - Desarrollo de aplicaciones para dispositivos móviles" src="https://www.youtube.com/embed/NUsQT3AgVwU?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/11mpxXrC3hrrdqgM4w6xzkw4XlyqrPbkl/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1F_PU-t1pzGMVnMFYQYBsChxuhlZ2fk-y/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>