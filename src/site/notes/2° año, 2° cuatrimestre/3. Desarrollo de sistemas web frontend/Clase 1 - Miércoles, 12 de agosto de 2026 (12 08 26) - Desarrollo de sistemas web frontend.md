---
{"dg-publish":true,"permalink":"/2-ano-2-cuatrimestre/3-desarrollo-de-sistemas-web-frontend/clase-1-miercoles-12-de-agosto-de-2026-12-08-26-desarrollo-de-sistemas-web-frontend/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio Integral: Desarrollo de Sistemas Web Frontend
> 
> Este documento constituye el material de estudio principal para la materia de Desarrollo de Sistemas Web Frontend. Integra los conceptos fundamentales, la metodología de trabajo, las herramientas técnicas y las pautas académicas necesarias para el dominio de la disciplina, basándose en las directrices de la cátedra.
> 
> ## 1. Introducción y Contexto de la Materia
> 
> La formación en desarrollo frontend se presenta como el primer paso en una carrera profesional continua. El objetivo central es garantizar que el estudiante sea capaz de desarrollar interfaces web sólidas y funcionales, con la capacidad de clonar y reproducir cualquier interfaz existente en el mercado laboral.
> 
> ### Perfil del Instructor y Filosofía de Trabajo
> 
> El curso es dictado por el profesor **Javi (o Xavi)**, especialista en Frontend y sistemas Linux. Su enfoque pedagógico prioriza:
> 
> - **La base técnica sólida:** Entender el "porqué" de cada etiqueta y línea de código.
> - **Filosofía Open Source:** Promoción del desarrollo abierto (de todos para todos), que es la génesis de la computación e internet.
> - **Autonomía profesional:** Formar "pilotos de aviación" en el código; profesionales que conozcan cada control de su cabina y no dependan de instrucciones externas automatizadas.
> 
> ## 2. Marco Conceptual: La Arquitectura Web
> 
> Para entender el desarrollo frontend, es necesario comprender cómo se divide el trabajo en la web y cómo interactúan sus componentes.
> 
> ### 2.1 Frontend vs. Backend
> 
> |   |   |   |
> |---|---|---|
> |Dimensión|Frontend|Backend|
> |**Definición**|Desarrollo de interfaces gráficas con las que el usuario interactúa directamente.|Parte de la web que no se ve; se encarga del manejo de la información.|
> |**Ubicación**|"Adelante": lo que el cliente ve.|"Atrás": el servidor que provee los datos.|
> |**Tecnologías Base**|HTML, CSS y JavaScript.|Lenguajes de servidor (ej. C#, Java/Springboot, Cobol).|
> 
> ### 2.2 El Trípode del Frontend
> 
> El desarrollo frontend se apoya en tres pilares fundamentales:
> 
> 1. **HTML (Los Ladrillos):** Define la estructura y el contenido de la web.
> 2. **CSS (La Pintura):** Define la capa de estilo, colores y posicionamiento.
> 3. **JavaScript (El Cerebro):** Aporta interacción y lógica a la interfaz.
> 
> ## 3. El Navegador como Intérprete
> 
> El navegador web funciona de manera análoga a un televisor. Es una herramienta que apunta a un **recurso** (ubicado en una ruta local o una URL) y lo visualiza.
> 
> ### Conceptos Clave del Funcionamiento:
> 
> - **Recursos:** El navegador puede visualizar imágenes, videos, PDFs y archivos de texto.
> - **Interpretación de Código:** Cuando el navegador recibe un archivo con extensión `.html`, no lo lee como texto plano, sino que interpreta las etiquetas para darles un formato específico (títulos, listas, enlaces).
> - **Protocolo HTTP:** Es el protocolo de comunicación fundamental entre el cliente (navegador) y el servidor.
> - **DNS (Domain Name Service):** Servicio que traduce direcciones físicas (IP) en nombres alfabéticos legibles (ej. google.com) para evitar que el usuario deba memorizar números.
> 
> ## 4. HTML: Lenguaje de Marcado de Hipertexto
> 
> HTML no es un lenguaje de programación, sino un **lenguaje de marcado** (etiquetas). Se utiliza para describir la estructura de un documento web.
> 
> ### 4.1 Estructura Básica de un Documento
> 
> Todo documento HTML debe seguir un orden jerárquico:
> 
> 1. `<!DOCTYPE html>`: Indica al navegador que el archivo es un documento HTML5.
> 2. `<html>`: Etiqueta raíz que envuelve todo el contenido. Posee el atributo `lang` (idioma).
> 3. `<head>`: Contiene la **información no visible** (metadatos, título de la pestaña, enlaces a estilos).
> 4. `<body>`: Contiene toda la **información visible** (títulos, párrafos, imágenes) con la que el usuario interactúa.
> 
> ### 4.2 Etiquetas Fundamentales
> 
> |   |   |   |
> |---|---|---|
> |Etiqueta|Función|Notas|
> |`<h1>` a `<h6>`|Encabezados|`<h1>` es el más grande; `<h6>` el más pequeño.|
> |`<p>`|Párrafo|Define bloques de texto.|
> |`<a>`|Ancla (Link)|Usa el atributo `href` para definir el destino.|
> |`<img>`|Imagen|Usa `src` (fuente) y `alt` (texto alternativo).|
> |`<ol>` / `<ul>`|Listas|`ol` es ordenada (números); `ul` es no ordenada (puntos).|
> |`<li>`|Ítem de lista|Elemento individual dentro de una lista.|
> |`<div>`|Divisor|Contenedor genérico para organizar elementos.|
> 
> ## 5. El Rol de la Inteligencia Artificial (IA)
> 
> El profesor establece una postura crítica y estratégica respecto al uso de herramientas como ChatGPT, Gemini o Claude:
> 
> - **Uso Correcto (La IA como Compañero):** Utilizarla para preguntar conceptos, pedir explicaciones "bajadas a tierra" o entender fundamentos.
> - **Uso Incorrecto (El "Sedentarismo Cognitivo"):** Delegar el desarrollo del código a la IA. Esto provoca que el estudiante no aprenda (desaprenda) y sea incapaz de defender su código en una entrevista técnica.
> - **Advertencia Laboral:** Las empresas detectan fácilmente el código generado por IA que el desarrollador no puede explicar. La IA es útil para resolver problemas aislados, pero no para construir la lógica integral de un proyecto sin supervisión experta.
> 
> ## 6. Metodología y Plan de Estudios
> 
> La cursada consta de **16 clases de una hora y media** cada una, distribuidas de la siguiente manera:
> 
> - **HTML (3 clases):** Incluyendo una clase entera dedicada exclusivamente a **Formularios**, por ser la base de la entrada de datos del cliente.
> - **CSS (3 clases):** Enfoque en Flexbox para el posicionamiento de elementos.
> - **JavaScript (8 módulos):** Desde bases básicas hasta niveles avanzados, preparando al alumno para entrevistas técnicas.
> 
> ### Herramientas Recomendadas
> 
> - **Sistema Operativo:** Linux (específicamente distribuciones como Ubuntu o Linux Mint).
> - **Editor de Texto:** Visual Studio Code o **BS Codium** (versión Open Source).
> - **Control de Versiones:** Git y GitHub.
> 
> ## 7. Fechas Importantes y Avisos Académicos
> 
> Esta sección detalla la organización de la materia y las opciones de evaluación.
> 
> ### Cronograma de Evaluación (Modalidad Estándar)
> 
> - **Trabajos Prácticos Individuales:**
>     - **Portfolio 1:** Diseño inicial.
>     - **Portfolio 2:** Continuación y despliegue del portfolio. Se puede entregar directamente el Portfolio 2.
> - **Trabajos Prácticos Grupales:**
>     - **TP Grupal 1:** Clonación de una web.
>     - **TP Grupal 2:** Clonación de web incorporando una API (pública o propia).
> 
> ### Propuesta de Articulación (Proyecto Optativo)
> 
> Existe un proyecto especial que **exime de los dos trabajos grupales de clonación**:
> 
> - **Evento:** "Jornada IT" (Banco de Proyectos para el Ministerio/Agencia).
> - **Tarea:** Desarrollo del Frontend de una página web para que alumnos de tecnicaturas presenten sus proyectos de PP4 a autoridades y empresas.
> - **Colaboración:** El frontend lo hace esta clase; el backend lo realizan alumnos del IFTS 18.
> - **Fecha de Entrega:** Finales de octubre.
> - **Grupos:** Mínimo 2 personas, máximo 5.
> 
> ### Avisos Académicos Importantes
> 
> - **Asistencia:** Se toma mediante captura de pantalla. Es obligatorio avisar por chat si hay problemas de conexión o necesidad de retirarse antes.
> - **Entrega de Trabajos:** La fecha límite general es **una semana antes de finalizar la cursada**. Se recomienda entregar antes para recibir feedback.
> - **Contacto Docente:** Javier Rodríguez (javie.rodriguez@bue.edu.ar).
> 
> ## 8. Síntesis del Contenido
> 
> 1. El Frontend se encarga de la interfaz y la experiencia del usuario (HTML + CSS + JS).
> 2. HTML es la estructura (ladrillos); CSS es el estilo (pintura); JS es la lógica (cerebro).
> 3. El navegador interpreta etiquetas para transformar texto plano en documentos formateados.
> 4. La IA debe ser una herramienta de consulta, nunca de sustitución del pensamiento lógico.
> 5. La práctica profesional requiere saber "clonar" interfaces y defender el código de forma oral.
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 6. ¿Cuál es la diferencia fundamental entre HTML y JavaScript?
> 7. ¿Para qué sirve la etiqueta `<head>` en un documento HTML?
> 8. ¿Qué hace el atributo `src` en una etiqueta `<img>`?
> 
> ### Nivel Intermedio
> 
> 9. Explique la analogía del "Navegador como televisor" y cómo se relaciona con las URLs.
> 10. ¿Qué es un DNS y por qué es importante para el usuario final?
> 11. ¿Cuál es la diferencia entre una lista ordenada (`ol`) y una no ordenada (`ul`) a nivel de interpretación del navegador?
> 
> ### Nivel Avanzado (Preparación para Examen)
> 
> 12. ¿Por qué el profesor advierte sobre el "sedentarismo cognitivo" al usar IA en el desarrollo?
> 13. Describa el proceso de petición y respuesta (Request/Response) cuando un usuario ingresa a una web como el Diario AR.
> 14. ¿Qué importancia tienen las APIs web (como Canvas) en la potencialidad del navegador moderno?

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 1 (12 08 26) - Desarrollo de sistemas web frontend" src="https://www.youtube.com/embed/vH9VgBQSsK8?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/19wCCHDLbaN6MaZGl-Q5TqP6SRVUoKC_N/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/11c74DMN8xNQwMIzjMgCRLJKJSIkoRih3/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>