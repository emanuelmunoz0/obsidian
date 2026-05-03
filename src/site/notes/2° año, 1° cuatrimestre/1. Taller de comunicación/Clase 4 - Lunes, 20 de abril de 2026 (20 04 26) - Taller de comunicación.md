---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/1-taller-de-comunicacion/clase-4-lunes-20-de-abril-de-2026-20-04-26-taller-de-comunicacion/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Análisis de la Comunicación en Proyectos Tecnológicos y Lingüísticos
> 
> Este documento constituye una guía de estudio integral basada en los conceptos de lingüística aplicada, comunicación estratégica y desarrollo de software presentados en el **Taller de Comunicación**. El objetivo es proporcionar una base sólida para entender cómo la lengua se articula con la tecnología y cómo adaptar el mensaje según el interlocutor.
> 
> ## 1. Introducción General
> 
> El estudio de la comunicación en contextos técnicos no se limita a la transmisión de información, sino que implica una comprensión profunda de cómo el lenguaje es procesado tanto por humanos como por máquinas. A través de experiencias en proyectos de análisis de datos y generación de texto, se observa que el éxito de una herramienta tecnológica depende de la precisión lingüística y de la capacidad de los profesionales para traducir conceptos complejos a diversos públicos (clientes, programadores, inversores).
> 
> ## 2. Contexto del Tema: Evolución de la IA y la Lingüística
> 
> El análisis lingüístico ha pasado por diversas etapas, influenciadas por el desarrollo de modelos de lenguaje (como las versiones tempranas de GPT).
> 
> - **2011: El auge del Análisis de Sentimiento:** En esta época, las empresas buscaban procesar grandes volúmenes de datos (Big Data) de plataformas como Twitter para determinar la percepción pública sobre políticos o productos.
> - **2019: Generación Automática de Contenido:** El enfoque cambió de la lectura al "escrito" automatizado, buscando que las máquinas generaran textos en lenguaje natural (como anuncios de Google Ads) que parecieran redactados por humanos.
> 
> ### Importancia y Relevancia
> 
> Entender estos procesos es crucial para cualquier profesional de la comunicación y la tecnología, ya que permite:
> 
> 1. Identificar sesgos en el procesamiento de datos.
> 2. Optimizar la interacción humano-máquina.
> 3. Gestionar proyectos donde convergen áreas técnicas y comerciales.
> 
> ## 3. Marco Conceptual
> 
> Para comprender el desarrollo del tema, es necesario definir términos fundamentales de la lingüística y la lógica:
> 
>
>
> |Concepto|Definición|
> |---|---|
> |**Contenido Proposicional**|El significado fáctico de una afirmación; lo que efectivamente se dice sobre la realidad.|
> |**Lógica Argumentativa**|Orden composicional del texto que permite evaluar la validez de lo que se afirma.|
> |**Polaridad**|La carga valorativa de una palabra o frase, que puede ser positiva, negativa o neutra.|
> |**Infinitud Discreta**|Concepto lingüístico (asociado a Descartes y Chomsky) que explica cómo, con un número limitado de elementos (sonidos/palabras), el ser humano puede crear mensajes infinitos.|
> |**Ítems Léxicos**|Unidades mínimas del vocabulario (palabras) que son categorizadas para ser procesadas por un programa.|
> |**Machine Learning (Outliers)**|En el contexto del taller, se refiere a puntos de datos que causan que un programa "delire" o genere resultados inesperados.|
> 
> ## 4. Desarrollo del Tema
> 
> ### 4.1. Análisis de Sentimiento (El modelo Verdad/Falsedad vs. Positivo/Negativo)
> 
> Originalmente, se intentó que los programas determinaran si una afirmación en redes sociales era **verdadera o falsa**. Este enfoque fracasó porque la "realidad" es a menudo una cuestión de perspectiva, lo que dificultaba la programación lógica.
> 
> **El giro hacia la polaridad:** El sistema evolucionó para clasificar el texto como **positivo o negativo**. Para ello, los lingüistas debieron:
> 
> - **Etiquetar palabras:** Asignar valores a adjetivos (ej. "pésimo" = negativo).
> - **Analizar el contexto:** Identificar cómo ciertas estructuras invierten el significado. Por ejemplo, "no es malo" cambia una palabra negativa en un sentido positivo.
> - **Uso de conectores:** El uso de "pero" puede invertir la lógica de una frase (ej. "El agua es pura... pero voy a tomar cerveza").
> 
> ### 4.2. Generación de Lenguaje Natural (NLG)
> 
> En proyectos de generación de anuncios (Google Ads), el desafío es que la máquina produzca textos coherentes y atractivos a partir de pocos datos de entrada (_inputs_).
> 
> **El proceso de jerarquización:**
> 
> 1. **Entrada de datos:** El usuario ingresa variables básicas (Producto, Ciudad, Características).
> 2. **Atribución semántica:** El programa debe saber qué adjetivos "combinan" con qué sustantivos. (Ej. Una pizza puede ser "rica", pero no "cáustica" o "automatizada").
> 3. **Resultados y Errores:** Aunque el sistema ahorra tiempo (generando opciones en minutos), puede fallar por falta de contexto cultural o semántico, vinculando conceptos de forma inapropiada (como asociar "licor" con "iglesia" o "aborto" por errores de valoración de verbos).
> 
> ## 5. Relaciones entre Conceptos
> 
> La comunicación es un sistema donde la **Economía y la Eficacia** son pilares.
> 
> - **Economía:** Decir lo máximo con el menor esfuerzo posible.
> - **Eficacia:** Que el receptor entienda el mensaje tal como fue planeado.
> 
> En el desarrollo de software, existe una desconexión comunicativa entre los actores:
> 
> - **El Lingüista** habla de "verboides" y "marcadores de frase".
> - **El Programador** se enfoca en el "codeo" y archivos "JSON".
> - **El Comercial/Cliente** solo ve el resultado final (ej. "pongo 4 palabras y obtengo 12 frases").
> 
> Esta disparidad demuestra que el lenguaje técnico funciona como un código compartido solo por los miembros de un equipo específico, mientras que para el exterior debe ser simplificado.
> 
> ## 6. Ejemplos Prácticos de Aplicación
> 
> ### Caso: Evaluación de Comentarios de un Servicio
> 
> - **Entrada:** "El servicio de la empresa X es malo".
> - **Análisis del sistema:**
>     - Detecta el verbo "es" (indicativo, voz activa).
>     - Detecta el adjetivo "malo" (previamente etiquetado con 90% de carga negativa).
>     - **Resultado:** Comentario evaluado como "Negativo".
> 
> ### Caso: Generación de Anuncio para Pizzería
> 
> - **Inputs:** Pizza + Saulo + Barato + Rápido.
> - **Proceso:** El programa busca sinónimos de "barato" (económico, bajo precio) y "rápido" (veloz, entrega inmediata) y los combina con la ubicación.
> - **Resultado:** "La pizza más rica de Saulo a bajo precio y entrega veloz".
> 
> ## 7. Errores Comunes y Confusiones
> 
> 1. **Sinonimia Extrema:** El programa puede confundir "barato" con "paupérrimo". Aunque semánticamente hay un vínculo, el uso social es totalmente distinto. "Paupérrimo" tiene una connotación de pobreza extrema que no es atractiva para una venta.
> 2. **Falta de Filtros Semánticos:** Asignar adjetivos positivos de un rubro a otro donde no tienen sentido (ej. "armas de fuego ricas").
> 3. **Asunción de Conocimiento:** Un error común en los equipos de trabajo es creer que el cliente entiende el "esqueleto" del desarrollo (el Trello, las etiquetas técnicas), cuando el cliente solo está interesado en la funcionalidad.
> 
> ## 8. Síntesis y Conclusiones
> 
> - La comunicación no es unívoca; depende totalmente del contexto y del interlocutor.
> - En la tecnología, la lingüística aporta la "inteligencia" necesaria para que las máquinas no solo procesen datos, sino que comprendan (o simulen comprender) el sentido humano.
> - La labor del analista es jerarquizar y etiquetar el mundo para que el software pueda operar sobre él de manera lógica y eficaz.
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia entre analizar un texto por "verdad/falsedad" y por "positivo/negativo"?
> 2. ¿Por qué es importante el etiquetado de adjetivos en el análisis de sentimiento?
> 
> ### Nivel Intermedio
> 
> 1. Explique el concepto de "infinitud discreta" y cómo se relaciona con la comunicación humana.
> 2. ¿Cómo influyen los conectores (como "pero" o "contrariamente") en la polaridad de una oración?
> 
> ### Nivel Avanzado
> 
> 1. Analice por qué un programa de IA puede generar resultados "delirantes" (outliers) desde una perspectiva semántica.
> 2. Describa cómo varían los niveles de lenguaje entre un lingüista, un programador y un cliente en un mismo proyecto.
> 
> ## 10. Fechas Importantes y Avisos Académicos
> 
> A continuación, se detallan las indicaciones proporcionadas para el desarrollo de la cursada:
> 
> - **Estado de la Materia:** Se ha habilitado un foro para la entrega y consulta de actividades.
> - **Tarea Principal (Proyecto de Cuatrimestre):**
>     - **Tipo de evento:** Trabajo práctico procesual (se trabajará durante todo el cuatrimestre).
>     - **Descripción:** Elegir un proyecto real o ficticio (App, web, emprendimiento) y redactar cuatro tipos de documentos:
>         1. **Documento Explicativo:** ¿En qué consiste el proyecto? (Género explicativo).
>         2. **Documento Argumentativo:** ¿Por qué el cliente debería comprarlo o contratarlo?
>         3. **Documento Técnico:** Explicación detallada para un nuevo integrante del equipo (uso de vocabulario especializado).
>         4. **Documento Informal:** Cómo se lo contarías a un familiar sin conocimientos técnicos (lenguaje lineal y simple).
>     - **Modalidad:** Individual o grupal.
>     - **Fecha de entrega sugerida:** Se recomienda tener un avance para la **próxima clase** para poder seguir trabajando sobre ello.
> - **Contacto del Profesor:**
>     - Se ha proporcionado un correo electrónico de contacto para dudas, consultas o reclamos (disponible en el pizarrón/chat de la clase).
>     - El profesor indica que responderá consultas por mail sin inconvenientes.
> - **Recordatorio Académico:** La materia requiere la realización de estas actividades de redacción de forma constante, ya que el nombre de la materia ("Taller de comunicación") implica un enfoque práctico y de producción de textos.

