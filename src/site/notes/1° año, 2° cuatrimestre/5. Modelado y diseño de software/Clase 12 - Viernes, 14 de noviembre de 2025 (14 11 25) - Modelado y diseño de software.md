---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/5-modelado-y-diseno-de-software/clase-12-viernes-14-de-noviembre-de-2025-14-11-25-modelado-y-diseno-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio: Modelado y Diseño de Software mediante Diagramas de Paquetes y Clases
> 
> Este documento constituye un material de estudio integral basado en el análisis de sistemas de software, la evolución de la computación y la implementación práctica de diagramas UML. Está diseñado para proporcionar una comprensión profunda desde los fundamentos históricos hasta la aplicación técnica en el diseño de arquitecturas de software.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción y Contexto Histórico
> 
> El diseño de software no es un proceso aislado, sino el resultado de décadas de evolución tecnológica y competencia industrial. Para entender la importancia de las estructuras actuales, es fundamental analizar los hitos que definieron la industria:
> 
> ### La Era de las Computadoras Personales y el Dominio de IBM
> 
> - **Hito de 1981:** El 15 de agosto de 1981, IBM lanzó la PC (modelo 5150), marcando la entrada de los microordenadores en el entorno de oficina. Aunque existía competencia técnica superior, la mentalidad abierta de IBM permitió que su arquitectura copara el mercado en pocos años.
> - **Evolución de Hardware:** En 1987 apareció la línea PS/2, que intentó introducir cambios en los estándares de la industria (como nuevos slots y cambios en el teclado QWERTY), aunque no siempre fueron seguidos por el resto del mercado de clones.
> - **Robustez vs. Obsolescencia:** Sistemas como el **AS/400** (y su base OS/400) son reconocidos históricamente por su robustez extrema, manteniéndose operativos y sin caídas en entornos críticos (como hospitales o bancos) frente a alternativas más modernas pero a veces menos estables.
> 
> ### Control del Sistema: CLI vs. GUI
> 
> Existe una tensión histórica entre las interfaces gráficas de usuario (**GUI**) y la línea de comandos (**CLI**).
> 
> - **Sistemas Operativos:** Desde el MS-DOS y Unix hasta las versiones modernas de Windows (95, 98, 7 en adelante), se ha observado una pérdida progresiva de control directo del usuario sobre la máquina en favor de la comodidad visual.
> - **Recomendación Técnica:** El uso de la consola (CMD) permite un control más profundo y familiar con la computadora, evitando la dependencia absoluta de la abstracción que imponen los sistemas operativos modernos.
> 
> --------------------------------------------------------------------------------
> 
> ## 2. Marco Conceptual: Definición de Conceptos Clave
> 
> En el desarrollo de software moderno, la visualización de la estructura es esencial para gestionar la complejidad.
> 
> ### Diagrama de Clases
> 
> Es un diagrama de estructura estática que describe la estructura de un sistema mostrando sus clases, atributos, operaciones y las relaciones entre los objetos. Es la base del diseño detallado.
> 
> ### Diagrama de Paquetes
> 
> Es un diagrama estructural que se utiliza para agrupar elementos de UML (como clases) en unidades lógicas. Su función principal es organizar el modelo de un sistema a gran escala.
> 
> - **Paquete:** Una carpeta lógica que contiene elementos relacionados.
> - **Dependencia:** Representada mediante flechas, indica que un cambio en un paquete puede afectar a otro.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: Relación y Evolución del Diseño
> 
> El diseño de un sistema no es estático. El proceso suele ser bidireccional entre los diagramas de clases y los de paquetes.
> 
> ### Interacción entre Diagramas
> 
> 1. **Refinamiento:** Al trabajar en un diagrama de paquetes, es común descubrir la necesidad de agregar, modificar o eliminar clases en el diagrama de clases original. Ambos se complementan para ofrecer una visión macro y micro del sistema.
> 2. **Organización Lógica:** Los paquetes permiten dividir el negocio en áreas manejables, como "Finanzas", "Negocios", "Personas" o "Interfaz".
> 3. **Representación de Dependencias:** Se recomienda el uso de flechas separadas para indicar direcciones de dependencia claras, facilitando la lectura de cómo fluye la información y el control entre módulos.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Ejemplos Prácticos de Aplicación
> 
> A continuación, se analizan casos aplicados que demuestran cómo estructurar sistemas complejos mediante paquetes:
> 
> ### Caso A: Sistema de Reserva de Hoteles
> 
> Este modelo requiere una separación clara de responsabilidades para garantizar la seguridad y la eficiencia:
> 
> - **Paquete Cliente:** Gestiona los datos del usuario.
> - **Paquete Interfaz Web:** Actúa como mediador entre el usuario y los servicios internos.
> - **Paquete de Pagos:** Procesa transacciones en línea y emite confirmaciones obligatorias hacia la interfaz.
> - **Paquete de Reservas:** Gestiona la disponibilidad y se comunica con el **Paquete de Gestión de Hotel** (el cual incluye clases como Hotel, Habitación y Personal).
> 
> ### Caso B: Franquicia de Supermercados
> 
> Se utiliza una estructura jerárquica para representar la magnitud del negocio:
> 
> - **Paquete Macro (Franquicia):** Contiene todos los sub-paquetes.
> - **Paquete Transacciones:** Agrupa Ventas, Clientes y Productos.
> - **Paquete Recursos Operativos:** Incluye Sucursal, Empleados y Medios de Contacto.
> - **Servicios Terciarios:** Un paquete dedicado a elementos externalizados como Proveedores, Logística y Pago de Servicios del local.
> 
> ### Caso C: Plataforma de E-commerce
> 
> En este escenario, el diagrama de paquetes ayuda a evitar que el diagrama de clases se vuelva inmanejable:
> 
> - **Organización:** Se divide en Interfaz de Usuario, Ventas, Facturación, Base de Datos, Usuarios y Logística/Envíos.
> - **Gestión de Inventario:** Un paquete de Almacenamiento específico permite la comunicación directa entre el stock y el sistema de pedidos para validaciones de disponibilidad.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Errores Comunes y Aclaraciones Importantes
> 
> |   |   |
> |---|---|
> |Error Común|Aclaración Técnica|
> |**No actualizar el diagrama de clases**|El diagrama de clases debe evolucionar a medida que el diagrama de paquetes revela nuevas dependencias estructurales.|
> |**Sobrecarga de información en un solo diagrama**|Si el diagrama de clases es demasiado grande, se debe recurrir a la abstracción mediante paquetes para reducir la carga cognitiva.|
> |**Confundir la flecha de dependencia**|La punta de la flecha indica qué paquete depende de cuál. Es vital para entender el impacto de futuros cambios en el código.|
> |**Descuidar la confirmación en procesos de pago**|En el diseño de sistemas financieros, siempre debe existir un flujo de confirmación de vuelta desde el procesador de pagos hacia la interfaz.|
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Síntesis y Conclusiones
> 
> - **Complementariedad:** Los diagramas de paquetes y clases son herramientas dinámicas. La creación de uno influye directamente en el refinamiento del otro.
> - **Escalabilidad:** El uso de paquetes es la única forma efectiva de diseñar sistemas de gran escala (como e-commerce o gestiones hospitalarias) sin perderse en el detalle de las clases individuales.
> - **Fidelidad Técnica:** Un buen arquitecto de software no solo diseña interfaces visuales, sino que comprende la robustez del hardware subyacente y la historia de los sistemas operativos para tomar decisiones informadas sobre la estabilidad del sistema.
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Qué ocurrió el 15 de agosto de 1981 y por qué es relevante para la computación?
> 2. ¿Cuál es la función principal de un paquete en un diagrama UML?
> 3. ¿Por qué es importante la confirmación de pago en un diagrama de secuencia o paquetes de un e-commerce?
> 
> ### Nivel Intermedio
> 
> 4. Explique la relación de dependencia entre un paquete de "Interfaz Web" y un paquete de "Reservas".
> 5. ¿Cómo ayuda el diagrama de paquetes a gestionar un diagrama de clases que se ha vuelto demasiado extenso y complejo?
> 6. ¿Qué ventajas ofrecía el sistema AS/400 de IBM en comparación con otros sistemas de su época?
> 
> ### Nivel Avanzado
> 
> 7. Analice el impacto de la política de patentes entre Intel y AMD (1974-1994) en el mercado de hardware.
> 8. Diseñe mentalmente la estructura de paquetes para un sistema de supermercado que incluya logística tercerizada. ¿Qué paquetes serían esenciales y cómo se conectarían?
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> A continuación se detallan las indicaciones administrativas y de evaluación proporcionadas por la cátedra:
> 
> - **Fecha de Evaluación / Firma de Carpetas:** Jueves 20 de junio.
> - **Horario de Inicio:** Se estima el inicio entre las **18:45 y 19:00 horas**.
> - **Evento:** Entrega de carpetas para firma y comunicación de notas finales.
> - **Naturaleza del Examen Parcial:**
>     - **Duración:** Los exámenes suelen ser de corta duración (**15 minutos**). El profesor enfatiza la necesidad de rapidez y precisión: "Si no te apuras, te lo saco".
>     - **Metodología:** El profesor valora la capacidad de respuesta inmediata y el conocimiento directo, evitando métodos como el "múltiple choice" (considerado por él como un invento psicológico con respuestas confusas) en favor de preguntas directas de aprobación.
> - **Recordatorio Importante:** Los alumnos deben asegurarse de tener todos sus trabajos prácticos registrados y la carpeta completa para la instancia del jueves 20. Aquellos alumnos con problemas de conectividad o técnicos durante las presentaciones deben garantizar siempre una vía de comunicación alternativa (como el audio vía teléfono o copias del trabajo en poder de otros miembros del grupo) para no comprometer su evaluación.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 12 - Modelado y diseño de software" src="https://www.youtube.com/embed/Ed7Uvhq38HU?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1p3ZmdVlWeVjLJH7LlacQDzzQY_tzZEaV/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1kYE3NjltdDAKFDT-tp4bVDPiQ9Onngj8/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>