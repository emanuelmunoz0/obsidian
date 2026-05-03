---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/4-desarrollo-de-aplicaciones-para-dispositivos-moviles/clase-2-jueves-09-de-abril-de-2026-09-04-26-desarrollo-de-aplicaciones-para-dispositivos-moviles/","dg-note-properties":{}}
---


> [!quote]- Resumen
> # Guía de Estudio: Desarrollo de Aplicaciones para Dispositivos Móviles
> 
> Este documento constituye un material de estudio exhaustivo sobre el desarrollo de aplicaciones móviles utilizando **React Native**, **Expo** y **TypeScript**, basado en las lecciones técnicas proporcionadas en el contexto académico. El objetivo es proporcionar una base sólida desde la configuración inicial hasta la construcción modular de interfaces de usuario.
> 
> ## 1. Introducción y Contexto del Desarrollo Mobile
> 
> El desarrollo de aplicaciones para dispositivos móviles ha evolucionado hacia el uso de frameworks que permiten la creación de aplicaciones nativas utilizando tecnologías web. En este contexto, se utiliza **React Native** bajo el ecosistema de **Expo**.
> 
> ### Entorno de Desarrollo
> 
> Para iniciar el desarrollo, se requieren las siguientes herramientas y consideraciones:
> 
> - **Visual Studio Code (VS Code):** El editor de código estándar para la cursada.
> - **Node.js:** Se requiere una versión actualizada (por ejemplo, la versión 20.20) para gestionar las librerías y el entorno de ejecución.
> - **Android Studio vs. Expo Go:** Aunque Android Studio es una opción nativa, se advierte que requiere un hardware de alto rendimiento y suele presentar lentitud. Como alternativa eficiente, se utiliza **Expo Go**, que permite visualizar la aplicación en un dispositivo real (Android o iPhone) escaneando un código QR.
> - **Expo CLI:** Interfaz de línea de comandos utilizada para crear y gestionar proyectos Expo.
> 
> ## 2. Marco Conceptual y Definición de Conceptos Clave
> 
> Para entender cómo funciona una aplicación móvil moderna, es necesario dominar los siguientes términos fundamentales:
> 
> ### 2.1. Componentes Funcionales
> 
> En React Native, los componentes son las piezas básicas de la interfaz. Un **Componente Funcional (Functional Component)** es una función de JavaScript/TypeScript que retorna elementos de interfaz. Se asemeja a la construcción con bloques (como Legos), donde piezas pequeñas se ensamblan para formar una estructura mayor.
> 
> ### 2.2. TypeScript vs. JavaScript
> 
> Mientras que JavaScript es el lenguaje base, **TypeScript (TSX)** añade "tipado" al código. Esto significa que se definen explícitamente los tipos de datos (números, cadenas de texto, objetos), lo que previene errores comunes de programación y facilita el autocompletado en el editor.
> 
> ### 2.3. Estructura del Proyecto
> 
> Un proyecto estándar de Expo contiene:
> 
> - **node_modules:** Librerías y dependencias necesarias para que el proyecto funcione.
> - **assets:** Carpeta para recursos estáticos como imágenes, fotos e iconos.
> - **index.ts:** El punto de entrada principal donde se registra la aplicación.
> - **app.tsx:** El componente principal o "raíz" de la aplicación.
> - **expo (privada):** Archivos de configuración y compilación propios de la herramienta.
> 
> ## 3. Desarrollo Técnico: Construcción de la Aplicación
> 
> ### 3.1. Etiquetas Fundamentales
> 
> React Native utiliza etiquetas propias que se traducen a componentes nativos del dispositivo:
> 
> - `<View>`**:** Actúa como un contenedor, similar al `<div>` en HTML. Es un cuadrado o caja en la pantalla que puede contener otros elementos. Es más restrictivo que un div tradicional.
> - `<Text>`**:** La única etiqueta permitida para mostrar texto.
> - `<Image>`**:** Utilizada para mostrar contenido visual.
> 
> ### 3.2. Propiedades (Props)
> 
> Las **Props** son variables que se pasan de un componente padre a un componente hijo para que este sea dinámico. Por ejemplo, un componente de "Bienvenida" puede recibir el nombre del usuario como una prop para mostrar un mensaje personalizado. En TypeScript, estas propiedades deben definirse mediante un `type` o `interface` (por ejemplo, `WelcomeProps`).
> 
> ### 3.3. Estilos y Layout (Flexbox)
> 
> React Native no utiliza CSS tradicional, sino un objeto de JavaScript denominado `StyleSheet`. El sistema de posicionamiento principal es **Flexbox**:
> 
> - **Flex:** Define cuánto espacio ocupa un componente proporcionalmente. Si un componente tiene `flex: 1`, ocupará todo el espacio disponible. Si hay dos componentes con `flex: 1`, cada uno ocupará el 50%.
> - **FlexDirection:** Define la orientación de los elementos. Por defecto en móviles es `column` (vertical), pero puede cambiarse a `row` (horizontal).
> - **JustifyContent y AlignItems:** Permiten centrar o distribuir el contenido dentro de un contenedor.
> 
> ## 4. Modularización y Organización del Código
> 
> Para mantener un proyecto escalable y profesional, el código no debe estar en un solo archivo. Se recomienda la siguiente estructura de carpetas:
> 
> 1. **Carpeta** `components/`**:** Contiene subcarpetas para cada componente específico (ej. `Bienvenida/`, `Boton/`).
> 2. **Archivos por componente:**
>     - `Componente.tsx`: La lógica y estructura del componente.
>     - `styles.tsx`: Los estilos específicos de esa pieza.
>     - `types.tsx` (o similar): Las definiciones de TypeScript para las propiedades.
> 
> Este enfoque permite que diferentes programadores trabajen en distintas partes de la aplicación sin generar conflictos, tratando a cada componente como una unidad independiente que se exporta e importa según se necesite.
> 
> ## 5. Gestión de Imágenes y Assets
> 
> Existen dos formas principales de cargar imágenes en una aplicación:
> 
> 1. **Locales:** Se almacenan en la carpeta `assets` y se acceden mediante la función `require('./ruta/imagen.png')`.
> 2. **Remotas:** Se acceden mediante una URL de internet utilizando la propiedad `uri`. Ejemplo: `source={{ uri: '<https://link.com/foto.jpg>' }}`.
> 
> _Nota técnica:_ Es crucial recordar que en los estilos y objetos de configuración, se utilizan **dos puntos (:)** para asignar valores, no el signo igual (=), lo cual es un error sintáctico frecuente.
> 
> ## 6. Errores Comunes y Aclaraciones
> 
> - **Versiones de SDK:** Un error frecuente es la falta de coincidencia entre la versión de Expo instalada en la computadora y la versión de la aplicación **Expo Go** en el celular (ej. SDK 54 vs 55). Se recomienda mantener ambas siempre actualizadas.
> - **Uso de etiquetas:** Intentar poner texto directamente dentro de una `<View>` sin usar la etiqueta `<Text>` provocará un error de compilación.
> - **Lógica de Flexbox:** El diseño en móviles es proporcional. No se recomienda usar píxeles fijos, ya que los dispositivos tienen diferentes tamaños de pantalla; en su lugar, se deben usar porcentajes o unidades de `flex`.
> 
> ## 7. Síntesis y Conclusiones
> 
> - **La aplicación es un árbol de componentes:** Todo se construye ensamblando piezas funcionales, desde la aplicación raíz (`App`) hasta los botones más pequeños.
> - **TypeScript es el aliado:** Aunque requiere definir tipos de datos adicionales, previene errores y mejora la calidad del código.
> - **Modularidad:** Dividir el código en archivos y carpetas es esencial para el trabajo en equipo y el mantenimiento.
> - **IA como herramienta:** El uso de herramientas de Inteligencia Artificial (como ChatGPT o Copilot) es válido siempre que el programador entienda la lógica detrás del código generado y no pierda su capacidad de análisis.
> 
> ## 8. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la función de la etiqueta `<View>` y a qué elemento de HTML se parece?
> 2. ¿Por qué se prefiere usar Expo Go en lugar de Android Studio en máquinas con recursos limitados?
> 3. ¿Cuál es la etiqueta obligatoria para mostrar cualquier cadena de texto?
> 
> ### Nivel Intermedio
> 
> 4. Explique la diferencia entre cargar una imagen con `require` y cargarla mediante una `uri`.
> 5. Si un contenedor tiene tres hijos con `flex: 1`, `flex: 2` y `flex: 1` respectivamente, ¿en cuántas partes se divide la pantalla y cuánto ocupa el segundo hijo?
> 6. ¿Para qué sirven las `Props` en un componente funcional?
> 
> ### Nivel Avanzado
> 
> 7. Describa el proceso de modularización de un componente: ¿qué archivos debería tener su carpeta y por qué?
> 8. ¿Qué problema ocurre cuando las versiones del SDK de Expo en el desarrollo y en el dispositivo móvil no coinciden?
> 9. ¿Cuál es la diferencia fundamental entre el sistema de grillas (grid) tradicional y el sistema Flexbox en React Native?
> 
> ## 9. Fechas importantes y avisos académicos
> 
> Basado en el contexto de la clase, se identifican las siguientes pautas y anuncios:
> 
> - **Horario de cursada:** La clase teórica/práctica tiene una duración establecida hasta las 10:30 o 11:00 PM (equivalente a 6 horas cátedra o 4 horas reloj).
> - **Requisito de Aprobación:** La aplicación final para aprobar la materia **debe acceder obligatoriamente a alguna funcionalidad nativa del teléfono** (ej. giroscopio, geolocalización, cámara, micrófono, calendario o SMS).
> - **Modalidad del Trabajo Final:** El proyecto es **individual**. Cada alumno debe desarrollar su propia aplicación con una funcionalidad específica.
> - **Recomendación del Profesor:** Se aconseja a los alumnos **estudiar la clase siguiente de antemano**. Debido a la intensidad del programa (aprender el lenguaje y desarrollar una app en 14 clases), venir con el material "masticado" permite aprovechar el tiempo para resolver dudas complejas en lugar de aprender conceptos básicos desde cero.
> - **Disponibilidad de Código:** El profesor ha compartido un repositorio en GitHub con el código de la "Clase 2" para que los alumnos puedan clonarlo, ejecutar `npm install` y estudiar la estructura de componentes presentada.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 2 (09 04 26) - Desarrollo de aplicaciones para dispositivos móviles" src="https://www.youtube.com/embed/OUxO8OasTdA?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1FITsYUk643XYesGm-n2JFx5XJXbS2uoM/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1f3oX7q1R00U41CzgglYwwGf43eytyuvT/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>