# Plataforma colaborativa de mapas mentales con IA

**Categoría:** [Plataformas web](README.md) · **Tecnologías:** Next.js, NestJS, PostgreSQL, Redis, Yjs, OpenAI

SaaS de mapas mentales, diagramas y pizarra colaborativa en tiempo real con asistente de IA.

> **Antes de usarlo, reemplaza:** `[TU_CONTRASEÑA_POSTGRES]`, `[TU_USUARIO_POSTGRES]`

## Prompt

````text
# PROMPT MAESTRO: PLATAFORMA COLABORATIVA DE MAPAS MENTALES, DIAGRAMAS Y PIZARRA CON IA

Actúa como un equipo senior completo formado por:

* Arquitecto de software.
* Ingeniero frontend especializado en editores gráficos.
* Ingeniero backend.
* Especialista en sistemas colaborativos en tiempo real.
* Diseñador UX/UI de productos SaaS.
* Ingeniero de bases de datos.
* Especialista en integración con OpenAI.
* Ingeniero DevOps.
* Especialista en seguridad.
* Ingeniero QA y automatización de pruebas.

Tu misión es diseñar y desarrollar desde cero una plataforma web SaaS robusta, escalable y lista para producción llamada provisionalmente:

**[BIGMAP]**

La plataforma debe combinar las mejores capacidades funcionales de una pizarra colaborativa, una aplicación de mapas mentales y una herramienta profesional de diagramación.

Debe inspirarse funcionalmente en productos como Miro, MindMeister, Lucidchart, Xmind, Mindomo, Coggle, FigJam, MindMup y GitMind, pero sin copiar su código, identidad visual, textos, logotipos, iconos propietarios ni diseño exacto.

El producto debe tener identidad, experiencia de usuario y arquitectura propias.

---

# 1. OBJETIVO DEL PRODUCTO

Construye una plataforma web que permita a personas, docentes, estudiantes, investigadores, empresas y equipos:

1. Crear mapas mentales.
2. Crear mapas conceptuales.
3. Crear diagramas de flujo.
4. Crear organigramas.
5. Crear diagramas de procesos.
6. Crear diagramas UML.
7. Crear diagramas entidad-relación.
8. Crear diagramas de red.
9. Crear líneas de tiempo.
10. Crear diagramas de espina de pescado.
11. Crear matrices FODA.
12. Crear árboles de decisión.
13. Crear estructuras de desglose del trabajo.
14. Crear mapas de experiencia del cliente.
15. Crear pizarras colaborativas.
16. Realizar lluvias de ideas.
17. Organizar notas adhesivas.
18. Convertir ideas en tareas.
19. Trabajar colaborativamente en tiempo real.
20. Crear automáticamente cualquiera de estas estructuras mediante la API de OpenAI.

El usuario debe poder comenzar desde:

* Un lienzo vacío.
* Una plantilla.
* Una descripción escrita.
* Un tema corto.
* Un texto extenso.
* Un documento cargado.
* Un esquema en Markdown.
* Un archivo JSON.
* Un mapa previamente creado.

---

# 2. PRINCIPIOS OBLIGATORIOS

La aplicación no debe ser una demostración visual ni un prototipo con botones falsos.

Debe cumplir estas reglas:

* Todas las funciones principales deben estar implementadas.
* No utilizar datos simulados como solución final.
* No incluir botones sin comportamiento.
* No guardar la clave de OpenAI en el frontend.
* No exponer secretos en el código JavaScript del navegador.
* No depender exclusivamente del almacenamiento local.
* No crear un único archivo gigante difícil de mantener.
* No copiar la interfaz de otra plataforma.
* No bloquear la interfaz mientras se genera contenido con IA.
* No reemplazar la colaboración real por una simulación.
* No almacenar imágenes en base64 dentro de PostgreSQL.
* No confiar en el JSON generado por la IA sin validarlo.
* No eliminar cambios de usuarios por conflictos de sincronización.
* No utilizar posiciones absolutas rígidas para toda la interfaz.
* No sacrificar accesibilidad por diseño.

El resultado debe ser modular, documentado, mantenible, probado y desplegable.

---

# 3. ARQUITECTURA RECOMENDADA

Construye un monorepo organizado de la siguiente manera:

```text
/apps
  /web
  /api
  /realtime
/packages
  /ui
  /editor-core
  /diagram-types
  /ai-schemas
  /database
  /auth
  /shared
  /config
  /testing
```

## Frontend

Utiliza:

* Next.js con App Router.
* React.
* TypeScript estricto.
* Tailwind CSS.
* Componentes accesibles y reutilizables.
* Una biblioteca de iconos consistente.
* Zustand o una solución equivalente para el estado local.
* TanStack Query para datos remotos.
* React Hook Form y Zod para formularios y validación.
* React Flow, tldraw, Konva o una combinación técnicamente justificada para el editor.
* Una biblioteca de autoorganización como ELK.js o Dagre.
* IndexedDB para caché local y recuperación temporal.
* Service Worker para funciones PWA cuando sea conveniente.

