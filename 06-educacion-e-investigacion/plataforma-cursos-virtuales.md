# Plataforma de cursos virtuales (LMS)

**Categoría:** [Educación e investigación](README.md) · **Tecnologías:** PostgreSQL + pgvector, MCP, full-stack

LMS completo inspirado en Platzi, Coursera, edX y Udemy, con búsqueda semántica y recomendaciones.

## Prompt

```text
Actúa como un arquitecto de software senior, experto en plataformas educativas tipo LMS, diseño de bases de datos PostgreSQL, pgvector, experiencia de usuario educativa y desarrollo full stack.

Necesito que construyas una plataforma educativa web completa para ofrecer cursos virtuales en línea de diferentes temáticas. La plataforma debe inspirarse en la estructura funcional de sitios como Platzi, Coursera, edX y Udemy, tomando como referencia sus mejores prácticas: catálogo de cursos, rutas de aprendizaje, clases en video, materiales PDF, evaluaciones, certificados, progreso del estudiante, panel del instructor, panel administrativo, comunidad o sección de preguntas, reseñas, búsqueda avanzada y experiencia moderna para el usuario.

CONTEXTO TÉCNICO:
Ya existe una base de datos vacía en PostgreSQL llamada:

“plataforma-educativa”

Debes conectarte a esta base de datos usando el MCP de PostgreSQL llamado:

“postgres-codex”

La base de datos ya tiene instalada la extensión pgvector, por lo tanto debes aprovecharla para funcionalidades de búsqueda semántica, recomendaciones de cursos, asistente educativo con IA o recuperación de contenido por similitud.

OBJETIVO GENERAL:
Crear una plataforma educativa funcional, moderna, administrable y escalable para ofrecer cursos virtuales. No quiero solamente una maqueta visual; quiero una estructura real de aplicación, con base de datos, módulos, roles, cursos precargados y lógica necesaria para administrar cursos, estudiantes, instructores, contenidos, evaluaciones y certificados.

ROLES DE USUARIO:
La plataforma debe manejar como mínimo los siguientes roles:

1. Administrador
   - Crear, editar, publicar y despublicar cursos.
   - Gestionar usuarios, instructores y participantes.
   - Ver estadísticas generales.
   - Administrar categorías, niveles, certificados y evaluaciones.
   - Gestionar matrículas y progreso de los estudiantes.

2. Instructor
   - Crear y administrar sus cursos.
   - Subir o registrar videos.
   - Agregar materiales PDF.
   - Crear módulos, lecciones, tareas y exámenes.
   - Revisar avances de los estudiantes.
   - Responder preguntas de los participantes.

3. Estudiante o participante
   - Registrarse e iniciar sesión.
   - Explorar el catálogo de cursos.
   - Inscribirse en cursos.
   - Ver clases en video.
   - Descargar o visualizar materiales PDF.
   - Presentar exámenes.
   - Consultar su progreso.
   - Obtener certificado al completar un curso.
   - Hacer preguntas o comentarios dentro del curso.
   - Valorar cursos.

MÓDULOS PRINCIPALES DE LA PLATAFORMA:
Diseña e implementa los siguientes módulos:

1. Página de inicio
   - Hero principal.
   - Buscador de cursos.
   - Cursos destacados.
   - Categorías principales.
   - Beneficios de la plataforma.
   - Sección de testimonios.
   - Llamado a la acción para registrarse.

2. Catálogo de cursos
   - Listado de cursos.
   - Filtros por categoría, nivel, duración, instructor, precio o estado.
   - Ordenamiento por popularidad, fecha, calificación o nivel.
   - Tarjetas de cursos con imagen, título, descripción corta, instructor, nivel, duración, calificación y número de estudiantes.

3. Página detalle del curso
   - Título del curso.
   - Descripción.
   - Objetivos de aprendizaje.
   - Requisitos.
   - Público objetivo.
   - Temario organizado por módulos y lecciones.
   - Vista previa de algunas clases.
   - Instructor.
   - Valoraciones.
   - Botón de inscripción.
   - Certificado disponible al finalizar.

4. Reproductor del curso
   - Menú lateral con módulos y lecciones.
   - Reproductor de video.
   - Materiales PDF asociados.
   - Botón para marcar lección como completada.
   - Barra de progreso.
   - Sección de comentarios o preguntas.
   - Acceso a exámenes o actividades.

5. Evaluaciones
   - Preguntas de selección múltiple.
   - Preguntas verdadero/falso.
   - Preguntas abiertas opcionales.
   - Calificación automática para preguntas cerradas.
   - Intentos permitidos.
   - Puntaje mínimo de aprobación.
   - Retroalimentación al estudiante.

6. Certificados
   - Generar certificado cuando el estudiante complete el curso y apruebe la evaluación.
   - Guardar código único de verificación.
   - Permitir descargar certificado en PDF.
   - Crear una página pública de verificación del certificado.

7. Panel administrativo
   - Dashboard con métricas.
   - Total de cursos.
   - Total de usuarios.
   - Total de estudiantes inscritos.
   - Cursos más vistos.
   - Progreso promedio.
   - Gestión CRUD de cursos, usuarios, categorías, módulos, lecciones, evaluaciones y certificados.

8. Panel del estudiante
   - Mis cursos.
   - Progreso por curso.
   - Certificados obtenidos.
   - Cursos recomendados.
   - Historial de evaluaciones.
   - Continuar donde quedó.

9. Panel del instructor
   - Mis cursos creados.
   - Crear nuevo curso.
   - Gestionar contenido.
   - Ver estudiantes inscritos.
   - Ver preguntas de estudiantes.
   - Ver estadísticas del curso.

10. Buscador inteligente con pgvector
   - Crear una tabla para embeddings.
   - Permitir búsqueda semántica de cursos, módulos, lecciones y contenidos.
   - Preparar la estructura para que posteriormente se puedan insertar embeddings de descripciones, lecciones, transcripciones o materiales.
   - Diseñar una función o consulta de similitud usando vector.

11. Asistente educativo con IA
   - Diseñar la estructura para un chatbot académico dentro de cada curso.
   - El chatbot debe responder con base en el contenido del curso.
   - Debe estar preparado para usar pgvector como base de recuperación semántica.
   - Debe guardar historial de conversaciones por usuario y curso.

BASE DE DATOS:
Usando el MCP “postgres-codex”, crea todas las tablas necesarias en PostgreSQL dentro de la base de datos “plataforma-educativa”.

La base de datos debe incluir como mínimo tablas y las demás que se necesiten para:

- users
- roles
- user_roles
- instructors
- categories
- courses
- course_modules
- lessons
- lesson_resources
- enrollments
- progress
- exams
- exam_questions
- exam_options
- exam_attempts
- exam_answers
- certificates
- course_reviews
- course_questions
- course_answers
- payments o transactions, si se decide manejar cursos pagos
- course_embeddings
- lesson_embeddings
- ai_chat_sessions
- ai_chat_messages
- notifications
- audit_logs

ojo si se necesitan mas tablas debes crearlas.

REQUISITOS DE BASE DE DATOS:
- Usa UUID como identificador principal cuando sea conveniente.
- Define claves primarias y foráneas.
- Define índices para mejorar rendimiento.
- Define campos created_at y updated_at.
- Usa restricciones para mantener integridad.
- Activa o usa pgvector para campos vectoriales.
- Crea datos semilla iniciales.
- No elimines información existente sin autorización.
- Las migraciones deben ser claras, ordenadas e idempotentes cuando sea posible.

CURSOS INICIALES PRECARGADOS:
La plataforma debe venir con 3 cursos ya creados:

1. Curso de Inteligencia Artificial para niños
   - Nivel: básico
   - Público: niños y principiantes
   - Debe incluir módulos sobre qué es la IA, ejemplos cotidianos, uso responsable, juegos con IA y proyecto final sencillo.

2. Curso básico de Python para todos
   - Nivel: básico
   - Público: personas sin experiencia en programación
   - Debe incluir módulos sobre instalación, variables, condicionales, ciclos, funciones, listas, pequeños proyectos y evaluación final.

3. Curso de Agentes de IA
   - Nivel: intermedio
   - Público: docentes, desarrolladores y personas interesadas en automatización con IA
   - Debe incluir módulos sobre qué son los agentes, herramientas, memoria, planificación, flujos de trabajo, casos de uso, integración con APIs y proyecto final.

Cada curso debe tener:
- Imagen o portada de referencia.
- Descripción corta.
- Descripción larga.
- Objetivos de aprendizaje.
- Requisitos.
- Público objetivo.
- Mínimo 4 módulos.
- Mínimo 3 lecciones por módulo.
- Recursos PDF simulados o referenciados.
- Videos simulados con URL de ejemplo.
- Examen final.
- Certificado al completar.

DISEÑO DE INTERFAZ:
Crea una interfaz moderna, limpia, responsive y profesional.

Debe tener una apariencia similar a una plataforma educativa comercial:
- Diseño tipo dashboard.
- Tarjetas de cursos.
- Barra lateral para el reproductor.
- Menú superior.
- Sección de usuario autenticado.
- Estados visuales de progreso.
- Diseño adaptable a computador, tablet y móvil.
- Componentes reutilizables.

FUNCIONALIDADES MÍNIMAS:
La plataforma debe permitir:

- Registro e inicio de sesión.
- Gestión de roles.
- Crear cursos.
- Editar cursos.
- Publicar cursos.
- Inscribir estudiantes.
- Ver contenido del curso.
- Marcar lecciones como completadas.
- Presentar exámenes.
- Calcular progreso.
- Generar certificados.
- Buscar cursos.
- Recomendar cursos.
- Guardar preguntas y respuestas.
- Administrar usuarios.
- Administrar categorías.
- Consultar estadísticas básicas.

SEGURIDAD:
Incluye buenas prácticas de seguridad:

- Contraseñas cifradas.
- Validación de formularios.
- Protección de rutas por rol.
- Control de permisos.
- Prevención de inyección SQL.
- Manejo seguro de sesiones o tokens.
- Logs de auditoría para acciones importantes.

ENTREGABLES ESPERADOS:
Al finalizar debes entregar:

1. Estructura completa del proyecto.
2. Código fuente organizado.
3. Script SQL o migraciones para PostgreSQL.
4. Tablas creadas en la base de datos “plataforma-educativa” usando el MCP “postgres-codex”.
5. Datos iniciales de los 3 cursos.
6. Backend funcional.
7. Frontend funcional.
8. Panel administrativo.
9. Panel del estudiante.
10. Panel del instructor.
11. Reproductor de cursos.
12. Sistema de evaluaciones.
13. Sistema de certificados.
14. Búsqueda tradicional y estructura para búsqueda semántica con pgvector.
15. Documentación de instalación y ejecución.
16. README con instrucciones claras.
17. Explicación de la arquitectura.
18. Diagrama o descripción de la base de datos.
19. Lista de mejoras futuras.

CRITERIOS DE ACEPTACIÓN:
La plataforma se considera terminada cuando:

- Se pueda iniciar sesión con usuarios de prueba.
- Se puedan ver los 3 cursos iniciales.
- Un estudiante pueda inscribirse a un curso.
- Un estudiante pueda ver videos y materiales.
- Un estudiante pueda completar lecciones.
- El sistema calcule el progreso.
- El estudiante pueda presentar un examen.
- El sistema genere un certificado si aprueba.
- El administrador pueda gestionar cursos y usuarios.
- El instructor pueda gestionar sus cursos.
- La base de datos PostgreSQL tenga todas las tablas necesarias.
- pgvector quede preparado para búsquedas semánticas.
- El proyecto pueda ejecutarse localmente siguiendo el README.

IMPORTANTE:
Antes de construir, analiza la arquitectura más conveniente. Si no existe un stack definido, selecciona uno moderno y justifica brevemente la elección. Prioriza una solución funcional, escalable, clara y fácil de mantener. No entregues solo una explicación: entrega la plataforma implementada con código, base de datos y datos iniciales.

Al final quiero que me entregues una plataforma educativa funcional.
```
