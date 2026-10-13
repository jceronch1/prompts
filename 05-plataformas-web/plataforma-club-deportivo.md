# Plataforma de gestión de un club deportivo

**Categoría:** [Plataformas web](README.md) · **Tecnologías:** NestJS, React + Vite, PostgreSQL + pgvector, MCP

Gestión integral de un club: socios, categorías, equipos, eventos, membresías, asistencia y documentos.

> **Antes de usarlo, reemplaza:** `[CONTRASEÑA_DE_PRUEBA]`

## Prompt

```text
Actúa como un arquitecto de software senior, experto en plataformas de gestión para clubes y asociaciones, diseño de bases de datos PostgreSQL con pgvector, experiencia de usuario y desarrollo full stack con NestJS, React y Vite.

Contexto técnico disponible:
- Base de datos PostgreSQL vacía llamada: ikaros_club_db
- Conexión mediante el MCP de PostgreSQL llamado: postgres_codex
- La base de datos ya tiene instalada la extensión pgvector, por lo que debes aprovecharla para búsqueda semántica de socios, eventos, documentos, comunicaciones, y asistencia.
- Stack tecnológico:
  - Backend: NestJS (TypeScript) – con soporte para GraphQL/REST, inyección de dependencias y fácil integración con PostgreSQL y pgvector.
  - Frontend: React con Vite – para interfaces reactivas y dinámicas.
  - Contenedores: Docker y Docker Compose – para despliegue en VPS.

Nombre comercial del producto: Koru Club Manager (KoruCM).

REFERENCIAS VISUALES PARA EL FRONTEND
Las siguientes imágenes proporcionan la guía de diseño y experiencia de usuario para la plataforma:

IMAGEN 1 - PANEL DE ADMINISTRACIÓN / DASHBOARD PRINCIPAL
- Barra lateral izquierda con navegación: Mi Perfil, Jugadores, Equipos, Entrenamientos, Partidos, Calendario, Asistencias, Evaluaciones, Comunicados, Pagos, Galería, Tienda, Documentos, Ajustes.
- Cabecera con saludo personalizado: "¡Hola, María! Bienvenida al panel de Ikaros Club".
- Widget destacado: "Próximo Partido" con fecha, hora, lugar, equipos y marcador (18-0 como placeholder).
- Tarjeta "Agenda de hoy" con lista de actividades (entrenamientos, reuniones) y horarios.
- Tarjeta "Estado de pagos" con gráficos circulares (75% al día, 15% pendientes, 10% vencidos) y botón "Realizar pago".
- Tarjeta "Mis Equipos" con lista de equipos y jugadoras destacadas.
- Tarjeta "Comunicados recientes" con lista de noticias (Torneo Interclubes, cambio de horario, tienda oficial).
- Pie de página con logos de App Store y Google Play.
- Eslogan: "Somos más que un club, somos familia. Disciplina, esfuerzo y pasión nos llevan a volar más alto."

IMAGEN 2 - PANEL DE USUARIO / ESPACIO PERSONAL (ACUDIENTE/PADRE)
- Barra lateral izquierda con navegación: Inicio, Mi Perfil, Mis Hijos, Entrenamientos, Partidos, Calendario, Comunicados, Pagos, Galería, Tienda, Documentos, Contacto.
- Cabecera con saludo personalizado: "¡Bienvenida, Ana! Aquí tienes todo lo que necesitas sobre Ikaros Club."
- Widgets resumen: "Mis Hijos" (1 deportista activo), "Próximo Entrenamiento", "Próximo Partido", "Saldo Pendiente" ($120.000), "Asistencia" (92%).
- Agenda semanal con días y actividades.
- Tarjeta de jugadora destacada: Valentina Gómez (U14 Femenino - #12, estado Activa).
- Comunicados recientes con fechas.
- Galería reciente con vista de imágenes.
- Sección de "Últimas evaluaciones" con calificaciones por categoría (Técnica, Táctica, Física, Actitud).
- Eslogan: "Ikaros es más que un club, es familia. Juntas volamos más alto."

ESTILOS A APLICAR EN EL FRONTEND:
- Paleta de colores: Tonos deportivos (naranja, azul oscuro, blanco, gris claro) con acentos en dorado o amarillo.
- Tipografía: Moderna y legible (ej. Inter, Roboto, Montserrat).
- Componentes: Tarjetas con sombras suaves, bordes redondeados, iconos claros (FontAwesome o Material Icons).
- Dashboard: Organización en grid de widgets con información priorizada.
- Gráficos: Chart.js o Recharts para visualización de pagos, asistencias, evaluaciones.
- Responsive: Adaptación a móvil, tablet y escritorio.
- Estados visuales: Carga con skeletons, errores con alertas amigables, acciones con feedback.

OBJETIVO GENERAL
Crear una plataforma funcional, moderna, administrable y escalable para la gestión integral del Ikaros Club, un club de baloncesto que necesita centralizar la administración de deportistas, padres/acudientes, finanzas, eventos, comunicaciones, logística, documentación, salud, inventario, reportes, patrocinios y marcador en tiempo real de partidos.

ROLES DE USUARIO
1. Administrador / Gestor del club
2. Entrenador / Preparador físico
3. Socio / Deportista (jugador)
4. Padre / Acudiente (con acceso limitado a la información de su(s) hijo(s))
5. Árbitro / Delegado (con permisos para registrar marcador en tiempo real)

MÓDULOS PRINCIPALES DE LA PLATAFORMA

1. Página de inicio (Dashboard público)
- Hero, llamado a la acción, resumen de próximos eventos, buscador global, beneficios, testimonios, widget de incentivos (si aplica), registro/acceso.

2. Panel de usuario autenticado (Espacio Personal)
- Resumen personalizado: cuotas, próximos entrenamientos/partidos, notificaciones, historial de pagos, inscripciones, documentos personales, acceso rápido a asistente KAI y búsqueda avanzada.
- Diseño basado en las imágenes referenciadas (widgets de resumen, agenda, comunicados, evaluaciones).

3. Gestión Deportiva
- Registro y administración de deportistas (nombre, fecha de nacimiento, categoría según año, posición, etc.).
- Control de categorías (por año de nacimiento) y equipos.
- Seguimiento de asistencia a entrenamientos (marcar asistencia, listado por fecha y categoría).
- Evaluaciones de rendimiento por los entrenadores (escalas, comentarios, fechas).
- Control de restricciones médicas (lesiones, recomendaciones).
- Planificación de entrenamientos (fecha, hora, lugar, contenido, responsable).

4. Gestión de Padres y Acudientes
- Registro de padres o acudientes asociados a uno o varios deportistas.
- Actualización de datos de contacto (teléfono, email, dirección).
- Autorizaciones y permisos digitales (para viajes, actividades extra, uso de imagen, etc.).
- Visibilidad de la información de sus hijos (calendario, asistencia, evaluaciones) con permisos.

5. Gestión Financiera
- Pago de mensualidades (cuotas periódicas) y suscripciones.
- Pago de inscripciones a torneos o actividades.
- Pago de viáticos para viajes.
- Registro de ingresos y egresos (concepto, categoría, fecha, comprobante).
- Generación de recibos y comprobantes (PDF).
- Alertas de pagos pendientes (envío automático).
- Reportes financieros (estado de cuenta, morosidad, ingresos vs gastos, etc.).
- Integración con Stripe para pagos online.
- Widgets visuales como los mostrados en las imágenes (gráficos circulares de estado de pagos).

6. Gestión de Eventos y Competencias
- Programación de partidos (local/visitante, fecha, hora, lugar, rival).
- Convocatorias a torneos (con inscripción de equipos y jugadores).
- Inscripción a eventos (torneos, clínicas, campamentos).
- Calendario compartido (sincronización con Google Calendar, iCal).
- Notificaciones de cambios de horario o lugar (push, email, SMS).

7. MARCADOR EN TIEMPO REAL - RESULTADOS DE PARTIDOS (NUEVO)
Este módulo permite registrar el marcador de los partidos del club en tiempo real, con una interfaz sencilla y rápida para uso durante el juego.

Funcionalidades:
- Selección del partido en curso (equipo local, equipo visitante, categoría, fecha).
- Pantalla de marcador en vivo con:
  - Nombre de los equipos y escudos.
  - Puntuación actualizada (local - visitante).
  - Cuarto / período actual (1, 2, 3, 4, tiempo extra).
  - Tiempo restante del cuarto (reloj de 10 minutos con posibilidad de pausa/reanudación).
  - Historial de puntos anotados (registro cronológico con tipo de tiro y jugador, si se desea).
- Botones para registrar puntos:
  - **1 punto** (tiro libre).
  - **2 puntos** (canasta de campo).
  - **3 puntos** (triple).
  - Botón para seleccionar el equipo que anota (Local o Visitante) antes de registrar.
- Botón para iniciar/detener el reloj del partido.
- Botón para cambiar de cuarto.
- Registro de faltas por equipo (opcional, pero recomendado).
- Posibilidad de añadir jugadores anotadores (asociado al número de camiseta) para estadísticas individuales.
- Resumen estadístico al finalizar el partido (puntos por cuarto, mejores anotadores, etc.).
- Visualización del marcador en vivo en el dashboard principal y en el panel del usuario (widget "Próximo Partido" con el marcador actualizado).
- Historial de resultados de partidos anteriores con posibilidad de ver detalles.

8. Gestión de Comunicación
- Envío masivo de mensajes por WhatsApp (usando API de WhatsApp Business o Twilio).
- Correos electrónicos automáticos (bienvenida, recordatorios, facturas, circulares).
- Circulares y comunicados (publicación en la plataforma y envío por email/SMS) – como se muestra en las imágenes.
- Chat integrado entre miembros del club (por equipos, categorías o grupos).
- Segmentación de destinatarios por categoría, equipo, rol, etc.

9. Gestión de Logística y Salidas
- Programación de viajes y desplazamientos (fecha, destino, medio de transporte).
- Control de asistencia en viajes (lista de participantes).
- Información de hospedajes y transporte (direcciones, contactos).
- Autorizaciones de salida (con firma digital de padres/acudientes).
- Gestión de viáticos y reembolsos asociados.

10. Gestión Documental
- Carga de documentos de identidad (cédula, pasaporte, etc.).
- Consentimientos informados (médicos, de participación, de imagen).
- Formulario de inscripción (digital, con validación y envío de documentos).
- Repositorio centralizado de documentos del club y por deportista (historial médico, certificados, etc.).

11. Gestión de Salud
- Registro de EPS y contacto de emergencia.
- Registro de tipo de sangre.
- Registro de alergias y condiciones médicas relevantes.
- Historial de lesiones y atenciones.
- Alertas médicas para entrenadores (mostrar restricciones).

12. Gestión de Inventario y Dotación
- Control de uniformes (tallas, cantidades, asignación a deportistas).
- Entrega de implementos deportivos (balones, conos, petos, etc.).
- Inventario de balones y equipos (cantidad, estado, ubicación).
- Historial de préstamos (quién, qué, cuándo, devolución).

13. Buscador inteligente con pgvector
- Tabla de embeddings para socios, eventos, documentos, comunicaciones, y ahora también para evaluaciones, inventario, viajes, partidos, etc.
- Búsqueda semántica de cualquier contenido.
- Función de similitud vectorial para recuperación de información.

14. Asistente conversacional con IA (KAI)
- Chatbot accesible desde cualquier vista.
- Responde preguntas sobre el club, eventos, finanzas, logística, reglamentos, etc.
- Usa pgvector para recuperación semántica.
- Guarda historial por usuario.

15. Módulo de notificaciones y alertas
- Notificaciones push, email y SMS para: pagos pendientes, cambios de horario, recordatorios de eventos, autorizaciones pendientes, resultados de partidos, etc.
- Configuración de preferencias por usuario.
- Historial de notificaciones enviadas.

16. Módulo de reportes e indicadores
- Número de deportistas activos por categoría.
- Asistencia a entrenamientos (porcentaje por categoría y deportista).
- Morosidad y cartera (deuda total, días de mora).
- Participación en torneos (número de torneos, partidos jugados, resultados).
- Indicadores financieros (ingresos, gastos, saldo, proyecciones).
- Exportación a Excel y PDF de todos los reportes.
- Carné digital del deportista (con foto, datos, categoría y código QR).
- Módulo de patrocinadores y donaciones: registro de patrocinadores, montos, beneficios, seguimiento de donaciones.

17. Módulo de administración general
- Gestión de usuarios, roles, categorías, equipos, planes de membresía, configuración del club.

BASE DE DATOS
Usando el MCP postgres_codex, crea todas las tablas necesarias en PostgreSQL dentro de la base de datos ikaros_club_db. Todos los nombres de tablas y columnas deben estar en inglés.

Tablas mínimas requeridas (incluyendo nuevas para el marcador en tiempo real):

- users, roles, user_roles
- members (con campos para deportistas: birth_date, category, position, medical_restrictions, etc.)
- member_custom_fields, member_groups, member_group_assignments
- membership_plans, membership_subscriptions
- parents (relación muchos a muchos con members)
- authorizations (digital signatures for travel, activities, image use)
- attendances (entrenamientos, viajes, partidos)
- performance_evaluations
- trainings
- payments
- income_expenses
- events
- event_registrations, event_tickets
- matches (id, home_team_id, away_team_id, match_datetime, location, stage, home_score, away_score, status, category_id)
- MATCH_LIVE_SCORES (NUEVA TABLA para marcador en tiempo real):
  - id, match_id, home_score, away_score, current_quarter (1-4, OT), time_remaining (seconds), is_running (boolean), last_updated
  - Se actualiza en tiempo real desde el frontend (WebSockets o polling)
- MATCH_SCORING_EVENTS (NUEVA TABLA para historial de puntos):
  - id, match_id, team_scored (home/away), points (1, 2, 3), player_id (opcional, quién anotó), minute (minuto del partido), quarter, created_at
- MATCH_PLAYER_STATS (NUEVA TABLA para estadísticas individuales por partido):
  - id, match_id, player_id, points, rebounds, assists, steals, blocks, fouls, minutes_played
- travel_plans, travel_participants
- products, orders, order_items
- documents
- health_records
- inventory_items, inventory_loans
- sponsors, donations
- notifications, embeddings, ai_chat_sessions, ai_chat_messages, audit_logs, club_settings

Todas las tablas deben tener campos created_at y updated_at.

Índices: email, member_id, event_date, category, match_id, etc. Índice vectorial para pgvector.

Datos semilla iniciales:
- Roles: admin, coach, member, parent, referee.
- Usuarios de prueba: admin (admin@ikaros.com / [CONTRASEÑA_DE_PRUEBA]), entrenador (coach@ikaros.com / [CONTRASEÑA_DE_PRUEBA]), socio (member@ikaros.com / [CONTRASEÑA_DE_PRUEBA]), padre (parent@ikaros.com / [CONTRASEÑA_DE_PRUEBA]), árbitro (referee@ikaros.com / [CONTRASEÑA_DE_PRUEBA]).
- Categorías: Sub-8, Sub-10, Sub-12, Sub-14, Sub-16, Sub-18, Senior.
- Equipos iniciales: al menos uno por categoría.
- Plan de membresía básico (ej. "Socio Anual" - $200.000 COP/año).
- Al menos 10 deportistas de prueba con sus datos.
- Algunos padres asociados.
- Entrenamientos programados.
- Eventos (partidos, torneos) futuros con marcador inicial en 0-0.
- Productos en tienda.
- Documentos de ejemplo.
- Configuración del club.

DISEÑO DE INTERFAZ (basado en las imágenes referenciadas)
- Dashboard principal con barra lateral colapsable (navegación clara).
- Widgets con información priorizada (próximo partido, agenda de hoy, estado de pagos, mis equipos, comunicados recientes).
- Tarjetas con sombras suaves y bordes redondeados.
- Paleta de colores: naranja (#F97316), azul oscuro (#1E293B), blanco (#FFFFFF), gris claro (#F1F5F9).
- Tipografía: Inter o Roboto.
- Gráficos: Chart.js o Recharts (pastel para pagos, barras para asistencias, líneas para rendimiento).
- Responsive: adaptación a móvil, tablet y escritorio.
- Iconos: FontAwesome o Lucide React.
- Estados: skeletons para carga, toast para notificaciones, modales para acciones.

FUNCIONALIDADES MÍNIMAS (resumen)
- Registro y autenticación con JWT.
- CRUD completo de deportistas, padres, categorías, equipos, entrenamientos, eventos, partidos, viajes, inventario, patrocinadores.
- Asistencia a entrenamientos y viajes.
- Evaluaciones de rendimiento.
- Pagos online (Stripe) para mensualidades, inscripciones, viáticos.
- Gestión de autorizaciones digitales.
- MARCADOR EN TIEMPO REAL con botones de 1, 2 y 3 puntos, reloj de partido, cambios de cuarto, historial de puntos.
- Envío de comunicaciones (WhatsApp, email, SMS).
- Reportes e indicadores con exportación a Excel/PDF.
- Carné digital con QR.
- Buscador semántico con pgvector.
- Asistente KAI con IA.
- Notificaciones push/email/SMS.
- Módulo de patrocinadores y donaciones.

SEGURIDAD
- Contraseñas hasheadas (bcrypt/argon2).
- Validación con Zod o class-validator.
- Protección de rutas por rol (guardias NestJS).
- Prevención de SQL injection (ORM/Query Builder).
- JWT con expiración y refresco.
- Logs de auditoría.
- CORS y rate limiting.

ENTREGABLES ESPERADOS
1. Estructura completa backend/ y frontend/.
2. Código organizado y comentado.
3. Migraciones SQL para PostgreSQL.
4. Tablas creadas en ikaros_club_db usando postgres_codex.
5. Datos semilla completos.
6. Backend funcional con API documentada (Swagger/OpenAPI).
7. Frontend funcional con React/Vite, siguiendo los estilos de las imágenes.
8. Panel de administración completo (todos los módulos).
9. Panel de usuario (Espacio Personal) con todas las funcionalidades.
10. Módulo de marcador en tiempo real con interfaz de puntuación (1, 2, 3 puntos) y reloj.
11. Buscador semántico y asistente KAI.
12. Sistema de notificaciones.
13. Dockerfile y docker-compose.yml para levantar todo con un solo comando.
14. README con instrucciones de instalación y ejecución.
15. Diagrama entidad-relación.
16. Lista de mejoras futuras.

CRITERIOS DE ACEPTACIÓN
- Inicio de sesión con usuarios de prueba.
- Administrador puede gestionar todos los módulos.
- Entrenador puede ver su calendario, marcar asistencias y evaluar.
- Deportista puede ver su perfil, pagos, asistencias, evaluaciones, calendario.
- Padre puede ver la información de sus hijos y autorizar documentos.
- Pagos online funcionales (Stripe en modo sandbox).
- Comunicaciones masivas (simuladas) y notificaciones en tiempo real.
- Reportes exportables.
- Carné digital generado.
- Buscador semántico y asistente responden consultas.
- **El módulo de marcador en tiempo real permite registrar puntos (1, 2, 3) para local/visitante, pausar/reanudar el reloj, cambiar de cuarto, y mostrar el marcador actualizado en el dashboard.**
- El proyecto se ejecuta con docker-compose up.

IMPORTANTE: Antes de codificar, analiza la arquitectura, selecciona ORM (TypeORM o Prisma) y justifícalo. Define modelos y relaciones claramente. La solución debe ser funcional, escalable, clara y mantenible.

Al final, entrega la plataforma completa, desplegable en un VPS con Docker.
```