Utiliza siempre versiones estables y compatibles entre sí.

## Backend

Utiliza:

* Node.js.
* TypeScript.
* NestJS o una arquitectura backend modular equivalente.
* API REST documentada con OpenAPI.
* WebSocket para colaboración y presencia.
* PostgreSQL.
* Prisma ORM o equivalente.
* Redis para presencia, caché, sesiones, rate limiting y colas.
* BullMQ o sistema equivalente para trabajos pesados.
* Almacenamiento compatible con S3 para archivos e imágenes.
* Procesamiento asíncrono de exportaciones y documentos.
* Logs estructurados.
* Manejo centralizado de excepciones.
* Métricas y trazabilidad.

## Colaboración en tiempo real

Implementa colaboración real utilizando:

* Yjs, CRDT o tecnología equivalente.
* WebSocket.
* Estado de presencia.
* Cursores remotos.
* Selecciones remotas.
* Sincronización incremental.
* Reconexión automática.
* Recuperación después de pérdida de conexión.
* Persistencia de actualizaciones.
* Resolución de conflictos.
* Edición optimista.
* Indicador de usuarios conectados.

No debe sobrescribirse todo el documento cada vez que un usuario mueve un nodo.

---

# 4. TIPOS DE USUARIO Y PERMISOS

Implementa los siguientes roles:

## Propietario

* Control total del espacio de trabajo.
* Administración de miembros.
* Facturación.
* Eliminación del espacio.
* Configuración de seguridad.
* Consulta de auditoría.

## Administrador

* Administración de usuarios y proyectos.
* Gestión de plantillas.
* Configuración de permisos.
* Consulta de actividad.

## Editor

* Crear y modificar tableros.
* Comentar.
* Invitar usuarios cuando tenga autorización.
* Utilizar funciones de IA.

## Comentarista

* Visualizar.
* Comentar.
* Responder comentarios.
* Reaccionar.
* Participar en votaciones.

## Espectador

* Acceso de solo lectura.
* Navegación y presentación.

## Invitado temporal

* Acceso mediante enlace con vencimiento.
* Permisos limitados.
* Sin acceso a otros archivos del espacio.

Los permisos deben evaluarse en el servidor y no solamente ocultarse en la interfaz.

---

# 5. ESTRUCTURA GENERAL DE LA APLICACIÓN

Crea las siguientes páginas:

## Página pública

* Encabezado.
* Explicación del producto.
* Ejemplos.
* Casos de uso.
* Plantillas destacadas.
* Funciones de IA.
* Planes.
* Preguntas frecuentes.
* Registro e inicio de sesión.

## Autenticación

* Registro.
* Inicio de sesión.
* Recuperación de contraseña.
* Inicio con proveedores externos.
* Verificación de correo.
* Gestión de sesiones.

## Dashboard

* Tableros recientes.
* Favoritos.
* Compartidos conmigo.
* Plantillas.
* Papelera.
* Carpetas.
* Espacios de trabajo.
* Buscador.
* Filtros.
* Ordenamiento.
* Creación rápida.
* Importación.
* Actividad reciente.

## Editor visual

Debe ser la pantalla principal del producto y contener:

* Barra superior.
* Barra lateral de herramientas.
* Lienzo central infinito.
* Panel derecho de propiedades.
* Minimapa.
* Controles de zoom.
* Lista de colaboradores.
* Comentarios.
* Historial.
* Botón de compartir.
* Botón de presentación.
* Botón de exportación.
* Asistente de IA.
* Navegador de páginas o marcos.
* Indicador de guardado.

## Administración

* Miembros.
* Roles.
* Grupos.
* Uso de almacenamiento.
* Consumo de IA.
* Auditoría.
* Seguridad.
* Integraciones.
* Facturación.
* Plantillas organizacionales.

---

# 6. LIENZO INFINITO

Implementa un editor visual fluido con:

* Desplazamiento horizontal y vertical.
* Zoom mediante rueda, teclado y controles.
* Zoom hacia el punto del cursor.
* Ajustar todo el contenido a pantalla.
* Centrar selección.
* Cuadrícula opcional.
* Reglas opcionales.
* Guías inteligentes.
* Ajuste a cuadrícula.
* Ajuste a objetos.
* Selección por rectángulo.
* Selección múltiple.
* Copiar, pegar y duplicar.
* Cortar.
* Arrastrar y soltar.
* Agrupar y desagrupar.
* Bloquear y desbloquear.
* Alinear.
* Distribuir.
* Ordenar al frente o al fondo.
* Rotar.
* Redimensionar.
* Deshacer y rehacer.
* Atajos de teclado.
* Menú contextual.
* Edición mediante doble clic.
* Navegación con teclado.
* Colapso de ramas.
* Expansión de ramas.
* Vista de minimapa.
* Modo pantalla completa.
* Modo enfoque.
* Modo presentación.

