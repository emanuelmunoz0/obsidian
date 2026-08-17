---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/5-modelado-y-diseno-de-software/clase-6-viernes-26-de-septiembre-de-2025-26-09-25-modelado-y-diseno-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio Avanzada: Modelado y Diseño de Software - Diagramas de Estado
> 
> Este documento constituye un material de estudio integral sobre los **Diagramas de Estado**, basado en el análisis técnico de la sesión académica correspondiente. Explora desde los fundamentos hasta las aplicaciones complejas de esta herramienta de modelado.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> El **Diagrama de Estado** es una de las herramientas de modelado más completas en la ingeniería de software. A diferencia de otros diagramas que se centran en la estructura o la interacción simple, el diagrama de estado encapsula la conducta dinámica de un sistema, integrando eventos, acciones y transiciones dentro de un marco coherente.
> 
> Históricamente, estos diagramas tienen sus raíces en la lógica booleana y el concepto de máquinas de estado finito. En la actualidad, son fundamentales para entender cómo un objeto o sistema reacciona ante estímulos externos a lo largo de su ciclo de vida.
> 
> ## 2. Contexto del Tema
> 
> ### Evolución y Naturaleza
> 
> Los diagramas de estado se originaron bajo una lógica binaria (0 y 1), pero han evolucionado hacia representaciones más ricas y visuales. Un ejemplo clásico de un diagrama de estado es la **computadora** misma, la cual funciona como una máquina de estado finito.
> 
> ### Importancia y Relevancia
> 
> Su relevancia radica en la capacidad de modelar comportamientos complejos y respuestas a eventos. Mientras que los diagramas de clases separan las cuestiones estructurales, el diagrama de estado une la conducta (qué hace) con el estado (cómo está) en un momento dado.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Marco Conceptual
> 
> Para comprender los diagramas de estado, es necesario definir sus componentes fundamentales desde cero:
> 
> - **Estado:** Condición o situación en la vida de un objeto durante la cual satisface alguna condición, realiza alguna actividad o espera algún evento. El objeto depende directamente de su estado actual para determinar su comportamiento.
> - **Evento:** Una ocurrencia que puede disparar una respuesta en un estado. Los eventos pueden ser **locales** (dentro del ámbito del objeto) o **externos** (provenientes del entorno o de otros objetos).
> - **Acción Atómica:** Se define como una acción que, a pesar de su nombre, puede contener múltiples componentes o elementos internos. Es una unidad de trabajo que ocurre durante una transición o dentro de un estado.
> - **Transición:** Es el paso de un estado a otro, generalmente motivado por un evento externo.
> - **Ámbito de Variables:**
>     - **Locales:** Variables confinadas a un ámbito específico.
>     - **Públicas:** Variables accesibles de forma global o externa.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Desarrollo del Tema: Dinámica de los Diagramas de Estado
> 
> ### El Ciclo de Vida del Diagrama
> 
> Todo diagrama de estado debe seguir una estructura lógica de inicio y fin:
> 
> 1. **Punto de Inicio:** Es obligatorio. No existe un diagrama de estado sin un punto de partida definido.
> 2. **Punto Final:** Generalmente requerido para indicar la conclusión del ciclo de vida del objeto. Sin embargo, existen casos especiales como el de un **ascensor**, que puede carecer de un punto final definitivo ya que está en constante ciclo de arranque, deteniéndose solo de forma transitoria para mantenimiento.
> 
> ### Tipos de Respuestas a Eventos Externos
> 
> Cuando un estado es "excitado" o estimulado por un evento externo, existen dos tipos principales de respuestas:
> 
> 1. **Transición:** Una respuesta momentánea que implica un cambio hacia un nuevo estado.
> 2. **Permanente:** Una respuesta que mantiene al objeto en una condición estable post-evento.
> 
> ### Acciones Implícitas
> 
> Dentro de un estado, existen acciones automáticas o implícitas que ocurren sin necesidad de una instrucción externa detallada en cada momento, específicamente las acciones de **Entry** (entrada al estado) y **Exit** (salida del estado).
> 
> ### Manejo de Interrupciones
> 
> Una interrupción ocurre cuando un evento externo obliga al objeto a abandonar su estado actual antes de haber completado la actividad programada.
> 
> - **Proceso de Interrupción:**
>     1. El sistema recibe el evento de interrupción.
>     2. Se asignan prioridades.
>     3. Se guarda o memoriza el punto exacto donde se dejó la tarea.
>     4. Se atiende la interrupción.
>     5. Una vez finalizada, el sistema regresa al punto anterior para continuar.
> 
> ### Estados Compuestos
> 
> Los estados no siempre son unidades simples. Existen **estados compuestos** que pueden contener sus propias transiciones y sub-estados internos, permitiendo un modelado mucho más profundo de sistemas complejos.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Relaciones entre Conceptos y Estructuras
> 
> La conexión entre los elementos del diagrama sigue una jerarquía lógica:
> 
> - **Objeto → Estado:** El objeto reside en un estado.
> - **Estado → Evento:** El estado contiene y reacciona a eventos.
> - **Evento → Transición:** El evento dispara la transición.
> - **Transición → Acción:** La transición ejecuta acciones (atómicas o actividades).
> 
> |   |   |
> |---|---|
> |Concepto|Relación con el Sistema|
> |**Secuencial**|Sigue un orden predeterminado, fijo y previsible.|
> |**Aleatorio (Random)**|El orden no es fijo ni controlable por el observador; depende de probabilidades.|
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Ejemplos Prácticos
> 
> ### Caso 1: La Máquina de Café (Estado Finito)
> 
> Este es un ejemplo de un ciclo con inicio y fin claro:
> 
> 1. **Inicio:** El usuario coloca una moneda.
> 2. **Evento:** Elección del menú.
> 3. **Transiciones:** La máquina pasa por diversos estados de preparación.
> 4. **Fin:** La máquina entrega el producto e inhibe al usuario de continuar hasta un nuevo inicio.
> 
> ### Caso 2: El Ascensor (Estado Continuo/Especial)
> 
> A diferencia de la máquina de café, el ascensor representa un sistema que parece no terminar:
> 
> - Está siempre "arrancando" o disponible.
> - Su "punto final" es en realidad un **stop transitorio** o punto de suspensión para tareas de mantenimiento.
> 
> ### Caso 3: Máquina Tragamonedas (Lógica Aleatoria)
> 
> - Representa un sistema donde el resultado no es controlado por el usuario.
> - Utiliza lógica de números aleatorios asociados a imágenes (frutas, por ejemplo).
> - La probabilidad de éxito (ej. tres números iguales) es baja pero existente dentro del diagrama de estados del juego.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Errores Comunes y Confusiones
> 
> - **Confundir Acción con Transición:** La transición es el movimiento entre estados; la acción es lo que ocurre durante ese movimiento o dentro del estado.
> - **Omitir el Punto de Inicio:** Es un error técnico grave; todo sistema debe tener un estado inicial definido.
> - **Asumir que lo Aleatorio es Predecible:** En el modelado, lo aleatorio (random) implica que el observador no controla la respuesta, a diferencia de los procesos secuenciales fijos.
> - **Confundir Acción Atómica con Simplicidad:** Una acción atómica se denomina así por ser una unidad indivisible en un nivel de abstracción, pero puede contener muchos elementos internos.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Síntesis y Conclusiones
> 
> Los diagramas de estado son representaciones dinámicas fundamentales para el diseño de software. Permiten visualizar cómo los objetos cambian y reaccionan ante estímulos. Sus puntos clave son:
> 
> - **Integralidad:** Contienen eventos y acciones dentro de los estados.
> - **Determinismo:** Pueden ser secuenciales (predecibles) o aleatorios (probabilísticos).
> - **Resiliencia:** Deben ser capaces de manejar interrupciones mediante la memorización del estado anterior.
> - **Estructura:** Requieren obligatoriamente un inicio y, en la mayoría de los casos, un fin o punto de suspensión.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso (Tipo Examen)
> 
> ### Nivel Básico
> 
> 1. ¿Es posible que un diagrama de estado no tenga un punto de inicio?
> 2. ¿Qué diferencia fundamental hay entre un proceso secuencial y uno aleatorio?
> 3. ¿Cómo se define una acción atómica?
> 
> ### Nivel Intermedio
> 
> 4. Explique las acciones implícitas `Entry` y `Exit`.
> 5. ¿Qué sucede técnicamente cuando ocurre una interrupción en un estado?
> 6. ¿Los estados compuestos pueden tener transiciones propias? Justifique.
> 
> ### Nivel Avanzado
> 
> 7. Analice el caso del ascensor: ¿Por qué se considera un caso especial en cuanto al punto final del diagrama?
> 8. Compare las dos respuestas posibles de un estado ante un evento externo (Transición vs. Permanente).
> 
> --------------------------------------------------------------------------------
> 
> ## 10. Fechas Importantes y Avisos Académicos
> 
> Basado en la comunicación docente durante la Clase 6:
> 
> - **Próxima Clase (Semana Siguiente):** Se continuará trabajando profundamente con el tema de **Diagramas de Estado**. El profesor reforzará los conceptos y resolverá dudas adicionales.
> - **Actividad Reciente:** Se realizó una actividad asincrónica que incluyó un cuestionario para evaluar la lectura de los apuntes y la capacidad de razonamiento sobre el tema.
> - **Sugerencia del Profesor:** Se insta a los alumnos a buscar diagramas de estado complejos o de una CPU para ser explicados técnicamente en clase. No deben temer a la complejidad técnica de estos ejemplos.
> - **Estado de la Materia:** El cronograma se encuentra "bien en tiempo" según la planificación docente.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 6 - Modelado y diseño de software" src="https://www.youtube.com/embed/qjR3sbo9reg?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1GgBCDzlbG6PBtp-jGEr7adTvwv-5uAKS/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1fhN3degT6kHwtVbF2N3wNS8NIbEF7r2O/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>