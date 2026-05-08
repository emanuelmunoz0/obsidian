---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/4-desarrollo-de-aplicaciones-para-dispositivos-moviles/clase-5-jueves-07-de-mayo-de-2026-07-05-26-desarrollo-de-aplicaciones-para-dispositivos-moviles/","dg-note-properties":{}}
---


> [!quote]- Resumen
> # Desarrollo de Aplicaciones Móviles: Navegación, Pasaje de Parámetros y Construcción de Formularios
> 
> Este documento constituye un material de estudio integral basado en las sesiones de desarrollo de aplicaciones móviles con React Native. Explora desde la resolución de problemas técnicos comunes hasta la implementación avanzada de lógica de negocios en pantallas interactivas.
> 
> ## 1. Introducción y Contexto
> 
> El desarrollo de aplicaciones móviles requiere no solo de conocimiento técnico, sino de una mentalidad resiliente. La transición entre el diseño de una interfaz estática y una aplicación funcional implica dominar la interacción entre pantallas y la captura de datos del usuario. Este proceso es fundamental para construir aplicaciones que no solo muestran información, sino que permiten al usuario operar sobre ella.
> 
> ### Importancia del Aprendizaje Basado en la Práctica
> 
> La resolución de errores de instalación o configuración (como problemas con dependencias de Expo o módulos de React Native Web) forma parte esencial de la formación. Entender el flujo de trabajo —desde la creación de un proyecto con `npx create-expo-app` hasta la ejecución en dispositivos reales o simuladores web— es el primer paso antes de profundizar en la lógica de programación.
> 
> ## 2. Marco Conceptual y Definiciones Clave
> 
> Para comprender el desarrollo en React Native, es imperativo distinguir los elementos fundamentales que rigen el comportamiento de la aplicación:
> 
> ### Conceptos Fundamentales
> 
> - **Estado (**`**State**`**):** Son variables internas de un componente que nacen y mueren en él. Cuando un estado cambia (mediante una función como `useState`), el componente se "escucha" a sí mismo y se vuelve a renderizar para reflejar el cambio.
> - **Propiedades (**`**Props**`**):** Información que se hereda de un componente padre a un hijo. A diferencia del estado, las props son el mecanismo de transporte de datos entre jerarquías.
> - **Componentes Funcionales:** Estructuras de código que devuelven elementos visuales (JSX) y gestionan su propia lógica interna.
> - **Manejadores de Eventos (**`**Event Handlers**`**):** Funciones que se activan ante acciones del usuario (ej. `onPress`, `onChangeText`). Casi todos los eventos comienzan con el prefijo "on".
> 
> ### Componentes de Interacción Visual
> 
> |   |   |   |
> |---|---|---|
> |Componente|Función Principal|Evento Clave|
> |`Text`|Muestra texto estático.|N/A|
> |`TextInput`|Permite la entrada de texto por teclado.|`onChangeText`|
> |`Button`|Disparador de acciones predefinido.|`onPress`|
> |`TouchableOpacity`|Hace que cualquier elemento sea "presionable" (estilo touch).|`onPress`|
> |`Switch`|Selector booleano (encendido/apagado).|`onValueChange`|
> |`View`|Contenedor estructural (no tiene evento de presión por defecto).|N/A|
> 
> ## 3. Desarrollo del Tema
> 
> ### 3.1. Navegación y Pasaje de Parámetros
> 
> La navegación no solo consiste en cambiar de pantalla, sino en trasladar el contexto de una a otra.
> 
> - **Configuración del Stack:** Se define una lista de parámetros donde se registran las pantallas disponibles (ej. `Home`, `Detalle`).
> - **Navegación con Datos:** Para ir de una pantalla a otra pasando información, se utiliza la función `navigation.navigate('NombrePantalla', { id: 1, nombre: 'Producto' })`.
> - **Recepción de Datos:** La pantalla de destino recibe un objeto llamado `route`. Los parámetros se extraen desde `route.params`.
> 
> ### 3.2. Construcción de Formularios
> 
> Un formulario es un componente construido por otros sub-componentes que guardan un estado interno hasta el momento de la ejecución de una acción (como guardar o enviar).
> 
> #### El Ciclo del Dato en un Input:
> 
> 1. El usuario escribe en el `TextInput`.
> 2. Se dispara el evento `onChangeText`.
> 3. Se ejecuta una función que utiliza el "set" del estado (ej. `setNombre`).
> 4. La variable de estado se actualiza.
> 5. El componente se re-renderiza y el `value` del input muestra el nuevo dato.
> 
> #### Agrupación de Datos (Objetos Complejos)
> 
> En lugar de declarar múltiples constantes para cada campo (usuario, mail, edad), es una buena práctica técnica definir un **Tipo de Formulario** (`type UserForm`). Esto permite manejar un único objeto de estado que contenga todas las variables, facilitando el envío de la información completa en una sola estructura JSON.
> 
> ## 4. Relaciones entre Conceptos y Lógica de Negocio
> 
> ### 4.1. Validaciones Dinámicas
> 
> La lógica de validación permite controlar la interactividad del usuario. Un ejemplo común es habilitar o deshabilitar un botón de "Enviar" basado en condiciones:
> 
> - **Condicionales Simples:** El botón se habilita solo si el email incluye un "@" y el usuario no está en blanco.
> - **Funciones de Validación:** Se pueden extraer lógicas complejas a funciones externas (ej. `esMayorDeEdad`) para mantener el código del componente limpio.
> 
> ### 4.2. Expresiones Regulares (Regex)
> 
> Se utilizan para encontrar patrones en cadenas de texto. Son fundamentales para:
> 
> - Validar formatos de Email.
> - Restringir que un campo solo acepte dígitos numéricos.
> - Identificar caracteres especiales prohibidos.
> 
> ## 5. Ejemplos Prácticos y Casos Reales
> 
> ### Caso 1: Navegación en una Lista de Productos
> 
> Si se tiene una lista de productos (Coca-Cola, Pepsi), cada ítem debe estar envuelto en un componente "presionable" (`TouchableOpacity`). El error común es poner el `onPress` en un `View`, lo cual no funcionará porque `View` no hereda propiedades de toque. La solución es envolver el contenido en un `TouchableOpacity` y pasar el ID del producto a la pantalla de detalles.
> 
> ### Caso 2: Formulario con Validación de Edad y Términos
> 
> Se implementa un formulario con:
> 
> 1. `TextInput` para usuario y email.
> 2. `TextInput` con `keyboardType="numeric"` para la edad.
> 3. `Switch` para "Aceptar términos y condiciones".
> 4. **Lógica:** El botón "Enviar" tiene la propiedad `disabled={!validar()}`. La función `validar` retorna `true` solo si los campos están completos, el mail es válido, la edad es > 18 y el switch está en `true`.
> 
> ## 6. Errores Comunes y Aclaraciones
> 
> - **Error de Componente No Presionable:** Intentar usar `onPress` en un componente `View` o `Text` sin envolverlo en un elemento `Touchable`.
> - **Círculo Vicioso en el Estado:** Intentar validar un valor usando la misma variable que aún no se ha actualizado. Se debe validar el valor entrante del evento, no el valor actual del estado.
> - **Dependencias Web:** Al probar aplicaciones Expo en el navegador, es común que falten módulos como `react-native-web`. El comando `npx expo start` suele sugerir la instalación de estos módulos faltantes.
> - **Confusión entre Estado y Props:** Recordar que el estado es "yo conmigo mismo" (privado del componente) y las props son "yo con el de afuera" (comunicación externa).
> 
> ## 7. Síntesis y Conclusiones
> 
> - **Resiliencia Técnica:** La programación implica lidiar con errores de sintaxis y configuración; la paciencia y el análisis paso a paso son herramientas clave.
> - **Interconectividad:** Una aplicación móvil exitosa depende de un flujo fluido de datos entre pantallas y una captura de datos de usuario validada y estructurada.
> - **Evolución del Rol:** En el contexto tecnológico actual (mencionado mediante la analogía de la IA en empresas como Amazon), el programador debe entender la lógica profunda para supervisar lo que las herramientas automatizadas generan. "Para supervisar, hay que entender".
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia principal entre un componente `View` y un `TouchableOpacity`?
> 2. ¿Para qué sirve la propiedad `placeholder` en un `TextInput`?
> 3. ¿Qué comando se utiliza para iniciar un proyecto de Expo y ver el código QR?
> 
> ### Nivel Intermedio
> 
> 4. Explique el flujo de un dato desde que el usuario escribe en un input hasta que se guarda en el estado de React.
> 5. ¿Cómo se reciben los parámetros enviados desde otra pantalla en el componente de destino?
> 6. ¿Qué propiedad del componente `Button` se utiliza para impedir que el usuario haga clic si no se cumplen ciertas condiciones?
> 
> ### Nivel Avanzado
> 
> 7. Describa por qué es preferible usar un objeto complejo (tipo `UserForm`) en lugar de múltiples variables de estado individuales en un formulario extenso.
> 8. ¿Cómo implementaría una validación que solo permita números en un `TextInput` sin depender exclusivamente del tipo de teclado (`keyboardType`)?
> 9. Analice la importancia de las expresiones regulares en la validación de datos críticos como el correo electrónico.
> 
> ## 9. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de las fuentes, se identifican las siguientes pautas para la materia:
> 
> - **Finalización de Teoría:** La última clase de teoría fuerte está estimada para el **11 de junio**.
> - **Cierre del Cuatrimestre:** Se estima que el periodo lectivo finaliza alrededor del **2 de julio**.
> - **Presentación Final:** La defensa del trabajo práctico final será de manera presencial. Se requerirá mostrar la aplicación funcionando en un teléfono móvil.
> - **Tareas Obligatorias de Clases Asincrónicas:**
>     - **Propósito:** Funcionan como "termómetro" para que el profesor entienda el nivel del grupo y los problemas que surgen.
>     - **Calificación:** No definen la nota final del cuatrimestre por sí solas (un 2 es mejor que un 0), pero son requisito para poner en práctica lo visto. La nota final depende de la defensa del proyecto.
> - **Indicación del Profesor:** Se recomienda empezar el proyecto final lo antes posible, integrando los componentes (listas, navegación, formularios) a medida que se aprenden en clase. No es obligatorio usar todas las funciones (como Tabs o Menú Hamburguesa) si la aplicación no lo requiere.
> - **Aviso de Disponibilidad:** Se dispone de los últimos 40-45 minutos de cada clase sincrónica para realizar consultas técnicas y corrección de errores en vivo.