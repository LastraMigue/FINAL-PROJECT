# GameMaster AI — Sprint 1: Necesidad, Innovación y Viabilidad Técnica

## Información del Proyecto y Sprint

**Proyecto:** GameMaster AI (plataforma de narración inteligente por voz para rol) | **Sprint 1:** Necesidad, benchmark, propuesta de solución y viabilidad técnica.  
**Solución principal desarrollada:** Web companion con voz e integración con Tabletop Simulator (TTS), complementada con el análisis comparativo de alternativas de narración y preparación.

---

## Índice

- [Información del Proyecto y Sprint](#información-del-proyecto-y-sprint)
- [1. Necesidad e investigación de jugadores](#1-necesidad-e-investigación-de-jugadores)
- [2. Benchmark y diferenciación frente al mercado](#2-benchmark-y-diferenciación-frente-al-mercado)
- [3. Propuesta de solución: GameMaster AI Companion](#3-propuesta-de-solución-gamemaster-ai-companion)
- [4. Viabilidad técnica y comparativa de soluciones](#4-viabilidad-técnica-y-comparativa-de-soluciones)
- [5. Bibliografía](#5-bibliografía)

---

## 1. Necesidad e investigación de jugadores

### 1.1. Perfil de jugadores y Dungeon Masters (DMs)
- **Estructura típica:** Mesas de 1 Director de Juego (DM/GM) y 3 a 5 jugadores en sesiones regulares de 3 a 4 horas.
- **División de roles:** Los jugadores buscan inmersión y dinamismo narrativo; el DM asume en solitario la preparación previa, la memorización de reglamentos y el arbitraje en vivo.
- **Herramientas en uso:** Ecosistema fragmentado (tableros virtuales como Roll20 o Tabletop Simulator, compendios digitales como D&D Beyond, canales de voz en Discord y notas dispersas). Alternar entre tantas aplicaciones rompe el ritmo de la sesión.

### 1.2. Problemas recurrentes y testimonios reales
- **Falta de jugadores y dificultad para consolidar mesas:** Problema estructural en el sector para encontrar suficientes participantes disponibles o coordinar horarios estables, lo que provoca la cancelación de campañas o impide que grupos reducidos puedan disfrutar de partidas completas.
- **Sobrecarga de preparación:** DMs invierten horas organizando tramas y encuentros que se desbaratan ante decisiones imprevistas.  
  > *«No quiero parecer que no estoy preparado cuando inevitablemente tenga que rebuscar entre las páginas para encontrar la sección adecuada...»*
- **Parones por consulta de reglas:** Búsquedas manuales en manuales densos que congelan la acción en momentos clave de combate.  
  > *«Al buscar las reglas, no encuentro nada sobre cómo liberar a los compañeros que están inmovilizados.»*
- **Fatiga de improvisación y pérdida de inmersión:** Dificultad para mantener ambientaciones creíbles ante giros inesperados.  
  > *«No se me da bien improvisar. ¿Qué puede hacer alguien a quien le cuesta inventar respuestas interesantes en el momento... sin que suene forzada?»*

### 1.3. Evidencia y justificación de urgencia
- **Datos de respaldo:** En encuestas del sector (3.663 respuestas), el **57 % de los DMs dedica 2 o más horas a preparar** cada sesión de 4 horas. En plataformas de juego virtual, *Tabletop Simulator* acumula **entre 2 y 5 millones de usuarios** con picos constantes de **~6.150 jugadores simultáneos**.
- **Justificación:** La falta de jugadores disponibles para cerrar mesas y la saturación del DM al preparar y consultar reglas en vivo son los grandes cuellos de botella que frenan las partidas de rol. La dispersión de herramientas actual fragmenta la experiencia, haciendo urgente una solución conectada que asista en tiempo real, agilice el juego y permita disfrutar de partidas dinámicas incluso con mesas reducidas.

---

## 2. Benchmark y diferenciación frente al mercado

### 2.1. Alternativas de mercado analizadas
- **[Roll20](https://roll20.net/)** (Freemium / 4,17–8,33 $/mes): Tablero VTT líder en navegador con mapas, dados y fichas. *Se limita a ser una mesa virtual; carece de narración por IA y no consulta manuales PDF propios.*
- **[D&D Beyond](https://www.dndbeyond.com/)** (Freemium / 2,17–4,58 $/mes): Plataforma oficial con visor Maps y reglas. *Ecosistema cerrado exclusivo de D&D; no admite manuales de otros juegos ni lectura semántica de documentos del usuario.*
- **[AI Dungeon](https://aidungeon.com/)** (Freemium / 9,99–29,99 $/mes): Ficción interactiva generada por IA con voz. *Pensada para historias libres; alucina con facilidad, ignora reglamentos estrictos y no interactúa con ningún tablero.*
- **[AI Game Master](https://www.aigamemaster.app/)** (Freemium / Micropagos): App móvil conversacional para partidas individuales con voz. *Enfocada a juego individual en pantalla móvil; inviable para una mesa colaborativa tradicional.*

### 2.2. Tabla comparativa de mercado

| Solución | Enfoque principal | ¿Voz en directo? | ¿RAG PDFs propios? | ¿Conexión con tablero? | Ámbito de uso |
|---|---|---|---|---|---|
| **Roll20** | Tablero VTT en navegador | Sí (chat WebRTC) | No | Sí (propio navegador) | Partidas online |
| **D&D Beyond** | Compendio oficial D&D | No | No (solo oficial D&D) | Sí (Maps integrado) | Ecosistema D&D |
| **AI Dungeon** | Ficción interactiva IA | Sí (lectura TTS) | No | No | Historias en solitario |
| **AI Game Master** | Rol en solitario en app | Sí (móvil) | No | No | Móvil individual |
| **GameMaster AI (A)** | **Narración, reglas y tablero** | **Sí (Bilateral streaming)** | **Sí (Manuales de usuario)** | **Sí (Tabletop Simulator)** | **Mesa de rol en vivo** |

### 2.3. Aspectos diferenciadores de GameMaster AI
1. **Contexto automático del tablero (Tecnología):** Recibe tiradas de dados y estado de la mesa directamente desde Tabletop Simulator, permitiendo que la IA adapte la narración sin que los jugadores tengan que teclear o dictar los resultados.
2. **RAG sobre manuales propios (Tecnología):** Respuestas normativas rigurosas con referencia exacta de página basadas únicamente en los PDFs aportados, eliminando las alucinaciones de las IAs generalistas y sirviendo para cualquier juego de rol.
3. **Flujo integrado sin cambio de ventana (Experiencia de usuario):** Combina voz en directo, resolución de reglas y visualización del tablero en una experiencia fluida que mantiene la concentración 100 % en la partida.

---

## 3. Propuesta de solución: GameMaster AI Companion

### 3.1. Descripción de la propuesta
GameMaster AI Companion es una aplicación web concebida como narrador virtual inteligente conectado a Tabletop Simulator. Está dirigida a directores de juego y grupos de rol que juegan en ordenador y buscan sesiones ágiles e inmersivas. Resuelve de forma directa los parones de consulta de reglas, la sobrecarga al improvisar y la dificultad para reunir suficientes jugadores, permitiendo disfrutar de partidas dinámicas e inmersivas incluso con grupos reducidos.

### 3.2. Flujo de uso paso a paso
1. **Preparación de la partida:** El director de juego accede a la aplicación web y carga los manuales o módulos de aventura en PDF que utilizará durante la sesión.
2. **Vinculación con el tablero:** Se inicia la sesión en Tabletop Simulator y se activa el enlace con la aplicación web para conectar la mesa de juego.
3. **Recepción de eventos en directo:** A medida que los jugadores tiran dados y mueven figuras en el tablero, la aplicación registra automáticamente los resultados y el estado de la partida.
4. **Asistencia y narración por voz:** Durante la partida, los participantes dialogan con la aplicación para resolver dudas reglamentarias o solicitar descripciones ambientales; el asistente responde por voz en tiempo real basándose en los manuales cargados y en lo ocurrido en la mesa.
5. **Cierre y memoria de sesión:** Al finalizar la partida, la aplicación recopila un resumen de eventos clave, tiradas relevantes y consultas de reglas realizadas para facilitar la continuidad en sesiones futuras.

---

## 4. Viabilidad técnica y comparativa de soluciones

### 4.1. Tecnologías de GameMaster AI (Solución A)

| Componente | Tecnología elegida | Función en el sistema |
|---|---|---|
| **Frontend** | React | Interfaz web companion reactiva, rápida y optimizada para operar como pantalla de apoyo. |
| **Backend & API** | Laravel (PHP) | Lógica de negocio, gestión de sesiones, endpoints RESTful y procesamiento de webhooks. |
| **Motor de IA & Reglas** | RAG (Embeddings + BD vectorial) + API LLM | Indexación semántica de PDFs para respuestas normativas exactas con cita de página. |
| **Interacción por voz** | Web Speech API / Streaming de audio | Reconocimiento de voz (STT) y síntesis hablada (TTS) para diálogo bilateral fluido. |
| **Integración de tablero** | Scripting Lua en Tabletop Simulator | Envío ligero de eventos (`onDiceRoll`) mediante peticiones HTTP (`WebRequest.post`). |

### 4.2. Evaluación y recuento final de puntos

| Criterio clave (1 a 5 puntos) | Solución A (Companion TTS) | Solución B (Voz sin tablero) | Solución C (Texto / Campañas) |
|---|:---:|:---:|:---:|
| Inmersión y juego en vivo | 5 | 4 | 2 |
| Diferenciación frente a rivales | 5 | 4 | 3 |
| Viabilidad técnica de desarrollo | 4 | 3 | 5 |
| Control de costes y consumo | 4 | 3 | 4 |
| Potencial de monetización | 5 | 4 | 3 |
| **Recuento total de puntos** | **23 / 25** | **18 / 25** | **17 / 25** |

### 4.3. Decisión final y descarte de alternativas

La **Solución A (23/25)** resulta la opción ganadora:
- **Resuelve el problema en directo:** Asiste por voz y reacciona a las tiradas justo cuando el DM se atasca en pleno combate o escena clave.
- **Aprovecha un motor ya consolidado:** Tabletop Simulator ya resuelve las físicas 3D, miniaturas y dados; el equipo solo necesita un script Lua de unas 10-15 líneas con `WebRequest.post` hacia Laravel.
- **Audio limpio garantizado:** El entorno de PC con auriculares y micrófono individual asegura reconocimiento de voz nítido sin problemas de insonorización.

*Descarte de alternativas:*
- **Solución B (18/25):** Se descarta porque el reconocimiento de voz en una habitación física con múltiples personas hablando a la vez sufre graves fallos acústicos, y obligar a los jugadores a dictar verbalmente cada tirada resulta tedioso y corta el ritmo.
- **Solución C (17/25):** Se descarta porque no aporta ninguna ayuda durante la partida en vivo; se limita a ser una libreta de notas con IA que compite en desventaja frente a herramientas consolidadas como Notion o ChatGPT.

---

## 5. Bibliografía

AI Dungeon. (s. f.). *AI Dungeon: Free-form text-based AI generated adventure game*. Latitude. https://aidungeon.com/

AI Game Master. (s. f.). *AI Game Master: Play RPG with AI*. https://www.aigamemaster.app/

Berserk Games. (2015). *Tabletop Simulator* [Juego de ordenador]. Berserk Games.

D&D Beyond. (s. f.). *Dungeons & Dragons digital toolset*. Wizards of the Coast. https://www.dndbeyond.com/

Roll20. (s. f.). *Roll20: Virtual tabletop for pen and paper RPGs*. The Orr Group. https://roll20.net/
