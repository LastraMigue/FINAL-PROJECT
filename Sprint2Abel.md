# GameMaster AI — Sprint 2:

## Apartado 02 · Definición de módulos

### 1. Módulos funcionales

1. **Interfaz y voz:** permite al DM gestionar la partida, hablar o escribir consultas y recibir respuestas en texto o audio.
2. **Sesiones y backend:** organiza la partida y conecta los distintos módulos mediante la API, validando solicitudes y permisos.
3. **Manuales y búsqueda (RAG):** procesa los PDF y localiza fragmentos relevantes, conservando sus páginas para poder citarlos.
4. **Asistente de IA:** combina la consulta, el contexto de la partida y los fragmentos encontrados para generar una respuesta fundamentada; si no encuentra información suficiente, lo indica.
5. **Integración con Tabletop Simulator:** un script Lua envía a la API eventos del tablero, inicialmente tiradas de dados, para añadirlos al contexto de la partida.
6. **Almacenamiento e historial:** conserva de forma aislada los datos necesarios de usuarios, sesiones, manuales y consultas recientes.

### 2. Integración entre módulos

La comunicación principal pasa por la API del backend. La interfaz web no accede directamente a la base de datos ni al índice documental. El conector de Tabletop Simulator también envía sus eventos a la API, que comprueba la sesión y los deriva al orquestador.


#### Flujo de consulta por voz

1. El DM inicia una sesión y selecciona los manuales que se usarán.
2. La interfaz captura la consulta y el módulo de voz genera una transcripción.
3. La API valida la solicitud y obtiene el contexto de la sesión.
4. El orquestador solicita al módulo RAG fragmentos relevantes de los manuales seleccionados.
5. El orquestador prepara la respuesta con esos fragmentos y conserva las referencias encontradas.
6. La API devuelve el texto, las referencias y el estado de la operación; la salida de voz reproduce la respuesta.
7. La consulta y su resultado pueden añadirse al registro de actividad de la partida.

#### Flujo de evento de Tabletop Simulator

1. El script Lua detecta un evento contemplado, como una tirada de dados.
2. El conector envía el evento y el identificador de sesión a la API.
3. La API valida el formato y que el evento corresponda a una sesión activa.
4. El evento validado se añade al contexto disponible para el asistente.
5. Si el DM solicita una respuesta, el orquestador utiliza ese contexto junto con la búsqueda documental; la respuesta se muestra y, si está disponible, se reproduce por voz.

La llegada de un evento del tablero no debe iniciar una respuesta hablada inesperada: el DM mantiene el control de cuándo pedir asistencia. Si la integración falla, la aplicación comunica el problema y permite continuar mediante consultas manuales.


### 3. Criterio de integración

El módulo se considerará integrado cuando la interfaz pueda enviar una consulta asociada a una sesión, el backend pueda obtener contexto documental y devolver una respuesta con sus referencias, y el usuario pueda recibirla en texto y, cuando la voz esté disponible, en audio. La conexión con Tabletop Simulator se verificará por separado: un evento válido deberá llegar a la sesión correcta, y la aplicación deberá seguir permitiendo consultas manuales cuando el conector no esté disponible.
