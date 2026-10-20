# GameMaster AI — Pitch Inicial & Análisis de Mercado

---

## Portada y Presentación

| Parámetro | Detalle |
| :--- | :--- |
| **Startup Ficticia** | **GameMaster AI Studios S.L.** |
| **Producto Digital** | **GameMaster AI** — SaaS Companion App Web para narración inteligente por voz con IA acotada para juegos de mesa de rol, integrable con Tabletop Simulator |
| **Equipo de Desarrollo** | **Abel Carbonero Mora**<br/>**Miguel Ángel Lastra Garcés**<br/>**Christian Said Jimenez Mahecha**<br/>**Rafael Riego Ruz** |
| **Ciclo Formativo** | 2º DAW (Desarrollo de Aplicaciones Web) — ILERNA (2026/2027)<br/>*Módulos: DWS, DWC, DIW, DA, IPE II, IP, PI* |

---

## Índice

- [1. Introducción al Sector y Propuesta de Valor](#1-introducción-al-sector-y-propuesta-de-valor)
- [2. Empresas Analizadas y Organigramas de Referencia](#2-empresas-analizadas-y-organigramas-de-referencia)
  - [2.1. Wizards of the Coast (Gran Empresa)](#21-wizards-of-the-coast-gran-empresa)
  - [2.2. Roll20 (Mediana Empresa)](#22-roll20-mediana-empresa)
  - [2.3. Latitude Inc. (Pequeña Empresa)](#23-latitude-inc-pequeña-empresa)
  - [2.4. Comparativa y Aplicación al Proyecto](#24-comparativa-y-aplicación-al-proyecto)
- [3. Organigrama de GameMaster AI](#3-organigrama-de-gamemaster-ai)
- [4. Necesidades y Volumen de Negocio](#4-necesidades-y-volumen-de-negocio)
  - [4.1. Análisis y Dimensión del Mercado](#41-análisis-y-dimensión-del-mercado)
  - [4.2. Necesidades del Cliente y Solución](#42-necesidades-del-cliente-y-solución)
  - [4.3. Modelo de Negocio e Ingresos](#43-modelo-de-negocio-e-ingresos)
  - [4.4. Estructura de Costes y Rentabilidad](#44-estructura-de-costes-y-rentabilidad)
- [5. Tendencias y Oportunidades](#5-tendencias-y-oportunidades)
  - [5.1. Tendencias Clave del Sector](#51-tendencias-clave-del-sector)
  - [5.2. Oportunidades Estratégicas para GameMaster AI](#52-oportunidades-estratégicas-para-gamemaster-ai)

---

## 1. Introducción al Sector y Propuesta de Valor

El sector de los juegos de mesa de rol (*Tabletop Role-Playing Games* - TTRPG) y las plataformas virtuales (*Virtual Tabletops* - VTT) vive una transformación histórica impulsada por la digitalización y el auge de las tecnologías generativas.

- **Mercado Global VTT & Digital:** Valoración superior a **3.800 millones de dólares**.
- **Mercado Específico TTRPG:** Movimiento estimado en más de **2.300 millones de dólares**, con un ritmo de crecimiento (**CAGR**) superior al **9,6%** anual.
- **Cuello de Botella Crítico:** La escasez de "Game Masters" o Directores de Juego. Dirigir una campaña exige decenas de horas de lectura de extensos manuales, diseño de escenarios y cálculo de reglas.

> [!NOTE]
> **Misión y Propuesta de Valor:** GameMaster AI es una **SaaS Companion App Web** concebida para actuar como un Narrador virtual por voz acotado por IA. Ingiere reglamentos y módulos en PDF, escucha las acciones de los jugadores por micrófono (Web Speech API) y responde narrando en tiempo real, integrándose de forma transparente con el tablero virtual de **Tabletop Simulator** mediante scripts en Lua y Webhooks automáticos.

---

## 2. Empresas Analizadas y Organigramas de Referencia

Las empresas se analizan por su relación estratégica con el producto: una compañía de referencia en propiedad intelectual y manuales de rol, una plataforma VTT consolidada en el navegador y un referente de narrativa interactiva impulsada por IA.

> [!NOTE]
> Los organigramas mostrados a continuación son **modelos funcionales elaborados para este proyecto** a modo de referencia orientativa y no corresponden a organigramas oficiales internos.

### 2.1. Wizards of the Coast (Gran Empresa)

Wizards of the Coast es una filial de Hasbro y referente mundial en el desarrollo de juegos de rol, cartas coleccionables y videojuegos. Cuenta con franquicias insignia como *Dungeons & Dragons*, *Magic: The Gathering* y *Avalon Hill*, con una plantilla de referencia estimada en LinkedIn de entre 501 y 1.000 empleados.

#### Análisis como referencia

- **Fortalezas:** Marcas consolidadas, universos narrativos de amplio recorrido, manuales reglados exhaustivos y comunidades masivas de jugadores activos.
- **Relación con GameMaster AI:** Referente en estructuración de campañas, ambientación y lore. La plataforma web permitirá que los usuarios suban sus manuales en PDF y consulten datos canónicos en tiempo real.
- **Aprendizaje aplicable:** Priorizar la coherencia absoluta entre narrativa y reglas vigentes, permitiendo indexar y localizar información clave de forma inmediata.
- **Diferencia de escala:** GameMaster AI no busca crear ni sustituir una editorial de contenidos, sino actuar como herramienta web complementaria para la dirección de partidas.

#### Organigrama funcional de referencia

```mermaid
flowchart TD
    H[Hasbro] --> W[Wizards of the Coast]
    W --> D[Dungeons & Dragons]
    W --> M[Magic: The Gathering]
    W --> A[Avalon Hill]
    W --> C[Funciones transversales]
    C --> G[Diseño y desarrollo de juegos]
    C --> P[Producción de contenido y arte]
    C --> DG[Juegos y productos digitales]
    C --> MC[Marketing y comunidad]
```

### 2.2. Roll20 (Mediana Empresa)

Roll20 es la plataforma web de referencia para partidas de rol y juegos de mesa en remoto. Ofrece un espacio integral accesible desde el navegador con gestión de fichas de personaje, mapas, audio y dados digitales. Su plantilla estimada en LinkedIn se sitúa en el rango de 51 a 200 empleados.

#### Análisis como referencia

- **Fortalezas:** Accesibilidad universal vía navegador web, centralización de herramientas de gestión de mesa y facilidad de coordinación de partidas a distancia.
- **Relación con GameMaster AI:** Constituye la referencia más directa de experiencia de usuario en navegador. GameMaster AI actúa como companion app web optimizada para pantalla secundaria, aportando narración por voz y contexto sin interferir con la mesa de juego.
- **Aprendizaje aplicable:** Diseñar una interfaz web ligera, temática y responsive (React) que facilite una navegación rápida y no interrumpa el ritmo de la partida en el ordenador.
- **Oportunidad de diferenciación:** Especializarse en la figura del Narrador asistido por IA acotada (RAG), garantizando respuestas estrictamente fidedignas a los documentos aportados y enlazadas con los eventos de Tabletop Simulator.

#### Organigrama funcional de referencia

```mermaid
flowchart TD
    R[Dirección de Roll20] --> PR[Producto y experiencia de usuario]
    R --> TI[Tecnología e ingeniería]
    R --> CT[Contenido y herramientas para juegos]
    R --> CM[Comunidad, marketing y soporte]
    PR --> UX[Diseño UX/UI]
    TI --> PL[Plataforma web y servicios]
    CT --> CA[Campañas, fichas y recursos]
```

### 2.3. Latitude Inc. (Pequeña Empresa)

Latitude representa una compañía ágil especializada en experiencias de narrativa interactiva impulsadas por modelos de lenguaje generativos, destacando por su producto web *AI Dungeon*. Permite a los usuarios sumergirse en aventuras narrativas donde las acciones del jugador modifican dinámicamente la historia.

> [!NOTE]
> **Aclaración sobre AI Game Master:** *AI Game Master - Dungeon RPG* es una app móvil comercial independiente desarrollada por Digital Dynasty Entertainment en tiendas de aplicaciones. Se toma únicamente como referencia externa de interacción por voz en el mercado. En contraposición, **GameMaster AI es una plataforma SaaS 100% Web (React + Laravel)** concebida para utilizarse desde el navegador en PC como pantalla de apoyo durante partidas virtuales en Tabletop Simulator.

#### Análisis como referencia

- **Fortalezas:** Generación de historias dinámicas no lineales, adaptabilidad a la creatividad de los jugadores y experiencia conversacional fluida.
- **Relación con GameMaster AI:** Permite estudiar dinámicas conversacionales ágiles con IA. GameMaster AI se diferencia al centrarse en partidas regladas, persistencia relacional del estado de la campaña y sincronización con el tablero de Tabletop Simulator.
- **Aprendizaje aplicable:** Mantener continuidad narrativa coherente entre intervenciones sucesivas respetando los límites del escenario.
- **Riesgo que se debe controlar:** La alucinación de contenido. GameMaster AI implementa *Guardrails* y un *System Prompt* estricto que acotan la IA a responder exclusivamente según los manuales PDF indexados, impidiendo desviaciones a temas ajenos a la partida.

#### Organigrama funcional de referencia

```mermaid
flowchart TD
    L[Dirección de Latitude] --> PR[Producto y experiencia narrativa]
    L --> IA[Ingeniería e IA]
    L --> ND[Narrativa y diseño de juego]
    L --> UX[Diseño de experiencia]
    L --> CC[Comunidad y crecimiento]
    PR --> EX[Experiencias interactivas]
    IA --> MO[Modelos, contexto y plataforma]
    ND --> HI[Historias y herramientas de creación]
```

### 2.4. Comparativa y Aplicación al Proyecto

| Referencia | Formato / Enfoque | Aportación principal | Qué aprende y cómo se diferencia GameMaster AI |
| :--- | :--- | :--- | :--- |
| **Wizards of the Coast** | Gran editorial internacional | Reglas oficiales, ambientación y lore de campañas | GameMaster AI incorpora indexación semántica (RAG) de manuales PDF para mantener fidelidad reglamentaria estricta |
| **Roll20** | Plataforma SaaS Web (VTT) | Herramientas web para organizar partidas en navegador | GameMaster AI adopta una arquitectura web desacoplada (React + Laravel) ágil y pensada como pantalla secundaria |
| **Latitude (*AI Dungeon*)** | Plataforma de narrativa con IA | Historias dinámicas y generación de texto interactivo | GameMaster AI aplica *Guardrails* estrictos para evitar alucinaciones y ceñirse al escenario cargado |
| ***AI Game Master* (Externa)** | App móvil comercial nativa | Interacción por voz y ambientación sonora en tiendas móviles | Referencia de voz; GameMaster AI se diferencia como solución **SaaS Web** integrada con **Tabletop Simulator** vía Lua y Webhooks |

> [!NOTE]
> **Conclusión Estratégica:** GameMaster AI integra las fortalezas de cada referencia: adopta el rigor reglamentario de las grandes editoriales de rol, la accesibilidad de una solución web moderna tipo SaaS (React/Laravel), la inmersión por voz y la interacción de modelos LLM acotados. Su gran elemento diferenciador radica en la ingesta de PDFs de la propia mesa y la comunicación bidireccional en tiempo real con Tabletop Simulator.

---

## 3. Organigrama de GameMaster AI

El organigrama funcional de **GameMaster AI Studios** se estructura a partir de las áreas funcionales de la empresa y los módulos clave de la plataforma web, siguiendo el mismo modelo organizativo de las compañías de referencia. 

Esta estructura distribuye las funciones del producto bajo la coordinación de **Miguel Ángel Lastra Garcés** (Lead Developer, Revisor de Código, Scrum Master y Release Manager) junto al equipo de programadores íntegros (*Core Developers*) asignados a cada dominio técnico:

```mermaid
flowchart TD
    GM[Dirección de GameMaster AI Studios] --> FE[Frontend & Experiencia Web]
    GM --> BE[Backend & Persistencia]
    GM --> IA[Motor de IA & RAG]
    GM --> IT[Integración VTT & Negocio]

    FE --> FE1[Companion App React y voz Web Speech API]
    BE --> BE1[API RESTful Laravel y gestión de campañas]
    IA --> IA1[Procesamiento de PDFs y LLM con Guardrails]
    IT --> IT1[Conexión Tabletop Simulator y pagos Stripe]
```

---

## 4. Necesidades y Volumen de Negocio

### 4.1. Análisis y Dimensión del Mercado

El proyecto se posiciona en la intersección entre los juegos de rol de mesa (**TTRPG**), las plataformas virtuales (**VTT**) y las aplicaciones SaaS impulsadas por inteligencia artificial.

- **Valoración Actual del Mercado TTRPG:** Estimado en **2.310 millones de dólares en 2025** a nivel mundial.
- **Proyección de Crecimiento:** Se proyecta alcanzar **5.230 millones de dólares en 2034**, con una tasa compuesta anual (**CAGR**) del **9,61%** *(Fuente: Fortune Business Insights)*.
- **Posicionamiento Estratégico:** GameMaster AI no compite con las grandes editoriales ni busca sustituir los tableros virtuales; actúa como una **companion app web complementaria** que reduce drásticamente las horas de preparación y asiste en la narración en directo.

### 4.2. Necesidades del Cliente y Solución

La principal barrera del sector es la **sobrecarga del Director de Juego (DM)**, quien debe memorizar cientos de páginas de reglas, coordinar la trama e interpretar personajes simultáneamente.

| Segmento de Usuario | Necesidad Principal | Solución de GameMaster AI |
| :--- | :--- | :--- |
| **DMs Experimentados** | Reducir el tiempo de preparación y agilizar consultas de reglas complejas. | Búsqueda semántica inmediata sobre manuales PDF (RAG) y narración asistida. |
| **DMs Principiantes** | Falta de soltura para improvisar narraciones y resolver dudas de juego en directo. | Soporte narrativo por voz en tiempo real con apego estricto a las reglas del manual. |
| **Jugadores de Rol** | Evitar parones prolongados que rompen la inmersión de la partida. | Diálogo continuo por voz mediante Web Speech API sin abandonar la partida. |
| **Grupos VTT en Remoto** | Conectar los eventos del tablero con la historia de forma automatizada. | Sincronización transparente con Tabletop Simulator vía Lua y Webhooks automáticos. |
| **Clubes y Tiendas** | Dinamizar múltiples mesas simultáneas y facilitar partidas introductorias. | Herramienta reutilizable y configurable para cualquier sistema de campaña. |

### 4.3. Modelo de Negocio e Ingresos

GameMaster AI opera bajo un modelo **SaaS Freemium** con pasarela de pago segura:

1. **Plan Gratuito (Free Tier):** Acceso a IA base, límite de prompts por sesión y carga de manuales PDF de tamaño estándar.
2. **Suscripción Pro / Individual:** Orientada a directores habituales con un ingreso medio proyectado de **8 €/mes**, desbloqueando modelos LLM avanzados, respuestas más elaboradas, mayor memoria contextual y carga de PDFs de gran tamaño.
3. **Planes para Grupos y Clubes:** Cuotas anuales o mensuales reducidas por volumen para asociaciones y tiendas especializadas.
4. **Servicios de Configuración:** Preparación personalizada de campañas complejas o integración de módulos a medida.

### 4.4. Estructura de Costes y Rentabilidad

Para garantizar la sostenibilidad económica, se monitorean los costes operativos directos frente al valor de vida del cliente (**LTV**):

| Área de Coste | Concepto | Estrategia de Control y Rentabilidad |
| :--- | :--- | :--- |
| **Consumo de APIs de IA** | Tokens de inferencia LLM y síntesis/transcripción de voz. | *Guardrails* estrictos, caché semántica y límites de consumo por plan. |
| **Infraestructura Cloud** | Servidores backend en Laravel, base de datos relacional y storage. | Arquitectura desacoplada y escalado elástico bajo demanda. |
| **Indexación y RAG** | Fragmentación (*chunking*) y procesamiento de PDFs de campañas. | Extracción y vectorización única por documento con persistencia eficiente. |
| **Adquisición (CAC)** | Promoción en comunidades especializadas de rol y VTT. | Crecimiento orgánico apoyado en el mod de Tabletop Simulator y el plan gratuito. |

> [!NOTE]
> **Criterio de Viabilidad:** La rentabilidad se alcanza asegurando que el coste variable medio de consumo de tokens por usuario de pago se mantenga por debajo del **25-30% de la cuota mensual (8 €)**, destinando el margen restante a costes fijos e inversión en producto.

---

## 5. Tendencias y Oportunidades

### 5.1. Tendencias Clave del Sector

1. **Digitalización Definitiva del Rol y Auge VTT:** Plataformas como Tabletop Simulator, Roll20 y Foundry VTT han dejado de ser alternativas puntuales para consolidarse como el estándar del juego a distancia.
2. **Adopción de IA Generativa en Ocio Interactivo:** Los usuarios demandan mundos reactivos y conversacionales que respondan a la creatividad individual sin encorsetarse en árboles de diálogo rígidos.
3. **Prioridad a la Voz y Experiencias Manos Libres:** Durante una sesión en ordenador, los jugadores prefieren interactuar hablando por micrófono en lugar de escribir comandos en un teclado.
4. **Democratización del Acceso:** El auge de la cultura popular (series, podcasts de rol) atrae a millones de novatos que requieren herramientas intuitivas que eliminen la barrera de entrada de manuales de 300+ páginas.

### 5.2. Oportunidades Estratégicas para GameMaster AI

- **Pioneros en Asistencia por Voz Multimodal:** No existe en el mercado actual ninguna companion app web que unifique voz en tiempo real, RAG estricto sobre manuales PDF y conexión directa con el tablero virtual de Tabletop Simulator.
- **Apalancamiento en un Ecosistema Ya Consolidado:** Al comunicarse con Tabletop Simulator vía scripts Lua y Webhooks, el proyecto no necesita desarrollar un costoso motor gráfico 3D propio, beneficiándose del extenso catálogo de mods existente.
- **Alta Retención de Grupos de Juego:** Las campañas de rol se juegan con frecuencia semanal o quincenal durante meses o años, lo que genera un *churn rate* muy reducido y una alta fidelización del cliente.
- **Escalabilidad para Futuras Actualizaciones:** La arquitectura desacoplada y el sistema RAG sientan las bases técnicas para que la plataforma pueda evolucionar en versiones posteriores, permitiendo incorporar progresivamente soporte para nuevos juegos, manuales y sistemas de rol según la acogida del proyecto.

> [!NOTE]
> **Conclusión:** La conjunción entre un mercado en expansión (CAGR 9,61%) y la falta de soluciones de narración por voz acotadas convierte a GameMaster AI en una oportunidad única para liderar el segmento de asistencia inteligente para juegos de rol virtuales.

---

### Fuentes

- [Fortune Business Insights — Tabletop Role-Playing Game Market](https://www.fortunebusinessinsights.com/tabletop-role-playing-game-market-119102): Datos y perspectivas de crecimiento del mercado global de juegos de rol.
- [Tabletop Simulator — Steam Store](https://store.steampowered.com/app/286160/TabletopSimulator/): Referencia sobre la plataforma VTT 3D y entorno de scripting Lua.