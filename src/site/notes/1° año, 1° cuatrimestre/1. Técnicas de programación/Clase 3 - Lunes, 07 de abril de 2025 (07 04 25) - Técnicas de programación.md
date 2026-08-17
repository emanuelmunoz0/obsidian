---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/1-tecnicas-de-programacion/clase-3-lunes-07-de-abril-de-2025-07-04-25-tecnicas-de-programacion/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía Completa de Técnicas de Programación: Lógica de Estructuras y Algoritmos Fundamentales
> 
> Este documento constituye un material de estudio exhaustivo basado en las lecciones técnicas sobre programación y lógica algorítmica. En él se sintetizan los conceptos, estructuras de control y resoluciones de problemas prácticos discutidos en clase, con un enfoque en el lenguaje JavaScript y el desarrollo del pensamiento computacional.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> La programación se fundamenta en la capacidad de traducir problemas complejos en una secuencia lógica de instrucciones que una computadora pueda ejecutar. Este documento explora el uso de estructuras de control (condicionales y bucles), la manipulación de datos y la implementación de algoritmos clásicos como el ordenamiento, la verificación de palíndromos y operaciones aritméticas mediante métodos iterativos.
> 
> ### Contexto del Tema
> 
> El contenido se sitúa en el aprendizaje de la lógica de programación intermedia, donde el estudiante ya conoce las variables y operadores básicos, y comienza a enfrentarse a problemas que requieren la integración de múltiples estructuras, como bucles anidados y validaciones complejas.
> 
> ### Importancia y Relevancia
> 
> Dominar estas técnicas es crucial porque:
> 
> - Permite la creación de programas dinámicos que interactúan con el usuario.
> - Fomenta la capacidad de optimizar procesos (escalabilidad).
> - Establece las bases para entender algoritmos de búsqueda y ordenamiento más avanzados.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual y Definiciones
> 
> Para comprender los ejercicios avanzados, es imperativo dominar los siguientes términos y herramientas:
> 
> ### Conceptos Clave de Interacción
> 
> - `**prompt**`: Ventana de diálogo que permite al usuario ingresar un valor (texto o número).
> - `**confirm**`: Ventana de diálogo con opciones de "Aceptar" y "Cancelar". Devuelve un valor booleano: `true` (verdadero) si se acepta, y `false` (falso) si se cancela o cierra.
> - `**alert**`: Muestra un mensaje informativo en pantalla al usuario.
> 
> ### Estructuras de Control e Iteración
> 
> - `**while**`: Bucle que se ejecuta mientras una condición específica sea verdadera.
> - `**break**`: Instrucción que interrumpe inmediatamente la ejecución de la estructura de iteración (bucle) en la que se encuentra, pasando a la siguiente línea de código fuera del bucle.
> - `**if / else if / else**`: Estructuras condicionales que permiten ejecutar diferentes bloques de código según se cumplan o no ciertas premisas.
> 
> ### Manipulación de Cadenas (Strings)
> 
> - `**length**`: Propiedad que indica la cantidad de caracteres de una cadena.
> - `**charAt(índice)**`: Método que devuelve el carácter en una posición específica de la cadena (empezando desde 0).
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: Lógica Aplicada
> 
> ### A. Estructuras de Bucles Anidados (Caso: Caja Registradora)
> 
> Un problema común es gestionar procesos que contienen subprocesos. Por ejemplo, una tienda que atiende a múltiples clientes, donde cada cliente compra múltiples productos.
> 
> 1. **Bucle Externo**: Controla la "apertura de la caja". Se mantiene activo hasta que la cajera indica el cierre del día (usualmente mediante un `confirm`).
> 2. **Bucle Interno**: Gestiona la compra individual de un cliente. Se mantiene activo recolectando productos y cantidades hasta que se ingresa una señal de término (como el número `0`).
> 
> ### B. Algoritmos de Ordenamiento
> 
> Ordenar elementos (como números) es una tarea fundamental. Existen dos enfoques principales:
> 
> - **Métodos no escalables**: Comparaciones manuales fijas (por ejemplo, usar múltiples `if` para comparar 3 números). Funcionan bien para pocos datos, pero se vuelven imposibles de mantener con 10 o 100 números.
> - **Métodos escalables (Burbujeo e Inserción)**: Utilizan bucles para recorrer listas de datos, comparando pares de elementos e intercambiándolos si están fuera de orden. Son aplicables a cualquier cantidad de datos.
> 
> ### C. Lógica de Intercambio (Swap)
> 
> Para intercambiar los valores de dos variables (`n1` y `n2`), se requiere una **variable temporal (**`**temp**`**)** para no perder los datos:
> 
> 1. `temp = n1` (Guardamos el valor de n1).
> 2. `n1 = n2` (Pasamos el valor de n2 a n1).
> 3. `n2 = temp` (Pasamos el valor guardado originalmente en n1 a n2).
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Ejemplos Prácticos Paso a Paso
> 
> ### Caso 1: Sistema de Descuentos en Tienda
> 
> El programa registra productos y aplica descuentos según el monto total.
> 
> **Valores de productos:** | Producto | Precio | | :--- | :--- | | Zapatillas | 5000 | | Remeras | 2500 | | Medias | 1250 |
> 
> **Escala de Descuentos:**
> 
> - Entre 10,000 y 20,000: **10%**
> - Entre 20,000 y 40,000: **20%**
> - Superior a 40,000: **25%**
> 
> **Lógica del algoritmo:**
> 
> 1. Inicializar `mayorCompra = 0`.
> 2. Bucle de caja abierta.
> 3. Reiniciar `compraActual = 0` para el nuevo cliente.
> 4. Bucle de productos: multiplicar `cantidad * precio` y sumar a `compraActual`.
> 5. Al finalizar los productos, aplicar el `if` de descuentos.
> 6. Comparar: `if (compraActual > mayorCompra) { mayorCompra = compraActual }`.
> 7. Al cerrar la caja, mostrar `mayorCompra`.
> 
> ### Caso 2: Verificación de Palíndromos
> 
> Un palíndromo es una palabra que se lee igual de izquierda a derecha que de derecha a izquierda (ej. "neuquen").
> 
> **Algoritmo paso a paso:**
> 
> 8. Obtener la palabra y su longitud (`palabra.length`).
> 9. Usar dos índices: `i0 = 0` (inicio) e `i1 = longitud - 1` (final).
> 10. Mientras `i0 < i1`:
>     - Comparar caracteres en `i0` e `i1` usando `charAt`.
>     - Si son distintos, marcar como "no palíndromo" y salir.
>     - Incrementar `i0` y decrementar `i1`.
> 
> ### Caso 3: División por Restas Sucesivas
> 
> Para hallar el cociente y el resto sin usar el operador de división:
> 
> - Ejemplo: `11 / 4`
>     - `11 - 4 = 7` (1 vez)
>     - `7 - 4 = 3` (2 veces)
>     - `3 - 4` daría negativo, entonces se detiene.
> - **Resultado**: Cociente = 2, Resto = 3.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Errores Comunes y Confusiones
> 
> 1. **Variables Constantes vs. Let**: Intentar reasignar un valor a una variable declarada con `const` (por ejemplo, en un intercambio de valores de ordenamiento) provocará un error de ejecución. Se debe usar `let`.
> 2. **Índices de Cadenas**: Olvidar que las posiciones de los caracteres empiezan en `0`. Si una palabra tiene 5 letras, sus índices son del `0` al `4`. Usar el índice `5` causará un error o devolverá un valor indefinido.
> 3. **Bucle Infinito**: No actualizar la variable de control dentro de un `while` (por ejemplo, olvidar el `i++`).
> 4. **Uso del Break**: Confundir que el `break` sale de todos los bucles anidados. Realmente, **solo sale del bucle inmediato** en el que está escrito.
> 
> **Resumen Parcial**: La clave de un buen código es la validación y el paso a paso. Es recomendable probar pequeñas partes del programa (usando `alert` o `console.log`) antes de completar toda la lógica para no arrastrar errores difíciles de localizar.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Síntesis y Conclusiones
> 
> - **Modularidad**: La lógica debe dividirse en problemas pequeños (primero calcular el precio, luego el descuento, luego el mayor).
> - **Flexibilidad**: Los algoritmos escalables son preferibles sobre las soluciones manuales fijas.
> - **Control de Flujo**: El uso correcto de `while` y `if` permite manejar procesos del mundo real, como transacciones comerciales o análisis de texto.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Preguntas de Repaso (Tipo Examen)
> 
> ### Nivel Básico
> 
> 1. ¿Qué diferencia hay entre el valor devuelto por `prompt` y `confirm`?
> 2. ¿Cómo se obtiene el último carácter de una palabra si no conocemos su longitud de antemano?
> 3. Defina la función de una variable temporal en un algoritmo de intercambio.
> 
> ### Nivel Intermedio
> 
> 4. En un sistema de bucles anidados, ¿qué sucede si se ejecuta un `break` dentro del bucle más interno?
> 5. Explique cómo funciona el método de división por restas sucesivas.
> 6. ¿Por qué es importante inicializar la variable `mayorCompra` en 0 al empezar un registro diario?
> 
> ### Nivel Avanzado
> 
> 7. Describa la lógica para verificar si un número es primo.
> 8. Compare un método de ordenamiento no escalable con uno escalable (como el de burbujeo) en términos de eficiencia y mantenimiento de código.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> Basado en la información proporcionada en la sesión, se detallan los siguientes puntos de relevancia administrativa y académica:
> 
> - **Trabajo Práctico 3 (TP3):** Se estima su publicación para el día **miércoles o jueves** (indicado como "hoy o mañana" en la sesión del martes).
> - **Próxima Clase de Lógica:** Se llevará a cabo el **jueves**. En esta sesión se revisarán los enunciados del TP3 para asegurar su total comprensión.
> - **Resolución de Ejercicios:** Las versiones definitivas y corregidas de los ejercicios del TP2 (específicamente el ejercicio 4) estarán disponibles en la **carpeta compartida** de la materia para consulta de los alumnos.
> - **Asistencia:** Se recuerda a los estudiantes registrar su presente en el archivo Excel de manera habitual.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 3 - Técnicas de programación" src="https://www.youtube.com/embed/E1fJGytI3Ag?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1nMk7vmr8gm-vrheKu9FgEkGmIS2qADUp/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1l8Xh618TEF4FRYhqkhld4tBc7PgWAqCU/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>