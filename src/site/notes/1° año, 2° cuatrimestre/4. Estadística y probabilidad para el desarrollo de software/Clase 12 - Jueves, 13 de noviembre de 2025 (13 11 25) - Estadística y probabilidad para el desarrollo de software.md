---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/4-estadistica-y-probabilidad-para-el-desarrollo-de-software/clase-12-jueves-13-de-noviembre-de-2025-13-11-25-estadistica-y-probabilidad-para-el-desarrollo-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio: Números Índice y Estadística Aplicada
> 
> Este documento constituye un material de estudio integral basado en la Clase 12 de la asignatura Estadística y Probabilidad para el Desarrollo de Software. En él se sintetizan los conceptos fundamentales sobre los números índice, su aplicación práctica y las pautas académicas para la evaluación final.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción a los Números Índice
> 
> Los números índice son herramientas estadísticas fundamentales para el análisis de datos a lo largo del tiempo o entre diferentes categorías. Su propósito principal es facilitar la **comparación** de magnitudes, ya sean precios, cantidades o cualquier otra variable medible.
> 
> ### Importancia y Relevancia
> 
> En el desarrollo de software y el análisis de datos, los índices permiten observar la evolución de una variable (como el costo de un servicio o el volumen de transacciones) respecto a un punto de referencia fijo. Son esenciales para entender conceptos económicos como el Índice de Precios al Consumidor (IPC) o índices de precios mayoristas.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual: Definiciones y Términos Clave
> 
> Para comprender los números índice desde cero, es necesario identificar sus componentes básicos:
> 
> - **Número Índice:** Es esencialmente el resultado de una división (cociente) entre una magnitud actual y una magnitud tomada como referencia.
> - **Periodo o Valor Base:** Es el número que se coloca en el **denominador** de la fórmula. Actúa como el punto de comparación y su elección puede ser arbitraria.
> - **Magnitud de Estudio:** Es el valor que se desea comparar, ubicado en el **numerador**.
> - **Relación Proporcional:** Los índices pueden ser:
>     - Menores a 1 (o menores a 100%).
>     - Iguales a 1 (cuando el valor es igual a la base).
>     - Mayores a 1 (o mayores a 100%).
> - **Tasa de Evolución:** Relacionada con el carácter geométrico de los datos (media geométrica), que permite observar cómo crece o decrece una serie temporal.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: Clasificación y Cálculo
> 
> ### Tipos de Números Índice
> 
> Aunque existen estructuras complejas para estadísticas más precisas, el enfoque de estudio se centra en los **índices simples**:
> 
> 1. **Precio Relativo:** Compara la evolución del valor monetario de un producto.
> 2. **Cantidad Relativa:** Compara el volumen o número de unidades de un producto o magnitud.
> 
> ### Procedimiento de Cálculo
> 
> El proceso se basa en una fórmula sencilla de cociente:
> 
> Índice = \frac{\text{Valor del año a estudiar}}{\text{Valor del año base}} \times 100
> 
> _(Nota: Multiplicar por 100 es una convención para expresar el índice como un porcentaje y facilitar su lectura)._
> 
> #### El Rol del Denominador
> 
> El denominador debe estar **fijo** durante toda una serie de comparaciones. En herramientas de software como Excel, esto se logra mediante una **referencia absoluta** (usando el símbolo de pesos, por ejemplo, `$D$29`) para permitir el arrastre de la fórmula sin que la base se mueva.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Aplicación de Diferentes Bases de Comparación
> 
> Un índice puede calcularse utilizando distintos criterios para el denominador:
> 
> ### A. Base en un año específico
> 
> Se elige un año de la serie (por ejemplo, el año inicial o el año final) y todos los demás valores se dividen por el valor de ese año seleccionado.
> 
> - _Ejemplo:_ Comparar los precios de 1953 a 1957 tomando como base fija el año 1958.
> 
> ### B. Base en la Media (Promedio)
> 
> En lugar de un año único, se puede utilizar el promedio de todos los valores de la serie como denominador.
> 
> - **Procedimiento:**
>     1. Sumar todos los valores de la serie.
>     2. Dividir por el número total de años para obtener la media aritmética.
>     3. Dividir cada valor individual de la serie por esta media.
> 
> ### C. Relación Inversa o Recíproca
> 
> Si se multiplican dos índices donde las bases están invertidas (por ejemplo, el índice de A respecto a B multiplicado por el de B respecto a A), el resultado es uno.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Ejemplos Prácticos Paso a Paso
> 
> ### Caso 1: Evolución de Precios con Año Fijo
> 
> Supongamos una serie de precios de 1953 a 1958:
> 
> - Si se pide la evolución de precios de 1957 tomando como base 1953:
>     - Numerador: Precio de 1957.
>     - Denominador: Precio de 1953.
>     - Resultado: Un valor > 1 indica que el precio aumentó respecto al inicio.
> 
> ### Caso 2: Uso de Referencias en Software (Excel)
> 
> Para calcular una serie completa contra la media:
> 
> 1. Se tiene el valor en la celda `D25`.
> 2. La media calculada está en la celda `D30`.
> 3. Fórmula: `=D25/$D$30`.
> 4. Se extiende la fórmula hacia la derecha para obtener los índices de toda la fila.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores Comunes y Aclaraciones
> 
> - **Confusión en la Base:** El error más frecuente es intercambiar el numerador y el denominador. La base (el "con respecto a") **siempre** va en el denominador.
> - **División por Cero:** Nunca se debe tomar el valor cero como base, ya que la operación matemática es indeterminada.
> - **Redondeo:** Se recomienda trabajar con una política uniforme de decimales (generalmente 2 o 3 decimales) para mantener la consistencia en los resultados.
> - **Naturaleza de los Datos:** A menudo, los valores anuales proporcionados ya son promedios (la media de los 12 meses del año), por lo que se está calculando un índice sobre otros promedios previos.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Síntesis y Conclusiones
> 
> - Los números índice simplifican la comparación de datos complejos.
> - La clave del cálculo reside en identificar correctamente el **periodo base**.
> - Se pueden calcular índices respecto a un punto fijo o respecto al promedio de una serie.
> - Son aplicables tanto a precios como a cantidades de manera idéntica.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> A continuación, se detallan las indicaciones cruciales para el cierre del ciclo lectivo:
> 
> |   |   |   |
> |---|---|---|
> |Evento / Obligación|Fecha|Descripción Detallada|
> |**Examen Final / Evaluación**|Próximo jueves|Evaluación presencial que abarca los temas principales del tramo final.|
> |**Feriado / Día No Laborable**|Viernes 21|Día no laborable; no habrá actividades académicas presenciales este día.|
> |**Entrega de Gráficos**|Próximo jueves|Fecha límite para la entrega de los trabajos de gráficos pendientes.|
> 
> ### Indicaciones Específicas para el Examen:
> 
> - **Temario:**
>     1. **Distribución Normal:** Incluye la tipificación de variables y el uso de tablas.
>     2. **Interpolación o Ajuste de Curvas.**
>     3. **Números Índice:** Cálculos simples como los vistos en esta sesión.
> - **Material Obligatorio:** Es necesario traer impresas las tablas de los anexos (Apéndice 1 y 2).
> - **Metodología:**
>     - Se permite el uso de Excel para realizar las operaciones.
>     - Los archivos de Excel deben enviarse por correo electrónico.
>     - Los resultados finales deben entregarse de forma manuscrita en una hoja (el docente prioriza el resultado final sobre el borrador del procedimiento).
> - **Modalidad:** El examen se realizará de forma grupal (el docente manifestó su preferencia por esta modalidad frente a la individual).
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Qué representa el denominador en la fórmula de un número índice?
> 2. Si un índice da como resultado 1.25, ¿qué significa esto en términos de porcentaje respecto a la base?
> 3. ¿Cuál es la diferencia entre un índice de precio relativo y uno de cantidad relativa?
> 
> ### Nivel Intermedio
> 
> 4. Explique el procedimiento para calcular un índice cuando la base es la media de una serie de 10 años.
> 5. ¿Cómo se fija una celda en Excel para que no cambie al arrastrar una fórmula de números índice?
> 
> ### Nivel Avanzado
> 
> 6. En un examen de distribución normal, ¿qué pasos se deben seguir para tipificar una variable antes de consultar las tablas del apéndice?
> 7. ¿Por qué se considera que los números índice tienen un carácter "arbitrario" en la elección de su base?

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 12 - Estadística y probabilidad para el desarrollo de software" src="https://www.youtube.com/embed/It-Resg23i8?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1GFHDg5W9pT561CIyJYH4_V8pGkXHeapd/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1yEBU8Q6GreuoIB285j4-SBZZ_68j9gk1/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>