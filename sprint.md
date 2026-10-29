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

**5.2 Flujo de uso**
- Preparación de la partida: El director de juego accede a la aplicación web y carga el manual o los documentos PDF que utilizará durante la partida

- Procesamiento del manual: El sistema procesa el documento y organiza su contenido para que la IA pueda recuperar información relevante cuando los jugadores hagan preguntas

- Inicio de la partida: Los jugadores utilizan Tabletop Simulator mientras la aplicación escucha sus intervenciones mediante el micrófono

- Narración de los eventos:La aplicación consulta los manuales para responder y narrar mediante voz. Un script Lua envía información sobre el estado del tablero a la aplicación mediante webhooks

**5.3 Funcionalidades y tecnologías clave**
- React: Desarrolla la interfaz web permite al director de juego configurar la aplicación y cargar los manuales.
- Laravel: Desarrolla la parte del servidor y la lógica de la aplicación.
- RAG: Permite buscar información relevante en los manuales PDF para que la IA pueda responder preguntas sobre las reglas.
- LUA: 
- Webhooks
- Reconocimiento y síntesis de voz
- Modelo de lenguaje (LLM)

**5.4 Ventajas e inconvenientes**

Solucion B:
Solucion C:


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