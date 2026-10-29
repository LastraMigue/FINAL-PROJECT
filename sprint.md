A. Web companion con voz e integración con Tabletop Simulator: React + Laravel, voz bilateral, RAG sobre PDFs y webhooks desde un script Lua que informa del estado del tablero.
B. Web/PWA de narración por voz sin integración con el tablero: misma idea de narrador con PDFs, pero los jugadores cuentan lo que pasa. Sirve para cualquier juego de rol, también en mesa física.
C. Web de preparación y consulta de campañas (texto primero): consulta de reglas, generación de escenas y PNJ, historial y resúmenes de sesión. La voz es un extra opcional.
Convención

(× A, B, C): la tarea se hace para cada una de las tres soluciones, con el mismo nivel de detalle y los mismos criterios. Se marca la casilla cuando está hecha para las tres.
(común): la tarea es igual para todas y se hace una sola vez.
Plan de 2 días

Rafa	5, 8, 12

Issue 5 · Propuestas: desarrollo de las soluciones A, B y C

EN: Solutions: development of solutions A, B and C · Label: propuestas · Responsable: Rafa

Desarrollar las tres soluciones con el mismo nivel de detalle, partiendo de las descripciones de arriba.

 (× A, B, C) Descripción: qué es, a quién va dirigida y qué problema de la issue 2 resuelve (3-4 líneas)
 (× A, B, C) Flujo de uso: cómo la usa un jugador o DM antes, durante y después de la partida, en 4-5 pasos
 (× A, B, C) Funcionalidades y tecnologías clave (solo lista, sin diagramas)
 (× A, B, C) Ventajas e inconvenientes: 3 y 3
 (común) Revisar que las tres tienen la misma extensión y profundidad

Hecho cuando: las tres fichas siguen la plantilla y ninguna queda más floja que las otras. Depende de: issues 2 y 4 (arranca con el borrador del problema acordado en el arranque y se cierra cuando ambas están hechas).

**5.1 Solución A: Aplicación web con voz e integración con Tabletop Simulator**

Consiste en una aplicación web que actúa como narrador virtual para partidas de rol. Está dirigida a directores de juego y grupos que quieren disfrutar de partidas dinámicas sin consultar constantemente los manuales o narrar todos los acontecimientos manualmente. La aplicación utiliza la IA para consultar manuales PDF, comunicarse con los jugadores mediante voz y reaccionar a los eventos del tablero.

**5.1.2 Flujo de uso**
- Preparación de la partida: El director de juego accede a la aplicación web y carga el manual o los documentos PDF que utilizará durante la partida

- Procesamiento del manual: El sistema procesa el documento y organiza su contenido para que la IA pueda recuperar información relevante cuando los jugadores hagan preguntas

- Inicio de la partida: Los jugadores utilizan Tabletop Simulator mientras la aplicación escucha sus intervenciones mediante el micrófono

- Narración de los eventos:La aplicación consulta los manuales para responder y narrar mediante voz. Un script Lua envía información sobre el estado del tablero a la aplicación mediante webhooks

**5.1.3 Funcionalidades y tecnologías clave**
- React: Desarrolla la interfaz web permite al director de juego configurar la aplicación y cargar los manuales

- Laravel: Desarrolla la parte del servidor y la lógica de la aplicación.
- RAG: Permite buscar información relevante en los manuales PDF para que la IA pueda responder preguntas sobre las reglas

- LUA: Permite crear un script para recoger información sobre los acontecimientos que suceden en Tabletop Simulator 

- Webhooks: Permiten enviar información desde Tabletop Simulator a la aplicación web

- Reconocimiento y síntesis de voz: Convierte la voz de los jugadores en texto para que la IA pueda interpretarla y convierte las respuestas de la IA en audio para narrar a los jugadores

- Modelo de lenguaje (LLM): Genera respuestas y narraciones adaptadas al contexto de la partida.

**5.1.4 Ventajas e inconvenientes**

- Ventajas

    1. Mayor inmersión: la narración por voz permite mantener el ritmo de la partida

    2. Automatización: la aplicación puede reaccionar a eventos del tablero sin depender únicamente de lo que cuenten los jugadores

    3. Consulta contextual: los manuales PDF sirven como fuente de información para responder preguntas sobre las reglas

- Inconvenientes

    1. Mayor complejidad técnica: requiere desarrollar y conectar la web, los servicios de IA, la voz y el script de Tabletop Simulator

    2. Dependencia de servicios externos: determinadas funciones pueden depender de proveedores de IA, audio o alojamiento

    3. Compatibilidad limitada: la integración específica con Tabletop Simulator puede dificultar su uso con otros tableros o en partidas físicas

**5.2 Solución B: Aplicación web con voz e integración con Tabletop Simulator**

Consiste en una aplicación web que actúa como narrador virtual durante partidas de rol, utilizando inteligencia artificial y manuales PDF para responder preguntas y narrar acontecimientos. Está dirigida a directores de juego y grupos que buscan una experiencia dinámica, tanto en partidas online como en partidas presenciales. A diferencia de la Solución A, no se conecta directamente con Tabletop Simulator, por lo que los jugadores deben explicar lo que sucede durante la partida

**5.2.2 Flujo de uso**

- Carga de los manuales: El director de juego sube a la aplicación los manuales PDF que se utilizarán durante la partida

- Preparación de la información: La aplicación procesa los documentos para poder buscar información relevante cuando los jugadores hagan preguntas

- Comunicación con la IA: Durante la partida, los jugadores hablan mediante un micrófono y explican qué sucede o qué quieren consultar

