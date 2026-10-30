# GameMaster AI — Sprint 1: Necesidad, Innovación y Viabilidad Técnica

**Proyecto:** GameMaster AI (narración por voz con IA para rol) | **Sprint 1:** Necesidad, benchmark y viabilidad técnica.  
**Soluciones analizadas:**  
- **A. Web companion con voz e integración con Tabletop Simulator (TTS):** React + Laravel, voz bilateral, RAG sobre PDFs y webhooks Lua con el estado del tablero.  
- **B. Web/PWA de narración por voz sin integración:** Mismo narrador y RAG sobre PDFs, pero jugadores narran verbalmente; para cualquier juego y mesa física u online.  
- **C. Web de preparación y consulta (texto primero):** Consulta de reglas, generador de escenas/PNJ e historial de campaña; voz opcional.  

---

## Issue 1 · Necesidad: Investigación del sector y de los jugadores

### 1.1. Sector: tamaño, evolución y tendencias
- **Tamaño:** Mercado TTRPG de **2.310 M$** en 2025, proyectado a **5.230 M$** en 2034 (CAGR 9,61 %; [Fortune Business Insights](https://www.fortunebusinessinsights.com/tabletop-role-playing-game-market-119102)). Plataformas de tablero virtual (VTT) superan los **3.800 M$** ([Polaris Market Research](https://www.polarismarketresearch.com/industry-analysis/virtual-tabletop-market)).
- **Evolución:** Transición del juego presencial tradicional hacia plataformas digitales (Roll20 en navegador, Tabletop Simulator con físicas 3D) y experimentación con narrativa por IA (*AI Dungeon* de Latitude Inc.).
- **Tendencias:** Partidas híbridas/remotas, servicios web freemium, asistentes de IA para reglas y alta demanda de herramientas que reduzcan la carga del DM sin eliminar la interacción social.

### 1.2. Perfil de jugadores y Dungeon Masters (DMs)
- **Quiénes son:** Jugadores (buscan inmersión y ritmo) y Directores de Juego / DMs (asumen la preparación, arbitraje e improvisación).
- **Frecuencia:** Práctica recurrente en campañas estructuradas (sesiones semanales o quincenales de 3-4 horas).
- **Cómo juegan online:** Partidas en PC con tableros virtuales (mapas, miniaturas, dados), hojas compartidas y voz simultánea en Discord.
- **Herramientas habituales:** Ecosistema fragmentado (Roll20/TTS para tablero, D&D Beyond para reglas, Discord para voz y Notion/Drive para notas). Cambiar entre ellas rompe el ritmo.

### 1.3. Problemas recurrentes y testimonios reales
- **Preparar sesiones:** Horas previas organizando tramas y encuentros.  
  > *«No quiero parecer que no estoy preparado cuando inevitablemente tenga que rebuscar entre las páginas para encontrar la sección adecuada...»* ([RPG Stack Exchange](https://rpg.stackexchange.com/questions/73672/as-a-dm-what-are-some-good-ways-to-study-in-preparation-for-an-adventure-module))
- **Consultar reglas:** Parones largos buscando tecnicismos en manuales de cientos de páginas.  
  > *«Al buscar las reglas, no encuentro nada sobre cómo liberar a los compañeros que están inmovilizados.»* ([RPG Stack Exchange](https://rpg.stackexchange.com/questions/169371/freeing-others-from-webs-during-combat))
- **Narrar e improvisar / Mantener inmersión:** Bloqueo ante decisiones imprevistas y pérdida de atmósfera por pausas.  
  > *«No se me da bien improvisar. ¿Qué puede hacer alguien a quien le cuesta inventar respuestas interesantes en el momento... sin que suene forzada?»* ([RPG Stack Exchange](https://rpg.stackexchange.com/questions/133208/how-to-add-descriptive-role-playing-flair-if-im-not-good-at-improvising))

### 1.4. Evidencia orientativa por solución

| Solución | Evidencia a favor | Límites / En contra |
|---|---|---|
| **A (TTS)** | TTS tiene **2–5 M de usuarios** (SteamSpy) y **~6.150 jugadores simultáneos** (SteamCharts, oct. 2026). D&D 5e copaba el 53,7 % de campañas en Roll20 (2021). | TTS no es exclusivo de rol (también juegos de mesa) y requiere PC. |
| **B (Voz física)** | Encuesta *Sly Flourish* (2.900 respuestas, 2023): **46 % juega presencial** y **13 % híbrido**. | 41 % juega online; ruido acústico en salas físicas dificulta la voz. |
| **C (Texto prep.)** | El **57 % de DMs dedica 2+ horas a preparar** una sesión de 4 h (encuesta D&D, 3.663 respuestas, 2020). | 43 % dedica $\le$ 1 h; el 76 % prefiere que los jugadores resuman la sesión anterior. |

### 1.5. Justificación de relevancia y urgencia
La sobrecarga del DM al preparar y consultar reglas en vivo es el gran cuello de botella del rol. La fragmentación de herramientas detiene las partidas y rompe la inmersión, urgiendo una solución conectada que asista en tiempo real sin añadir fricción.

---

## Issue 2 · Necesidad: Problema y usuario afectado

### 2.1. Descripción del problema
El DM debe coordinar simultáneamente narración, reglas complejas y el estado del tablero. Consultar dudas en manuales densos o saltar entre aplicaciones genera pausas de varios minutos que rompen la inmersión dramática, saturan al director y dispersan al grupo.

### 2.2. Colectivo afectado
- **DMs/GMs:** Sobrecarga mental por memorizar reglas, arbitrar e improvisar.
- **Jugadores:** Pérdida de inmersión y aburrimiento durante los parones.
- **Mesas novatas y grupos remotos:** Barrera de entrada por reglas densas y fatiga de alternar pantallas.

### 2.3. Persona principal (Arquetipo apoyado en datos)
- **Perfil:** Dungeon Master habitual de campañas continuadas (sesiones de 4 h, invierte 2+ h semanales en preparar).
- **Objetivo:** Dirigir partidas fluidas, dinámicas y cinematográficas con reglas a mano sin cortar el ritmo.
- **Frustración:** Parar la partida en momentos cumbre para rebuscar reglas en PDFs o bloquearse al improvisar.

### 2.4. Historias de usuario por solución
- **A (DM en Tabletop Simulator):** *«Como DM en Tabletop Simulator, quiero consultar reglas y recibir narración por voz conectada al tablero, para dirigir sin cambiar de ventana ni pausar el combate.»*
- **B (GM en mesa física/sin VTT):** *«Como GM presencial, quiero consultar manuales por voz describiendo las acciones, para resolver dudas y enriquecer escenas sin depender de un VTT.»*
- **C (DM organizador de campañas):** *«Como DM organizador, quiero generar escenas y consultar reglas por texto, para reducir a la mitad la preparación semanal y guardar el historial.»*

---

## Issue 3 · Innovación: Benchmark de alternativas existentes

### 3.1. Alternativas de mercado analizadas
- **[Roll20](https://roll20.net/)** (Activa, Freemium / 4,17–8,33 USD/mes): Tablero VTT líder en navegador con mapas, dados y fichas. *Sin IA narradora ni RAG sobre PDFs propios.*
- **[D&D Beyond](https://www.dndbeyond.com/)** (Activa, Freemium / 2,17–4,58 USD/mes): Herramienta oficial con reglas y visor Maps. *Ecosistema cerrado a D&D; no admite manuales de otros sistemas ni RAG de PDFs propios.*
- **[AI Dungeon](https://aidungeon.com/)** (Activa, Freemium / 9,99–29,99 USD/mes): Narrativa interactiva libre por IA con voz. *Alucina fácilmente, no valida reglas de rol ni se conecta a tableros.*
- **[AI Game Master](https://www.aigamemaster.app/)** (Activa, Freemium / Micropagos): App móvil para aventuras individuales con voz. *Enfocada a juego individual en móvil; no apta para mesas de rol tradicionales.*

### 3.2. Tabla comparativa de mercado

| Herramienta | Qué ofrece | Voz | PDFs propios (RAG) | Conexión tablero | Prep. campaña | Precio |
|---|---|---|---|---|---|---|
| **Roll20** | Tablero VTT, mapas, fichas, dados | Sí (WebRTC chat) | No | Sí (propio navegador) | Sí (básica) | Gratis / 4,17–8,33 $/mes |
| **D&D Beyond** | Reglas D&D, fichas, visor Maps | No | No (solo oficial D&D) | Sí (Maps integrado) | Sí (encuentros D&D)| Gratis / 2,17–4,58 $/mes |
| **AI Dungeon** | Historias generadas por IA | Sí (TTS) | No | No | Sí (escenarios) | Gratis / 9,99–29,99 $/mes|
| **AI Game Master**| Aventuras conversacionales IA | Sí (móvil) | No | No | Sí (individual) | Gratis / Suscripción |

### 3.3. Huecos de mercado desatendidos
1. **RAG documental estricto:** Ninguna permite cargar un PDF de cualquier sistema y obtener respuestas textuales con cita de página.
2. **Voz bilateral contextual:** No hay asistentes que escuchen y respondan según lo que ocurre en la partida.
3. **Conexión tablero–IA:** Los VTTs son tableros mudos; la IA no sabe qué sale en los dados ni dónde están las figuras.
4. **Continuidad multijuego:** Falta memoria estructurada de campaña aplicable a cualquier reglamento.

### 3.4. Posicionamiento de las tres soluciones
- **A (Companion TTS):** Cubre tablero + voz + RAG de PDFs propios. No existe hoy nada similar que conecte TTS con IA.
- **B (Voz sin tablero):** Cubre voz y RAG documental con portabilidad para mesa física, compitiendo con AI Dungeon pero con reglas verificables.
- **C (Asistente texto):** Cubre preparación, generación y memoria de campaña multijuego; compite con Notion y D&D Beyond en modo asíncrono.

---

## Issue 6 · Innovación: Aspectos diferenciadores de A, B y C

### 6.1. Diferenciadores por solución y clasificación
- **Solución A (Companion TTS):**
  - *Contexto automático del tablero* (**Tecnología**): Script Lua y webhooks envían tiradas y estado a la IA sin dictado manual (cubre hueco 3).
  - *RAG sobre PDFs propios* (**Tecnología**): Citas exactas de reglas sin alucinaciones (cubre hueco 1).
  - *Flujo sin cambio de ventana* (**Experiencia de usuario**): Voz, reglas y tablero en la misma pantalla (cubre hueco 2).
- **Solución B (Voz sin tablero):**
  - *Portabilidad total* (**Experiencia de usuario**): Juega en mesa física o Discord sin licencias de software VTT.
  - *Arbitraje multi-sistema por voz* (**Tecnología**): Consulta de reglas por voz sobre los PDFs del usuario (cubre hueco 1).
  - *Despliegue sin scripts* (**Proceso**): Acceso web directo sin configurar clientes externos.
- **Solución C (Asistente texto):**
  - *Memoria estructurada de campaña* (**Tecnología/Proceso**): Registro de PNJs, decisiones y trama entre sesiones (cubre hueco 4).
  - *Preparación centralizada* (**Proceso**): Generación de escenas y notas en una sola interfaz.
  - *Interacción silenciosa* (**Experiencia de usuario**): Ideal para planificar por escrito sin audio.

### 6.2. Matriz comparativa de diferenciación

| Criterio | Solución A (Companion TTS) | Solución B (Voz genérica) | Solución C (Asistente texto) |
|---|---|---|---|
| **Eje de innovación** | Tecnología e integración en vivo | Experiencia de usuario y portabilidad | Proceso y gestión de información |
| **Sincronización tablero** | **Sí (Lua + Webhooks nativos)** | No aplica | No aplica |
| **Interacción por voz** | **Bilateral en vivo (Streaming)** | Bilateral en vivo | Opcional / Secundaria |
| **Consulta RAG de PDFs** | **Sí (asistencia en directo)** | Sí (asistencia en directo) | Sí (consulta previa/notas) |
| **Ámbito principal de uso**| Partida digital en vivo (PC/TTS) | Mesa física o remota | Preparación previa y post-sesión |

---

## Issue 7 · Viabilidad técnica de A, B y C

### 7.1. Competencias actuales del equipo (DAW)
Bases consolidadas de 2º DAW: frontend interactivo (HTML/CSS/JS, React), backend y APIs RESTful (PHP/Laravel), bases de datos relacionales (MySQL/PostgreSQL) y gestión ágil (Scrumban con Git).

### 7.2. Recursos, infraestructura y huecos de aprendizaje

| Solución | Recursos tecnológicos | Infraestructura requerida | Huecos de competencias |
|---|---|---|---|
| **A (TTS)** | React, Laravel (API/Webhooks), BD relacional y vectorial, API LLM, Web Speech API, Lua. | Hosting web, BD, almacenamiento seguro de PDFs, API LLM, Tabletop Simulator en PC. | Pipeline RAG (embeddings/chunking), voz en streaming y script Lua en TTS. |
| **B (Voz)** | React/PWA, Laravel API, BD vectorial, API LLM, Web Speech API. | Hosting web, BD, almacenamiento de PDFs, API LLM, navegador con micrófono. | Pipeline RAG, consumo LLM y captura de voz multi-navegador. |
| **C (Texto)**| React, Laravel API, BD relacional y vectorial, API LLM. | Hosting web, BD relacional/documental, almacenamiento PDFs, API LLM. | Pipeline RAG, consumo LLM y modelado de memoria de campañas. |

### 7.3. Limitaciones técnicas y mitigaciones en una línea
- **A — Latencia evento $\to$ voz:** Respuestas breves en streaming, caché de embeddings y procesamiento asíncrono.
- **A — Dependencia de TTS local:** Arquitectura desacoplada; si falla el webhook Lua, la web permite uso manual sin caerse.
- **B — Ruido ambiental en mesa física:** Modo Push-to-Talk obligatorio y fallback garantizado a entrada por texto.
- **B — Soporte desigual de Web Speech:** Detección de compatibilidad al inicio y alternativa escrita transparente.
- **C — Límite de contexto en campañas:** Resúmenes recursivos por sesión para no saturar la ventana del LLM.
- **Común (A, B, C) — Derechos de autor de PDFs:** Almacenamiento privado por usuario en local, sin reentrenar modelos públicos.

### 7.4. Comparativa técnica de viabilidad

| Criterio | Solución A (Companion TTS) | Solución B (Voz sin tablero) | Solución C (Asistente texto) |
|---|---|---|---|
| **Complejidad** | Media-alta (web + LLM + voz + eventos TTS) | Media (web + LLM + voz) | Baja-media (web + LLM + BD relacional) |
| **Dependencias** | API LLM + cliente local de TTS | API LLM + API de voz del navegador | API LLM |
| **Riesgo técnico** | Latencia de cadena de voz y eventos | Mala captación de audio en salas físicas | Quedar como un gestor de texto sin impacto |
| **Viabilidad MVP** | **Plenamente viable (acotando eventos clave)** | Viable con riesgo acústico en presencial | Altamente viable con stack estándar DAW |

### 7.5. Validación y elección final fundamentada
Tras el análisis completo, la **Solución A (Web companion con voz e integración en Tabletop Simulator)** resulta ser la más viable y la que resuelve mejor el problema:
1. **Resuelve el problema real:** Actúa durante la partida en vivo (el momento crítico de sobrecarga), eliminando parones al sincronizar dados y reglas con la narración sin exigir dictados manuales al DM.
2. **Aprovecha un motor ya resuelto:** *Tabletop Simulator* aporta las físicas 3D, dados y miniaturas; el equipo no tiene que construir un VTT desde cero.
3. **Script Lua ultra-ligero:** La API de TTS incluye `WebRequest.post` nativo; emitir tiradas de dados (`onDiceRoll`) a Laravel toma menos de 15 líneas de código Lua.
4. **Viabilidad acústica garantizada:** En PC con auriculares y micrófono individual (estándar en TTS/Discord), la captura de voz es limpia, evitando el grave problema de ruido y voces solapadas que compromete a la Solución B en salas físicas.
5. **Arquitectura modular y alcance acotado:** La web en React + Laravel opera de forma autónoma (tolerante a fallos si el webhook cae). Acotar el MVP a tiradas clave y consultas de reglas asegura un desarrollo robusto y entregable dentro del curso.
