---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/1-tecnicas-de-programacion/clase-9-lunes-26-de-mayo-de-2025-26-05-25-tecnicas-de-programacion/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio Avanzada: Técnicas de Programación con Node.js y JavaScript
> 
> Este documento constituye un material de estudio integral sobre el desarrollo con JavaScript fuera del entorno del navegador, enfocándose en el uso de **Node.js**, la gestión de paquetes, la interacción con la terminal y la manipulación avanzada de estructuras de datos (arrays y objetos).
> 
> ## 1. Introducción General
> 
> La programación moderna en JavaScript ha trascendido el ámbito de las páginas web para convertirse en una herramienta potente en el desarrollo de servidores y aplicaciones de consola. Esta transición requiere el dominio de entornos de ejecución como Node.js y herramientas de edición como Visual Studio Code, además de una comprensión profunda de la lógica de algoritmos para el procesamiento de datos.
> 
> ## 2. Contexto del Tema
> 
> El desarrollo en JavaScript se divide principalmente en dos entornos:
> 
> 1. **Entorno del Navegador:** Donde se utilizan funciones como `alert()` y se interactúa con el DOM.
> 2. **Entorno de Servidor (Node.js):** Donde JavaScript se ejecuta directamente en el sistema operativo, permitiendo el acceso a archivos, bases de datos y redes.
> 
> ### Importancia y Relevancia
> 
> Dominar Node.js permite a los programadores utilizar un mismo lenguaje para todo el stack de desarrollo. La capacidad de gestionar paquetes a través de **NPM (Node Package Manager)** y de versionar código con **GitHub** es fundamental para el trabajo profesional y colaborativo.
> 
> ## 3. Marco Conceptual
> 
> ### Definición de Conceptos Clave
> 
> - **Node.js:** Entorno de ejecución de JavaScript fuera del navegador. Permite ejecutar scripts directamente en la terminal.
> - **NPM (Node Package Manager):** Gestor de paquetes que permite descargar e instalar librerías o módulos creados por terceros.
> - **Módulo/Paquete:** Conjunto de funciones listas para ser usadas (ej. `readline` para entrada de datos, `express` para servidores web).
> - **Terminal/Consola:** Interfaz de texto donde se ejecutan comandos y se visualizan los resultados de los programas (`console.log`).
> - **JSON (JavaScript Object Notation):** Formato para agrupar datos mediante pares de "nombre de campo" y "valor". En JavaScript, estos se denominan objetos.
> 
> ### Términos Fundamentales en el Código
> 
> |   |   |
> |---|---|
> |Término|Descripción|
> |`require`|Función utilizada para importar un módulo o paquete instalado.|
> |`Math.random()`|Genera un número aleatorio decimal entre 0 y 1.|
> |`Math.floor()`|Redondea un número hacia abajo al entero más cercano.|
> |`push()`|Método para agregar un elemento al final de un array.|
> |`JSON.stringify()`|Convierte un objeto de JavaScript en una cadena de texto (string).|
> 
> ## 4. Desarrollo del Tema
> 
> ### Configuración y Extensiones en Visual Studio Code
> 
> Para programar en JavaScript/Node.js, no es estrictamente obligatorio instalar extensiones adicionales en Visual Studio Code, ya que el soporte es nativo. Sin embargo, existen asistentes como **GitHub Copilot** o **Cursor** que ayudan a autocompletar código. Lo fundamental es tener Node.js instalado en el sistema operativo.
> 
> ### Gestión de Paquetes con NPM
> 
> La interacción con los paquetes se realiza desde la terminal con los siguientes comandos:
> 
> - `npm -v`: Verifica la versión instalada de NPM.
> - `npm install [nombre-paquete]`: Descarga e instala una librería específica.
>     - _Ejemplos comunes:_ `express` (para servidores), `mariadb` (bases de datos), `http` (protocolos de red).
> 
> ### Ejecución de Scripts
> 
> Para ejecutar un archivo JavaScript en Node.js, se utiliza el comando: `node nombre_del_archivo.js` Es imperativo que la terminal esté posicionada en la carpeta donde reside el archivo.
> 
> ### Entrada de Datos: `readline` vs. `prompt-sync`
> 
> Existen dos formas principales de capturar datos del usuario en la terminal:
> 
> 1. **Readline:** Módulo nativo de Node.js. Su implementación es más compleja porque requiere configurar una interfaz de entrada y salida (`process.stdin` y `process.stdout`).
> 2. **Prompt-sync:** Una alternativa más sencilla que permite capturar datos de forma similar al `prompt()` del navegador, aunque debe instalarse previamente.
> 
> ## 5. Relaciones entre Conceptos
> 
> ### Diferencia entre Referencia y Copia en Arrays
> 
> Un error común es intentar copiar un array mediante una asignación directa (ej. `array2 = array1`). En JavaScript, esto no crea una copia, sino que ambas variables apuntan a la misma dirección de memoria. Si se modifica `array2`, `array1` también cambiará. Para crear una copia real, se deben utilizar métodos de clonación de arrays.
> 
> ### Objetos y Estructuras Compuestas (Composites)
> 
> Los objetos permiten organizar la información de manera lógica. Un objeto puede contener arrays, y un array puede contener múltiples objetos. Esta estructura es la base de las APIs modernas.
> 
> - **Acceso:** Se utiliza la notación de punto (ej. `objeto.campo`) o corchetes para índices de arrays (ej. `objeto.array[0]`).
> 
> ## 6. Ejemplos Prácticos
> 
> ### Ejemplo 1: Generación de Números Aleatorios Enteros
> 
> Para obtener un número entero entre 0 y 9, se utiliza la siguiente lógica:
> 
> ```javascript
> let numeroAleatorio = Math.floor(Math.random() * 10);
> ```
> 
> - `Math.random()` da un valor como 0.543.
> - Multiplicar por 10 da 5.43.
> - `Math.floor()` elimina los decimales, dejando el 5.
> 
> ### Ejemplo 2: Eliminación de Números Impares en un Array
> 
> Este algoritmo recorre un array y, al encontrar un número impar, lo "pisa" desplazando los elementos siguientes y reduciendo la longitud del array.
> 
> ```javascript
> function eliminarImpar(array) {
>     for (let i = 0; i < array.length; i++) {
>         if (array[i] % 2 !== 0) { // Si el resto de dividir por 2 no es 0
>             // Lógica para desplazar elementos y reducir .length
>             eliminarPosicion(i, array);
>             i--; // Se decrementa i para volver a evaluar la posición movida
>         }
>     }
> }
> ```
> 
> ### Ejemplo 3: Contar Números Repetidos usando Objetos
> 
> Se crea un array de respuesta que almacena objetos con el formato `{ numero: X, contador: Y }`.
> 
> 1. Se recorre el array original.
> 2. Por cada número, se busca si ya existe en el array de objetos.
> 3. Si existe, se incrementa el `contador`.
> 4. Si no existe, se añade el nuevo objeto con `contador` en 0 (o 1, según la lógica preferida).
> 
> ## 7. Errores Comunes y Confusiones
> 
> 1. **Uso de** `**alert()**` **en Node.js:** El comando `alert()` es exclusivo del navegador. En Node.js se debe usar `console.log()`.
> 2. **Rutas en la Terminal:** Intentar ejecutar un archivo sin estar en la carpeta correcta resultará en un error de "archivo no encontrado".
> 3. **Sincronización en GitHub:** No realizar un `pull` antes de empezar a trabajar en un entorno colaborativo puede generar conflictos de versiones. Es obligatorio sincronizar (Stage -> Commit -> Sync) para mantener el repositorio actualizado.
> 4. **Manejo de Longitud en Arrays:** Al eliminar elementos manualmente dentro de un ciclo `for`, la propiedad `.length` cambia, lo que puede provocar que el ciclo salte elementos si no se ajusta el índice (`i--`).
> 
> ## 8. Síntesis y Conclusiones
> 
> - **Node.js** es la herramienta clave para ejecutar JavaScript en el sistema operativo.
> - **NPM** es el ecosistema que permite expandir las capacidades del lenguaje mediante paquetes.
> - La **Lógica Algorítmica** es esencial para manipular arrays y objetos, especialmente en tareas de filtrado y conteo.
> - **GitHub** no es solo un respaldo, sino una herramienta de versionado necesaria para el desarrollo profesional.
> 
> ## 9. Preguntas de Repaso
> 
> ### Básicas
> 
> 1. ¿Cuál es el comando para ejecutar un script de JavaScript en la terminal?
> 2. ¿Qué diferencia hay entre `console.log()` y `alert()`?
> 3. ¿Cómo se instala un paquete nuevo usando NPM?
> 
> ### Intermedias
> 
> 4. Explique por qué hacer `let b = a` (siendo `a` un array) puede causar problemas si se desea modificar `b` sin alterar `a`.
> 5. ¿Para qué sirve el método `JSON.stringify()` al mostrar un objeto en un `alert` o consola?
> 6. ¿Cómo se accede a un valor dentro de un objeto que está dentro de un array?
> 
> ### Avanzadas
> 
> 7. Describa el proceso lógico para eliminar un elemento de una posición específica de un array sin usar métodos nativos como `splice`.
> 8. En un algoritmo de conteo de repetidos, ¿cuál es la ventaja de usar un objeto con campos `numero` y `contador` en lugar de solo un array de números?
> 
> ## 10. Fechas Importantes y Avisos Académicos
> 
> A partir del análisis de las fuentes, se identifican los siguientes puntos relevantes para la organización de la materia:
> 
> - **Trabajo Práctico N° 5 (TP5):** Actualmente en curso. Se han resuelto ejercicios como la eliminación de números impares y el conteo de repetidos con objetos. Se espera que los estudiantes completen los ejercicios restantes.
> - **Trabajo Práctico N° 6 (TP6):** El profesor indica que probablemente se publicará a la brevedad tras finalizar el TP5.
> - **Evaluaciones:** Se menciona que los ejercicios de arrays (como el de buscar un número) son similares a los tomados en los parciales, lo que sugiere que la lógica de manipulación de arrays es un tema central de examen.
> - **Recursos Adicionales:** Se ha dejado un archivo de prueba sobre `readline` y las resoluciones de los ejercicios en el Drive de la materia.
> 
> **Aviso Importante:** El profesor enfatiza la importancia de aprender el flujo de trabajo con GitHub (Pull, Commit, Sync), calificándolo como "obligatorio" para el trabajo en equipo y como una herramienta que "salva la vida" al permitir recuperar versiones anteriores.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 9 - Técnicas de programación" src="https://www.youtube.com/embed/fMfHSUzFs9I?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1ZY5Gk9R-c6-n_zoR62BtexYIKgCoESY3/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1v5mVpxuF77SUAJijMVKcLkGHKQIy3a8q/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>