Mantén 60 FPS en interacciones normales y virtualiza elementos cuando el tablero sea grande.

---

# 7. ELEMENTOS DEL EDITOR

Permite insertar:

* Nodo de mapa mental.
* Nodo de mapa conceptual.
* Texto.
* Título.
* Nota adhesiva.
* Rectángulo.
* Rectángulo redondeado.
* Círculo.
* Elipse.
* Rombo.
* Triángulo.
* Hexágono.
* Nube.
* Contenedor.
* Tarjeta.
* Imagen.
* Icono.
* Emoji.
* Enlace.
* Archivo adjunto.
* Tabla.
* Código.
* Fórmula matemática.
* Lista de tareas.
* Marco.
* Sección.
* Línea.
* Flecha.
* Conector curvo.
* Conector ortogonal.
* Conector bidireccional.
* Dibujo a mano alzada.
* Resaltador.
* Sello.
* Reacción.
* Comentario anclado.
* Video o recurso incrustado mediante URL segura.

Cada elemento debe tener propiedades editables como:

* Posición.
* Tamaño.
* Rotación.
* Color de fondo.
* Color de borde.
* Grosor.
* Opacidad.
* Sombra.
* Tipografía.
* Tamaño de texto.
* Alineación.
* Espaciado.
* Iconos.
* Estado de bloqueo.
* Hipervínculos.
* Metadatos.
* Datos de tarea.
* Usuario responsable.
* Fecha límite.
* Prioridad.
* Progreso.

---

# 8. MAPAS MENTALES

Implementa mapas mentales profesionales con:

* Tema central.
* Temas principales.
* Subtemas ilimitados.
* Creación rápida con Tab y Enter.
* Arrastre de ramas entre padres.
* Reordenamiento.
* Plegado de ramas.
* Numeración opcional.
* Límites visuales.
* Resúmenes de ramas.
* Relaciones cruzadas.
* Notas.
* Enlaces.
* Archivos.
* Imágenes.
* Etiquetas.
* Iconos.
* Prioridades.
* Progreso.
* Tareas.
* Colores automáticos por rama.
* Estilos heredados.
* Diferentes estilos de conexión.
* Diseño radial.
* Diseño hacia la derecha.
* Diseño hacia la izquierda.
* Diseño equilibrado.
* Diseño de árbol.
* Diseño lógico.
* Diseño organizacional.
* Vista de esquema.
* Conversión entre esquema y mapa.

El usuario debe poder cambiar el diseño sin perder contenido ni relaciones.

---

# 9. DIAGRAMACIÓN PROFESIONAL

Implementa bibliotecas de figuras para:

## Diagramas de flujo

* Inicio y fin.
* Proceso.
* Decisión.
* Entrada y salida.
* Documento.
* Subproceso.
* Base de datos.
* Conectores.

## UML

* Casos de uso.
* Clases.
* Secuencia.
* Actividad.
* Componentes.
* Despliegue.
* Estados.

## Bases de datos

* Entidades.
* Atributos.
* Relaciones.
* Cardinalidades.
* Claves primarias y foráneas.

## Redes

* Servidores.
* Computadores.
* Routers.
* Switches.
* Nubes.
* Firewalls.
* Bases de datos.
* Dispositivos móviles.

## Negocios y educación

* Organigramas.
* BPMN básico.
* Matriz FODA.
* Diagrama de Ishikawa.
* Línea de tiempo.
* Árbol de decisión.
* Mapa conceptual.
* Mapa de empatía.
* Customer journey.
* Modelo Canvas.
* WBS.
* Diagrama de Venn.
* Matrices.
* Tableros Kanban.

Las conexiones deben permanecer vinculadas al mover o redimensionar objetos.

---

# 10. PIZARRA COLABORATIVA

Incluye herramientas para reuniones, clases y talleres:

* Notas adhesivas.
* Escritura libre.
* Dibujos.
* Resaltador.
* Temporizador.
* Votación.
* Reacciones.
* Emoticonos.
* Sellos.
* Puntero láser.
* Seguimiento del presentador.
* Música o señales opcionales para sesiones.
* Ordenamiento automático de notas.
* Agrupación por categorías.
* Detección de duplicados.
* Resumen de ideas.
* Conversión de notas en tareas.
* Plantillas para retrospectivas.
* Design thinking.
* Brainstorming.
* Clases.
* Planeación estratégica.
* Reuniones.
* Investigación.
* Gestión de proyectos.

