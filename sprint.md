## 5. ISSUE:  Propuestas: desarrollo de las soluciones A, B y C ##

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


## 8. ISSUE: Propuestas: comparativa y elección final ##

Para comparar las tres soluciones propuestas para GameMaster AI, utilizaremos una escala del 1 al 5, donde 1 representa una valoración muy desfavorable y 5 una valoración muy favorable.

En los criterios de coste y riesgo legal, una puntuación alta indica un coste menor o un riesgo legal más reducido.



| Criterio                           | Descripción                                                                                                      |
| ---------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| Viabilidad técnica y de tiempo     | Valora si podemos desarrollar la solución con los conocimientos, recursos y tiempo disponibles durante el curso. |
| Coste                              | Estima el coste de desarrollo y mantenimiento de la aplicación.                                                  |
| Inmersión y experiencia de usuario | Valora cuánto mejora la experiencia de juego y la interacción de los usuarios.                                   |
| Diferenciación frente al mercado   | Evalúa si la solución ofrece características que la distinguen de otras aplicaciones de rol.                     |
| Potencial de monetización          | Estima las posibilidades de obtener ingresos mediante suscripciones u otras funciones prémium.                   |
| Riesgo legal                       | Valora los riesgos relacionados con los derechos de autor de los manuales PDF y su utilización.                      |

## 8.1 Matriz de evaluación inicial

| Criterio | Solución A | Solución B | Solución C |
|---|---:|---:|---:|
| Viabilidad técnica y de tiempo | 3 | 4 | 5 |
| Coste | 3 | 3 | 4 |
| Inmersión y experiencia de usuario | 5 | 4 | 2 |
| Diferenciación frente al mercado | 5 | 4 | 3 |
| Potencial de monetización | 4 | 4 | 3 |
| Riesgo legal | 3 | 3 | 3 |
| **Total** | **23/30** | **22/30** | **20/30** |
| **Media** | **3,83/5** | **3,67/5** | **3,33/5** |


## 8.2. Justificación de las puntuaciones

### Solución A: Aplicación web con voz e integración con Tabletop Simulator

- **Viabilidad técnica y de tiempo — 3/5:** Combina interfaz web, inteligencia artificial, procesamiento de voz e integración con Tabletop Simulator mediante Lua y webhooks. Aunque es más compleja, podemos desarrollar primero una versión básica y añadir progresivamente las funciones avanzadas.

- **Coste — 3/5:** El coste se considera medio, ya que los servicios de IA y voz pueden generar gastos, aunque estos pueden controlarse limitando las funcionalidades y el uso.

- **Inmersión y experiencia de usuario — 5/5:** La narración por voz y la capacidad de reaccionar a los acontecimientos del tablero pueden hacer que las partidas sean más dinámicas e inmersivas.

- **Diferenciación frente al mercado — 5/5:** Combina consulta de manuales, narración por voz e integración con los eventos del tablero en una misma aplicación.

- **Potencial de monetización — 4/5:** Podría ofrecer una suscripción prémium con funciones avanzadas, límites de uso más amplios y herramientas adicionales para directores de juego.

- **Riesgo legal — 3/5:** Existe un riesgo que debe controlarse al utilizar manuales PDF. Para reducirlo, se priorizarán documentos propios, autorizados o con licencias compatibles.

### Solución B: Narración por voz sin integración con Tabletop Simulator

- **Viabilidad técnica y de tiempo — 4/5:** Es más sencilla que la Solución A porque no necesita desarrollar la integración con Tabletop Simulator.

- **Coste — 3/5:** Los servicios de inteligencia artificial y procesamiento de voz pueden generar gastos.

- **Inmersión y experiencia de usuario — 4/5:** Permite narrar por voz, aunque depende de que los jugadores describan manualmente los acontecimientos de la partida.

- **Diferenciación frente al mercado — 4/5:** Combina narración por voz y consulta de manuales, pero no automatiza la recepción de eventos del tablero.

- **Potencial de monetización — 4/5:** Podría comercializarse mediante suscripciones y funciones prémium.

- **Riesgo legal — 3/5:** Presenta riesgos similares a la Solución A por el posible uso de manuales PDF protegidos.

### Solución C: Preparación de campañas y consulta de reglas

- **Viabilidad técnica y de tiempo — 5/5:** Es la propuesta más sencilla si se limita inicialmente a consultas por texto y gestión básica de campañas.

- **Coste — 4/5:** Puede evitar los costes asociados al procesamiento de voz en tiempo real y a la integración con Tabletop Simulator.

- **Inmersión y experiencia de usuario — 2/5:** Ayuda a preparar partidas, pero interviene menos directamente en la experiencia de juego.

- **Diferenciación frente al mercado — 3/5:** Sus funciones son útiles, aunque existen otras herramientas que permiten organizar campañas y preparar aventuras.

- **Potencial de monetización — 3/5:** Podría monetizarse mediante funciones prémium, aunque necesitaría diferenciarse de otras herramientas existentes.

- **Riesgo legal — 3/5:** Depende de cómo se obtengan, procesen y utilicen los manuales.

## 8.3 Matriz de comparación ponderada

Como el objetivo principal de GameMaster AI es ofrecer una experiencia de narración inmersiva, consideramos razonable dar mayor importancia a la inmersión y a la diferenciación frente al mercado.

### Pesos de los criterios

| Criterio | Peso |
|---|---:|
| Viabilidad técnica y de tiempo | 20 % |
| Coste | 10 % |
| Inmersión y experiencia de usuario | 25 % |
| Diferenciación frente al mercado | 20 % |
| Potencial de monetización | 15 % |
| Riesgo legal | 10 % |
| **Total** | **100 %** |

### Resultados ponderados

| Criterio | Peso | Solución A | Solución B | Solución C |
|---|---:|---:|---:|---:|
| Viabilidad técnica y de tiempo | 20 % | 3 | 4 | 5 |
| Coste | 10 % | 3 | 3 | 4 |
| Inmersión y experiencia de usuario | 25 % | 5 | 4 | 2 |
| Diferenciación frente al mercado | 20 % | 5 | 4 | 3 |
| Potencial de monetización | 15 % | 4 | 4 | 3 |
| Riesgo legal | 10 % | 3 | 3 | 3 |
| **Puntuación ponderada** | **100 %** | **4,00/5** | **3,80/5** | **3,45/5** |

La puntuación ponderada se obtiene multiplicando la valoración de cada criterio por su peso y sumando los resultados.

## 8.4 Justificación de la solución elegida

### Solución seleccionada: A — Aplicación web con voz e integración con Tabletop Simulator

Hemos elegido la Solución A porque es la que mejor representa la idea original de GameMaster. Aunque requiere un mayor esfuerzo técnico, ofrece una experiencia más inmersiva al combinar la narración por voz, la consulta de manuales y la reacción a los acontecimientos de la partida.

Además, su integración con Tabletop Simulator permite diferenciar el proyecto de una herramienta centrada únicamente en responder preguntas o generar contenido.

## 8.5 Conclusión

La Solución A es la opción que mejor se ajusta a los objetivos de GameMaster AI, ya que obtiene la mejor puntuación al priorizar la inmersión y la diferenciación, sin dejar de considerar el coste, la viabilidad técnica y los riesgos legales. Además combina funcionalidades que pueden mejorar la experiencia de las partidas de rol y aportar un elemento diferenciador frente a otras herramientas.

Aunque las soluciones B y C presentan ventajas en cuanto a simplicidad técnica y coste, la Solución A ofrece un mayor potencial para desarrollar la idea principal del proyecto.