> [!quote]- Glosario
> # Glosario Académico: Análisis Lingüístico y Comunicación en Proyectos de Inteligencia Artificial
> 
> La integración de la lingüística en el desarrollo de software ha transformado radicalmente el procesamiento de información, permitiendo una transición crítica desde la rigidez de la lógica proposicional —centrada en valores binarios de verdad o falsedad— hacia el análisis matizado de la polaridad. Este cambio de paradigma representa un hito en el análisis de datos, pues permite que los sistemas no solo identifiquen información, sino que interpreten la carga actitudinal en el lenguaje natural. Entender estos fundamentos es un imperativo estratégico para garantizar la precisión del Procesamiento de Lenguaje Natural (PLN), ya que permite capturar la intención comunicativa y reducir el margen de error en la interpretación de grandes volúmenes de datos textuales.
> 
> ### 1. Conceptos Fundamentales de Lingüística Aplicada
> 
> **Contenido proposicional**
> 
> - **Definición:** Significado nuclear de una afirmación que puede ser contrastado con la realidad para determinar su veracidad.
> - **Explicación ampliada:** En las etapas iniciales del análisis automatizado, los sistemas buscaban comparar lo que una oración afirmaba con los hechos del mundo real, arrojando un veredicto lógico de verdadero o falso. Esta relación depende estrictamente de la correspondencia entre la aserción y la perspectiva de la realidad observada.
> - **Ejemplo:** La frase "el agua es transparente" posee un contenido proposicional verificable mediante la observación directa de la realidad física.
> 
> **Infinitud discreta**
> 
> - **Definición:** Capacidad del lenguaje humano para producir una cantidad ilimitada de mensajes a partir de un conjunto finito y limitado de elementos.
> - **Explicación ampliada:** Basado en el "problema de Descartes", este concepto describe cómo el aparato fonador, mediante la combinación de sonidos finitos (fonemas), permite articular pensamientos infinitos. Esta facultad es el núcleo de lo que los modelos de generación de texto intentan replicar artificialmente.
> - **Ejemplo:** A la pregunta "¿Cómo estás?", un hablante puede responder con un simple "bien" o desarrollar una narrativa inagotable sobre sus vivencias y planes futuros.
> 
> **Economía y eficacia**
> 
> - **Definición:** Pilares de la comunicación pragmática que exigen transmitir la mayor cantidad de información con el menor esfuerzo posible, asegurando la comprensión del receptor.
> - **Explicación ampliada:** Estos principios son vitales para evitar que el lenguaje generado por una IA pierda el hilo conductor o se vuelva inentendible. Una comunicación que ignora la economía resulta ineficiente para el interlocutor, quien pierde la relevancia del mensaje original.
> 
> **Modo indicativo**
> 
> - **Definición:** Categoría gramatical utilizada para expresar acciones reales y afirmaciones objetivas sobre el mundo.
> - **Explicación ampliada:** En la programación de sistemas de verificación lógica, el modo indicativo funciona como el identificador principal de aseveraciones verificables. Se utilizaba para que el software reconociera sentencias en redes sociales (como Twitter) y pudiera contrastar su contenido proposicional con la realidad.
> 
> La sólida base teórica proporcionada por la lingüística constituye el cimiento necesario para la formación de los perfiles profesionales interdisciplinarios que lideran los proyectos de IA contemporáneos.
> 
> ### 2. Roles y Responsabilidades en el Ciclo de Vida del Proyecto
> 
> La diversidad de roles en proyectos de Inteligencia Artificial es fundamental para su éxito, aunque las brechas en el lenguaje técnico suelen representar un desafío para la cohesión del equipo. Mientras que el área de sistemas opera bajo lógicas de programación, el área lingüística gestiona estructuras de sentido; por ello, la gestión de expectativas es la clave para mediar entre las capacidades técnicas reales y las demandas de los clientes o financistas.
> 
> **Analista lingüístico**
> 
> - **Definición:** Profesional responsable de etiquetar, jerarquizar y traducir las sutilezas del lenguaje humano a categorías procesables por el sistema.
> - **Explicación ampliada:** Su rol es fundamental para asignar valores numéricos o gramaticales a ítems léxicos, permitiendo que el programa reconozca elementos como la inversión de sentido o la carga emocional de una palabra.
> 
> **Stakeholder**
> 
> - **Definición:** Persona o entidad que financia el desarrollo y posee un interés directo en sus resultados, generalmente sin poseer conocimientos técnicos profundos.
> - **Explicación ampliada:** Dado que el stakeholder evalúa el proyecto basándose en su rentabilidad y utilidad práctica, requiere una comunicación simplificada que omita los detalles complejos de la arquitectura lingüística o del código.
> 
> **Asesor comercial**
> 
> - **Definición:** Perfil que actúa como puente explicativo entre la alta complejidad del equipo técnico y las necesidades del mercado.
> - **Explicación ampliada:** Su función es traducir meses de trabajo técnico en beneficios directos y comprensibles para el cliente, simplificando procesos complejos —como la generación automatizada de textos— para facilitar la contratación del servicio.
> 
> **Lingu (Equipo de lingüística)**
> 
> - **Definición:** Denominación técnica utilizada en plataformas de gestión para las tareas específicas de los expertos en lengua.
> - **Explicación ampliada:** Este rol abarca tareas operativas de alta precisión como la adaptación de marcadores de frase, la traducción de verboides o la revisión de construcciones nominales, actividades que resultan opacas para los especialistas en sistemas pero esenciales para el entrenamiento del modelo.
> 
> La adaptación del mensaje técnico según el rol del receptor garantiza la operatividad interna y permite una transición fluida hacia el uso de herramientas operativas y formatos de intercambio de datos como Trello y JSON.
> 
> ### 3. Técnicas de Análisis y Metodologías de Procesamiento
> 
> El procesamiento de lenguaje natural ha evolucionado desde el análisis de sentimiento binario en 2011 hacia modelos de generación de texto sofisticados en 2019. En este trayecto, la valoración de contextos se ha vuelto indispensable para evitar errores semánticos graves que podrían comprometer la coherencia de los resultados generados.
> 
> **Polaridad (Positiva/Negativa)**
> 
> - **Definición:** Valoración de la carga emocional de un texto que sustituye a la lógica proposicional de verdad o falsedad.
> - **Explicación ampliada:** Se utiliza para determinar si una mención en flujos de datos masivos (como el feed de Twitter) favorece o perjudica la imagen de un político, marca o servicio, asignando etiquetas de sentimiento en lugar de valores de verdad.
> 
> **Etiquetado (Tags)**
> 
> - **Definición:** Asignación de categorías gramaticales y pesos estadísticos a palabras y estructuras de frase.
> - **Explicación ampliada:** El analista señala si un término es un adjetivo, adverbio o participio, y determina su probabilidad de uso en contextos específicos para que el sistema pueda interpretar el sentido de la oración de manera automatizada.
> 
> **Jerarquización de ítems léxicos**
> 
> - **Definición:** Proceso de selección y priorización de términos semánticamente aptos para la generación automática de contenidos.
> - **Explicación ampliada:** Consiste en determinar qué adjetivos o atributos son coherentes con un sustantivo específico, descartando aquellos que, aunque positivos en otros campos, resultan incoherentes para el producto en cuestión.
> - **Ejemplo:** Para el ítem "pizza", se jerarquizan términos como "rica" o "fabulosa", descartando "cáustica" o "automatizada" por su incompatibilidad semántica.
> 
> **Inversión de polaridad**
> 
> - **Definición:** Fenómeno donde conectores específicos alteran el sentido lógico o emocional de una secuencia de frases.
> - **Explicación ampliada:** El uso de conectores como "pero" o "en cambio" puede anular la carga positiva de una enumeración previa, forzando al sistema a reconocer un cambio en la intención final del hablante.
> - **Ejemplo:** "El agua es pura y quita la sed, **pero** voy a tomar cerveza". A pesar de la necesidad lógica de hidratación mencionada al inicio, el conector invierte la decisión final.
> 
> **Valoración de contextos**
> 
> - **Definición:** Uso de porcentajes estadísticos para determinar la carga de una palabra según su entorno lingüístico habitual.
> - **Explicación ampliada:** Se establece que una palabra tiene una carga negativa, por ejemplo, en un 90% de los casos. Este margen permite que el sistema entienda que la polaridad puede invertirse ante la presencia de estructuras de negación (ej. "no es malo"), donde el término negativo adquiere un sentido positivo.
> - **Ejemplo:** El término "pésimo" se etiqueta con un 90% de negatividad, reconociendo que en construcciones específicas su valor puede variar.
> 
> Estas técnicas se integran en modelos de procesamiento masivo que permiten escalar la interpretación humana a niveles industriales de datos.
> 
> ### 4. Modelos y Procesos de Generación de Lenguaje
> 
> La evolución de los modelos GPT representa el esfuerzo por replicar artificialmente la facultad del lenguaje humano. Este desafío requiere una vigilancia constante a través de la edición humana, dado que la automatización total aún se enfrenta a obstáculos semánticos y "delirios" lógicos que pueden surgir durante el procesamiento.
> 
> **GPT (Versiones rudimentarias y GPT-2)**
> 
> - **Definición:** Modelos diseñados para emular el "órgano mental" o módulo computacional del cerebro humano responsable de la adquisición de la lengua.
> - **Explicación ampliada:** Estos sistemas buscan replicar la infinitud discreta, permitiendo que la máquina genere texto en lenguaje natural que simule la capacidad creativa y comunicativa del ser humano.
> 
> **Análisis de Sentimiento (Social Matrix)**
> 
> - **Definición:** Sistema de evaluación masiva de textos utilizado para emitir un veredicto sobre la percepción pública de un objeto.
> - **Explicación ampliada:** Implementado en proyectos como Social Matrix (2011), este modelo analizaba originalmente flujos de datos de Twitter (X) para cuantificar si la imagen de una entidad era mayormente positiva o negativa, superando la limitación del análisis binario previo.
> 
> **Google Ads Automáticos**
> 
> - **Definición:** Proceso de generación de opciones publicitarias a partir de inputs básicos suministrados por el usuario.
> - **Explicación ampliada:** Mediante el uso de sinónimos y juegos de palabras, el sistema toma datos mínimos (producto, ciudad y características) para producir múltiples variantes de anuncios en pocos minutos.
> - **Ejemplo:** Al ingresar "pizza", "San Pablo", "barato" y "rápido", el programa genera opciones como: "La pizza más rica de San Pablo a un bajo precio y entrega veloz".
> 
> **Matching Learning (Outliers)**
> 
> - **Definición:** Errores en el aprendizaje automático que producen resultados incoherentes o "delirios" debido a una excesiva distancia semántica.
> - **Explicación ampliada:** Estos fallos ocurren principalmente por errores en la valoración de los verbos y sus conexiones. El sistema realiza vinculaciones erróneas que lo alejan de la palabra original, perdiendo el hilo lógico de la generación de texto.
> - **Ejemplo:** Un error en la valoración semántica que llevó a asociar "alcohol" con "penas", luego con "iglesia", resultando en un anuncio que sugería "licor para abortar niños en la iglesia".
> 
> La supervisión técnica sobre estos modelos automatizados es vital para corregir desviaciones operativas, lo que subraya la importancia de una gestión técnica rigurosa.
> 
> ### 5. Conceptos de Gestión Técnica y Operativa
> 
> El flujo de trabajo interdisciplinario exige herramientas de comunicación y documentación técnica que actúen como un lenguaje común entre especialistas en lingüística y programadores.
> 
> **Trello**
> 
> - **Definición:** Herramienta de gestión visual que funciona como el esqueleto del desarrollo del proyecto.
> - **Explicación ampliada:** Organiza las tareas en columnas y notas técnicas (ej. "valor ADB"), permitiendo que las áreas de sistemas, lingüística y comercial sigan el avance del proyecto y compartan archivos de entrenamiento.
> 
> **Jason (JSON)**
> 
> - **Definición:** Formato de intercambio de datos ligero y editable que sirve como vehículo de interoperabilidad entre el análisis cualitativo y el procesamiento cuantitativo.
> - **Explicación ampliada:** Es el formato estándar en el que los analistas lingüísticos entregan las bases de datos con las valoraciones de palabras para que los desarrolladores puedan cargarlas y entrenar al sistema de manera eficiente.
> 
> **ADB (Valor ADB)**
> 
> - **Definición:** Tarea técnica consistente en asignar valores de polaridad y peso estadístico específicamente a los adverbios.
> - **Explicación ampliada:** Es un proceso crítico en el entrenamiento de la IA, donde se cuantifica cómo un adverbio (como "extremadamente" o "muy") modifica la intensidad y polaridad de un adjetivo dentro de una frase.
> 
> **Género Explicativo vs. Argumentativo**
> 
> - **Definición:** Distinción entre la exposición objetiva del funcionamiento de un sistema y la retórica orientada a la persuasión.
> - **Explicación ampliada:** El género explicativo se emplea para capacitar a nuevos integrantes del equipo con rigurosidad técnica, mientras que el argumentativo se utiliza para convencer al stakeholder o cliente de la viabilidad y necesidad de contratar el producto.
> 
> La rigurosidad técnica en la comunicación académica y profesional garantiza que el conocimiento complejo sea transferido, ejecutado y comercializado con éxito en el ecosistema de la Inteligencia Artificial.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 4 (20 04 26) - Taller de comunicación" src="https://www.youtube.com/embed/_HGkwWI1ZMU?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1MV54PHNO9Lm324pNCMXQPxCLAcXMCfmH/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1jdBuLCQSYrAbyn8fI7K3mH_Z9nj6MKtj/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>