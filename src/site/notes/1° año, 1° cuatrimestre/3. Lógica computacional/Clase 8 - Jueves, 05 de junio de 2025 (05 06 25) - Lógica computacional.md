---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/3-logica-computacional/clase-8-jueves-05-de-junio-de-2025-05-06-25-logica-computacional/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Lógica Computacional: Simplificación, Leyes de Morgan y Mapas de Karnaugh
> 
> Este documento constituye una guía de estudio integral y profunda sobre los temas avanzados de lógica computacional abordados en el ámbito académico. Su objetivo es proporcionar una comprensión total desde los fundamentos de la suma y producto booleano hasta la simplificación de expresiones mediante Leyes de Morgan y el uso técnico de los Mapas de Karnaugh.
> 
> ## 1. Introducción y Contexto
> 
> La lógica computacional es la base inamovible de la tecnología. A diferencia de las herramientas de programación o software que pueden quedar obsoletos (como el caso histórico de _Flash_), la lógica permanece constante a través de las décadas. El dominio de esta disciplina permite diseñar circuitos más eficientes, optimizar código y entender el funcionamiento profundo de los sistemas binarios.
> 
> El enfoque actual se centra en la **simplificación**: reducir expresiones complejas a su forma mínima necesaria sin alterar su valor de verdad.
> 
> ## 2. Marco Conceptual: Álgebra de Boole y Operaciones Fundamentales
> 
> Para avanzar hacia la simplificación, es imperativo traducir la lógica proposicional al lenguaje del álgebra de Boole.
> 
> ### Definición de Conceptos Clave
> 
> - **Valores Binarios:** Se sustituye el concepto de Verdadero (V) y Falso (F) por **1** y **0** respectivamente.
> - **Complemento (NOT):** La negación se representa mediante una barra o "techo" sobre la variable (\bar{A}). Es decir, si A = 1, entonces \bar{A} = 0.
> - **Suma Booleana (Operación OR):** Se representa con el signo **+**.
>     - _Regla:_ El resultado es 1 si al menos una de las variables es 1.
>     - 0 + 0 = 0
>     - 0 + 1 = 1
>     - 1 + 0 = 1
>     - 1 + 1 = 1
> - **Multiplicación Booleana (Operación AND):** Se representa con un punto (**·**).
>     - _Regla:_ El resultado es 1 solo si todas las variables son 1.
>     - 0 \cdot 0 = 0
>     - 0 \cdot 1 = 0
>     - 1 \cdot 0 = 0
>     - 1 \cdot 1 = 1
> 
> ### La Implicación (Entonces) en Circuitos
> 
> Un desafío común es representar la condicional (P \rightarrow Q) en compuertas lógicas, ya que no existe una compuerta física directa para "entonces". Se utiliza la equivalencia:
> 
> **P \rightarrow Q \equiv \bar{P} + Q** (No P o Q)
> 
> ## 3. Leyes de Morgan
> 
> Las Leyes de Morgan son herramientas de distribución de la negación que permiten transformar conjunciones en disyunciones y viceversa, facilitando la simplificación de circuitos electrónicos.
> 
> ### Las dos leyes fundamentales
> 
> 1. **Negación de una conjunción:** \overline{P \cdot Q} \equiv \bar{P} + \bar{Q}
>     - _Explicación:_ El negado de un "Y" se distribuye negando cada término y cambiando el conector a "O".
> 2. **Negación de una disyunción:** \overline{P + Q} \equiv \bar{P} \cdot \bar{Q}
>     - _Explicación:_ El negado de un "O" se distribuye negando cada término y cambiando el conector a "Y".
> 
> ### Ejemplo Práctico
> 
> - **Frase original:** "John es alto y Jim es pelirrojo" (P \cdot Q).
> - **Negación aplicada:** "No es cierto que (John es alto y Jim es pelirrojo)".
> - **Equivalencia de Morgan:** "John no es alto **o** Jim no es pelirrojo" (\bar{P} + \bar{Q}).
> 
> ## 4. Equivalencias Lógicas y Simplificación
> 
> Existen diversas leyes que permiten reducir términos en una expresión. El objetivo es pasar de una expresión extensa a una más pequeña que sea lógicamente equivalente.
> 
> ### Tabla de Leyes Principales
> 
> |   |   |
> |---|---|
> |Nombre de la Ley|Expresión de Equivalencia|
> |**Doble Negación**|\bar{\bar{P}} = P|
> |**Identidad**|P + 0 = P ; P \cdot 1 = P|
> |**Idempotencia**|P + P = P ; P \cdot P = P|
> |**Complemento / Negación**|P \cdot \bar{P} = 0 (Contradicción) ; P + \bar{P} = 1 (Tautología)|
> |**Conmutativa**|P + Q = Q + P|
> |**Distributiva**|P + (Q \cdot R) = (P + Q) \cdot (P + R)|
> 
> **Resumen del Proceso de Simplificación:** Para simplificar, se deben aplicar estas leyes paso a paso. Por ejemplo, al encontrar un término como Q \cdot \bar{Q}, este se convierte en una **contradicción (0)**, lo que permite eliminarlo de una suma posterior mediante la ley de identidad.
> 
> ## 5. Suma de Productos (SOP) y Tabla de Verdad
> 
> La **Suma de Productos** es una forma de representar una función lógica a partir de su tabla de verdad, enfocándose únicamente en los casos donde la salida es **1**.
> 
> ### Cómo construir la expresión desde la tabla
> 
> 1. Identificar las filas donde el resultado final sea 1.
> 2. Para cada una de esas filas, escribir el producto (AND) de las variables.
> 3. Si la variable vale **0**, se pone negada (\bar{A}). Si vale **1**, se pone normal (A).
> 4. Unir todos los productos mediante una suma (OR).
> 
> **Ejemplo de Conversión:** Si tenemos una fila donde A=0, B=1, C=0 y la salida es 1:
> 
> - El término binario es: `010`.
> - La expresión booleana es: \bar{A} \cdot B \cdot \bar{C}.
> 
> ## 6. Mapas de Karnaugh (K-Maps)
> 
> El Mapa de Karnaugh es un método gráfico utilizado para simplificar funciones booleanas sin necesidad de aplicar todas las leyes algebraicas manualmente. Es, en esencia, una tabla de verdad organizada de forma bidimensional.
> 
> ### Estructura y Celdas
> 
> La cantidad de celdas depende del número de variables (n):
> 
> - 2 variables: 2^2 = 4 celdas.
> - 3 variables: 2^3 = 8 celdas.
> - 4 variables: 2^4 = 16 celdas.
> 
> ### El Código Gray (La Regla de Oro)
> 
> En los mapas de Karnaugh, al movernos entre celdas adyacentes (filas o columnas), **solo puede cambiar un bit a la vez**. Esto altera el orden tradicional binario:
> 
> **Orden correcto: 00 - 01 - 11 - 10**
> 
> _Nota importante:_ El salto de `01` a `11` es necesario para que solo cambie el primer bit. El valor `10` queda al final.
> 
> ### Proceso de Llenado del Mapa
> 
> 1. Se dibuja el cuadro según la cantidad de variables.
> 2. Se asignan las coordenadas (filas y columnas) siguiendo el código Gray.
> 3. Se toma la expresión binaria (por ejemplo, `0111`) y se coloca un **1** en la intersección correspondiente de la tabla.
> 4. Las celdas donde no hay coincidencia con la expresión se completan con **0**.
> 
> ## 7. Errores Comunes y Aclaraciones
> 
> 1. **Confusión en los Conectores:** Es común confundir el símbolo de suma (+) con la conjunción (AND). Recordar: + es **OR** (O), \cdot es **AND** (Y).
> 2. **Error en el Mapa de Karnaugh:** El error más frecuente es usar el orden binario natural (`00, 01, 10, 11`) en lugar del código Gray (`00, 01, 11, 10`). Esto invalida toda la simplificación.
> 3. **Negaciones Mal Distribuidas:** Al aplicar Morgan, muchos olvidan cambiar el signo central. Si niegas un `(A + B)`, el resultado _debe_ tener un producto: `$\bar{A} \cdot \bar{B}$`.
> 4. **Uso de la IA:** Herramientas como ChatGPT o Gemini pueden cometer errores al representar gráficos de compuertas o mapas complejos. Siempre se debe verificar manualmente la lógica de las coordenadas.
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> Basado en la comunicación del docente durante la sesión:
> 
> - **Entrega de Tarea/Ejercicio:** Se ha extendido el plazo de entrega hasta el **lunes**. El docente aclaró que la fecha en la configuración no es determinante a menos que se avise lo contrario.
> - **Próxima Clase:** Se dedicará íntegramente a la **práctica plena** de Mapas de Karnaugh y simplificación con Leyes de Morgan.
> - **Evaluaciones:** El docente ya cuenta con una evaluación realizada y la próxima semana se buscará realizar otra para cerrar el segundo bloque de notas.
> - **Material de Apoyo:** Existe un PDF de "Equivalencias Lógicas" en alta resolución disponible para consultar las 10 leyes durante los ejercicios.
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es el equivalente booleano de la operación OR y la operación AND?
> 2. Si A=1, B=0, C=1, ¿cuál es el valor de la expresión \bar{A} + B + C?
> 3. ¿Cómo se representa la implicación (P \rightarrow Q) usando solo sumas y negaciones?
> 
> ### Nivel Intermedio
> 
> 4. Aplique las Leyes de Morgan para negar la siguiente expresión: \overline{A \cdot \bar{B}}.
> 5. Dada una fila de la tabla de verdad donde A=1, B=0, C=0, D=1 con salida 1, escriba su término en Suma de Productos (SOP).
> 6. ¿Por qué se utiliza el orden `00, 01, 11, 10` en las coordenadas de un Mapa de Karnaugh?
> 
> ### Nivel Avanzado
> 
> 7. Simplifique la expresión (P + Q) \cdot (P + \bar{Q}) utilizando leyes de equivalencia y explique qué ley aplica en cada paso.
> 8. Diseñe un Mapa de Karnaugh de 8 celdas para la función F = A\bar{B}C + \bar{A}BC + ABC. Indique la posición de los 1s en binario.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 8 - Lógica computacional" src="https://www.youtube.com/embed/3KBx85JkIpo?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1oun6S-2tucrqgb18vczv78W6IDGUiwFE/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1pqkDDfRcqRBdgAhUz0dX68goo9CZyqyP/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>