El creador de una sesión debe poder iniciar y cerrar una votación y consultar los resultados.

---

# 11. COLABORACIÓN

Implementa:

* Edición simultánea.
* Cursores identificados por nombre y color.
* Avatares de usuarios activos.
* Indicador de conexión.
* Comentarios generales.
* Comentarios anclados a elementos.
* Menciones con `@usuario`.
* Respuestas.
* Resolución y reapertura de comentarios.
* Reacciones.
* Historial de actividad.
* Notificaciones.
* Enlaces compartidos.
* Permisos de lectura, comentario y edición.
* Protección mediante contraseña.
* Fecha de expiración.
* Acceso de invitado.
* Seguimiento del presentador.
* Vista independiente del tablero.
* Presencia en tiempo real.
* Registro de quién realizó cada cambio importante.

---

# 12. HISTORIAL Y VERSIONES

Implementa:

* Guardado automático.
* Indicador “Guardando”.
* Indicador “Guardado”.
* Recuperación ante cierre inesperado.
* Historial de versiones.
* Versiones nombradas.
* Vista previa de versiones.
* Restauración.
* Duplicación desde una versión.
* Registro de autor y fecha.
* Comparación de cambios relevantes.
* Papelera con restauración.
* Eliminación definitiva protegida.

Utiliza instantáneas periódicas y actualizaciones incrementales.

---

# 13. ASISTENTE DE INTELIGENCIA ARTIFICIAL

Integra la API de OpenAI exclusivamente desde el backend.

Usa la Responses API y salidas estructuradas.

La clave debe leerse desde:

```env
OPENAI_API_KEY=
OPENAI_MODEL=
```

Nunca envíes `OPENAI_API_KEY` al navegador.

## Formulario “Crear con IA”

Solicita:

* Tema.
* Objetivo.
* Tipo de diagrama.
* Público objetivo.
* Idioma.
* Nivel de profundidad.
* Número aproximado de ramas.
* Número máximo de niveles.
* Estilo visual.
* Orientación.
* Incluir ejemplos.
* Incluir tareas.
* Incluir recursos.
* Incluir preguntas.
* Incluir resumen.
* Incluir referencias proporcionadas por el usuario.

## Tipos generables

La IA debe poder crear:

* Mapa mental.
* Mapa conceptual.
* Diagrama de flujo.
* Organigrama.
* Línea de tiempo.
* Árbol de decisión.
* Matriz FODA.
* Diagrama de Ishikawa.
* WBS.
* Customer journey.
* Mapa de empatía.
* Plan de proyecto.
* Plan de clase.
* Ruta de aprendizaje.
* Resumen visual.
* Diagrama UML básico.
* Modelo entidad-relación.
* Lluvia de ideas.
* Notas adhesivas organizadas.

## Acciones de IA sobre una selección

Al seleccionar un nodo o rama, ofrecer:

* Expandir.
* Resumir.
* Simplificar.
* Explicar.
* Reescribir.
* Traducir.
* Crear ejemplos.
* Crear preguntas.
* Crear tareas.
* Crear riesgos.
* Crear soluciones.
* Generar ideas relacionadas.
* Reorganizar jerarquía.
* Detectar duplicados.
* Identificar conceptos faltantes.
* Convertir en otro tipo de diagrama.
* Mejorar redacción.
* Cambiar nivel académico.
* Crear una presentación.
* Generar descripción accesible.

La IA nunca debe reemplazar el tablero sin confirmación. Debe mostrar una vista previa o permitir deshacer la operación.

---

# 14. FLUJO DE GENERACIÓN CON IA

Implementa este proceso:

1. El usuario escribe el tema.
2. El frontend valida el formulario.
3. Se envía la solicitud al backend.
4. El backend valida identidad, permisos, cuota y tamaño.
5. El backend construye un prompt seguro.
6. El backend llama a OpenAI.
7. OpenAI devuelve un JSON estructurado.
8. El backend valida el JSON con Zod o JSON Schema.
9. Se rechazan estructuras inválidas.
10. Se normalizan identificadores y posiciones.
11. Se ejecuta el algoritmo de autoorganización.
12. Se guarda una versión previa del tablero.
13. Se incorporan nodos y conexiones.
14. Se registra el consumo.
15. El usuario puede aceptar, modificar o deshacer.

Incluye:

* Timeout.
* Reintentos limitados.
* Cancelación.
* Streaming del estado de generación.
* Manejo de rate limits.
* Manejo de respuestas incompletas.
* Mensajes de error comprensibles.
* Registro técnico sin almacenar secretos.
* Control de costo por usuario.
* Límites por plan.
* Prevención de solicitudes duplicadas.

---

# 15. ESQUEMA ESTRUCTURADO PARA OPENAI

