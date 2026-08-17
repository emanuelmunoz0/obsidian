---
{"dg-publish":true,"permalink":"/1-ano-2-cuatrimestre/5-modelado-y-diseno-de-software/clase-8-viernes-10-de-octubre-de-2025-17-10-25-modelado-y-diseno-de-software/","dg-note-properties":{}}
---

> [!quote]- Resumen
> # Guía de Estudio Avanzada: Modelado y Diseño de Software
> 
> Este documento constituye una síntesis exhaustiva de la sesión académica centrada en el modelado de sistemas mediante diagramas de colaboración y de estado. El contenido integra las presentaciones de proyectos prácticos, el análisis técnico de flujos de trabajo y las perspectivas históricas sobre el funcionamiento del hardware y software.
> 
> --------------------------------------------------------------------------------
> 
> ## 1. Introducción General
> 
> El modelado de software es una etapa crítica en el diseño de sistemas que permite visualizar la interacción entre componentes y los cambios de estado de las entidades. A través del análisis de casos prácticos como reservas hoteleras, ventas de pasajes aéreos y plataformas de comercio electrónico, se establecen las bases para construir sistemas robustos, capaces de gestionar excepciones (como la falta de stock o errores de pago) y de adaptarse a las normativas vigentes (facturación electrónica).
> 
> ## 2. Marco Conceptual
> 
> Para comprender los sistemas presentados, es fundamental definir los dos pilares del modelado discutidos:
> 
> ### Conceptos Clave
> 
> - **Diagrama de Colaboración:** Se centra en la organización de los objetos que participan en una interacción. Muestra cómo los objetos se comunican entre sí para cumplir con una función específica del sistema. Es una vista dinámica que enfatiza la relación entre los elementos.
> - **Diagrama de Estado:** Describe el comportamiento de un sistema o un objeto específico al mostrar sus transiciones entre diferentes estados a lo largo de su ciclo de vida, respondiendo a eventos o estímulos.
> - **Time-out (Tiempo de espera):** Un mecanismo de control que determina la expiración de una acción o reserva si no se completa en un plazo determinado.
> - **Stock Dinámico:** Estado de disponibilidad de un producto que debe actualizarse en tiempo real para evitar errores de sobreventa.
> 
> --------------------------------------------------------------------------------
> 
> ## 3. Desarrollo del Tema: Análisis de Casos Prácticos
> 
> El estudio se divide en cuatro áreas lógicas basadas en los modelos presentados por los grupos de trabajo:
> 
> ### A. Sistema de Reserva Hotelera
> 
> Este modelo abarca desde la intención del cliente hasta la confirmación de la estancia.
> 
> - **Flujo de Colaboración:**
>     1. El cliente inicia la reserva hacia el hotel (el sistema).
>     2. El hotel crea la reserva en el sistema interno.
>     3. Se verifica la disponibilidad de habitaciones.
>     4. Se solicitan y entregan datos de los huéspedes.
>     5. Se gestiona el pago (seña o total).
> - **Consideraciones de Estado:**
>     - **Iniciada:** La reserva comienza su ciclo.
>     - **Verificación:** Si hay disponibilidad, se asigna habitación; si no, se cancela.
>     - **Pago:** Puede requerir un adelanto (10%, 50%) o el 100% según la política. Si el pago falla, la reserva se cancela.
>     - **Confirmada:** Estado final tras el pago y la asignación de personal.
> 
> ### B. Sistema de E-commerce (Comercio Electrónico)
> 
> Inspirado en modelos como Amazon o Mercado Libre, enfocado en la automatización.
> 
> - **Interacciones Principales:**
>     - **Carga de Productos:** Al abrir la página, se instancian los productos disponibles.
>     - **Carrito de Compras:** Se crea una instancia única por usuario donde se acumulan los ítems.
>     - **Gestión de Pedido:** El carrito envía la información al módulo de pedido, el cual se vincula con el módulo de pago.
> - **Gestión de Excepciones:**
>     - Si un método de pago es rechazado, el sistema debe permitir "Grados de Libertad", ofreciendo al usuario modificar el método antes de cancelar.
>     - En caso de falta de stock (por compras simultáneas), el sistema debe permitir reprogramar el envío o cancelar la operación.
> 
> ### C. Venta de Pasajes Aéreos
> 
> Un modelo complejo que incluye servicios adicionales y múltiples canales de salida.
> 
> - **Estados del Proceso:**
>     1. **Búsqueda:** Filtrado por fechas y destinos.
>     2. **Reserva:** Generación de datos preliminares.
>     3. **Criterios Adicionales:** Inclusión de seguros y equipaje extra.
>     4. **Abonar:** Transición al éxito del pago o al canal de atención al cliente en caso de rechazo.
>     5. **Finalización:** Entrega de tarjeta de embarque (formato físico o código QR).
> 
> ### D. Compra Presencial (Supermercado)
> 
> Un modelo simplificado de interacción física.
> 
> - **Componentes:** Cliente, carrito físico, sucursal y vendedor.
> - **Proceso:** El cliente elige productos, el vendedor confirma la venta y la sucursal procesa el pago.
> 
> --------------------------------------------------------------------------------
> 
> ## 4. Relaciones entre Conceptos y Profundización Técnica
> 
> ### La Importancia del "Time-out"
> 
> Los sistemas de reserva y las aplicaciones web deben implementar ventanas de espera. Si un usuario no concreta una acción (como un pago o un inicio de sesión) en el tiempo previsto, el sistema debe cerrar la sesión o liberar el recurso para mantener la eficiencia y seguridad.
> 
> ### Redes y "Upgrades"
> 
> En industrias de alta demanda (hotelería/aerolíneas), las empresas suelen operar en redes o monopolios. Esto permite que, ante una sobreventa ("overbooking"), el sistema gestione un traslado a otro establecimiento de igual o mayor categoría (upgrade) para evitar quejas legales y proteger la reputación de la marca.
> 
> ### Evolución de los Estados del Hardware (CPU)
> 
> El modelado de estados no es exclusivo del software; es la base de la electrónica y las CPUs.
> 
> - **Sistemas Antiguos:** El arranque (boot) era visible y manual (ej. carga mediante disquetes).
> - **Modo Real vs. Modo Protegido:** Las CPUs antiguas trabajaban en modo real (limitado a 1MB de memoria). El modo protegido permite reconocer toda la memoria física instalada.
> - **Automatización:** Hoy en día, los estados de inicialización ocurren a velocidades que el ojo humano no percibe, saltando directamente a la interfaz del sistema operativo.
> 
> --------------------------------------------------------------------------------
> 
> ## 5. Ejemplos Prácticos de Flujo de Datos
> 
> |   |   |   |   |
> |---|---|---|---|
> |Paso|Actor|Acción del Sistema|Estado Resultante|
> |1|Cliente|Selecciona "Reservar"|Reserva Iniciada|
> |2|Sistema|Consulta Base de Datos|Disponibilidad Verificada|
> |3|Cliente|Ingresa Tarjeta de Crédito|Pago en Proceso|
> |4|Pasarela|Valida Fondos|Pago Confirmado / Rechazado|
> |5|Sistema|Emite Voucher / Factura|Reserva Finalizada|
> 
> --------------------------------------------------------------------------------
> 
> ## 6. Errores Comunes y Confusiones
> 
> 1. **Omisión del Stock:** Un error frecuente es no prever que el stock puede agotarse entre el momento en que se añade al carrito y se realiza el pago. El sistema debe validar el stock en el último paso.
> 2. **Falta de Feedback:** No informar al usuario por qué falló un pago o una reserva genera fricción. Siempre se deben incluir estados de "Atención al Cliente" o "Reintento".
> 3. **Rigidez del Sistema:** No permitir volver atrás para cambiar un método de pago obliga al usuario a iniciar todo el proceso de nuevo, aumentando el riesgo de abandono.
> 4. **Ignorar la Normativa Fiscal:** En el diseño de facturación, se suele olvidar que existen diferentes condiciones frente al IVA (Monotributista, Responsable Inscripto) que deben estar contempladas en el sistema para la emisión de facturas legales (AFIP).
> 
> --------------------------------------------------------------------------------
> 
> ## 7. Síntesis y Conclusiones
> 
> - **Fidelidad del Modelo:** Los diagramas deben reflejar la realidad del negocio (ej. políticas de seña o sobreventa).
> - **Interconectividad:** Un sistema de ventas no es una isla; se conecta con inventarios, pasarelas de pago y servicios de atención al cliente.
> - **De lo Macro a lo Micro:** El diseño inicial debe capturar el flujo general ("macro"), para luego pulir los detalles finos ("micro"), como los tipos de factura o los tiempos exactos de expiración.
> 
> --------------------------------------------------------------------------------
> 
> ## 8. Fechas Importantes y Avisos Académicos
> 
> Tras el análisis de la sesión, se establecen las siguientes pautas:
> 
> - **Fecha de entrega/finalización del TP:** La semana próxima (contada desde el 17 de octubre).
> - **Formato de Presentación:** Los diagramas deben presentarse **impresos**.
> - **Estado de los Trabajos:** Se permiten presentaciones de borradores o bocetos para corrección previa.
> - **Recordatorio Académico:** Es fundamental que los diagramas (especialmente los de estado) incluyan realimentación y contemplen todas las opciones posibles de salida.
> 
> --------------------------------------------------------------------------------
> 
> ## 9. Preguntas de Repaso
> 
> ### Nivel Básico
> 
> 1. ¿Cuál es la diferencia principal entre un diagrama de colaboración y uno de estado?
> 2. ¿Por qué es importante el estado de "verificación de disponibilidad" en un hotel?
> 
> ### Nivel Intermedio
> 
> 1. ¿Qué sucede técnicamente cuando un sistema de reserva llega a un "time-out"?
> 2. Explique cómo funciona el proceso de "Upgrade" en una red de hoteles y por qué se considera una política de ética empresarial.
> 
> ### Nivel Avanzado
> 
> 1. Analice la transición del "Modo Real" al "Modo Protegido" en las CPUs y cómo esto afectó la gestión de estados en el software de los años 90.
> 2. En un sistema de e-commerce, ¿qué medidas de diseño evitarían que dos personas compren el último producto disponible al mismo tiempo?

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 8 - Modelado y diseño de software" src="https://www.youtube.com/embed/AYE68k-py0A?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1ZFid3tBvZunVoN99H6CFYeoeZIE008UG/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1XzvbPkuPraHnIXRLd0ABHX3lIKytcpt-/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>