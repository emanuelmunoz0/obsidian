---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/3-logica-computacional/clase-7-jueves-29-de-mayo-de-2025-29-05-25-logica-computacional/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía Integral de Estudio: Lógica Computacional y Circuitos Digitales
> 
> Este documento constituye un material de estudio exhaustivo basado en la sesión académica del 29 de mayo. Integra los conceptos fundamentales de la lógica proposicional, su representación en circuitos digitales y la aplicación práctica de estos conocimientos en el desarrollo de software.
> 
> ## 1. Introducción General
> 
> La lógica computacional es la base de toda tecnología moderna. Mientras que los lenguajes de programación y las herramientas evolucionan, la lógica subyacente permanece intacta. Este documento aborda la transición desde los enunciados en lenguaje natural hacia la formalización lógica y su implementación física o simulada mediante compuertas lógicas.
> 
> ## 2. Contexto del Tema
> 
> El estudio de la lógica se sitúa en el primer cuatrimestre de la formación en desarrollo de software. Es una materia con una carga horaria significativa (6 horas semanales), lo que subraya su relevancia frente a otras disciplinas como Base de Datos o Análisis Matemático. El enfoque actual se centra en cerrar la brecha entre la teoría de las tablas de verdad y la arquitectura de circuitos lógicos.
> 
> ## 3. Importancia y Relevancia
> 
> - **Universalidad:** Las sentencias lógicas son universales y se aplican a cualquier tecnología.
> - **Fundamento de Programación:** Es esencial para la creación de estructuras condicionales (`if`, `else`) y el control de flujos en el desarrollo de software.
> - **Optimización:** El uso de herramientas lógicas permite a los desarrolladores trabajar de manera metódica y rápida, utilizando enunciados con formas predefinidas.
> 
> ## 4. Marco Conceptual
> 
> ### Definición de Conceptos Clave
> 
> |   |   |
> |---|---|
> |Concepto|Definición|
> |**Variables Proposicionales**|Símbolos (comúnmente P, Q, R) que representan enunciados que pueden ser verdaderos (1) o falsos (0).|
> |**Diccionario de Variables**|El proceso de asignar una variable lógica a un enunciado en lenguaje natural.|
> |**Tautología**|Una sentencia lógica cuyo resultado en la tabla de verdad es siempre verdadero, independientemente de los valores de sus variables.|
> |**Contradicción**|Una sentencia lógica cuyo resultado es siempre falso.|
> |**Compuertas Lógicas**|Dispositivos (físicos o virtuales) que implementan funciones booleanas.|
> |**Expresión Booleana**|Representación matemática de una función lógica.|
> 
> ### Simbología y Notación
> 
> En el ámbito académico y técnico, se utilizan diversas notaciones. Durante el desarrollo del tema se han identificado las siguientes equivalencias para el uso en teclado y fórmulas:
> 
> - **Negación (NOT):** Representado frecuentemente por el símbolo `~` o una barra sobre la variable.
> - **Conjunción (AND / "Y"):** Representado por un punto `.` o, en ciertas metodologías, por el signo `+`.
> - **Disyunción (OR / "O"):** Representado por el signo `+` o una `V`.
> - **Nota sobre ambigüedad:** Es vital verificar la convención utilizada por el docente, ya que algunos sistemas asocian el `+` al "Y" y otros al "O". Según la práctica actual, se sugiere: `+` para la relación obligatoria (I/AND) y `.` para la optativa (O/OR).
> 
> ## 5. Desarrollo del Tema: De la Lógica al Circuito
> 
> El proceso de diseño lógico computacional sigue una progresión lógica de cuatro instancias:
> 
> 1. **Enunciado en lenguaje natural:** La descripción de un problema o condición.
> 2. **Diccionario de variables:** La traducción de la idea a P, Q, R.
> 3. **Tabla de verdad y Fórmula:** El análisis de todas las combinaciones posibles de valores.
> 4. **Circuito:** La representación gráfica mediante nodos y compuertas.
> 
> ### Compuertas Lógicas Fundamentales
> 
> - **NOT (Inversora):** Si entra 1, devuelve 0; si entra 0, devuelve 1.
> - **AND (Y):** La salida es 1 solo si todas las entradas son 1.
> - **OR (O):** La salida es 1 si al menos una de las entradas es 1.
> - **NOR (O negada):** Es la combinación de una OR seguida de una NOT. La salida es 0 si cualquiera de las entradas es 1.
> 
> ## 6. Relaciones entre Conceptos
> 
> La conexión entre la lógica proposicional y los circuitos digitales se establece a través de la **señal de salida**.
> 
> - Un **0** lógico equivale a una señal **Falsa** o un interruptor desactivado.
> - Un **1** lógico equivale a una señal **Verdadera** o un interruptor activado (que en un circuito físico encendería un LED).
> 
> Las **Leyes de Morgan** y los **Mapas de Karnaugh** (temas de profundización) se utilizan para simplificar estas expresiones, permitiendo que un circuito complejo con muchas compuertas se convierta en uno más eficiente con menos componentes sin alterar el resultado final.
> 
> ## 7. Ejemplos Prácticos
> 
> ### Ejemplo 1: Análisis de Señal en Circuito
> 
> **Consigna:** Dado un circuito con entradas P y Q, donde P = 1 y Q = 1. Q pasa por una compuerta NOT antes de entrar a una compuerta OR con P. **Paso a paso:**
> 
> 1. **Entrada Q:** Vale 1. Al pasar por NOT, se convierte en **0**.
> 2. **Entrada P:** Vale **1** (pasa directo).
> 3. **Compuerta OR:** Recibe 1 (de P) y 0 (de Q negada).
> 4. **Resultado:** Como una OR solo necesita un verdadero para ser verdadera, la salida final es **1 (Verdadero)**.
> 
> ### Ejemplo 2: Identificación de Expresión Booleana
> 
> Para un circuito donde P entra directo a una AND, y Q y R entran negadas a la misma AND, la fórmula se expresaría como: `F = P . ~Q . ~R` (usando el punto como representación de AND).
> 
> ## 8. Errores Comunes y Confusiones
> 
> 1. **Confusión de Símbolos:** Confundir la representación de AND y OR (especialmente al usar `+` y `.`). Se recomienda siempre aclarar la leyenda o diccionario de símbolos antes de resolver.
> 2. **Omisión de Nodos de Negación:** En los diagramas de circuitos, olvidar el pequeño círculo o triángulo que representa la negación (NOT) puede invalidar toda la tabla de verdad.
> 3. **Lectura Incorrecta de la Tabla de Verdad:** Asumir que una tabla es una tautología cuando existe al menos un caso falso por un error de cálculo en las filas intermedias.
> 4. **Dependencia de la IA:** Usar herramientas como ChatGPT para generar tablas de verdad puede llevar a "alucinaciones" o errores lógicos si la sentencia es compleja. Siempre se debe verificar manualmente o con software especializado de código abierto.
> 
> ## 9. Síntesis y Conclusiones
> 
> - La lógica es la estructura que permite el funcionamiento del hardware y el software.
> - El proceso de trabajo ideal es: **Lenguaje Natural -> Diccionario -> Tabla de Verdad -> Fórmula -> Circuito.**
> - La comprensión de las compuertas básicas (AND, OR, NOT) es el requisito previo para avanzar hacia herramientas de simplificación como los Mapas de Karnaugh.
> - La práctica constante con ejercicios de diagnóstico es fundamental para identificar debilidades antes de las instancias evaluativas.
> 
> ## 10. Fechas Importantes y Avisos Académicos
> 
> |   |   |   |
> |---|---|---|
> |Fecha|Evento|Descripción Detallada|
> |**Próxima Clase**|Entrega de Práctica|Resolución de un ejercicio de diagnóstico (Elegir 1 de los 50 enunciados proporcionados).|
> |**Próximas 3 semanas**|Clases Teórico-Prácticas|Se cubrirán temas de Mapas de Karnaugh y Leyes de Morgan.|
> |**Fecha a confirmar**|Parcial|Evaluación de contenidos desde compuertas lógicas en adelante.|
> |**Fecha a confirmar**|Recuperatorio|Instancia para quienes no aprueben el parcial.|
> 
> **Avisos Importantes:**
> 
> - **Propuesta de Evaluación:** El docente está gestionando la posibilidad de reemplazar el parcial tradicional por un **Trabajo Práctico (TP) o coloquio**, sujeto a aprobación institucional.
> - **Metodología:** Se priorizará tomar en el examen ejercicios similares a los resueltos en clase para asegurar que no haya contenidos "sorpresa".
> - **Recursos:** Se recomienda descargar los PDF de Lógica de Predicados, Formas Lógicas y Circuitos Lógicos Digitales de la página de recursos del docente, ya que no se darán de baja pero son esenciales para el estudio "offline".
> 
> ## 11. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Qué diferencia hay entre una tautología y una contradicción?
> 2. Defina la función de una compuerta NOT.
> 3. Si en una compuerta AND una entrada es 0 y la otra es 1, ¿cuál es el resultado?
> 
> ### Nivel Intermedio
> 
> 4. Traduzca la siguiente frase a un diccionario de variables: "Si llueve y no tengo paraguas, entonces me mojo".
> 5. Dada la expresión `P . ~Q`, construya su tabla de verdad.
> 6. ¿Para qué sirve un "Diccionario de Variables" en lógica computacional?
> 
> ### Nivel Avanzado
> 
> 7. Explique cómo se forma una compuerta NOR a partir de compuertas básicas y cuál es su comportamiento lógico.
> 8. Analice por qué es importante la simplificación de circuitos en el diseño de hardware.
> 9. En una tabla de verdad de 3 variables (P, Q, R), ¿cuántas combinaciones posibles existen? (Pista: 2^n).

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 7 - Lógica computacional" src="https://www.youtube.com/embed/TpMrb7o_k9Q?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1G56UGGk2imgo4muExTdFZzxOD2lNgHun/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1tJFdOj7IsN2nQTgFK7l3ktcZpj57NOKy/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>