---
{"dg-publish":true,"permalink":"/1-ano-1-cuatrimestre/1-tecnicas-de-programacion/clase-6-lunes-28-de-abril-de-2025-28-04-25-tecnicas-de-programacion/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio Completa: Técnicas de Programación - Sesión 6
> 
> Este documento constituye un compendio exhaustivo de los temas abordados en la sexta sesión de la materia Técnicas de Programación. Funciona como un manual de estudio integral que cubre desde herramientas auxiliares de inteligencia artificial y entornos de desarrollo, hasta la resolución lógica de algoritmos complejos y estructuras de control.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción y Contexto de la Sesión
> 
> La programación moderna no se limita exclusivamente a la escritura de código; implica el dominio de un ecosistema de herramientas de asistencia, entornos de ejecución, infraestructura de redes y sistemas de control de versiones. Esta sesión se centra en integrar estos conceptos prácticos con el desarrollo de la lógica algorítmica necesaria para resolver problemas complejos mediante estructuras de iteración (bucles) y condicionales.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Herramientas de Asistencia y Desarrollo
> 
> ### 2.1. Inteligencia Artificial como Asistente de Codificación
> 
> El uso de modelos de lenguaje (LLM) como **ChatGPT** o **Claude** se ha convertido en una práctica estándar para optimizar el flujo de trabajo del programador.
> 
> - **Aplicaciones Principales:**
>     - **Explicación paso a paso:** Útil para entender fragmentos de código o algoritmos complejos.
>     - **Generación de módulos cerrados:** Resolución de componentes repetitivos o extensos que consumen tiempo.
>     - **Depuración (Debugging):** Ayuda a identificar errores lógicos o de sintaxis.
> - **Limitaciones Críticas:** La IA no reemplaza el conocimiento propio. Se debe utilizar como un "Copilot" (asistente). El código generado puede no ser eficiente o humano en su lógica, y a veces adaptarlo consume más tiempo que escribirlo desde cero.
> 
> ### 2.2. Control de Versiones: Git y GitHub
> 
> El versionado es una práctica obligatoria en el desarrollo profesional para mantener un historial de cambios y facilitar el trabajo colaborativo.
> 
> - **Git:** Es el concepto y la herramienta técnica de versionado.
> - **GitHub:** Es la plataforma web que aloja los repositorios de Git en la nube.
> - **Conceptos Clave:**
>     - **Repositorio:** Carpeta del proyecto vinculada a la nube.
>     - **Commit:** Registro de un cambio con un nombre descriptivo.
>     - **Sync (Sincronizar):** Es preferible a un "Push" directo cuando se trabaja en equipo, ya que sincroniza de forma inteligente las versiones de varios programadores para evitar sobrescribir el trabajo ajeno.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Infraestructura y Entornos de Desarrollo
> 
> ### 3.1. Conceptos de Redes para Programadores
> 
> Para que un sistema informático sea accesible, debe estar integrado en una red.
> 
> - **Dirección IP:** Es la identificación única ("patente") de cada equipo en internet o en una red local. Se compone de cuatro números separados por puntos.
> - **IP Pública vs. Privada:** La IP pública identifica un servidor en internet; la privada es interna a una red local (detrás de un router).
> - **DNS (Domain Name Service):** Es un servicio que traduce nombres de dominio (como `google.com`) en direcciones IP técnicas, facilitando el acceso humano.
> - **SSH (Secure Shell):** Protocolo que permite acceder a la terminal de un servidor remoto de manera segura para instalar aplicaciones o gestionar el sistema operativo (generalmente Linux).
> 
> ### 3.2. El Stack de Desarrollo (Entorno)
> 
> Para desarrollar sistemas completos, se requiere un ecosistema de componentes:
> 
> |   |   |   |
> |---|---|---|
> |Componente|Descripción|Ejemplos|
> |**Back-end**|Lógica del servidor y procesamiento de datos.|Node.js (Ecosistema), Python.|
> |**Framework Web**|Servidor encargado de interpretar las peticiones.|Express (para JavaScript).|
> |**Base de Datos**|Almacenamiento persistente de información.|**Relacionales:** MariaDB, MySQL. **No relacionales:** MongoDB.|
> |**Front-end**|Interfaz y experiencia del usuario (HTML/CSS).|React (Framework avanzado).|
> 
> **Nota sobre MariaDB:** Es una bifurcación (_fork_) de código abierto de MySQL, creada después de que Oracle comprara el proyecto original de MySQL.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Desarrollo de Lógica Algorítmica (TP3 y TP4)
> 
> ### 4.1. Análisis de Series Numéricas Complejas
> 
> El estudio de series requiere identificar el patrón lógico antes de codificar. Un error común es intentar resolverlo con un solo bucle cuando la estructura pide **bucles anidados**.
> 
> **Caso Práctico: Serie 1 2 3, 2 3 4, 3 4 5... (TP3 Ejercicio 10B)**
> 
> - **Lógica:** La serie avanza de a tres números. El primer número de cada grupo incrementa en uno en cada iteración, y los dos siguientes son consecutivos al primero.
> - **Implementación:** Se utiliza un bucle externo para controlar el inicio de cada tríada y un bucle interno para generar los números consecutivos dentro de esa tríada.
> 
> ### 4.2. Conceptos Matemáticos Aplicados a la Programación (TP4)
> 
> El Trabajo Práctico 4 introduce algoritmos que requieren un procesamiento intensivo de datos:
> 
> 1. **Distribución de Maxwell (Simulación):** Consiste en realizar múltiples experimentos aleatorios para obtener una cantidad fija de "éxitos". Un éxito se define si la suma de 100 números aleatorios es inferior a un umbral (ej. 355).
> 2. **Números de Armstrong:** Aquellos donde la suma de sus n dígitos elevados a la potencia n es igual al número mismo (ej. 153 = 1^3 + 5^3 + 3^3).
> 3. **Números Perfectos:** Números cuya suma de divisores (excluyéndose a sí mismo) es igual al número (ej. 6 = 1 + 2 + 3).
> 4. **Sucesión de Fibonacci:** Cada número es la suma de los dos anteriores (0, 1, 1, 2, 3, 5, 8...). Es fundamental para practicar recursividad o iteración acumulativa.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Errores Comunes y Aclaraciones Didácticas
> 
> - **Bucles Infinitos:** Ocurren cuando la condición de salida nunca se cumple (ej. olvidar incrementar el contador `i++`). Navegadores como Firefox suelen manejarlos mejor, mientras que Chrome puede colapsar el sistema.
> - **Ámbito de las Variables (**`**let**`**):** Al definir una variable con `let` dentro de un bloque de un bucle (entre llaves `{}`), esa variable se destruye al terminar cada iteración. Si se necesita persistencia, debe definirse fuera del bucle.
> - **Depuración con** `**debugger**`**:** El uso de la instrucción `debugger` en el código permite pausar la ejecución en el navegador y analizar el valor de las variables paso a paso mediante el Inspector.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de la sesión, se identifican las siguientes novedades en la organización de la materia:
> 
> - **Cambio de Docente:** Se anuncia la incorporación de un nuevo profesor. El docente actual mantendrá una charla con él para asegurar la continuidad pedagógica de los temas vistos hasta ahora. Se recomienda a los alumnos manifestar cualquier inquietud sobre la línea de enseñanza al nuevo docente.
> - **Actualización de Material:**
>     - Se ha subido el **TP3** (ya disponible aunque hubo retrasos en la carga).
>     - Se ha publicado el **TP4**, que incluye ejercicios de alta complejidad lógica (Maxwell, Fibonacci, Armstrong, Perfectos y una versión del juego Tatetí).
> - **Advertencia sobre TP4:** Ejercicios como los Números Perfectos o de Armstrong pueden requerir mucho procesamiento. Se sugiere probar primero con cantidades pequeñas de números (ej. los primeros 3 o 4) para evitar que la computadora se tilde.
> - **Exámenes de otras materias:** Se reconoce que los estudiantes están actualmente en periodo de estudio para exámenes de **Matemática**.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia entre Git y GitHub?
> 2. ¿Qué función cumple el DNS en la navegación web?
> 3. En un bucle `for`, ¿cuántas veces se ejecuta la sección de inicialización (la primera parte antes del primer punto y coma)?
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia entre una IP Pública y una IP Privada.
> 5. ¿Por qué es importante utilizar "Sync" en lugar de "Push" al trabajar con repositorios compartidos en GitHub?
> 6. Describa la lógica necesaria para determinar si un número es "Perfecto".
> 
> ### Nivel Avanzado
> 
> 7. Dado el ejercicio de la serie de Maxwell, ¿por qué el programa podría entrar en un bucle infinito si el umbral de éxito es demasiado bajo (ej. menor a 300)?
> 8. Diseñe el pseudocódigo para la serie de Fibonacci hasta la posición N ingresada por el usuario.
> 9. Explique el concepto de "bifurcación" (_fork_) en el contexto de MariaDB y MySQL.
> 
> --------------------------------------------------------------------------------
> 
> _Este documento resume la Clase 6 de Técnicas de Programación. Se recomienda practicar los ejercicios de los TPs 3 y 4 para consolidar los conceptos de lógica de iteración._

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 6 - Técnicas de programación" src="https://www.youtube.com/embed/hwmNYOQ5boM?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1GYrUtNAJJoJMbN1ZRrJwakNWuI-f7Y78/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1JrstiPpAR5z6oVd_Uo41-YI7i2HkvLj9/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>