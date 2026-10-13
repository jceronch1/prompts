# Polla futbolera del Mundial 2026

**Categoría:** [Plataformas web](README.md) · **Tecnologías:** NestJS, React + Vite, PostgreSQL + pgvector

Plataforma de pronósticos del Mundial 2026 con puntuación, ranking, premios y análisis con IA.

> **Antes de usarlo, reemplaza:** `[CONTRASEÑA_DE_PRUEBA]`

## Prompt

```text
Actúa como un arquitecto de software senior, experto en aplicaciones de análisis deportivo, sistemas de predicción, inteligencia artificial, diseño de bases de datos PostgreSQL con pgvector y desarrollo full stack.

IMPORTANTE: Todos los identificadores de la base de datos (tablas, columnas, claves, índices, restricciones) deben estar en inglés. Usa nombres claros y descriptivos en inglés para mantener consistencia y facilitar la internacionalización.

Necesito que construyas una plataforma web completa para la Polla Futbolera de Kamila Innovation, donde los participantes puedan pronosticar los resultados de los partidos del Mundial de Fútbol 2026. La plataforma debe permitir a los usuarios registrarse, realizar pronósticos (apuestas) sobre partidos específicos habilitados por el administrador, y competir entre sí. El valor de la apuesta para cada partido habilitado debe ser definido mediante una encuesta de consenso creada por el administrador.

Reglas de puntuación y premio global:
- Sistema de puntos por partido:
  - 1 punto por acertar el ganador del partido (o el empate, si se pronostica empate y el partido termina en empate).
  - 1 punto adicional por acertar el marcador exacto (goles de local y visitante). Por lo tanto, si un participante acierta tanto el ganador como el marcador exacto, obtiene 2 puntos en ese partido.
  - Si no acierta ni el ganador ni el marcador, obtiene 0 puntos.
  - Si no realiza pronóstico para un partido habilitado, obtiene 0 puntos y no participa en ese encuentro.
- Una vez enviado el pronóstico para un partido, no se puede modificar (ni siquiera por el administrador). Se debe implementar un bloqueo de edición.
- Premio global: El administrador podrá definir un monto en pesos colombianos (ej. 300.000 COP) que se otorgará al participante que acumule más puntos al final del torneo (o al final de la fase definida por el administrador). El premio se mostrará públicamente en la plataforma y el ranking será actualizado automáticamente.

Debe inspirarse en plataformas de apuestas deportivas y análisis estadístico, pero enfocada en la predicción educativa y lúdica dentro de un entorno laboral o comunitario.

CONTEXTO TÉCNICO:
- Base de datos PostgreSQL vacía llamada: mundial_prediction_db
- Conexión mediante el MCP de PostgreSQL llamado: postgres_codex
- La base de datos ya tiene instalada la extensión pgvector, por lo que debes aprovecharla para búsqueda semántica, recomendaciones de partidos, asistente con IA y recuperación de información por similitud.
- El stack tecnológico seleccionado debe ser:
  - Backend: NestJS (TypeScript) – por su robustez, estructura modular, soporte para GraphQL/REST, inyección de dependencias y facilidad de integración con PostgreSQL y pgvector.
  - Frontend: React con Vite como bundler – por su velocidad, experiencia de desarrollo moderna, y capacidad para construir interfaces reactivas y dinámicas.
  - Contenedores: Docker y Docker Compose – para facilitar el despliegue, escalabilidad y reproducibilidad del entorno en cualquier VPS.
- Justificación: NestJS ofrece una arquitectura limpia y escalable, con soporte nativo para TypeScript y ORM (TypeORM). React + Vite asegura un frontend ligero y rápido. Docker permite empaquetar la aplicación y desplegarla en un VPS sin conflictos de dependencias.

OBJETIVO GENERAL
Crear una plataforma funcional, moderna, administrable y escalable para la Polla Futbolera de Kamila Innovation, donde los participantes puedan pronosticar resultados de partidos del Mundial 2026, con un sistema de puntuación claro y un premio global. No se trata de un prototipo visual, sino de una aplicación real con base de datos, módulos, roles, datos precargados (equipos, grupos, calendario, estadísticas históricas) y lógica de negocio para gestionar predicciones, usuarios, administración, encuestas de consenso, puntuación y análisis.

ROLES DE USUARIO
La plataforma debe manejar como mínimo los siguientes roles:

1. Administrador
   - Gestionar equipos, grupos, fases del torneo y calendario de partidos.
   - Habilitar/deshabilitar partidos para la polla (inicialmente solo los del Grupo K en fase de grupos, y posteriormente los que defina para eliminación directa).
   - Crear encuestas para definir el valor de la apuesta por partido habilitado.
   - Configurar el premio global (monto en COP, fechas de inicio y fin de la competencia, si aplica).
   - Gestionar usuarios y roles.
   - Ver estadísticas globales de predicciones y participación.
   - Gestionar notificaciones y contenido de la plataforma.
   - Visualizar el ranking completo de participantes y el ganador provisional.

2. Participante
   - Registrarse e iniciar sesión.
   - Visualizar el calendario de partidos y las predicciones generadas.
   - Realizar pronósticos (apuestas) sobre partidos habilitados (marcador exacto, ganador, etc.), con bloqueo de edición una vez enviado.
   - Participar en encuestas de consenso para definir el valor de la apuesta de cada partido.
   - Consultar el valor de la apuesta definido para cada partido.
   - Comparar sus predicciones con las del sistema y otros usuarios.
   - Consultar su puntuación acumulada, puntos por partido y su posición en el ranking general.
   - Ver el premio global y el líder actual.
   - Recibir recomendaciones de partidos basadas en su historial.
   - Consultar estadísticas y análisis de cada equipo.
   - Hacer preguntas al asistente inteligente sobre el torneo.
   - Recibir notificaciones de resultados.

MÓDULOS PRINCIPALES DE LA PLATAFORMA
Diseña e implementa los siguientes módulos funcionales:

1. Página de inicio (Dashboard público)
   - Hero con mensaje principal y llamado a la acción.
   - Resumen de próximos partidos y predicciones destacadas.
   - Buscador global de equipos, partidos y predicciones.
   - Beneficios de la plataforma.
   - Sección de testimonios o estadísticas de usuarios.
   - Widget del premio global y líder actual.
   - Botón de registro y acceso a áreas protegidas.

2. Panel de usuario autenticado (Dashboard personal)
   - Tablero con predicciones recientes, partidos favoritos, y recomendaciones.
   - Historial de predicciones realizadas por el usuario (con puntos obtenidos en cada una).
   - Resumen de puntos totales y posición en el ranking.
   - Comparativa de aciertos vs sistema.
   - Acceso rápido a asistentes y búsqueda avanzada.
   - Visualización de partidos habilitados para la polla y su valor de apuesta.

3. Módulo de partidos y predicciones (Polla Futbolera)
   - Listado de partidos con filtros (grupo, fase, fecha, equipo, habilitado para polla).
   - Vista detallada de cada partido: equipos, fecha, estadísticas históricas, predicción del sistema.
   - Interfaz para que el usuario ingrese su propio pronóstico (marcador exacto, ganador, etc.) SOLO para partidos habilitados por el administrador.
   - Validación estricta: una vez enviado, el pronóstico no puede ser modificado (deshabilitar botón de edición y mostrar mensaje claro).
   - Visualización del valor de la apuesta para cada partido habilitado (definido por consenso).
   - Actualización automática de resultados (simulados o reales) y cálculo de puntos para cada predicción.
   - Ranking de usuarios con puntos acumulados (ordenado de mayor a menor), mostrando el premio global y el ganador provisional.

4. Módulo de administración de la polla
   - Habilitar/deshabilitar partidos para la polla (por grupo, fase o partido individual).
   - Crear encuestas de consenso para cada partido habilitado:
     - La encuesta debe mostrar opciones de valor de apuesta (ej. $5.000, $10.000, $20.000, etc.).
     - Los participantes votan por su opción preferida.
     - El administrador visualiza los resultados de la encuesta y define el valor final.
   - Gestionar el valor de la apuesta para cada partido.
   - Configurar el premio global: monto en COP, fechas de inicio y fin de la competencia (si aplica), y activar/desactivar el premio.
   - CRUD de equipos (nombre, país, escudo, ranking FIFA, etc.).
   - CRUD de grupos y fases del torneo.
   - Gestión del calendario de partidos (fecha, hora, estadio).
   - Carga masiva de datos históricos.
   - Visualización de métricas de uso y precisión general.
   - Visualización del ranking completo y estadísticas de puntos.

5. Buscador inteligente con pgvector
   - Crear una tabla para almacenar embeddings de equipos, partidos, estadísticas y predicciones.
   - Permitir búsqueda semántica de contenido.
   - Diseñar una función de similitud vectorial que retorne los elementos más relevantes según la consulta del usuario.
   - Preparar la infraestructura para ingestas futuras de datos y actualización de embeddings.

6. Asistente conversacional con IA
   - Chatbot integrado en la plataforma, accesible desde cualquier vista.
   - Debe responder preguntas sobre el torneo: historial, estadísticas, reglas, predicciones, etc.
   - Utilizar pgvector para recuperación semántica de información relevante.
   - Guardar el historial de conversaciones por usuario para contexto y mejora continua.

7. Módulo de notificaciones y alertas
   - Enviar notificaciones a los usuarios sobre resultados de partidos, cambios en predicciones, recordatorios.
   - Notificar cuando se habilite un nuevo partido para la polla y cuando se defina el valor de la apuesta.
   - Notificar el resultado de cada partido y los puntos obtenidos por el usuario.
   - Notificar cambios en el ranking y el nuevo líder.
   - Permitir configuración de preferencias.
   - Guardar historial de notificaciones enviadas.

8. Módulo de estadísticas y reportes
   - Visualización de gráficos (rendimiento de equipos, precisión de predicciones, participación de usuarios).
   - Estadísticas específicas de la polla: total apostado, ganancias/pérdidas de cada usuario, ranking.
   - Exportación de reportes en CSV o PDF.
   - Acceso solo para administradores y opcionalmente para usuarios avanzados.

BASE DE DATOS
Usando el MCP postgres_codex, crea todas las tablas necesarias en PostgreSQL dentro de la base de datos mundial_prediction_db. La estructura debe ser extensible y normalizada.

Tablas mínimas requeridas (añade todas las que consideres necesarias). **Todos los nombres de tablas y columnas deben estar en inglés**:
- users – id (UUID), name, email, password_hash, role, created_at, updated_at.
- roles – id, name (admin, participant), description.
- user_roles – user_id, role_id.
- teams – id, name, country, flag (URL or emoji code), crest (URL), fifa_ranking, group_id, etc.
- groups – id, name (e.g., Group A), stage (groups, round_of_16, etc.).
- matches – id, home_team_id, away_team_id, match_datetime (timestamp with timezone), stadium, stage, group_id (optional), home_score, away_score, status (scheduled, played, cancelled), enabled_for_pool (boolean), bet_value (decimal).
- predictions – id, user_id, match_id, predicted_home_score, predicted_away_score, predicted_winner, points_earned (integer, default 0), created_at, locked (boolean, default false).
- poll_consensus_surveys – id, match_id, created_by (admin_id), start_date, end_date, status (active, closed).
- poll_consensus_votes – id, survey_id, user_id, option_value (decimal), voted_at.
- poll_consensus_results – id, survey_id, final_value_defined (decimal), defined_by (admin_id), defined_at.
- global_prize – id, amount (decimal), start_date, end_date, is_active (boolean), description.
- historical_data – id, team_id, match_id (optional), statistics (JSON), date.
- embeddings – id, entity_type (team, match, etc.), entity_id, vector (pgvector), metadata (JSON).
- ai_chat_sessions – id, user_id, started_at, updated_at.
- ai_chat_messages – id, session_id, role (user/assistant), content, created_at.
- notifications – id, user_id, title, message, is_read, created_at, type.
- audit_logs – id, user_id (optional), action, affected_table, record_id, old_data (JSON), new_data (JSON), ip, created_at.
- transactions (optional) – id, user_id, amount, status, created_at.

Asegúrate de incluir índices apropiados para búsquedas frecuentes (por fecha, equipo, usuario, etc.) y para las consultas vectoriales usando pgvector.

DATOS INICIALES (SEEDERS) - MUNDIAL 2026
Los seeders deben precargar TODOS los equipos participantes con su bandera, fechas, calendarios y horarios del Mundial 2026.

Para obtener esta información, el sistema debe realizar una búsqueda en internet de los grupos exactos y el cronograma de fechas y horarios, teniendo como base la zona horaria de Colombia (UTC-5). Por defecto, todos los horarios deben mostrarse en hora colombiana.

Grupos del Mundial 2026 (confirmados):
- Grupo A: México, Sudáfrica, Corea del Sur, República Checa
- Grupo B: Canadá, Bosnia y Herzegovina, Catar, Suiza
- Grupo C: Brasil, Marruecos, Haití, Escocia
- Grupo D: Estados Unidos, Paraguay, Australia, Turquía
- Grupo E: Alemania, Curazao, Costa de Marfil, Ecuador
- Grupo F: Países Bajos, Japón, Suecia, Túnez
- Grupo G: Bélgica, Egipto, Irán, Nueva Zelanda
- Grupo H: España, Cabo Verde, Arabia Saudita, Uruguay
- Grupo I: Francia, Senegal, Irak, Noruega
- Grupo J: Argentina, Argelia, Austria, Jordania
- Grupo K: Portugal, RD Congo, Uzbekistán, Colombia
- Grupo L: Inglaterra, Croacia, Ghana, Panamá

Calendario de la fase de grupos (fechas y horarios en hora colombiana UTC-5): Incluye todos los 72 partidos. Se proporcionan los partidos de Colombia como referencia:
- Fecha 1: 18 de junio - 04:00 h - Uzbekistán vs Colombia - Estadio Azteca, CDMX.
- Fecha 2: 24 de junio - 04:00 h - Colombia vs RD Congo - Estadio Akron, Guadalajara.
- Fecha 3: 28 de junio - 01:30 h - Colombia vs Portugal - Hard Rock Stadium, Miami.

Los seeders deben incluir todos los partidos de la fase de grupos (72 partidos). Para la fase de eliminación directa, se debe dejar la estructura preparada para que el administrador pueda agregar los partidos a medida que avance el torneo.

Equipos con banderas: Cada equipo debe tener su bandera asociada (puede ser mediante un código de emoji de bandera o una URL de imagen). Ejemplo: 🇨🇴 para Colombia, 🇧🇷 para Brasil, etc.

REQUISITOS DE BASE DE DATOS
- Usa UUID como identificador principal en la mayoría de tablas (o serial si es más conveniente).
- Define claves primarias y foráneas con ON DELETE CASCADE o RESTRICT según la lógica de negocio.
- Índices para mejorar rendimiento en columnas de búsqueda (ej. email, match_date, team_id).
- Campos created_at y updated_at con valores automáticos.
- Restricciones de integridad (CHECK, NOT NULL, UNIQUE).
- Uso de pgvector: crea columnas de tipo vector para almacenar embeddings. Define índices de tipo ivfflat o hnsw para acelerar búsquedas.
- Datos semilla iniciales:
  - Todos los equipos con sus banderas, grupos y ranking FIFA (simulado).
  - Calendario completo de la fase de grupos (72 partidos) con fechas en hora colombiana.
  - Usuarios de prueba: admin (admin@kamila.com / [CONTRASEÑA_DE_PRUEBA]) y participante (user@kamila.com / [CONTRASEÑA_DE_PRUEBA]).
  - Partidos del Grupo K habilitados inicialmente para la polla (con valor de apuesta pendiente de definir mediante encuesta).
  - Premio global: inicialmente configurado en 300.000 COP, activo para toda la duración del torneo.
- Las migraciones deben ser claras, ordenadas e idempotentes (usar IF NOT EXISTS o migraciones versionadas).

DISEÑO DE INTERFAZ
Crea una interfaz moderna, limpia, responsive y profesional, similar a plataformas de análisis deportivo como SofaScore, ESPN o Transfermarkt.

Características visuales:
- Diseño tipo dashboard con barra lateral (colapsable) y menú superior.
- Tarjetas para partidos y equipos con información resumida.
- Tablas de clasificación y estadísticas.
- Gráficos interactivos (Chart.js o Recharts) para mostrar tendencias y precisión.
- Indicadores visuales para partidos habilitados para la polla, valor de la apuesta, y estado de la encuesta de consenso.
- Widget destacado del premio global y líder actual.
- Modo claro/oscuro (opcional).
- Estados visuales de carga, errores y acciones.
- Adaptación completa a móvil, tablet y escritorio.
- Componentes reutilizables (botones, inputs, modales, tarjetas).

FUNCIONALIDADES MÍNIMAS
La plataforma debe permitir:
- Registro e inicio de sesión con JWT.
- Gestión de roles y permisos.
- Creación/edición/eliminación de equipos, grupos, partidos (admin).
- Visualización de calendario y detalles de partidos.
- Habilitación/deshabilitación de partidos para la polla (admin).
- Creación de encuestas de consenso para definir el valor de la apuesta (admin).
- Votación en encuestas de consenso (participantes).
- Definición del valor final de la apuesta basado en consenso (admin).
- Realización de pronósticos (apuestas) por parte de los usuarios SOLO en partidos habilitados, con bloqueo de edición una vez enviado.
- Cálculo automático de puntos al finalizar cada partido (basado en el resultado real y las reglas de puntuación).
- Actualización en tiempo real del ranking y del líder.
- Visualización del premio global y el ganador actual.
- Consulta de predicciones del sistema.
- Comparativa de precisión del usuario vs el sistema.
- Búsqueda semántica con pgvector.
- Chatbot con IA.
- Notificaciones push en la interfaz y por correo (simulado).
- Panel de administración con estadísticas y gestión completa (incluyendo configuración del premio).
- Historial de predicciones y auditoría.

SEGURIDAD
Incluye buenas prácticas de seguridad:
- Contraseñas hasheadas con bcrypt o argon2.
- Validación de formularios (frontend y backend) con esquemas (Zod o class-validator).
- Protección de rutas por rol (guardias en NestJS).
- Control de permisos granulares.
- Prevención de inyección SQL (usar ORM/Query Builder parametrizado).
- Manejo seguro de sesiones con JWT (expiración, refresco).
- Logs de auditoría para acciones críticas.
- CORS configurado adecuadamente.
- Límites de tasa (rate limiting) para prevenir ataques de fuerza bruta.

ENTREGABLES ESPERADOS
Al finalizar, debes entregar:
1. Estructura completa del proyecto (carpetas backend/ y frontend/).
2. Código fuente organizado y comentado en las partes clave.
3. Scripts SQL o migraciones para PostgreSQL.
4. Tablas creadas en la base de datos mundial_prediction_db usando el MCP postgres_codex.
5. Datos iniciales de todos los equipos, grupos y 72 partidos de la fase de grupos con horarios en hora colombiana.
6. Backend funcional con todas las rutas API (REST o GraphQL) documentadas (Swagger/OpenAPI).
7. Frontend funcional con React y Vite, consumiendo la API.
8. Panel de administración completo (incluyendo gestión de polla, encuestas y premio global).
9. Panel de usuario con todas las funcionalidades (incluyendo votación, apuestas, puntos y ranking).
10. Módulo de predicciones y comparativas.
11. Buscador semántico con pgvector.
12. Asistente conversacional integrado.
13. Sistema de notificaciones básico.
14. Documentación de instalación y ejecución (README).
15. Explicación de la arquitectura y decisiones técnicas.
16. Diagrama entidad-relación de la base de datos.
17. Lista de mejoras futuras y posibles extensiones.
18. Archivos Dockerfile y docker-compose.yml para levantar toda la aplicación (backend, frontend, PostgreSQL) con un solo comando.

CRITERIOS DE ACEPTACIÓN
La plataforma se considera terminada cuando:
- Se pueda iniciar sesión con los usuarios de prueba (admin y participante).
- El administrador pueda ver el dashboard, gestionar equipos, partidos y usuarios.
- El administrador pueda habilitar/deshabilitar partidos para la polla.
- El administrador pueda crear una encuesta de consenso para un partido habilitado.
- Los participantes puedan votar en la encuesta para definir el valor de la apuesta.
- El administrador pueda definir el valor final de la apuesta basado en el consenso.
- Los participantes puedan realizar pronósticos (apuestas) solo en partidos habilitados y con valor de apuesta definido.
- Una vez enviado un pronóstico, no se pueda modificar (bloqueo efectivo).
- Al finalizar un partido, el sistema calcule automáticamente los puntos de cada participante según las reglas (1 punto por ganador/empate + 1 punto extra por marcador exacto).
- El ranking se actualice automáticamente y se muestre el líder y el premio global.
- El participante pueda ver el calendario, seleccionar un partido y realizar su predicción.
- El sistema muestre predicciones automáticas basadas en datos históricos.
- La búsqueda semántica devuelva resultados relevantes usando pgvector.
- El asistente conversacional responda preguntas básicas sobre equipos y partidos.
- Las notificaciones se generen para eventos clave.
- El proyecto se pueda ejecutar localmente con docker-compose up y siguiendo el README.
- La base de datos contenga todas las tablas y datos semilla (con todos los equipos y partidos de la fase de grupos).
- El código esté bien estructurado, con separación de responsabilidades y buenas prácticas.

IMPORTANTE: Antes de codificar, realiza un análisis de la arquitectura más conveniente. Selecciona el ORM (TypeORM o Prisma) y justifícalo. Define claramente los modelos de datos y las relaciones. Prioriza una solución funcional, escalable, clara y fácil de mantener. No entregues solo explicaciones: entrega la plataforma implementada con código, base de datos y datos iniciales.

Al final quiero una plataforma de predicción de mundial (Polla Futbolera Kamila Innovation) funcional, desplegable en un VPS con Docker.
```