Define un esquema equivalente al siguiente y valídalo tanto en la respuesta del modelo como en el servidor:

```typescript
type AIDiagram = {
  title: string;
  description: string;
  diagramType:
    | "mind_map"
    | "concept_map"
    | "flowchart"
    | "org_chart"
    | "timeline"
    | "decision_tree"
    | "swot"
    | "fishbone"
    | "wbs"
    | "customer_journey"
    | "empathy_map"
    | "uml"
    | "erd"
    | "brainstorm";
  layout:
    | "radial"
    | "horizontal"
    | "vertical"
    | "tree"
    | "freeform"
    | "grid";
  nodes: Array<{
    id: string;
    type: string;
    label: string;
    description: string;
    parentId: string | null;
    level: number;
    order: number;
    x: number | null;
    y: number | null;
    width: number | null;
    height: number | null;
    style: {
      backgroundColor: string | null;
      borderColor: string | null;
      textColor: string | null;
      icon: string | null;
      shape: string | null;
    };
    metadata: {
      tags: string[];
      priority: "low" | "medium" | "high" | null;
      progress: number | null;
      assignee: string | null;
      dueDate: string | null;
      notes: string | null;
    };
  }>;
  edges: Array<{
    id: string;
    source: string;
    target: string;
    label: string | null;
    type: "straight" | "curved" | "orthogonal";
    directed: boolean;
  }>;
  groups: Array<{
    id: string;
    title: string;
    nodeIds: string[];
  }>;
  summary: string;
  suggestedActions: string[];
};
```

Reglas del esquema:

* Usar modo estricto.
* Todos los campos deben estar definidos.
* No aceptar propiedades adicionales.
* Los identificadores deben ser únicos.
* Ninguna conexión puede apuntar a un nodo inexistente.
* No permitir ciclos en estructuras jerárquicas, salvo que el tipo de diagrama lo admita.
* El nodo raíz debe existir en mapas mentales.
* Los niveles deben ser coherentes.
* El número de nodos debe respetar el límite solicitado.
* Los colores deben ser valores válidos.
* Las fechas deben usar ISO 8601.
* El progreso debe estar entre 0 y 100.

---

# 16. PROMPT INTERNO PARA GENERAR DIAGRAMAS

Crea en el backend una plantilla de instrucciones similar a esta:

```text
Eres un especialista en organización visual de conocimiento,
mapas mentales, diagramación, educación y gestión de proyectos.

Tu tarea es transformar la solicitud del usuario en una estructura
visual rigurosa, clara, editable y jerárquicamente coherente.

No generes explicaciones fuera del esquema solicitado.

Reglas:
1. Respeta el idioma solicitado.
2. Crea etiquetas breves y comprensibles.
3. Utiliza las descripciones para ampliar información.
4. Evita ramas redundantes.
5. Mantén equilibrio entre las ramas principales.
6. Respeta el número máximo de niveles.
7. No inventes fuentes ni datos que el usuario no haya pedido.
8. Si el tema es académico, organiza de lo general a lo particular.
9. Si es un proceso, garantiza una secuencia lógica.
10. Si es un árbol de decisión, diferencia claramente condiciones y resultados.
11. Si es una línea de tiempo, conserva el orden cronológico.
12. Si es un organigrama, conserva la jerarquía.
13. Si es una matriz FODA, usa exactamente cuatro grupos.
14. Si es un diagrama de flujo, utiliza nodos y conexiones válidos.
15. Devuelve exclusivamente el objeto estructurado solicitado.
```

Separa claramente:

* Instrucciones del sistema.
* Datos del usuario.
* Contenido extraído de archivos.
* Opciones de generación.

Nunca concatenes datos no confiables como si fueran instrucciones del sistema.

---

# 17. CARGA Y CONVERSIÓN DE CONTENIDO

Prepara la arquitectura para aceptar:

* TXT.
* Markdown.
* PDF.
* DOCX.
* PPTX.
* CSV.
* JSON.
* OPML.
* Imágenes.
* Audio.
* Video.
* URL.

Implementa inicialmente los formatos que puedan procesarse correctamente y deja adaptadores claramente definidos para los demás.

El flujo debe ser:

1. Carga segura.
2. Validación MIME real.
3. Límite de tamaño.
4. Escaneo.
5. Almacenamiento temporal.
6. Extracción de contenido.
7. Segmentación.
8. Resumen.
9. Generación de estructura.
10. Eliminación o conservación según política.

No proceses archivos únicamente por su extensión.

---

# 18. IMPORTACIÓN Y EXPORTACIÓN

Permite importar:

* JSON propio.
* Markdown jerárquico.
* Texto indentado.
* OPML.
* CSV estructurado.
* Imágenes como referencia.
* Archivos compatibles que puedan transformarse sin infringir formatos propietarios.

