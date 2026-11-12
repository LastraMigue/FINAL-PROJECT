## 3. Asignación de Recursos Humanos y Roles

Adoptando una metodología ágil (**Scrumban**), todos los integrantes forman parte del equipo de desarrollo. La asignación técnica se basa en la arquitectura y las tecnologías definidas para GameMaster AI; Miguel Ángel también desempeña los roles de *Scrum Master*, controlador de versiones y *Release Manager*.

| Miembro / Rol | Competencias Clave | Responsabilidades Principales |
|---|---|---|
| **Miguel Ángel Lastra Garcés — Lead Developer / Backend** | Laravel, PHP, API REST, MySQL/PostgreSQL, Git | Definición de la arquitectura; desarrollo de la API, autenticación, campañas, sesiones e historial; integración de suscripciones y pasarela de pago (Stripe Sandbox); control de versiones y releases. |
| **Abel Carbonero Mora — Core Developer / IA y RAG** | APIs de LLM, procesamiento de PDF, fragmentación, embeddings, base de datos vectorial | Implementación del procesamiento e indexación de manuales y aventuras PDF, recuperación de contexto y generación de respuestas acotadas a las reglas mediante el LLM. |
| **Christian Said Jimenez Mahecha — Core Developer / Integración con Tabletop Simulator** | Lua, Webhooks, Tabletop Simulator, API REST | Desarrollo del script Lua que detecta eventos relevantes del tablero y los envía a Laravel mediante webhooks para mantener actualizado el contexto de la partida. |
| **Rafael Riego Ruz — Core Developer / Frontend y voz** | React, diseño responsive y accesible, Web Speech API | Desarrollo de la interfaz para campañas, sesiones, archivos y planes; integración de captura de voz y reproducción de narraciones, en coordinación con el backend para la gestión de suscripciones. |

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