- Generación de respuestas: La IA utiliza la información de los manuales y lo que han contado los jugadores para generar una respuesta o narrar la escena.

**5.2.3 Funcionalidades y tecnologías clave**

- React: Permite desarrollar la interfaz web con la que interactúa el usuario.

- Laravel: Gestiona la lógica de la aplicación y la comunicación con el servidor.

- RAG: Permite buscar información relevante en los manuales PDF para utilizarla como contexto en las respuestas de la IA.

- Reconocimiento de voz: Convierte lo que dicen los jugadores en texto para que la IA pueda interpretarlo.

- Síntesis de voz: convierte las respuestas de la IA en audio para narrarlas durante la partida.

- Modelo de lenguaje (LLM): Genera respuestas y narraciones teniendo en cuenta las preguntas y los acontecimientos descritos por los jugadores.

**5.2.4 Ventajas e inconvenientes**
- Ventajas

    1. Mayor versatilidad: Puede utilizarse en partidas online o presenciales

    2. Menor complejidad técnica: No necesita conectarse a Tabletop Simulator ni desarrollar scripts para leer sus eventos

    3. Más accesible para distintos grupos: No depende de utilizar un tablero virtual concreto


- Inconvenientes

    1. Dependencia de los jugadores: La IA necesita que le expliquen los acontecimientos de la partida

    2. Posibles interrupciones: Los jugadores pueden tener que detenerse para describir acciones o hacer consultas

    3. Menor automatización: No puede detectar directamente los movimientos o resultados que suceden en un tablero virtual

**5.2 Solución C: Web de preparación y consulta de campañas**

Consiste en una aplicación web que usa la IA para ayudar a los directores de juego a preparar campañas, crear personajes y escenarios, y consultar las reglas de los juegos de rol. Está dirigida principalmente a directores de juego que quieren organizar sus sesiones y reducir el tiempo dedicado a preparar contenido. A diferencia de las soluciones A y B, se centra en las tareas previas y posteriores a las partidas, y no en la narración por voz en tiempo real que se podria incorporar como extra menos desarrollado

**5.3.2 Flujo de uso**

- Preparación de la campaña: El director de juego accede a la aplicación, crea una campaña y, si lo necesita, añade los manuales PDF que utilizará como referencia

- Generación de contenido: La IA ayuda a crear escenarios, personajes, misiones y otros elementos que el director puede utilizar en sus partidas

- Consulta de reglas: El director de juego realiza preguntas mediante texto y la IA busca información relevante en los manuales para responderlas

- Organización de las sesiones: El director utiliza la aplicación para guardar información relevante de la campaña y consultar los datos que haya registrado anteriormente


**5.3.3 Funcionalidades y tecnologías clave**

- React: Permite desarrollar la interfaz web para crear campañas, consultar reglas y gestionar la información.

- Laravel: Gestiona la lógica de la aplicación y las peticiones que recibe del usuario.

- RAG: Permite buscar información relevante en los manuales PDF para utilizarla como contexto en las respuestas.

- Modelo de lenguaje (LLM): genera contenido para las campañas, como personajes, escenarios y misiones, y responde a las consultas del director de juego.

- Síntesis y reconocimiento de voz (opcionales): permitirían añadir consultas habladas y respuestas por audio si se decide ampliar la aplicación con funciones de voz.

**5.3.4 Ventajas e inconvenientes**
- Ventajas

    1. Menor complejidad técnica: No necesita procesar audio en tiempo real ni conectarse a un tablero virtual

    2. Mejor organización: Permite centralizar la información de las campañas y las sesiones en una aplicación

    3. Preparación más rápida: La IA puede ayudar a crear contenido y resolver dudas sobre las reglas.


- Inconvenientes

    1. Menor interacción durante la partida: No está diseñada principalmente para narrar acontecimientos en tiempo real

    2. Dependencia de la IA: Las respuestas y el contenido generado pueden contener errores y necesitan revisión

    3. Menor automatización de la narración: El director de juego sigue teniendo que dirigir la partida y transmitir la información a los jugadores


Issue 8 · Propuestas: comparativa y elección final

EN: Solutions: comparison and final choice · Label: propuestas · Responsable: Rafa

 (común) Cada miembro del equipo puntúa por separado las 3 soluciones con los criterios de la issue 4 y se calcula la media
 (común) Revisar juntos las puntuaciones con diferencias grandes (más de 2 puntos) y explicar el porqué
 (común) Construir la matriz comparativa ponderada
 (común) Redactar la justificación de la elección final basada en la matriz, no en opinión
 (común) Preparar el contenido de las slides de propuestas: las 3 alternativas con pros y contras, y la matriz con la decisión
 (común) Marcar la solución elegida en las slides de innovación y viabilidad (issues 6 y 7)

Hecho cuando: alguien externo puede entender por qué se descartan las otras dos. Depende de: issues 3, 5, 6 y 7.

Issue 12 · Observación de otras presentaciones

EN: Observing other teams' presentations · Label: gestión · Responsable: Rafa, Migue, Christian y Abel

Recomendado por la revisión: al menos un miembro del equipo observa las presentaciones y el feedback de los demás equipos.

 (común) Designar a quién observa
 (común) Apuntar el feedback recibido por otros equipos que también nos pueda aplicar
 (común) Compartir con el equipo un resumen corto (5 líneas) de lo aprendido

Hecho cuando: el equipo tiene una lista de aprendizajes aplicables a su propio proyecto.