Permite exportar:

* PNG.
* JPEG.
* SVG.
* PDF.
* JSON editable.
* Markdown.
* OPML.
* CSV de tareas.
* Presentación.
* Enlace público.
* Código Mermaid cuando el tipo de diagrama sea compatible.

La exportación debe respetar:

* Fondo transparente opcional.
* Resolución.
* Área seleccionada.
* Tablero completo.
* Márgenes.
* Escala.
* Orientación.
* Inclusión o exclusión de comentarios.
* Inclusión o exclusión de notas.

---

# 19. PLANTILLAS

Crea una galería de plantillas con categorías:

* Educación.
* Investigación.
* Desarrollo de software.
* Inteligencia artificial.
* Negocios.
* Planeación estratégica.
* Gestión de proyectos.
* Marketing.
* Diseño.
* Reuniones.
* Recursos humanos.
* Ingeniería.
* Diagramas técnicos.
* Desarrollo personal.

Cada plantilla debe incluir:

* Nombre.
* Descripción.
* Miniatura.
* Categoría.
* Etiquetas.
* Autor.
* Visibilidad.
* Fecha.
* Número de usos.
* Estructura inicial.
* Variables configurables.

Permite:

* Crear una plantilla desde un tablero.
* Duplicar.
* Compartir.
* Publicar dentro de una organización.
* Marcar como favorita.
* Buscar.
* Filtrar.

---

# 20. PRESENTACIONES

Permite convertir el tablero en presentación:

* Crear marcos o diapositivas.
* Ordenarlas.
* Seleccionar el área visible.
* Ocultar herramientas.
* Navegar con teclado.
* Añadir notas del presentador.
* Seguir al presentador.
* Compartir mediante enlace.
* Pantalla completa.
* Exportar a PDF.
* Transiciones discretas.
* Controles accesibles.

---

# 21. MODELO DE DATOS

Diseña entidades como mínimo para:

* User.
* Account.
* Session.
* Organization.
* Workspace.
* Membership.
* Team.
* Folder.
* Board.
* BoardPage.
* BoardSnapshot.
* BoardUpdate.
* Template.
* ShareLink.
* Comment.
* CommentReply.
* Notification.
* Attachment.
* AIRequest.
* AIUsage.
* Subscription.
* AuditLog.
* Invitation.
* Favorite.
* ExportJob.

Incluye:

* UUID.
* Fechas de creación y modificación.
* Eliminación lógica cuando corresponda.
* Índices.
* Restricciones.
* Relaciones.
* Control de propietario.
* Versionado.
* Metadatos JSON únicamente cuando sea apropiado.
* Políticas de retención.

No almacenes todo el sistema en una única columna JSON.

---

# 22. API

Diseña endpoints para:

```text
POST   /auth/register
POST   /auth/login
POST   /auth/logout

GET    /workspaces
POST   /workspaces
PATCH  /workspaces/:id
DELETE /workspaces/:id

GET    /boards
POST   /boards
GET    /boards/:id
PATCH  /boards/:id
DELETE /boards/:id
POST   /boards/:id/duplicate

GET    /boards/:id/comments
POST   /boards/:id/comments

POST   /boards/:id/share
DELETE /boards/:id/share/:shareId

GET    /boards/:id/versions
POST   /boards/:id/versions
POST   /boards/:id/versions/:versionId/restore

POST   /ai/generate-diagram
POST   /ai/expand-node
POST   /ai/summarize-selection
POST   /ai/reorganize
POST   /ai/convert-diagram
POST   /ai/extract-tasks

POST   /imports
POST   /exports
GET    /jobs/:id

GET    /templates
POST   /templates
POST   /templates/:id/use
```

Incluye:

* Autenticación.
* Autorización.
* Validación.
* Rate limiting.
* Idempotencia para operaciones sensibles.
* Paginación.
* Filtros.
* Códigos HTTP correctos.
* Formato de errores consistente.
* OpenAPI.
* Pruebas de contrato.

---

# 23. EXPERIENCIA VISUAL

Diseña una interfaz moderna, humana y profesional.

Características visuales:

* Estética SaaS contemporánea.
* Espacios amplios.
* Jerarquía tipográfica clara.
* Buen contraste.
* Iconografía coherente.
* Animaciones breves.
* Respuesta visual inmediata.
* Modo claro.
* Modo oscuro.
* Temas personalizados.
* Diseño responsive.
* Estados vacíos útiles.
* Skeleton loaders.
* Mensajes de error claros.
* Tooltips.
* Onboarding interactivo.
* Comandos rápidos.
* Paleta de comandos.
* Atajos visibles.

No abuses de:

* Gradientes.
* Sombras excesivas.
* Tarjetas innecesarias.
* Texto genérico.
* Animaciones decorativas.
* Elementos que parezcan generados automáticamente sin criterio.

