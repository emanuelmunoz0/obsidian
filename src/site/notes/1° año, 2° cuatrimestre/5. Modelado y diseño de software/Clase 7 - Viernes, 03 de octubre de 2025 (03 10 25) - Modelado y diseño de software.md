---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/5-modelado-y-diseno-de-software/clase-7-viernes-03-de-octubre-de-2025-03-10-25-modelado-y-diseno-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía Integral de Estudio: Modelado, Diseño de Software y Estadística Aplicada
> 
> Este documento sintetiza los conceptos fundamentales abordados en la sesión académica, integrando las áreas de estadística descriptiva y el modelado de sistemas mediante diagramas de estado. Está diseñado para servir como material de referencia único, cubriendo desde la resolución de problemas técnicos hasta la teoría de diseño de software.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> El desarrollo de software y el análisis de datos requieren una comprensión profunda de cómo se organizan los elementos y cómo cambian con el tiempo. En el ámbito estadístico, es crucial entender la transición de datos poblacionales simples a datos agrupados en intervalos para obtener métricas precisas como la media. En el diseño de software, el enfoque se centra en el **Modelado de Estados y Transiciones**, permitiendo capturar el comportamiento dinámico de un sistema ante diversos estímulos y el paso del tiempo.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual y Definiciones
> 
> Para comprender el tema desde cero, es necesario definir los términos fundamentales que estructuran ambas disciplinas:
> 
> ### Conceptos de Estadística
> 
> - **Media (Promedio):** Medida de tendencia central. Existen variantes según la naturaleza de los datos:
>     - **Media Aritmética:** El promedio estándar.
>     - **Media Geométrica y Armónica:** Utilizadas para tasas de cambio o razones.
>     - **Media Cuadrática (RMS - Root Mean Square):** Medida que requiere cálculo manual (según la cátedra) y se utiliza para evaluar magnitudes.
> - **Intervalos:** Rangos en los que se agrupan los datos cuando la población es extensa.
> - **Marca de Clase:** El punto medio de un intervalo, esencial para calcular la media en datos agrupados.
> - **Frecuencia:** Cantidad de veces que se repite un valor o los valores dentro de un intervalo.
> 
> ### Conceptos de Modelado de Software
> 
> - **Estado:** Un momento o condición estática en la vida de un objeto. No hay cambio mientras se está en un estado (ej. "Encendido" o "Apagado").
> - **Transición:** El paso de un estado a otro. A diferencia del estado, la transición involucra una dimensión temporal y un cambio.
> - **Disparo (Trigger):** El evento o mensaje que inicia el movimiento entre estados.
> - **Acción de Entrada/Salida:** Respuestas que ocurren al entrar o salir de un estado (ej. encender una luz, mostrar un mensaje).
> - **Tiempo de Latencia:** Periodo en el que el sistema espera una decisión antes de forzar un cambio de estado (ej. _Time Out_).
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: Modelado de Estados y Transiciones
> 
> ### El Acople de la Transición al Estado
> 
> En el diseño de software, el diagrama de estados suele considerarse estático. Sin embargo, la **transición** actúa como un "acople" necesario que introduce la variable del tiempo.
> 
> 1. **Estado vs. Tiempo:** El estado por sí solo no mide el tiempo; es una condición (True/False). La transición es la que gestiona el intervalo temporal existente entre un estado A y un Benedicto.
> 2. **Flexibilidad en Software:** Aunque teóricamente son distintos, en el desarrollo de software se permite integrar el tiempo dentro del diagrama de estados para representar sistemas que no pueden permanecer indefinidamente en una sola condición.
> 
> ### Relación entre Conceptos
> 
> La conexión entre estos elementos se manifiesta en la respuesta del sistema. Por cada acción (un "Play" en un reproductor), debe haber una respuesta visible o interna (encendido de un display, inicio de un contador). Si un sistema no recibe un disparo en un tiempo determinado, la transición puede llevarlo a un estado de error o cierre (_Time Out_).
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Ejemplos Prácticos y Casos Reales
> 
> A continuación se presentan ejemplos explicados paso a paso para visualizar la aplicación de estos conceptos:
> 
> ### Ejemplo 1: El Cajero Automático (Transición por Tiempo)
> 
> - **Estado inicial:** Esperando ingreso de PIN.
> - **Acción:** El usuario no interactúa.
> - **Transición:** El sistema detecta un tiempo de latencia excedido.
> - **Respuesta:** Aparece un mensaje: "¿Necesita más tiempo?". Si no hay respuesta, el sistema transiciona al estado "Fin de Sesión".
> 
> ### Ejemplo 2: El Semáforo (Diagrama Visual)
> 
> - **Estados:** Verde, Amarillo, Rojo.
> - **Transición:** El paso de Verde a Amarillo es una transición pura basada en un temporizador. No requiere intervención externa (disparo de usuario), sino que el tiempo es el propio disparador.
> 
> ### Ejemplo 3: Máquina de Café
> 
> - **Estado:** Latencia/Esperando moneda.
> - **Disparo:** Inserción de moneda.
> - **Acción durante el estado:** La máquina muestra un display de selección. Si el usuario no elige, el sistema debe tener una transición de seguridad para devolver la moneda o cancelar.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Errores Comunes y Confusiones
> 
> |   |   |
> |---|---|
> |Error Frecuente|Aclaración Importante|
> |**Confundir Estado con Transición**|El estado es "estar" (estático); la transición es "pasar a" (dinámico y temporal).|
> |**Omitir la Marca de Clase**|Al calcular la media con intervalos, es imposible obtener el resultado si no se calcula primero el punto medio de cada intervalo.|
> |**Asumir que todo estado es infinito**|En sistemas reales (como una CPU), los estados duran microsegundos. El "Time Out" es una herramienta para evitar estados indefinidos.|
> |**Uso de fórmulas de población para intervalos**|Los intervalos requieren una lógica distinta basada en frecuencias y marcas de clase, no simplemente el promedio simple de Excel.|
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Síntesis y Conclusiones
> 
> - **Estadística:** La correcta organización de intervalos y la detección de frecuencias son la base para aplicar fórmulas de media (aritmética, geométrica o armónica). El proceso es tan importante como el resultado final.
> - **Modelado:** El diagrama de estados mejorado con transiciones permite prever el comportamiento del software bajo condiciones de tiempo reales.
> - **Interacción:** Todo cambio de estado debe idealmente generar una respuesta (visual, mensaje de software o señal de hardware).
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de las fuentes, se establecen las siguientes pautas organizativas:
> 
> |   |   |   |
> |---|---|---|
> |Fecha|Tipo de Evento|Descripción Detallada|
> |**11 de Septiembre**|Feriado|No hubo actividad académica.|
> |**10 de Octubre**|Sin Clases|Se confirma que no habrá actividad este día.|
> |**17 de Octubre**|Entrega/Presentación|Presentación de uno de los dos diagramas pendientes (Estado-Transición o Colaboración).|
> |**24 de Octubre**|Entrega/Presentación|Presentación del segundo diagrama pendiente.|
> 
> **Recordatorios Críticos:**
> 
> - **Temas de Examen:** Existe una controversia sobre la **Media Cuadrática (RMS)**. El profesor sostiene que se explicó como un cálculo manual, mientras que los alumnos (apoyados en grabaciones y resúmenes de IA) indican que no fue impartida. El docente revisará los archivos; si no se encuentra la evidencia, se otorgarán puntos extra a los alumnos.
> - **Metodología de Trabajo:** Las entregas deben ser en grupo. Se debe priorizar la explicación del proceso y no solo el resultado final en las hojas de cálculo.
> - **Participación:** El docente solicita mayor participación de la población femenina y mayor uso de cámaras en sesiones virtuales para mejorar la comunicación.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia fundamental entre un estado y una transición?
> 2. En estadística, ¿qué es la marca de clase y para qué sirve?
> 3. ¿Qué es un "disparo" (trigger) en un diagrama de estados?
> 
> ### Nivel Intermedio
> 
> 4. Explique el concepto de _Time Out_ aplicado a un cajero automático utilizando los términos "estado" y "transición".
> 5. ¿Por qué se dice que el tiempo es un "acople" en el diagrama de estados?
> 6. Describa cómo se calcularía la media si solo tiene los intervalos y sus frecuencias.
> 
> ### Nivel Avanzado
> 
> 7. Analice el caso del puerto paralelo de una impresora (mencionado en clase): ¿Cómo interactúan las señales de respuesta (_ACK_) con el cambio de estado del envío de datos?
> 8. Si un docente pide calcular la media aritmética de una población y luego de una muestra por intervalos, ¿cuál de los dos procesos es más complejo y por qué?

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 7 - Modelado y diseño de software" src="https://www.youtube.com/embed/1MjIPSM1BZ4?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1M5hDDt70tRCw-d8uiGvZWix9SBM3poDM/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1ReQZ_jKo2ORPD4XD6WuomfonMrUanWoN/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>