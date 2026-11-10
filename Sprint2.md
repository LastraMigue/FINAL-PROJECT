# GameMaster AI — Sprint 2: Estructuración, Recursos y Presupuesto

---

## 1. Incorporación de Feedback del Sprint 1

Tras la revisión del **Sprint 1**, se consolida la **Solución A (Companion para Tabletop Simulator)** como la arquitectura principal del proyecto[cite: 8]. 

### Principales ajustes realizados:
- **Acotación de eventos Lua:** Para evitar saturación y latencia, el script de TTS no enviará cada micro-movimiento del tablero, sino únicamente eventos clave (inicio/fin de turno, tiradas de dados confirmadas y cambios de estado de fichas/miniaturas)[cite: 8].
- **Arquitectura desacoplada:** La web companion funcionará de forma autónoma. Si la conexión con TTS falla o el usuario decide no usar el tablero 3D, el bot de voz y el sistema RAG sobre los manuales PDF seguirán operativos manualmente.
- **Control de latencia en audio:** Se implementa un modelo de respuestas por streaming con buffering rápido para que la voz no genere parones durante la partida en vivo.

---

## 2. Estructura de Módulos del Sistema

El sistema **GameMaster AI** se divide en cuatro módulos principales interconectados[cite: 8]:


[![](https://mermaid.ink/img/pako:eNqNk91umzAUx1_FcqVdEcpHIARVlUhCM7R8KbBV29iFgw8NCsGRMf1Y0qfYo-wR-mIzbjMtUS_GlX18fj__D4I9zhgF7OO8ZA_ZmnCBkkHK0wrJ5yb8nmJTRzfL-SwJZyN0Gw6uVvzyegkkE2p1CysU7wCyNQoWkSp9jtCI1OsVI5ym-EcrOwoHrdDS0SAYfmp9H1oILcM4UeSEcHIPpVqPoRbFy-8KUUAx1AWroD6zJUksdbaOIpluvAyG0cuvWVtVgjjjxU6gSUMQVG31jA4iCXd1NJ0n8yUahSgK0Fe0DMaK_gKZYByNXuedTKYq6eXbrGeqmxBddTrXh3YQ2SPfScyyDYj6ICc-nR-1feE9VILVKtvHJFmgxTxODirjabOyDllVN6UgdRtO6mWYg0z_b2stnkpoY-RFWfoXluPasNIyVjLuX-R5rtWCsw34FybtAvVOscER62U2Afoe5lLLo_1TTKZ944y857rw7nWmA84ZF0T_iWEN3_GCYl_wBjS8Bb4l7RbvX4UpFmvYQop9ueRAm8cOJXzTUcIUt03P0rEj1TfGtkcNZ83dGvs5KWu5a3aUCBgV5I6T7d8qh4oCH7KmEtjv95UD-3v8iH2rb-im7Tqm3Te8nucYjoafsN9xDd21el1LnnflkeO4zxr-qe41ddOw-nbXs3t217QNz9Uw0EJ-XtPXX0_9gc9_AL7lF3s?type=png)](https://mermaid.live/edit#pako:eNqNk1uO2jAUhrdieaQ-QSYXEiAajRQg0KjcRNKO2qYPJj6BiBAjx5lLgVV0KV3CbKyOGaqC5qF5Orf_838ie48TRgG7OOZxkebsKVkTLlDUq3Mkv6H_PcaGhoaL2TTypwP04Pfulvz2fgEkESp6gCUKdwDJGnnzQJU-B2hAyvWSEU5j_KOGnYG9GmhqqOf1P9W8D7UILfwwUsox4eQRchWPoBTZ6-8CUUAhlBkroLyiRVEocZaGAulutPD6weuvaV1VgDDh2U6gcUUQFHX1Su0FUtzS0GQWzRZo4KPAQ1_Rwhsp9RdIBONocNp3PJ4op7dvu16hhj66azbvD_Uickb-k5AlGxDlQW58uT-q5_xHKAQrlbePUTRH81kYHZTHy2FF7bOirHJBytqcxEszB-n-39FSvORQ20izPHdvTNuxYNlIWM64e5OmaaMUnG3AvTFoC2jnUtY7y9qJRYC-J3Oo2aHdS5l0-6bT07bjwLvHGTbYVzov-E8ZbuAVzyh2Ba-ggbfAt6RO8f4EjLFYwxZi7MqQA62em5TwTVMBY3Wpj5KxI8U3xrZnDGfVao3dlOSlzKodJQIGGVlxsv1b5VBQ4H1WFQK7XVsxsLvHz9g1u7pmWI5tWF290-7Yuuy-YLfp6Jpjtlum7Ldky7adYwP_VOcamqGbXavVsdpWy7D0jtPAQDN5vSan56de4fEPYgMZDw)

1. **Módulo Frontend (React):** Interfaz web donde el DM gestiona la partida, visualiza el historial de consultas, activa la entrada/salida de voz y configura la campaña.
2. **Módulo Backend & API (Laravel):** Orquesta la lógica de negocio, autenticación, gestión de usuarios, recepción de webhooks y persistencia en base de datos.
3. **Módulo Integración TTS (Lua):** Script ligero ejecutado dentro de Tabletop Simulator que detecta las tiradas de dados y el estado de la mesa, enviándolos vía HTTP POST hacia la API en Laravel.
4. **Módulo Core IA & RAG (Python / Servidor de IA):** Pipeline encargado de procesar los manuales en PDF, generar los *embeddings* vectoriales y consultar al LLM para devolver respuestas en texto y sintetizarlas a voz.

---

## 3. Asignación de Recursos Humanos y Roles

Adoptando una metodología ágil (**Scrumban**), todos los integrantes forman parte del equipo de desarrollo, rotando las funciones de *Scrum Master* y *Product Owner* por sprint, y manteniendo **roles técnicos fijos** según sus competencias[cite: 9]:

| Miembro / Rol | Competencias Clave | Responsabilidades Principales |
|---|---|---|
| **Lead Developer / Fullstack** | React, PHP / Laravel, API REST, Git | Orquestación del backend en Laravel, integración del frontend en React y arquitectura de la API. |
| **AI & Data Engineer** | Python, DB Vectorial, Embeddings, LLMs | Desarrollo del pipeline RAG sobre manuales PDF, optimización de prompts y consulta al LLM. |
| **Lua & Integrations Developer** | Scripting Lua, Webhooks, Tabletop Simulator | Desarrollo del script de comunicación en TTS para envío de tiradas y estados del tablero. |
| **UI/UX & Frontend Designer** | HTML/CSS, React, Web Speech API | Diseño de la experiencia de usuario, panel interactivo y gestión del audio en streaming. |

---

## 4. Recursos Materiales y Servicios Externos

Para el desarrollo y pruebas del proyecto se requiere el siguiente equipamiento e infraestructura[cite: 9]:

### Material y Equipamiento:
- **Estaciones de trabajo de desarrollo:** Equipos personales (PC/Mac) con IDEs (VS Code), entornos local PHP/Node/Python y Git.
- **Dispositivos de audio:** Auriculares con micrófono para pruebas de reconocimiento de voz sin ruido ambiental.
- **Licencias de Software:** Copias de *Tabletop Simulator* (Steam) para pruebas de integración[cite: 9].

### Servicios Externos e Infraestructura Cloud:
- **Servidor Web y Base de Datos:** Hosting VPS / Cloud (ej. DigitalOcean / AWS) para el despliegue del backend Laravel y la base de datos relacional (MySQL/PostgreSQL).
- **Base de Datos Vectorial:** Servicio gestionado (ej. Qdrant / Pinecone) para el almacenamiento de embeddings de los PDFs.
- **APIs de Inteligencia Artificial:** Consumo de API LLM (ej. OpenAI / Anthropic) y servicios de TTS/STT para voz[cite: 9].

---

## 5. Presupuesto Económico Estimado

Estimación básica de costes directos para la fase de desarrollo y prueba del proyecto[cite: 9]:

| Concepto | Detalle / Cantidad | Coste Estimado |
|---|---|:---:|
| **Licencias de Software** | 2x Licencias Tabletop Simulator (Steam) | 39,98 € |
| **Servidores / Cloud Infrastructure** | Hosting VPS (2 meses de desarrollo) | 30,00 € |
| **Consumo de APIs (LLM & Voz)** | Pruebas de desarrollo RAG, STT y TTS (OpenAI/ElevenLabs) | 50,00 € |
| **Base de Datos Vectorial (Tier dev)** | Instancia de prueba (Pinecone / Qdrant) | 0,00 € (Free Tier) |
| **Subtotal Costes Directos** | | **119,98 €** |
| **Contingencias (15%)** | Margen para imprevistos en consumo de APIs o ajuste de servidores[cite: 9] | 18,00 € |
| **PRESUPUESTO TOTAL ESTIMADO** | | **137,98 €** |

---

## 6. Documentación de Diseño (Prototipos Iniciales)

### Diagrama de Flujo de Interacción:
1. **Jugador / DM** realiza una acción o tira dados en Tabletop Simulator.
2. **Script Lua** captura el valor de los dados $\to$ Envía evento `POST /api/v1/game-event` a Laravel.
3. **Laravel API** recibe el evento $\to$ Consulta al **Módulo RAG** con el texto y contexto actual.
4. **Módulo RAG** extrae la regla del PDF vectorial $\to$ Pasa el contexto al **LLM**.
5. **LLM & Speech Engine** devuelven la respuesta en texto + audio sintetizado al **Dashboard de React** en tiempo real