---

# 24. ACCESIBILIDAD

Cumple como mínimo:

* Navegación por teclado.
* Indicadores de foco.
* Etiquetas ARIA.
* Contraste adecuado.
* Textos alternativos.
* Compatibilidad con lectores de pantalla.
* Reducción de movimiento.
* Tamaño mínimo de objetivos táctiles.
* No depender exclusivamente del color.
* Atajos configurables.
* Descripción textual del diagrama.
* Lista jerárquica alternativa al lienzo.
* Exportación accesible cuando sea posible.

---

# 25. SEGURIDAD

Implementa:

* Cookies seguras y HTTP-only.
* Protección CSRF cuando corresponda.
* Protección XSS.
* Sanitización de HTML.
* Prevención de SQL Injection.
* Content Security Policy.
* Validación de URLs.
* Restricción de iframes.
* CORS limitado.
* Rate limiting.
* Bloqueo temporal ante abuso.
* Auditoría.
* Control de acceso en cada recurso.
* Enlaces compartidos con tokens no predecibles.
* Rotación y expiración de tokens.
* Cifrado en tránsito.
* Protección de secretos.
* Validación de archivos.
* Límites de carga.
* Control de consumo de IA.
* Prevención de prompt injection desde documentos.
* Registro de operaciones administrativas.

Nunca confíes en identificadores enviados por el frontend sin comprobar propiedad y permisos.

---

# 26. RENDIMIENTO

Establece objetivos:

* Carga inicial optimizada.
* División de código.
* Carga diferida.
* Caché.
* Compresión.
* Virtualización de objetos.
* Actualizaciones incrementales.
* Consultas indexadas.
* Paginación.
* Optimización de imágenes.
* Generación de miniaturas.
* Web Workers para cálculos pesados.
* Exportaciones en segundo plano.
* Reconexión WebSocket eficiente.
* Debounce de operaciones frecuentes.
* No enviar el documento completo por cada movimiento.

Prueba tableros con:

* 100 nodos.
* 1.000 nodos.
* 5.000 nodos.
* Múltiples conexiones.
* Al menos 20 usuarios simultáneos en una sesión de prueba.

Documenta las limitaciones reales encontradas.

---

# 27. PRUEBAS

Incluye:

## Pruebas unitarias

* Transformaciones.
* Validadores.
* Esquemas.
* Permisos.
* Autoorganización.
* Conversión de formatos.
* Cálculo de límites.

## Pruebas de integración

* Base de datos.
* Autenticación.
* API.
* Redis.
* OpenAI mediante mocks controlados.
* Colaboración.
* Persistencia.
* Exportación.

## Pruebas end-to-end

* Registro.
* Creación de tablero.
* Creación de mapa.
* Edición.
* Guardado.
* Compartir.
* Colaboración.
* Comentarios.
* Generación mediante IA.
* Deshacer generación.
* Exportación.
* Restauración de versión.
* Permisos.

## Pruebas adicionales

* Accesibilidad.
* Rendimiento.
* Seguridad básica.
* Reconexión.
* Conflictos simultáneos.
* Responsive.
* Navegadores principales.

---

# 28. OBSERVABILIDAD

Implementa:

* Logs estructurados.
* Identificador de solicitud.
* Seguimiento de errores.
* Métricas de API.
* Latencia.
* Errores por endpoint.
* Conexiones WebSocket.
* Usuarios concurrentes.
* Tiempo de generación con IA.
* Tokens o unidades consumidas.
* Costos estimados.
* Fallos de validación.
* Trabajos en cola.
* Alertas.
* Health checks.
* Readiness checks.

No registres claves, contraseñas ni contenido privado completo.

---

# 29. DESPLIEGUE

Entrega:

* Dockerfile para cada servicio.
* Docker Compose para desarrollo.
* Variables de entorno documentadas.
* Migraciones de base de datos.
* Datos iniciales.
* Script de creación de administrador.
* Configuración de PostgreSQL.
* Configuración de Redis.
* Configuración de almacenamiento.
* Pipeline CI/CD.
* Ejecución de lint.
* Type checking.
* Pruebas.
* Build.
* Migraciones seguras.
* Despliegue.
* Rollback.
* Copias de seguridad.

El proyecto debe poder iniciarse localmente con instrucciones claras.

---

# 30. PLANES Y LÍMITES

Prepara una arquitectura de planes:

## Gratuito

* Número limitado de tableros privados.
* Colaboradores básicos.
* Exportación estándar.
* Créditos limitados de IA.

## Profesional

* Tableros ilimitados según política.
* Exportación avanzada.
* Historial extendido.
* Más créditos de IA.
* Plantillas personalizadas.

## Equipo

