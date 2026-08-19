---
{"dg-publish":true,"permalink":"/2-ano-2-cuatrimestre/3-desarrollo-de-sistemas-web-frontend/clase-2-miercoles-19-de-agosto-de-2026-19-08-26-desarrollo-de-sistemas-web-frontend/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía Integral de Desarrollo Frontend: HTML y Fundamentos Académicos
> 
> Este documento constituye un compendio exhaustivo y estructurado de los contenidos abordados en la materia de Desarrollo de Sistemas Web Frontend. Su propósito es servir como material de estudio principal, cubriendo desde la filosofía de aprendizaje de la programación hasta los aspectos técnicos detallados de la estructura web mediante HTML.
> 
> ## 1. Introducción al Aprendizaje de la Programación
> 
> El ingreso al mundo del desarrollo de software no es un proceso inmediato. Es fundamental establecer un marco de expectativas realista para evitar la frustración y gestionar adecuadamente la ansiedad y el fenómeno de _FOMO_ (miedo a perderse de algo).
> 
> ### La Realidad del Aprendizaje
> 
> - **No existen métodos rápidos:** Aprender a programar toma años. Las promesas de "aprender JavaScript en 6 horas" o los _bootcamps_ exprés no ofrecen la profundidad necesaria para una formación profesional sólida.
> - **Diversidad de trayectorias:** Los estudiantes provienen de distintos contextos (_backgrounds_). La comparación con pares que poseen más experiencia previa es contraproducente; cada estudiante debe seguir su propio ritmo de avance.
> - **Satisfacción en la resolución de problemas:** La capacidad de dedicar horas a la lectura y resolución de un inconveniente técnico es lo que define a un usuario avanzado y, eventualmente, a un programador exitoso.
> 
> ### Salidas Laborales y Versatilidad
> 
> El conocimiento en Frontend (HTML y CSS) abre múltiples puertas laborales, incluso antes de dominar lenguajes de programación complejos:
> 
> 1. **Desarrollador Freelance:** Especialmente mediante el uso de herramientas como WordPress.
> 2. **Maquetador de Interfaces (UI/UX):** Diseño de la experiencia y la interfaz de usuario en entornos bancarios o corporativos.
> 3. **Especialista en SEO:** Optimización de sitios web para motores de búsqueda mediante el uso correcto de etiquetas HTML.
> 4. **Desarrollo de Videojuegos:** Aplicación de lógica en herramientas como Godot o el uso de la etiqueta `<canvas>` en HTML para gráficos 2D y 3D.
> 
> ## 2. Marco Conceptual del Entorno Web
> 
> Para entender el frontend, es necesario comprender cómo interactúan el cliente (navegador) y el servidor.
> 
> ### La Analogía del Televisor
> 
> El navegador funciona como un televisor. En lugar de un control remoto, el usuario escribe una dirección (URL) que enmascara una dirección IP física.
> 
> 1. **Petición (Request):** El navegador solicita un recurso al servidor.
> 2. **Servidor:** Una computadora especializada que espera peticiones y devuelve el código HTML.
> 3. **Interpretación:** El navegador recibe el código y lo visualiza para el usuario.
> 
> ### Herramientas del Desarrollador (DevTools)
> 
> Al presionar **F12** o usar el inspector de elementos, el desarrollador puede:
> 
> - **Alterar el HTML/CSS localmente:** Modificar textos, colores o fondos en tiempo real (esto no afecta al servidor, es solo un cambio en la computadora local).
> - **Consola de JavaScript:** Un espacio para ejecutar código de programación directamente en el navegador y visualizar errores o logs.
> 
> ## 3. Desarrollo del Tema: HTML (HyperText Markup Language)
> 
> HTML es un lenguaje de marcas que define la estructura y el contenido de una página web, no su lógica de programación.
> 
> ### Estructura de las Etiquetas
> 
> Se compone generalmente de:
> 
> - **Etiqueta de apertura:** `<nombre>`
> - **Etiqueta de cierre:** `</nombre>`
> - **Atributos:** Información extra dentro de la etiqueta de apertura (ej. `src`, `href`, `alt`).
> 
> ### Conceptos Clave de Visualización
> 
> |   |   |   |
> |---|---|---|
> |Tipo de Elemento|Descripción|Ejemplos|
> |**En Bloque**|Ocupan todo el ancho disponible de la pantalla. Cada elemento nuevo aparece debajo del anterior.|`<div>`, `<p>`, `<h1>` a `<h6>`, `<header>`, `<footer>`|
> |**En Línea**|Solo ocupan el espacio necesario para su contenido. Permiten otros elementos a su lado.|`<span>`, `<a>`, `<img>`, `<button>`, `<input>`|
> 
> ## 4. Elementos y Etiquetas Fundamentales
> 
> ### Títulos y Párrafos
> 
> - **Encabezados (**`**<h1>**` **a** `**<h6>**`**):** Definen la jerarquía del contenido. Se recomienda usar un solo `<h1>` por página para el título principal.
> - **Párrafos (**`**<p>**`**):** Contenedores de texto estándar.
> - **Regla Horizontal (**`**<hr>**`**):** Crea una línea divisoria para separar secciones.
> 
> ### Enlaces y Navegación (`<a>`)
> 
> La etiqueta _Anchor_ requiere el atributo `href` para indicar el destino.
> 
> - **Atributo** `**target="_blank"**`**:** Abre el enlace en una pestaña nueva.
> - **Atributo** `**target="_self"**`**:** Abre el enlace en la misma pestaña (valor por defecto).
> - **Protocolo** `**mailto:**`**:** Permite abrir el gestor de correo predeterminado del usuario.
> 
> ### Imágenes (`<img>`)
> 
> Es una etiqueta que no requiere cierre explícito. Atributos esenciales:
> 
> - `**src**` **(source):** Ruta local o URL de la imagen.
> - `**alt**` **(alternative text):** Descripción para accesibilidad y motores de búsqueda (SEO).
> - `**width**` **/** `**height**`**:** Dimensiones (se recomienda gestionarlas mediante CSS, pero HTML permite ajustes básicos).
> 
> ### Listas
> 
> 1. **Desordenadas (**`**<ul>**`**):** Lista con viñetas (puntos). Útiles para ingredientes o menús de navegación.
> 2. **Ordenadas (**`**<ol>**`**):** Lista numerada automáticamente. Útiles para pasos de una receta o procesos secuenciales.
> 3. **Elementos de lista (**`**<li>**`**):** Cada ítem dentro de `<ul>` u `<ol>`.
> 
> ### Tablas (`<table>`)
> 
> Se utilizan para mostrar datos matriciales.
> 
> - `**<tr>**` **(Table Row):** Define una fila.
> - `**<th>**` **(Table Heading):** Define el encabezado de una columna (negrita por defecto).
> - `**<td>**` **(Table Data):** Define una celda de datos.
> 
> ## 5. Maquetación y Estructura Semántica
> 
> Una página web bien organizada debe evitar tener etiquetas "sueltas". Se debe utilizar una estructura de "esqueleto" basada en contenedores semánticos que facilitan la interpretación del navegador y buscadores.
> 
> ### Contenedores Principales
> 
> - `**<header>**`**:** Cabecera de la página (logo, título).
> - `**<nav>**`**:** Barra de navegación (enlaces principales).
> - `**<main>**`**:** Contenido central y único de la página.
> - `**<footer>**`**:** Pie de página (créditos, contacto, redes sociales).
> - `**<div>**`**:** Contenedor genérico. Se utiliza para agrupar elementos cuando no hay una etiqueta semántica específica que aplique.
> 
> ### El Favicon
> 
> Es el icono de 16x16 píxeles que aparece en la pestaña del navegador junto al título. Se vincula en la sección `<head>` del documento mediante la etiqueta `<link rel="icon" ...>`.
> 
> ## 6. Ejemplos Prácticos: Estructura de una Receta
> 
> Para practicar los conceptos aprendidos, se sugiere estructurar una página de recetas siguiendo este flujo lógico:
> 
> 1. **Título principal:** Usar `<h1>`.
> 2. **Descripción:** Usar `<p>`.
> 3. **Ingredientes:** Usar `<ul>` con múltiples `<li>`.
> 4. **Pasos de preparación:** Usar `<ol>` para enumerar el proceso.
> 5. **Imagen del plato:** Usar `<img>` con su respectivo `alt`.
> 6. **Separadores:** Usar `<hr>` entre secciones.
> 
> ## 7. Errores Comunes y Aclaraciones
> 
> - **Confundir HTML con Programación:** HTML no tiene lógica (condicionales o bucles); es solo estructura.
> - **Uso excesivo de etiquetas en línea:** Colocar elementos como `<span>` o `<img>` fuera de contenedores de bloque (como `<div>` o `<p>`) puede dificultar el posicionamiento posterior con CSS.
> - **Omitir el atributo** `**alt**`**:** Esto perjudica el SEO y la accesibilidad para personas que utilizan lectores de pantalla.
> - **Redundancia en dimensiones:** No es estrictamente necesario poner "px" en los atributos `width` o `height` dentro de las etiquetas HTML de imagen, aunque es una práctica común.
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> |   |   |   |
> |---|---|---|
> |Fecha|Tipo de Evento|Descripción Detallada|
> |**Próximo Miércoles**|Entrega / Revisión|**Práctica Sugerida:** Armar una página web de una receta utilizando etiquetas de títulos, párrafos, listas, imágenes y contenedores semánticos.|
> |**Próxima Reunión**|Coordinación|Reunión para definir la conformación de grupos para el Trabajo Práctico (TP). Se recomienda la asistencia de los voluntarios inscritos.|
> |**Próxima Clase**|Temario Técnico|Se profundizará en **HTML Forms** (Formularios), esenciales para recibir datos del usuario.|
> |**Fines de agosto**|Administrativo|Registro de asistencia: Quienes ingresen tarde a la clase virtual deben poner "Presente" en el chat de la sesión.|
> 
> **Recordatorio:** No existe información oficial unilateral sobre los grupos de TP debido a que se requiere coordinación entre institutos. Se espera tener más novedades tras la reunión de articulación de las 20:00 hs mencionada por el docente.
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia entre una etiqueta `<ul>` y una `<ol>`?
> 2. ¿Para qué sirve el atributo `alt` en una imagen?
> 3. ¿Qué etiquetas definen la estructura básica de una tabla?
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia de comportamiento entre un elemento "en bloque" y uno "en línea".
> 5. ¿Por qué es importante utilizar etiquetas semánticas como `<nav>` o `<main>` en lugar de solo usar `<div>`?
> 6. ¿Cómo se logra que un enlace se abra en una pestaña nueva del navegador?
> 
> ### Nivel Avanzado
> 
> 7. Describa el proceso de comunicación entre el navegador y el servidor cuando un usuario ingresa una URL.
> 8. ¿Qué relación existe entre el correcto etiquetado HTML y el SEO de una página web?
> 9. ¿Cómo influye el uso de contenedores semánticos en la escalabilidad de un proyecto que luego requerirá CSS y JavaScript?

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 2 (19 08 26) - Desarrollo de sistemas web frontend" src="https://www.youtube.com/embed/Ma_8vO25B1s?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/18MVqG-D6rr_FDad5zDKGGnuMoxoAd_Qg/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1Uo0eyya5aMQaAtFYY7Wg_dCAGBWLcnpL/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>