---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/4-desarrollo-de-aplicaciones-para-dispositivos-moviles/clase-6-jueves-14-de-mayo-de-2026-14-05-26-desarrollo-de-aplicaciones-para-dispositivos-moviles/","dg-note-properties":{}}
---


> [!quote]- Resumen
> # Desarrollo de Aplicaciones Móviles: Estructuras Condicionales, Estados y Eventos en React Native
> 
> Este documento constituye una guía de estudio exhaustiva basada en las sesiones académicas sobre el desarrollo de aplicaciones móviles utilizando React Native. El contenido abarca desde los fundamentos de la transpilación hasta la implementación avanzada de lógica condicional y gestión de estados.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción y Contexto
> 
> El desarrollo móvil con **React Native** se basa en un ecosistema derivado de React, el cual utiliza JavaScript como lenguaje base. Sin embargo, para entornos profesionales, se suele integrar **TypeScript** para añadir un tipado fuerte que proteja al desarrollador de errores comunes durante el tiempo de escritura de código.
> 
> ### La Transpilación y Compilación
> 
> Un concepto fundamental es la diferencia entre transpolar y compilar:
> 
> - **Transpilador (ej. Babel):** Realiza una traducción de una forma de escribir código a otra (por ejemplo, de TypeScript a JavaScript o de versiones modernas de JS a versiones más compatibles).
> - **Compilación:** Es el proceso donde el código (ya transpilado a JS) se empaqueta y se convierte en código nativo para el dispositivo móvil.
> - **Nota técnica:** Aunque TypeScript detecte errores de tipado (mismatch), esto no siempre impide que el código funcione en tiempo de ejecución en JavaScript, aunque el comportamiento puede ser impredecible o erróneo.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual: Tipado y Herramientas
> 
> ### TypeScript vs. JavaScript
> 
> - **JavaScript:** No es tipado. Es flexible pero propenso a errores en proyectos grandes.
> - **TypeScript:** Introduce tipos (string, number, boolean, tipos personalizados/objetos).
>     - **Tipo** `**any**`**:** Es un comodín que permite cualquier dato, pero su uso excesivo rompe la seguridad del tipado fuerte.
>     - **Ventaja:** Permite que el Entorno de Desarrollo (IDE) advierta si se intenta realizar una operación inválida (como sumar un número a una letra) antes de ejecutar el código.
> 
> ### El uso de Inteligencia Artificial (IA) en el Desarrollo
> 
> Es válido utilizar IA para generar código, pero bajo una regla ética y profesional estricta: **"Se puede delegar la tarea a la IA, pero no la responsabilidad"**. El desarrollador debe entender qué hace cada línea generada por la IA y ser capaz de explicar su funcionamiento.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Estructuras Condicionales en React Native
> 
> La renderización condicional permite mostrar u ocultar componentes en la interfaz según el estado de la aplicación.
> 
> ### Operador Ternario
> 
> Es la forma más común de incluir lógica dentro del método `return` (JSX).
> 
> - **Sintaxis:** `condición ? caso_verdadero : caso_falso`
> - **Ejemplo:**
> 
> ### Operador Lógico AND (`&&`)
> 
> Se utiliza cuando solo se quiere mostrar algo si se cumple una condición, sin necesidad de un "si no" (else).
> 
> - **Sintaxis:** `condición && componente`
> - **Uso:** Si la condición es falsa, React ignora el componente.
> 
> ### Lógica fuera del Return
> 
> Para lógica compleja o que requiere múltiples `if`, es recomendable procesar los datos antes de la sentencia `return` para mantener el código limpio.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Gestión de Estado con `useState`
> 
> El estado es la "memoria" del componente. Cuando el estado cambia, el componente se vuelve a renderizar automáticamente para reflejar los cambios.
> 
> ### El Setter del Estado
> 
> La función que modifica el estado (ej. `setContador`) puede recibir dos tipos de parámetros:
> 
> 1. **Valor directo:** `setContador(10)`. Sobrescribe el valor anterior.
> 2. **Función de actualización (Callback):** `setContador(prev => prev + 1)`. Recibe el valor previo y devuelve el nuevo. Es la forma más segura cuando el nuevo estado depende del anterior para evitar problemas de sincronía o bucles.
> 
> ### Errores Comunes: Bucles Infinitos
> 
> Un error frecuente es modificar el estado directamente en el cuerpo del componente (fuera de una función de evento o un hook como `useEffect`). Esto causa que:
> 
> 1. El componente se renderiza.
> 2. El estado cambia.
> 3. El cambio de estado dispara una nueva renderización.
> 4. El ciclo se repite infinitamente hasta que React bloquea la ejecución.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Eventos y Callbacks
> 
> Los componentes interactivos (como `Button` o `TouchableOpacity`) utilizan eventos para disparar acciones.
> 
> - `**onPress**`**:** Es el evento principal para detectar toques.
> - **Callback:** Es una función que se pasa como parámetro a otra función para ser ejecutada después. En el caso de un botón, el desarrollador pasa una función al evento `onPress`, y el sistema la ejecuta cuando el usuario presiona el dispositivo.
> 
> ### Ejemplo de Flujo de Evento:
> 
> 1. El usuario presiona un botón.
> 2. Se llama a la función vinculada al `onPress` (Callback).
> 3. Esta función ejecuta lógica (ej. `setIndice(prev => prev + 1)`).
> 4. El estado cambia y se notifica a todos los componentes que usan esa variable.
> 5. Los componentes se actualizan en pantalla con el nuevo valor.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Herramientas de Documentación y Visualización
> 
> ### Documentación en GitHub (README.md)
> 
> El archivo `README.md` es la cara visible de un proyecto.
> 
> - **Markdown:** Permite usar tablas, negritas, enlaces y fragmentos de código.
> - **Diagramas Programáticos:** En lugar de usar herramientas visuales manuales (donde al mover una caja se desacomoda todo), se pueden usar lenguajes declarativos:
>     - **PlantUML:** Permite codificar diagramas de secuencia, clases y casos de uso.
>     - **Mermaid:** Similar a PlantUML, integrado directamente en muchas plataformas de Git para renderizar gráficos a partir de texto.
> 
> ### Emulación y Pruebas
> 
> 1. **Pruebas en Web:** Rápidas para diseño general, pero no garantizan fidelidad total (los estilos Flexbox o botones nativos pueden variar).
> 2. **Android Studio Emulator:** Permite simular dispositivos específicos (Pixel, Samsung, Tablets) con precisión técnica, aunque consume muchos recursos de la computadora.
> 3. **Dispositivo Físico:** Es la prueba definitiva. Se recomienda usar la aplicación Expo en el celular para testear el comportamiento real del hardware.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Fechas importantes y avisos académicos
> 
> |   |   |   |
> |---|---|---|
> |Evento / Acción|Fecha / Detalle|Descripción|
> |**Finalización de clases**|02/07/2026*|Fecha establecida para el cierre del ciclo.|
> |**Próxima clase**|21/05/2026*|Se recomienda traer ideas para el trabajo final.|
> |**Entrega Final (Metodología)**|Últimas 4 clases|Periodo para iterar, presentar y corregir el proyecto final en clase.|
> |**Presentación Presencial**|10-15 min por persona|Evaluación individual del funcionamiento y código de la app.|
> 
> _*Nota: El contexto de las fuentes indica el año 2026; se mantiene fidelidad a dicha cronología._
> 
> **Advertencias Académicas:**
> 
> - Se valorará más el **comportamiento y funcionamiento** de la aplicación que el diseño visual.
> - El desarrollador debe ser capaz de explicar toda la lógica, especialmente si utilizó ayuda de IA.
> - La corrección de tareas se realiza mediante feedback; es crucial incluir el archivo `README.md` en la raíz del repositorio para su correcta visualización.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia entre el tipado de JavaScript y el de TypeScript?
> 2. ¿Para qué sirve el operador ternario en React Native?
> 3. ¿Cómo se define un estado inicial en un componente funcional?
> 
> ### Nivel Intermedio
> 
> 4. Explique el concepto de "transpilación" y por qué es necesario en este entorno.
> 5. ¿Por qué ocurre un bucle infinito al setear un estado en el cuerpo del componente?
> 6. ¿Qué es un "callback" en el contexto del evento `onPress`?
> 
> ### Nivel Avanzado
> 
> 7. Compare el uso de un valor directo vs. una función callback dentro de un `setVariable` de un estado. ¿En qué casos es preferible cada uno?
> 8. Describa el flujo completo desde que un usuario presiona un botón hasta que se actualiza un cálculo complejo (como la serie de Fibonacci) en la pantalla.
> 9. ¿Cuáles son las ventajas de utilizar herramientas como PlantUML o Mermaid frente a herramientas de dibujo visual como Visio o Draw.io?
> 
> --------------------------------------------------------------------------------
> 
> **Resumen Final:** El dominio de React Native requiere entender que la interfaz es una representación del estado. La lógica condicional y la correcta gestión de eventos mediante callbacks permiten crear aplicaciones dinámicas y robustas, siempre respaldadas por una documentación técnica sólida en Markdown.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 6 (14 05 26) - Desarrollo de aplicaciones para dispositivos móviles" src="https://www.youtube.com/embed/bvV5X0N2u2A?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1iPzgJW27TWZQJyoXKFkxTKBFZZ87MPZm/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1XFLa1WsNwJGGOVtjAl9epZt2UbruP1Wa/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>