* Espacios compartidos.
* Roles.
* Administración.
* Plantillas organizacionales.
* Auditoría.
* Facturación centralizada.

## Institucional

* SSO.
* Aprovisionamiento.
* Controles avanzados.
* Retención.
* Auditoría extendida.
* Opciones de residencia y administración.

No integres pagos hasta que el núcleo funcional esté estable, pero deja el modelo preparado.

---

# 31. FASES DE DESARROLLO

## Fase 1: núcleo funcional

* Autenticación.
* Dashboard.
* Creación de tableros.
* Lienzo infinito.
* Nodos.
* Conectores.
* Mapas mentales.
* Guardado.
* Historial básico.
* Exportación JSON y PNG.

## Fase 2: colaboración

* WebSocket.
* CRDT.
* Cursores.
* Presencia.
* Comentarios.
* Compartir.
* Roles.
* Versiones.

## Fase 3: inteligencia artificial

* Generación desde tema.
* Structured Outputs.
* Expansión.
* Resumen.
* Reorganización.
* Conversión.
* Medición de consumo.

## Fase 4: diagramas avanzados

* Flujo.
* UML.
* ERD.
* Organigramas.
* Líneas de tiempo.
* Plantillas.

## Fase 5: producción

* Seguridad.
* Accesibilidad.
* Rendimiento.
* Observabilidad.
* CI/CD.
* Facturación preparada.
* Documentación.

Cada fase debe producir una aplicación ejecutable y verificable.

---

# 32. CRITERIOS DE ACEPTACIÓN

El producto se considerará funcional cuando:

1. Un usuario pueda registrarse e iniciar sesión.
2. Pueda crear un tablero.
3. Pueda crear, editar, mover, conectar y eliminar nodos.
4. Pueda deshacer y rehacer.
5. El tablero se guarde automáticamente.
6. Dos usuarios puedan editar simultáneamente.
7. Los cursores y selecciones remotas sean visibles.
8. Pueda compartir el tablero con permisos.
9. Pueda comentar sobre un elemento.
10. Pueda restaurar una versión.
11. Pueda escribir un tema y generar un mapa con OpenAI.
12. El mapa generado sea completamente editable.
13. La respuesta de IA sea validada mediante esquema estricto.
14. La clave de OpenAI nunca llegue al navegador.
15. Pueda exportar el tablero.
16. Los permisos se validen en el servidor.
17. La aplicación tenga pruebas automatizadas.
18. La instalación esté documentada.
19. No existan errores críticos en consola.
20. No haya botones principales sin funcionamiento.

---

# 33. ENTREGABLES

Entrega:

1. Arquitectura explicada.
2. Árbol de carpetas.
3. Código fuente completo.
4. Esquema de base de datos.
5. Migraciones.
6. API documentada.
7. Editor visual funcional.
8. Servicio de colaboración.
9. Integración con OpenAI.
10. Esquemas Zod o JSON Schema.
11. Pruebas.
12. Docker.
13. Archivo `.env.example`.
14. Datos iniciales.
15. Manual de instalación.
16. Manual de despliegue.
17. Manual de usuario básico.
18. Decisiones técnicas.
19. Riesgos y limitaciones.
20. Lista de mejoras futuras.

---

# 34. INSTRUCCIONES PARA LA GENERACIÓN DEL CÓDIGO

Trabaja de manera incremental.

Antes de escribir código:

1. Explica brevemente la arquitectura elegida.
2. Presenta el árbol del proyecto.
3. Define el modelo de datos.
4. Define el formato del documento visual.
5. Define el mecanismo de colaboración.
6. Define el flujo de OpenAI.
7. Identifica riesgos técnicos.

Después:

1. Crea la configuración del monorepo.
2. Implementa la base de datos.
3. Implementa autenticación.
4. Implementa el editor.
5. Implementa persistencia.
6. Implementa colaboración.
7. Implementa IA.
8. Implementa exportación.
9. Añade pruebas.
10. Documenta.

En cada etapa:

* Entrega archivos completos.
* Indica claramente la ruta de cada archivo.
* Evita fragmentos inconexos.
* No reemplaces código ya funcional sin necesidad.
* Conserva tipado estricto.
* Ejecuta mentalmente y valida las importaciones.
* Corrige errores antes de continuar.
* Incluye manejo de errores.
* Incluye estados de carga.
* Incluye estados vacíos.
* Incluye pruebas relevantes.
* No afirmes que una función está terminada si solo está maquetada.

Si depronto necesitas ingresar a crea una base PostgreSQL local los datos son usuario: [TU_USUARIO_POSTGRES] y password: [TU_CONTRASEÑA_POSTGRES]

El resultado final debe sentirse como un producto SaaS real, no como una plantilla genérica ni como una demostración de inteligencia artificial.
````
