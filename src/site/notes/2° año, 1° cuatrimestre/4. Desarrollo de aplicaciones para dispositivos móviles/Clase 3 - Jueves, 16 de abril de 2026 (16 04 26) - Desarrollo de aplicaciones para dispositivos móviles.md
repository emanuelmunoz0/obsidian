---
{"dg-publish":true,"permalink":"/2-ano-1-cuatrimestre/4-desarrollo-de-aplicaciones-para-dispositivos-moviles/clase-3-jueves-16-de-abril-de-2026-16-04-26-desarrollo-de-aplicaciones-para-dispositivos-moviles/","dg-note-properties":{}}
---


> [!quote]- Resumen
> # Guía Completa de Desarrollo en React Native: Estados, Propiedades y Listas
> 
> Este documento constituye un material de estudio integral sobre el desarrollo de aplicaciones móviles utilizando React Native. Se enfoca en los pilares fundamentales para la creación de interfaces interactivas: el manejo de propiedades (props), el estado interno (state) y la visualización eficiente de colecciones mediante listas.
> 
> ## 1. Introducción General
> 
> El desarrollo en React Native se basa en la construcción de interfaces a través de **componentes funcionales**. Estos componentes actúan como bloques de construcción que, al combinarse como "capas de cebolla", forman una aplicación completa. Para que estos componentes sean dinámicos y respondan a la interacción del usuario, es imperativo comprender cómo se transfiere la información entre ellos y cómo gestionan su propia información interna.
> 
> ### Contexto e Importancia
> 
> En el ecosistema de React Native, la interfaz debe reaccionar a los cambios de datos. La diferencia entre una aplicación estática y una dinámica radica en la correcta implementación de los conceptos de **Propiedades (Props)** y **Estados (States)**. Sin el manejo del estado, la aplicación no sabría cuándo redibujar la pantalla (renderizar) ante una acción del usuario, como presionar un botón o recibir datos de un sensor GPS.
> 
> ## 2. Marco Conceptual: Definiciones Clave
> 
> Para entender el tema desde cero, es necesario distinguir los términos fundamentales que rigen la lógica de los componentes:
> 
> ### Conceptos Fundamentales
> 
> - **Componente Funcional:** Una función de JavaScript que retorna código similar a HTML (JSX) y se convierte en un elemento de la interfaz.
> - **Props (Propiedades):** Parámetros que se pasan de un componente padre a un componente hijo para inicializarlo. Son, por definición, de solo lectura desde la perspectiva del hijo.
> - **State (Estado):** Un valor que vive dentro del componente y representa su situación interna en un momento dado. A diferencia de las props, el estado es mutable y su cambio provoca un nuevo renderizado.
> - **Hook (**`useState`**):** Una función especial de React que permite añadir un estado interno a un componente funcional.
> - **Renderizado (Rendering):** El proceso mediante el cual React dibuja o actualiza la interfaz de usuario basándose en los datos actuales.
> 
> ## 3. Desarrollo del Tema: Estados, Propiedades y Comunicación
> 
> ### 3.1. Diferencia entre Props y State
> 
> La relación entre estos dos conceptos puede entenderse mediante una analogía biológica:
> 
> - **El Estado es como los órganos internos:** El corazón o el estómago de una persona. Tienen sentido solo dentro de ese cuerpo (componente) y definen cómo se encuentra ese individuo.
> - **Las Propiedades son como el agua o la comida:** Información o recursos que vienen del exterior. Al ingresar al cuerpo, estas propiedades pueden modificar el estado interno (por ejemplo, el estómago se hincha al recibir comida), pero el "input" proviene de afuera.
> 
> |Característica|Propiedades (Props)|Estado (State)|
> |---|---|---|
> |**Origen**|Externo (del padre)|Interno (del componente)|
> |**Mutabilidad**|Inmutable (para el hijo)|Mutable (vía modificador)|
> |**Propósito**|Configuración/Inicialización|Interactividad/Dinámica interna|
> 
> ### 3.2. El Hook `useState` y la Convención de "Setters"
> 
> Para declarar un estado en React Native, se utiliza una **dupla** (un arreglo de dos elementos) que se desestructura a partir de `useState`:
> 
> ```jsx
> const [edad, setEdad] = useState(10);
> ```
> 
> 1. **Variable de estado (**`edad`**):** Contiene el valor actual.
> 2. **Función modificadora (**`setEdad`**):** Es el único camino oficial para cambiar el valor. Por convención, se usa el prefijo "set" seguido del nombre de la variable.
> 
> ### ¿Por qué usar un modificador?
> 
> Si se cambia el valor de una variable directamente (ej. `edad = 20`), el valor interno cambia, pero **React no se entera**. Al usar `setEdad(20)`, se le notifica al núcleo de React que hubo un cambio, lo que dispara un "refresh" (redibujado) de la pantalla para mostrar el nuevo valor en todos los lugares donde se use.
> 
> ### 3.3. Comunicación con Aplicaciones Nativas (Intents)
> 
> En el desarrollo móvil, a veces es más eficiente delegar tareas a aplicaciones ya instaladas en el dispositivo en lugar de usar APIs complejas.
> 
> - **Bridge Nativo:** Es el puente de comunicación entre el código JavaScript y las capas del sistema operativo (Android/iOS).
> - **Intent:** Es un "intento" de comunicación entre aplicaciones. Por ejemplo, en lugar de integrar todo el motor de Google Maps vía API (que puede tener costos o restricciones), se puede enviar una latitud y longitud a la aplicación nativa de Mapas mediante un _Intent_ para que esta gestione la ruta.
> 
> ## 4. Visualización de Datos: Listas y FlatList
> 
> Cuando se tiene una colección de datos (como una lista de productos o estacionamientos), existen dos formas de visualizarlos:
> 
> ### 4.1. Mapeo Manual (`.map`)
> 
> Se recorre un arreglo de datos y, por cada ítem, se retorna un componente. Es funcional pero menos eficiente para listas largas, ya que renderiza todo de una vez.
> 
> ### 4.2. El Componente `FlatList`
> 
> Es el estándar en React Native para listas eficientes. Solo renderiza los elementos que están visibles en pantalla. Requiere tres propiedades básicas:
> 
> 1. `data`**:** El arreglo de objetos a mostrar.
> 2. `keyExtractor`**:** Una función para extraer un ID único de cada elemento (ayuda a React a identificar qué cambió).
> 3. `renderItem`**:** Una función que define cómo se debe dibujar cada elemento de la lista.
> 
> ## 5. Ejemplos Prácticos Paso a Paso
> 
> ### Ejemplo 1: Contador de Edad (Estado Simple)
> 
> Este ejemplo muestra cómo un botón puede modificar el estado interno.
> 
> ```jsx
> const SaludoComponent = ({ nombreProp }) => {
>   const [edad, setEdad] = useState(10);
> 
>   return (
>     <View>
>       <Text>Hola {nombreProp}, tenés {edad} años</Text>
>       <Button
>         title="Aumentar edad"
>         onPress={() => setEdad(edad + 10)}
>       />
>     </View>
>   );
> };
> ```
> 
> ### Ejemplo 2: Lista de Productos con `FlatList`
> 
> Supongamos una colección de productos con nombre y precio.
> 
> ```jsx
> const ListaProductos = ({ productos }) => {
>   return (
>     <FlatList
>       data={productos}
>       keyExtractor={(item) => item.id.toString()}
>       renderItem={({ item }) => (
>         <View style={styles.tarjeta}>
>           <Text>{item.nombre}</Text>
>           <Text>${item.precio}</Text>
>         </View>
>       )}
>       ListEmptyComponent={<Text>No hay productos disponibles</Text>}
>     />
>   );
> };
> ```
> 
> ## 6. Errores Comunes y Confusiones
> 
> 4. **Modificar el estado directamente:** Intentar hacer `variable = nuevoValor`. Esto no activará el redibujado de la interfaz. Siempre se debe usar la función `set`.
> 5. **Asincronía del Estado:** Al ejecutar un `setEstado` seguido de un `console.log(estado)`, es probable que el log muestre el valor viejo. Esto ocurre porque el cambio de estado es un proceso asincrónico manejado por React.
> 6. **Confusión entre Web y Mobile:** Usar elementos como `alert()` o etiquetas HTML (`div`, `p`) que no existen en React Native. Se deben usar componentes nativos como `View`, `Text` y `Button`.
> 7. **No retornar el JSX:** En funciones de mapeo o componentes, olvidar la palabra clave `return` (o los paréntesis en arrow functions), lo que resulta en una pantalla vacía.
> 
> ## 7. Síntesis y Conclusiones
> 
> - Los **Componentes** son la base de la UI.
> - Las **Props** permiten la configuración inicial desde el exterior.
> - El **State** permite que la aplicación sea dinámica e interactiva.
> - El hook `useState` vincula variables con la lógica de renderizado de React.
> - La función `set` (modificadora) es indispensable para actualizar la interfaz.
> - `FlatList` es la herramienta optimizada para mostrar colecciones de datos, gestionando memoria y rendimiento.
> 
> ## 8. Preguntas de Repaso
> 
> ### Básicas
> 
> 1. ¿Cuál es la principal diferencia entre una Prop y un State?
> 2. ¿Qué componente de React Native se utiliza para mostrar texto?
> 3. ¿Qué sucede en la interfaz si cambio el valor de una variable de estado sin usar su función "set"?
> 
> ### Intermedias
> 
> 4. Explique para qué sirve la propiedad `keyExtractor` en un `FlatList`.
> 5. ¿Cómo se puede inicializar un estado interno utilizando un valor que viene de una propiedad?
> 6. ¿Por qué se recomienda declarar los estados como `const` en lugar de `var` o `let`?
> 
> ### Avanzadas
> 
> 7. Describa el flujo que sigue React cuando se presiona un botón que ejecuta un `setEstado`.
> 8. En el contexto de geolocalización, ¿cuándo es preferible usar un _Intent_ hacia Google Maps en lugar de su API oficial?
> 9. ¿Cuál es la ventaja de usar `ListEmptyComponent` en lugar de un condicional simple fuera del `FlatList`?
> 
> ## 9. Fechas Importantes y Avisos Académicos
> 
> Basado en la sesión analizada, se extraen las siguientes indicaciones:
> 
> - **Estado de la Materia:** Se encuentra en la Clase 3.
> - **Contenidos Próximos:** Se menciona que temas de conexión a bases de datos externas (como Superbase) no forman parte del núcleo obligatorio de esta materia (se ven en Frontend), aunque podrían explorarse hacia el final del curso si se avanza rápido.
> - **Recomendación de Desarrollo:** Para el proyecto de la materia, se sugiere priorizar el uso de bases de datos locales inicialmente y luego hacer el "switch" a la nube si es necesario.
> - **Uso de APIs:** Se advierte no gastar dinero en APIs pagas (como Google Maps API) para entregas facultativas; se deben buscar alternativas gratuitas o usar _Intents_ hacia las aplicaciones nativas del teléfono.
> - **Material Adicional:** Existe un "Anexo Clase 3" en el aula virtual con ejemplos de `FlatList` y desafíos prácticos (como sumar un quinto producto a la lista) que los estudiantes deben realizar.
> - **Aviso sobre Evaluaciones:** No se mencionan fechas específicas de exámenes parciales en este audio, pero se enfatiza que los puntos básicos de la materia definen la nota inicial de aprobación, y los agregados complejos (como bases de datos externas) suman a la nota final.
> 
> **Nota:** Si alguna fecha de entrega no es explícita en este documento, se recomienda consultar el calendario oficial en el aula virtual.

> [!quote]- Video resumen, infografía y presentación
> # 1. Video resumen
> 
> <iframe title="Clase 3 (16 04 26) - Desarrollo de aplicaciones para dispositivos móviles" src="https://www.youtube.com/embed/CqfDRB82T18?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 2. Infografía
> 
> <iframe src="https://drive.google.com/file/d/1hpuM4svP3U8fQgmtkQvfMF1XYh1nMuVS/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
> 
> # 3. Presentación
> 
> <iframe src="https://drive.google.com/file/d/1n0YPWS4Vxxi72neaTCRU88qcGtVFH4Ha/preview" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>