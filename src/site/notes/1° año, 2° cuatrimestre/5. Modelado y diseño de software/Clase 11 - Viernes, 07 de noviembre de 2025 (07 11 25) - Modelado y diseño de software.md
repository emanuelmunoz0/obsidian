---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/5-modelado-y-diseno-de-software/clase-11-viernes-07-de-noviembre-de-2025-07-11-25-modelado-y-diseno-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía Integral de Estudio: Desarrollo de Sistemas Orientados a Objetos
> 
> Este documento constituye una síntesis exhaustiva de los fundamentos de la programación orientada a objetos (POO) y la configuración de entornos de desarrollo, diseñada como material de estudio principal para la materia.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General al Paradigma
> 
> El desarrollo de sistemas ha evolucionado a través de diferentes **paradigmas de programación**, que son esencialmente modelos o estilos de programación que definen cómo se estructura y ejecuta el código. La transición hacia la **Programación Orientada a Objetos (POO)** surge como una respuesta a las limitaciones de los modelos anteriores para gestionar la complejidad creciente de los sistemas informáticos.
> 
> Esta materia se define como un "híbrido": combina la teoría profunda de la POO con el aprendizaje práctico de la **infraestructura y el setup de desarrollo**. El objetivo es que el estudiante no solo comprenda la lógica de objetos, sino que también domine el ecosistema de herramientas (servidores, bases de datos, entornos de ejecución) necesarias para profesionalizar el desarrollo de aplicaciones.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Contexto e Importancia: Del Modelo Procedimental a la POO
> 
> ### El Paradigma Procedimental
> 
> Históricamente, la programación era predominantemente procedimental. Se basaba en una secuencia de instrucciones con estructuras de control (condicionales e iteraciones). Aunque funcional, presentaba dos problemas críticos al escalar:
> 
> 1. **Dificultad de Mantenimiento:** Modificar una funcionalidad en un sistema extenso implicaba rastrear infinitas líneas de código, con un alto riesgo de romper partes no relacionadas ("efecto dominó").
> 2. **Baja Reutilización:** El código estaba tan entrelazado con funciones específicas de una aplicación que era casi imposible trasladarlo a otro proyecto.
> 
> ### El Surgimiento de la POO
> 
> En la década de los 90, la POO se consolidó (con lenguajes como Java y C++) como la solución para organizar el software de manera similar a cómo percibimos el mundo real: a través de entidades con características y comportamientos definidos. Hoy en día, los lenguajes modernos como JavaScript o Python son multiparadigma, permitiendo combinar lo procedimental, lo lógico, lo funcional y lo orientado a objetos de forma fluida.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Marco Conceptual: Definición de Conceptos Clave
> 
> Para entender la POO desde cero, es fundamental distinguir entre sus componentes básicos:
> 
> ### A. Clase (El Molde)
> 
> Es una abstracción que define la estructura de un tipo de objeto. Se escribe siempre en **singular** (ej. `Cliente`, no `Clientes`). Define qué datos tendrá el objeto y qué podrá hacer.
> 
> ### B. Objeto o Instancia (El Resultado)
> 
> Es la materialización de la clase. Mientras que la clase es el "plano", el objeto es la "casa construida". Cada objeto ocupa un lugar en la memoria (variable) y tiene valores específicos para sus atributos.
> 
> - _Sintaxis conceptual:_ `Variable = New Clase()`.
> 
> ### C. Atributos (Datos/Características)
> 
> Son las variables internas de la clase que definen las propiedades del objeto.
> 
> - **Públicos:** Accesibles desde cualquier parte del código.
> - **Privados:** Solo pueden ser modificados por los métodos internos de la misma clase (crucial para la seguridad de datos como contraseñas o saldos).
> - **De Instancia:** Valores que cambian entre objetos (ej. el nombre de cada cliente).
> - **De Clase:** Valores compartidos por todos los objetos de esa clase (ej. la anatomía básica en una clase `Persona`).
> 
> ### D. Métodos (Funciones/Comportamientos)
> 
> Son las acciones que el objeto puede realizar.
> 
> - **Constructores:** El método especial que se ejecuta automáticamente al crear un objeto (`new`). Se encarga de inicializar los atributos.
> - **Getters:** Métodos para obtener/leer el valor de un atributo.
> - **Setters:** Métodos para establecer o modificar el valor de un atributo, permitiendo incluir validaciones.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Los Cuatro Pilares de la POO
> 
> La solidez de este paradigma se apoya en cuatro conceptos fundamentales que guían el diseño de software:
> 
> |   |   |   |
> |---|---|---|
> |Pilar|Descripción|Analogía / Ejemplo|
> |**Abstracción**|Proceso de simplificar la realidad, seleccionando solo los atributos y métodos relevantes para el sistema y descartando el resto.|Para un banco, un `Cliente` es un DNI y un saldo; no importa su altura o color de ojos.|
> |**Encapsulamiento**|Ocultar la complejidad interna. Los datos están "protegidos" dentro del objeto y solo se accede a ellos a través de métodos autorizados.|Para conducir un auto, presionas el acelerador (método); no necesitas saber cómo funciona la inyección de combustible (lógica interna).|
> |**Herencia**|Capacidad de crear clases nuevas a partir de clases existentes, heredando sus atributos y métodos. Permite jerarquías (clase padre/hijo).|Una clase `Persona` (padre) hereda sus rasgos a `Empleado` y `Cliente` (hijos).|
> |**Polimorfismo**|Capacidad de que diferentes clases respondan de manera distinta a un mismo mensaje o método.|El método `CerrarCuenta` actuará distinto si es una `Caja de Ahorro` o una `Cuenta Corriente`.|
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Desarrollo del Entorno y Ecosistema Tecnológico
> 
> Un pilar de esta formación es el **Setup de Infraestructura**. No basta con programar la lógica; se debe configurar el entorno donde la aplicación "vive".
> 
> - **Ecosistema JavaScript:** Es la decisión estándar para el desarrollo en este curso.
> - **Node.js:** El entorno que permite ejecutar JavaScript fuera del navegador (en el servidor). Es vital saber gestionar paquetes (instalar/desinstalar).
> - **Express:** Framework de Node para crear servidores web y APIs que responden a solicitudes de navegadores.
> - **Bases de Datos:** Se requiere conexión y capacidad de realizar consultas (queries) para crear, modificar y acceder a datos. Se mencionan opciones vectoriales para IA como Pinecone o Chroma.
> - **Frontend:** El usuario interactúa mediante HTML y CSS. Se permite el uso de frameworks como Angular, React o Next para quienes deseen mayor complejidad.
> - **Inteligencia Artificial (IA):** Se incentiva el uso de IAs (vía API o modelos locales) tanto para asistir en la codificación como para integrarlas como funcionalidades dentro de las aplicaciones.
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Ejemplos Prácticos: Sistema Bancario
> 
> A continuación, se detalla cómo se estructuraría una aplicación bancaria bajo este paradigma:
> 
> ### Clase: `CuentaBancaria`
> 
> - **Atributos:** `numeroCuenta`, `propietario`, `CBU`, `montoDisponible` (privado), `limite`.
> - **Métodos:**
>     - `getSaldo()`: Retorna el dinero disponible.
>     - `setLimite(nuevoLimite)`: Modifica el límite previa validación.
>     - `checkOperacion()`: Verifica si una transacción no supera el límite.
> 
> ### Relación entre Clases
> 
> Un sistema real conecta múltiples moldes:
> 
> 1. Un **Banco** (clase) tiene un atributo que es una **Lista/Array** de **Cuentas Bancarias**.
> 2. Al ejecutar el método `aperturaCuenta()` en la clase `Cliente`, se invoca al **Constructor** de la clase `CuentaBancaria` para generar un nuevo objeto.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Errores Comunes y Clarificaciones
> 
> - **Confusión entre Clase y Objeto:** Es frecuente intentar asignar un valor (como un nombre específico) a la clase. El valor pertenece al objeto; la clase solo define que _existirá_ un nombre.
> - **Exceso de Atributos:** No realizar una abstracción correcta lleva a sistemas pesados con datos innecesarios.
> - **Transparencia en Cambios:** Una gran ventaja del encapsulamiento es que si se cambia la lógica de un método (ej. cómo se autentica una contraseña), el resto del sistema no se entera ni se rompe, siempre que la respuesta final del método siga siendo la misma.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> Basado en la planificación docente y los anuncios de clase, se establecen los siguientes hitos:
> 
> |   |   |   |
> |---|---|---|
> |Fecha (Estimada/Fija)|Tipo de Evento|Descripción Detallada|
> |**Clase 3 o 4**|Inicio de Proyecto|Comienzo del trabajo grupal y configuración de infraestructura (Node, bases de datos).|
> |**Fines de Agosto - 20 Sept.**|Viaje del Profesor|El docente estará en Italia. Las clases podrían ser grabadas o reprogramadas ante problemas de conexión.|
> |**Mediados de Octubre**|Trabajo Práctico (TP)|Entrega de TP de ejercicios (posiblemente un TP largo de ~20 ejercicios).|
> |**22 de Octubre**|Clase Presencial|Tercera instancia presencial obligatoria (según planificación tentativa).|
> |**29 de Octubre**|**Examen Parcial**|Evaluación presencial de contenidos teóricos y prácticos.|
> |**Noviembre (Post-Parcial)**|Avances de Proyecto|Dinámica de tutorías: cada grupo tiene 30 min asignados para corrección.|
> |**Fines de Noviembre**|Presentación Final|Exposición presencial de los proyectos grupales funcionales.|
> 
> **Recordatorios Importantes:**
> 
> - **Asistencia:** Hay 4 clases presenciales mínimas obligatorias.
> - **Grupos:** El trabajo es grupal para simular entornos de desarrollo reales.
> - **Entorno:** Es obligatorio tener Node.js instalado y funcional en las máquinas personales para el inicio del proyecto.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso
> 
> ### Básicas
> 
> 1. ¿Cuál es la diferencia principal entre una Clase y un Objeto?
> 2. Defina los conceptos de Atributo y Método.
> 3. ¿Para qué sirve el método Constructor de una clase?
> 
> ### Intermedias
> 
> 4. Explique la importancia del Encapsulamiento con un ejemplo que no sea el del automóvil.
> 5. ¿Por qué el paradigma procedimental dificulta el mantenimiento de sistemas grandes?
> 6. ¿Qué diferencia hay entre un atributo de instancia y un atributo de clase?
> 
> ### Avanzadas
> 
> 7. Describa el proceso de Abstracción al diseñar una clase `Producto` para un banco vs. para un supermercado.
> 8. ¿Cómo se relaciona la herencia con la reutilización de código?
> 9. Analice por qué JavaScript se considera un lenguaje apto para este paradigma a pesar de ser multiparadigma.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 1 - Desarrollo de sistemas orientado a objetos" src="https://www.youtube.com/embed/vnjtJeCOHYM?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1fSpXQSUxFjlAgI2zsIKVRtyF_kkjPB_D/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1qvm3ckFbOSYjyvO2XjnR2_5t-FU_M-rf/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>