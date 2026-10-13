# Prompt maestro: plataforma SaaS de edición de video con IA

**Categoría:** [Video y presentaciones](README.md) · **Tecnologías:** Next.js, NestJS, PostgreSQL, Redis, S3, FFmpeg, OpenAI

Plataforma profesional de edición de video con IA para la nube: colaboración, almacenamiento S3, colas y planes con créditos.

> **Antes de usarlo, reemplaza:** `[TU_CONTRASEÑA_POSTGRES]`, `[TU_USUARIO_POSTGRES]`

## Prompt

```text
PROMPT MAESTRO: PLATAFORMA WEB PROFESIONAL DE EDICIÓN DE VIDEO CON INTELIGENCIA ARTIFICIAL

Actúa como un equipo senior compuesto por:
- Arquitecto de software especializado en plataformas multimedia.
- Ingeniero full stack experto en TypeScript.
- Ingeniero de video especializado en FFmpeg, códecs, renderizado y procesamiento audiovisual.
- Diseñador UX/UI especializado en editores creativos.
- Ingeniero de inteligencia artificial especializado en la API de OpenAI.
- Especialista en aplicaciones colaborativas en tiempo real.
- Ingeniero DevOps especializado en procesamiento distribuido y almacenamiento de archivos.
- Especialista en seguridad, privacidad y escalabilidad.
- Product Manager de productos SaaS para creadores de contenido.
Tu misión es diseñar y desarrollar desde cero una plataforma web robusta de edición de video llamada provisionalmente:

VIRTUALAB Video AI

La aplicación debe permitir editar videos directamente desde el navegador mediante una línea de tiempo profesional, herramientas manuales y un asistente de inteligencia artificial capaz de ejecutar acciones reales dentro del editor.
La plataforma debe inspirarse funcionalmente en editores como Clipchamp, CapCut Online, VEED, InVideo AI, Flixier, Kapwing, FlexClip y WeVideo, pero debe tener identidad visual, arquitectura, código, componentes y experiencia de usuario propios.
No copies código, textos, marcas, iconos exclusivos, diseños registrados ni interfaces exactas de las plataformas mencionadas.

1. OBJETIVO DEL PRODUCTO

Construye una plataforma web SaaS que permita a usuarios principiantes, docentes, estudiantes, empresas, equipos de marketing y creadores de contenido:
  1. Subir videos, imágenes y audios.
  2. Grabar pantalla, cámara, micrófono o pantalla y cámara simultáneamente.
  3. Editar contenido mediante una línea de tiempo multicapa.
  4. Crear videos desde plantillas.
  5. Generar subtítulos automáticos.
  6. Editar un video modificando su transcripción.
  7. Eliminar silencios, pausas y muletillas.
  8. Generar narraciones mediante inteligencia artificial.
  9. Convertir textos, artículos o guiones en proyectos de video.
  10. Detectar automáticamente momentos destacados.
  11. Crear versiones para YouTube, TikTok, Instagram, Facebook y LinkedIn.
  12. Trabajar colaborativamente en tiempo real.
  13. Exportar y renderizar los proyectos en la nube.
  14. Controlar el editor mediante órdenes naturales escritas o habladas.
  15. Mantener historial de versiones, deshacer cambios y recuperar proyectos.
La experiencia debe combinar dos formas de edición:
- Modo manual: el usuario manipula directamente clips, pistas, textos, efectos
  y transiciones.
- Modo asistido por IA: el usuario escribe instrucciones como “elimina los
  silencios mayores a dos segundos” y el sistema ejecuta la acción de manera controlada.

2. PRINCIPIOS FUNDAMENTALES

La plataforma debe cumplir estos principios:
- No destructiva: los archivos originales nunca se modifican.
- Reversible: todas las acciones deben poder deshacerse.
- Rápida: usar proxies, miniaturas, formas de onda y renderizado en segundo plano.
- Segura: la API de OpenAI nunca debe exponerse en el navegador.
- Modular: cada módulo debe poder sustituirse o ampliarse.
- Escalable: separar la aplicación web de los trabajadores de procesamiento.
- Colaborativa: soportar presencia, comentarios y edición concurrente.
- Accesible: navegación con teclado, contraste adecuado y subtítulos.
- Responsive: escritorio como experiencia principal y adaptación a tablet.
- Tolerante a fallos: los proyectos deben recuperarse tras una interrupción.
- Transparente: antes de una operación grande, la IA debe explicar qué modificará.
- Orientada a producción: no crear solamente una demostración visual.

3. STACK TECNOLÓGICO

Utiliza versiones estables y compatibles de las siguientes tecnologías.

Frontend

- Next.js.
- React.
- TypeScript con modo estricto.
- Tailwind CSS.
- Componentes accesibles basados en shadcn/ui o Radix UI.
- Zustand o Redux Toolkit para el estado local del editor.
- TanStack Query para el estado remoto.
- Canvas o WebGL para la previsualización.
- Web Audio API para audio y formas de onda.
- WebCodecs cuando esté disponible.
- Service Worker para recuperación, caché y cargas resilientes.
- WebSocket para actualizaciones en tiempo real.

Backend

- Node.js con TypeScript.
- NestJS o una arquitectura equivalente modular.
- API REST para operaciones normales.
- WebSocket para colaboración y estado en vivo.
- PostgreSQL como base de datos principal.
- Prisma como ORM.
- Redis para caché, bloqueos, presencia y colas.
- BullMQ para trabajos asíncronos.
- FFmpeg y FFprobe para análisis, transcodificación y renderizado.
- Almacenamiento compatible con S3.
- URLs firmadas para cargas y descargas.
- Contenedores Docker.
- Nginx o un proxy equivalente.

Inteligencia artificial

- OpenAI Responses API.
- Function calling para ejecutar acciones del editor.
- Structured Outputs con JSON Schema.
- API de transcripción para generar texto y marcas temporales.
- API de texto a voz para narraciones.
- Modelos con entrada visual para analizar fotogramas.
- API de imágenes para crear fondos, ilustraciones y miniaturas.
- API de video como módulo opcional para generar clips breves.
- Moderación de instrucciones y contenidos cuando corresponda.

Infraestructura

Diseña inicialmente un monolito modular con trabajadores separados, pero deja preparada la arquitectura para evolucionar a servicios independientes.
Servicios mínimos:
  1. Aplicación web.
  2. API principal.
  3. Worker de procesamiento multimedia.
  4. Worker de inteligencia artificial.
  5. Worker de renderizado.
  6. PostgreSQL.
  7. Redis.
  8. Almacenamiento de objetos.
  9. Servicio de eventos en tiempo real.

4. EXPERIENCIA VISUAL

Diseña una interfaz original, profesional, moderna y limpia.
No debe parecer una página genérica creada por inteligencia artificial.

Estilo visual

- Tema oscuro como opción predeterminada del editor.
- Tema claro disponible.
- Fondo oscuro neutro.
- Paneles bien delimitados.
- Tipografía clara y profesional.
- Iconos consistentes.
- Animaciones breves y funcionales.
- Densidad visual controlada.
- Tooltips en todas las herramientas importantes.
- Estados de carga tipo skeleton.
- Indicadores claros de guardado, sincronización y renderizado.

Distribución principal

Barra superior

Debe contener:
- Logo.
- Nombre editable del proyecto.
- Estado de guardado.
- Botones deshacer y rehacer.
- Selector de relación de aspecto.
- Selector de calidad de previsualización.
- Estado de colaboración.
- Botón compartir.
- Botón exportar.
- Menú de usuario.

Barra lateral izquierda

Pestañas:
- Multimedia.
- Grabar.
- Plantillas.
- Texto.
- Subtítulos.
- Audio.
- Música.
- Elementos.
- Transiciones.
- Efectos.
- Marca.
- Biblioteca de recursos.
- Inteligencia artificial.

Área central

Debe incluir:
- Reproductor de video.
- Controles de reproducción.
- Timecode.
- Zoom del lienzo.
- Guías inteligentes.
- Márgenes seguros.
- Herramientas de selección, recorte y transformación.
- Vista de calidad baja, media o completa.
- Selector de fondo del lienzo.

Panel derecho

Debe cambiar según el elemento seleccionado y mostrar:
- Posición.
- Escala.
- Rotación.
- Opacidad.
- Recorte.
- Máscara.
- Bordes.
- Sombras.
- Corrección de color.
- Velocidad.
- Volumen.
- Animaciones.
- Fotogramas clave.
- Efectos.
- Propiedades de subtítulos.
- Propiedades de transición.

Zona inferior

Línea de tiempo multicapa con:
- Regla temporal.
- Cabezal de reproducción.
- Pistas de video.
- Pistas de audio.
- Pistas de texto.
- Pistas de subtítulos.
- Pistas de elementos.
- Miniaturas de clips.
- Formas de onda.
- Bloqueo de pista.
- Ocultar pista.
- Silenciar pista.
- Solo de audio.
- Ajuste magnético.
- Agrupación.
- Selección múltiple.
- Zoom.
- Marcadores.
- Regiones.
- Comentarios asociados a un tiempo.

5. PANEL DE PROYECTOS

Construye un dashboard completo con:
- Crear proyecto vacío.
- Crear desde plantilla.
- Crear video con IA.
- Importar proyecto.
- Proyectos recientes.
- Carpetas.
- Favoritos.
- Compartidos conmigo.
- Papelera.
- Plantillas personales.
- Kit de marca.
- Espacios de trabajo.
- Papelera con recuperación temporal.
- Búsqueda por nombre, etiqueta, propietario o fecha.
- Ordenamiento y filtros.
- Vista en cuadrícula y lista.
- Miniatura automática de cada proyecto.
- Estado de procesamiento.
- Fecha de modificación.
- Duración.
- Relación de aspecto.
- Propietario.
- Colaboradores.
Implementa autosave y recuperación automática.

6. CREACIÓN DE PROYECTOS

Permite crear proyectos en:
- 16:9 para YouTube y presentaciones.
- 9:16 para TikTok, Reels y Shorts.
- 1:1 para publicaciones cuadradas.
- 4:5 para publicaciones verticales.
- 21:9 para contenido cinematográfico.
- Resolución personalizada.
Configuraciones:
- Resolución.
- Cuadros por segundo.
- Relación de aspecto.
- Color de fondo.
- Duración inicial.
- Frecuencia de muestreo de audio.
- Perfil de exportación.
- Espacio de color.
- Nombre del proyecto.

7. IMPORTACIÓN Y GESTIÓN MULTIMEDIA

Permite importar:
- MP4.
- MOV.
- WebM.
- AVI cuando pueda convertirse.
- MKV cuando pueda convertirse.
- MP3.
- WAV.
- AAC.
- M4A.
- PNG.
- JPG.
- JPEG.
- WebP.
- GIF.
- SVG seguro.
- Archivos de subtítulos SRT y VTT.
Formas de importación:
- Arrastrar y soltar.
- Selector de archivos.
- URL directa permitida.
- Google Drive u otros proveedores mediante módulos opcionales.
- Grabación directa.
- Biblioteca de recursos.
- Generación con IA.
Después de subir un archivo:
  1. Validar formato real, extensión, MIME y tamaño.
  2. Analizarlo con FFprobe.
  3. Extraer metadatos.
  4. Crear un proxy de edición.
  5. Generar miniaturas.
  6. Generar forma de onda.
  7. Extraer fotogramas representativos.
  8. Guardar el original.
  9. Registrar el estado de procesamiento.
  10. Notificar al frontend mediante WebSocket.
Las cargas deben ser reanudables y dividirse en partes para archivos grandes.

8. MODELO DE LA LÍNEA DE TIEMPO

La línea de tiempo debe ser no destructiva.
No uses números flotantes imprecisos para representar internamente el tiempo. Usa microsegundos, ticks enteros o una representación basada en fotogramas y frecuencia racional.
Entidades principales:

Project

- id
- workspaceId
- ownerId
- name
- description
- width
- height
- frameRateNumerator
- frameRateDenominator
- duration
- backgroundColor
- status
- createdAt
- updatedAt
- version

Asset

- id
- projectId
- type
- originalUrl
- proxyUrl
- thumbnailUrl
- waveformUrl
- mimeType
- codec
- width
- height
- duration
- frameRate
- fileSize
- processingStatus
- metadata

Track

- id
- projectId
- type
- order
- name
- locked
- hidden
- muted
- solo

Clip

- id
- trackId
- assetId
- start
- duration
- sourceIn
- sourceOut
- speed
- volume
- opacity
- zIndex
- transform
- crop
- effects
- transitions
- keyframes
- metadata

CaptionSegment

- id
- projectId
- trackId
- start
- end
- text
- speaker
- confidence
- words
- style

Marker

- id
- projectId
- time
- label
- color
- description

VersionSnapshot

- id
- projectId
- sequence
- createdBy
- operations
- snapshot
- createdAt
Toda operación debe registrarse como un comando reversible.
Ejemplo conceptual:
{
"operationId": "op_123",
"projectId": "project_123",
"type": "TRIM_CLIP",
"payload": {
"clipId": "clip_15",
"newSourceOut": 12400000
},
"inverse": {
"type": "TRIM_CLIP",
"payload": {
"clipId": "clip_15",
"newSourceOut": 18900000
}
}
}

9. HERRAMIENTAS DE EDICIÓN MANUAL

Implementa de manera funcional:
- Seleccionar.
- Cortar.
- Dividir.
- Recortar inicio y final.
- Eliminar.
- Duplicar.
- Copiar y pegar.
- Mover clips.
- Edición ripple.
- Cierre automático de espacios.
- Ajuste magnético.
- Agrupar y desagrupar.
- Bloquear clips.
- Congelar fotograma.
- Reversa.
- Control de velocidad.
- Curvas de velocidad.
- Zoom y panorámica.
- Recorte.
- Rotación.
- Volteo.
- Opacidad.
- Mezcla.
- Máscaras.
- Chroma key.
- Fondo desenfocado.
- Picture-in-picture.
- Superposiciones.
- Fotogramas clave.
- Transiciones.
- Fades.
- Estabilización como tarea de procesamiento.
- Corrección básica de color.
- Brillo.
- Contraste.
- Saturación.
- Temperatura.
- Tinte.
- Sombras.
- Luces.
- LUT como módulo avanzado.
- Efectos visuales.
- Filtros.
- Animaciones de entrada y salida.
- Títulos.
- Lower thirds.
- Stickers.
- Formas.
- Barras de progreso.
- Indicadores visuales.
- Marcos.
- Fondos.
Incluye atajos de teclado configurables.

10. EDICIÓN DE AUDIO

Implementa:
- Separar audio del video.
- Silenciar clip.
- Controlar volumen.
- Normalización.
- Fade de entrada y salida.
- Reducción de ruido.
- Ecualización básica.
- Compresor.
- Limitador.
- Eliminación de zumbidos.
- Mejora de voz.
- Detección de silencios.
- Eliminación automática de silencios.
- Ducking automático de música durante la voz.
- Sincronización de audio y video.
- Formas de onda.
- Grabación de narración.
- Reemplazo de música.
- Biblioteca musical.
- Efectos de sonido.
- Medidores de nivel.
- Avisos de clipping.

11. SUBTÍTULOS Y TRANSCRIPCIÓN

Construye un sistema completo para:
  1. Extraer el audio.
  2. Dividir audios grandes en fragmentos sin cortar frases cuando sea posible.
  3. Transcribirlos.
  4. Guardar marcas temporales.
  5. Identificar hablantes cuando el modelo utilizado lo permita.
  6. Generar segmentos.
  7. Mostrar el texto junto a la línea de tiempo.
  8. Editar el texto.
  9. Sincronizar los cambios.
  10. Exportar SRT, VTT y TXT.
  11. Incrustar subtítulos durante el renderizado.
Funciones:
- Subtítulos palabra por palabra.
- Resaltado de la palabra hablada.
- Subtítulos por frase.
- Estilos animados.
- Plantillas de subtítulos.
- Fuentes, color, borde y sombra.
- Posición segura.
- Traducción.
- Corrección ortográfica.
- Glosario personalizado.
- Identificación de términos técnicos.
- División y combinación de segmentos.
- Ajuste manual de tiempos.

Edición basada en texto

Cuando el usuario elimine palabras o frases de la transcripción:
- Calcular el intervalo temporal asociado.
- Crear una operación de corte.
- Mostrar una previsualización.
- Aplicar edición ripple cuando corresponda.
- Permitir restaurar el contenido.
- Mantener sincronizados texto y video.
Permite buscar una palabra dentro de la transcripción y saltar al momento exacto.

12. GRABADOR INTEGRADO

Incluye:
- Grabación de pantalla.
- Grabación de ventana.
- Grabación de pestaña.
- Grabación de cámara.
- Grabación de micrófono.
- Pantalla y cámara simultáneas.
- Selección de dispositivo.
- Cuenta regresiva.
- Pausa y reanudación.
- Indicador de nivel de micrófono.
- Vista previa.
- Teleprompter.
- Fondo virtual.
- Eliminación de fondo.
- Diseño picture-in-picture.
- Guardado automático por fragmentos para evitar pérdidas.

13. SISTEMA DE PLANTILLAS

Crea una biblioteca de plantillas originales para:
- YouTube.
- Shorts.
- TikTok.
- Instagram Reels.
- Publicidad.
- Videos educativos.
- Presentaciones.
- Tutoriales.
- Podcasts.
- Noticias.
- Promociones.
- Productos.
- Testimonios.
- Cumpleaños.
- Eventos.
- Intros.
- Outros.
- Memes.
- Videos corporativos.
Las plantillas deben usar variables reemplazables:
- Texto.
- Logo.
- Colores.
- Fuente.
- Imagen.
- Video.
- Música.
- Duración.
- Relación de aspecto.
Incluye buscador, categorías, favoritos y vista previa.

14. KIT DE MARCA

Permite guardar por espacio de trabajo:
- Logos.
- Isotipos.
- Paleta de colores.
- Tipografías.
- Estilos de subtítulos.
- Intros.
- Outros.
- Lower thirds.
- Música.
- Voz preferida.
- Plantillas.
- Reglas de uso.
La inteligencia artificial debe poder consultar el kit de marca y aplicarlo a un proyecto.

15. ASISTENTE DE IA DENTRO DEL EDITOR

Añade un panel lateral llamado:

Asistente de edición con IA

Debe incluir:
- Historial de conversación.
- Caja de texto.
- Entrada por voz.
- Sugerencias rápidas.
- Adjuntar archivos o referencias.
- Selector de alcance:
  o Proyecto completo.
  o Clips seleccionados.
  o Intervalo seleccionado.
  o Pista activa.
- Vista previa de acciones.
- Botón aplicar.
- Botón cancelar.
- Botón deshacer.
- Estado de cada tarea.
- Consumo aproximado de créditos.
- Explicación de cambios.
Ejemplos de instrucciones aceptadas:
- “Elimina todos los silencios mayores de 1,5 segundos”.
- “Quita las muletillas sin cortar palabras importantes”.
- “Crea un video vertical de 45 segundos con los mejores momentos”.
- “Genera subtítulos dinámicos en español”.
- “Traduce los subtítulos al inglés”.
- “Coloca música suave y reduce su volumen mientras hablo”.
- “Busca los cinco momentos más interesantes”.
- “Agrega un título al inicio que diga Introducción a la inteligencia artificial”.
- “Aplica mi kit de marca”.
- “Convierte este video de YouTube en tres Shorts”.
- “Haz que el ritmo sea más rápido”.
- “Recorta las partes repetidas”.
- “Crea una introducción de cinco segundos”.
- “Genera una narración formal”.
- “Cambia el proyecto a formato 9:16”.
- “Centra automáticamente al hablante”.
- “Agrega imágenes de apoyo relacionadas con el tema”.
- “Resume esta clase en un video de dos minutos”.
- “Oculta un rostro entre los segundos 15 y 22”.
- “Silencia una palabra específica”.
- “Genera una miniatura para este video”.
- “Prepara el proyecto para YouTube”.
- “Crea título, descripción, capítulos y etiquetas”.

16. ARQUITECTURA DE LAS ACCIONES DE IA

La IA no debe modificar directamente el DOM ni alterar libremente el estado del editor.
Flujo obligatorio:
  1. El usuario escribe una instrucción.
  2. El frontend envía:
  o Instrucción.
  o ID del proyecto.
  o Estado resumido de la línea de tiempo.
  o Elementos seleccionados.
  o Transcripción relevante.
  o Kit de marca.
  o Preferencias.
  3. El backend consulta la API de OpenAI.
  4. El modelo devuelve llamadas a funciones.
  5. El backend valida:
  o Autorización.
  o Existencia de elementos.
  o Tipos.
  o Límites.
  o Duraciones.
  o Costos.
  o Riesgos.
  6. Se construye un plan de operaciones.
  7. Se muestra una previsualización.
  8. El usuario confirma cuando la acción sea destructiva o costosa.
  9. El backend ejecuta las operaciones.
  10. Se guarda un snapshot.
  11. El editor recibe los cambios.
  12. La acción puede deshacerse.
Nunca permitas que una respuesta textual de la IA se ejecute como código.

17. HERRAMIENTAS EXPUESTAS A OPENAI

Implementa funciones con JSON Schema estricto.

Funciones de consulta

- get_project_summary
- get_timeline_state
- get_selected_clips
- get_asset_metadata
- get_transcript_range
- get_brand_kit
- get_available_templates
- get_render_profiles
- estimate_operation_cost

Funciones de edición

- split_clip
- trim_clip
- delete_clip
- delete_time_range
- move_clip
- duplicate_clip
- change_clip_speed
- reverse_clip
- freeze_frame
- crop_clip
- resize_clip
- rotate_clip
- set_clip_opacity
- set_clip_volume
- add_fade
- add_transition
- add_effect
- remove_effect
- add_keyframe
- group_clips
- ungroup_clips
- create_track
- mute_track
- lock_track

Funciones de texto

- add_text_layer
- update_text_layer
- style_text_layer
- animate_text_layer
- add_lower_third
- apply_text_template

Funciones de subtítulos

- transcribe_asset
- generate_captions
- update_caption_segment
- translate_captions
- style_captions
- export_captions
- delete_words_from_transcript

Funciones de audio

- detach_audio
- clean_audio
- normalize_audio
- remove_silences
- remove_filler_words
- apply_audio_ducking
- add_music
- add_sound_effect
- generate_voiceover

Funciones creativas

- generate_script
- generate_storyboard
- find_highlights
- create_highlight_reel
- create_social_variants
- suggest_broll
- insert_broll
- generate_image_asset
- generate_video_asset
- generate_thumbnail
- apply_brand_kit
- apply_template

Funciones de proyecto

- change_aspect_ratio
- create_project_version
- restore_project_version
- render_project
- cancel_render
- publish_video

18. EJEMPLO DE FUNCIÓN PARA RECORTAR UN CLIP

{
"type": "function",
"name": "trim_clip",
"description": "Modifica los puntos de entrada o salida de un clip existente sin alterar el archivo original.",
"strict": true,
"parameters": {
"type": "object",
"properties": {
"projectId": {
"type": "string"
},
"clipId": {
"type": "string"
},
"sourceInMicroseconds": {
"type": ["integer", "null"],
"minimum": 0
},
"sourceOutMicroseconds": {
"type": ["integer", "null"],
"minimum": 0
},
"ripple": {
"type": "boolean"
},
"reason": {
"type": "string"
}
},
"required": [
"projectId",
"clipId",
"sourceInMicroseconds",
"sourceOutMicroseconds",
"ripple",
"reason"
],
"additionalProperties": false
}
}

19. EJEMPLO DE FUNCIÓN PARA ELIMINAR SILENCIOS

{
"type": "function",
"name": "remove_silences",
"description": "Detecta y elimina silencios de los clips indicados usando parámetros configurables.",
"strict": true,
"parameters": {
"type": "object",
"properties": {
"projectId": {
"type": "string"
},
"clipIds": {
"type": "array",
"items": {
"type": "string"
}
},
"minimumSilenceMilliseconds": {
"type": "integer",
"minimum": 200,
"maximum": 10000
},
"thresholdDb": {
"type": "number",
"minimum": -80,
"maximum": -10
},
"preservePaddingMilliseconds": {
"type": "integer",
"minimum": 0,
"maximum": 2000
},
"ripple": {
"type": "boolean"
},
"previewOnly": {
"type": "boolean"
}
},
"required": [
"projectId",
"clipIds",
"minimumSilenceMilliseconds",
"thresholdDb",
"preservePaddingMilliseconds",
"ripple",
"previewOnly"
],
"additionalProperties": false
}
}

20. PLAN ESTRUCTURADO DE OPERACIONES

Antes de aplicar acciones múltiples, la IA debe devolver una estructura semejante a:
{
"summary": "Se eliminarán 12 silencios y se reducirá la duración en aproximadamente 38 segundos.",
"scope": "selected_clips",
"estimatedDurationBefore": 420000000,
"estimatedDurationAfter": 382000000,
"estimatedCostCredits": 4,
"requiresConfirmation": true,
"warnings": [],
"operations": [
{
"tool": "remove_silences",
"arguments": {
"projectId": "project_123",
"clipIds": ["clip_10", "clip_11"],
"minimumSilenceMilliseconds": 1500,
"thresholdDb": -38,
"preservePaddingMilliseconds": 150,
"ripple": true,
"previewOnly": false
}
}
]
}
Cada operación debe tener:
- ID único.
- Estado.
- Progreso.
- Resultado.
- Error.
- Operación inversa.
- Usuario que la inició.
- Fecha.
- Costo.
- Modelo utilizado.
- Confirmación, cuando corresponda.

21. CONTEXTO MULTIMODAL PARA LA IA

No envíes videos largos completos de forma indiscriminada.
Crea un pipeline que genere:
- Metadatos.
- Transcripción.
- Resumen temporal.
- Fotogramas clave.
- Detección de escenas.
- Miniaturas.
- Información de hablantes.
- Niveles de audio.
- Objetos o temas detectados.
- Marcadores del usuario.
Para analizar un video:
  1. Extraer un conjunto representativo de fotogramas.
  2. Combinarlo con la transcripción y marcas temporales.
  3. Dividir el contenido en escenas.
  4. Crear resúmenes por escena.
  5. Generar un índice consultable.
  6. Enviar solamente el contexto relevante para cada petición.

22. FUNCIONES DE IA PRIORITARIAS

A. Video desde texto

El usuario proporciona:
- Tema.
- Objetivo.
- Audiencia.
- Duración.
- Tono.
- Formato.
- Plataforma.
- Idioma.
- Kit de marca.
La IA genera:
  1. Idea.
  2. Estructura.
  3. Guion.
  4. Escenas.
  5. Texto en pantalla.
  6. Narración.
  7. Sugerencias visuales.
  8. Música sugerida.
  9. Subtítulos.
  10. Primer borrador editable en la línea de tiempo.

B. Clips destacados

- Analizar transcripción, energía de voz y cambios visuales.
- Identificar frases fuertes.
- Detectar preguntas, respuestas, conclusiones y momentos emocionales.
- Evitar cortes en mitad de una oración.
- Generar clips con inicio atractivo y cierre comprensible.
- Crear versiones 9:16, 1:1 y 4:5.

C. Eliminación de silencios y muletillas

- Detectar silencios.
- Identificar “eh”, “mmm”, “este”, “pues” y otras muletillas.
- No eliminar palabras cuando pueda afectar el significado.
- Conservar respiraciones naturales.
- Permitir elegir intensidad: suave, equilibrada o agresiva.
- Mostrar las regiones antes de aplicar.

D. Reencuadre inteligente

- Detectar rostro, hablante y objeto principal.
- Crear keyframes de posición.
- Mantener el sujeto dentro del área segura.
- Adaptar horizontal a vertical.
- Permitir corrección manual.

E. B-roll inteligente

- Interpretar la transcripción.
- Detectar conceptos que necesitan apoyo visual.
- Buscar primero en recursos del usuario.
- Consultar después la biblioteca autorizada.
- Generar recursos únicamente cuando sea necesario.
- Registrar procedencia y licencia.
- Insertar recursos como propuesta, no de forma irreversible.

F. Traducción y doblaje

- Traducir subtítulos manteniendo intención.
- Conservar términos técnicos mediante glosarios.
- Generar voz en el idioma seleccionado.
- Ajustar la duración del audio.
- Permitir mezcla con el audio original.
- Mostrar claramente cuando una voz sea generada por IA.

G. Contenido para redes

A partir de un proyecto terminado, generar:
- Título.
- Descripción.
- Resumen.
- Capítulos.
- Hashtags.
- Frases destacadas.
- Miniatura.
- Tres clips cortos.
- Copias para distintas redes.
- Variantes de relación de aspecto.

23. COLABORACIÓN EN TIEMPO REAL

Implementa:
- Espacios de trabajo.
- Propietario.
- Administrador.
- Editor.
- Comentarista.
- Lector.
- Presencia en tiempo real.
- Cursores o selecciones visibles.
- Comentarios asociados a un timecode.
- Respuestas a comentarios.
- Menciones.
- Resolución de comentarios.
- Historial de actividad.
- Versiones nombradas.
- Enlaces de revisión.
- Aprobación o solicitud de cambios.
- Bloqueo suave de elementos en edición.
- Resolución de conflictos.
- Notificaciones.
La colaboración no debe provocar pérdida de operaciones.
Usa un sistema de operaciones, CRDT o un modelo equivalente para sincronizar cambios.

24. MÓDULO EDUCATIVO

Incluye una modalidad opcional para instituciones educativas:
- Organización.
- Institución.
- Docentes.
- Estudiantes.
- Cursos.
- Grupos.
- Actividades.
- Fecha de entrega.
- Rúbrica.
- Proyectos individuales.
- Proyectos grupales.
- Retroalimentación por timecode.
- Biblioteca institucional.
- Plantillas del docente.
- Control de permisos.
- Exportación de calificaciones.
- Historial de participación.
- Modo seguro para menores.
- Límites de publicación.
- Elementos interactivos:
  o Preguntas.
  o Encuestas.
  o Pausas reflexivas.
  o Enlaces.
  o Recursos complementarios.

25. RENDERIZADO

El renderizado final debe ejecutarse en trabajadores de servidor.
Flujo:
  1. Crear snapshot inmutable del proyecto.
  2. Validar recursos.
  3. Resolver fuentes y efectos.
  4. Descargar recursos necesarios al worker.
  5. Construir un grafo de renderizado.
  6. Ejecutar FFmpeg.
  7. Publicar progreso.
  8. Generar archivo final.
  9. Crear miniatura.
  10. Guardar metadatos.
  11. Notificar al usuario.
  12. Limpiar archivos temporales.
Perfiles:
- 720p.
- 1080p.
- 1440p.
- 4K.
- MP4 H.264.
- MP4 H.265 como opción.
- WebM.
- GIF.
- Solo audio MP3 o WAV.
- Fotograma PNG o JPG.
- Transparencia cuando el formato y el pipeline lo permitan.
Opciones:
- Calidad.
- Bitrate.
- FPS.
- Resolución.
- Códec.
- Audio.
- Normalización.
- Subtítulos incrustados.
- Fondo transparente.
- Marca de agua según el plan.
- Nombre del archivo.
El usuario debe poder cerrar la aplicación mientras se procesa el renderizado y consultar posteriormente su estado.

26. OPTIMIZACIÓN DEL RENDIMIENTO

Implementa:
- Proxies de baja resolución para editar.
- Miniaturas generadas previamente.
- Forma de onda precalculada.
- Carga diferida.
- Virtualización de la línea de tiempo.
- Caché de frames.
- Web Workers.
- Procesamiento fuera del hilo principal.
- Debounce de operaciones.
- Actualizaciones optimistas con recuperación.
- Compresión de eventos.
- Paginación de recursos.
- CDN.
- Cargas multipartes.
- Renderizado en segundo plano.
- Reintentos con backoff.
- Trabajos idempotentes.
- Límites de concurrencia.
- Cancelación de tareas.
- Limpieza de archivos temporales.
La reproducción no debe volver a renderizar el proyecto completo después de cada cambio pequeño.

27. SEGURIDAD

Requisitos obligatorios:
- API keys únicamente en el servidor.
- Variables de entorno.
- Autenticación segura.
- Sesiones protegidas.
- Autorización por recurso.
- URLs firmadas.
- Límites de tamaño.
- Validación de MIME real.
- Sanitización de nombres.
- Protección contra path traversal.
- Protección CSRF cuando corresponda.
- Protección XSS.
- Content Security Policy.
- Rate limiting.
- Protección contra abuso de IA.
- Cuotas por usuario.
- Escaneo de archivos.
- Registro de auditoría.
- Secretos fuera del repositorio.
- Validación estricta de llamadas generadas por IA.
- Lista explícita de operaciones permitidas.
- Confirmación antes de borrar, publicar o consumir muchos créditos.
- Eliminación programada de archivos.
- Controles de privacidad.
- Exportación y eliminación de datos.
- Consentimiento para voces o rostros personalizados.
- Bloqueo de suplantaciones y usos no autorizados.
Nunca ejecutes comandos de shell construidos directamente desde texto generado por la IA.
Usa argumentos seguros y plantillas de FFmpeg controladas por el backend.

28. SISTEMA DE PLANES Y CRÉDITOS

Diseña planes configurables:

Gratuito

- Resolución limitada.
- Almacenamiento limitado.
- Créditos de IA limitados.
- Marca de agua opcional.
- Número limitado de proyectos.

Creador

- Exportación Full HD.
- Más almacenamiento.
- Más créditos.
- Kit de marca.
- Subtítulos.
- Plantillas premium.

Profesional

- 4K.
- Colaboración.
- Historial ampliado.
- Renderizado prioritario.
- Más recursos.
- Herramientas avanzadas de IA.

Educación o equipos

- Usuarios administrados.
- Clases o espacios.
- Permisos.
- Facturación centralizada.
- Colaboración.
- Analítica.
- Privacidad institucional.
Registra por operación:
- Tokens consumidos.
- Minutos transcritos.
- Minutos de voz generados.
- Segundos de video generado.
- Minutos renderizados.
- Almacenamiento.
- Ancho de banda.
- Créditos descontados.

29. BASE DE DATOS

Crea modelos y migraciones para:
- User.
- Account.
- Session.
- Workspace.
- WorkspaceMember.
- Subscription.
- CreditBalance.
- CreditTransaction.
- Project.
- ProjectMember.
- ProjectSnapshot.
- Asset.
- AssetProcessingJob.
- Track.
- Clip.
- CaptionTrack.
- CaptionSegment.
- Marker.
- Template.
- BrandKit.
- BrandAsset.
- Comment.
- CommentReply.
- Notification.
- AIConversation.
- AIMessage.
- AIToolCall.
- AIOperation.
- RenderJob.
- Export.
- AuditLog.
- Course.
- ClassGroup.
- Assignment.
- Submission.
Añade:
- Índices.
- Restricciones.
- Eliminación lógica cuando corresponda.
- Fechas de creación y modificación.
- Control de versiones.
- Relaciones explícitas.
- Estados mediante enums.
- Transacciones para operaciones sensibles.

30. API INTERNA

Organiza rutas semejantes a:
/api/auth
/api/users
/api/workspaces
/api/projects
/api/projects/:id/timeline
/api/projects/:id/assets
/api/projects/:id/transcript
/api/projects/:id/captions
/api/projects/:id/comments
/api/projects/:id/versions
/api/projects/:id/ai
/api/projects/:id/render
/api/templates
/api/brand-kits
/api/uploads
/api/recordings
/api/notifications
/api/billing
/api/education
Características:
- Validación con Zod o class-validator.
- Errores normalizados.
- IDs de correlación.
- Idempotency keys.
- Paginación.
- Filtros.
- Logs estructurados.
- OpenAPI.
- Control de versiones de API.

31. ESTADOS DE TRABAJO

Usa estados claros:

Asset

- uploaded
- validating
- analyzing
- proxying
- ready
- failed
- quarantined

Render

- queued
- preparing
- rendering
- uploading
- completed
- failed
- cancelled

Acción de IA

- requested
- planning
- awaiting_confirmation
- queued
- executing
- completed
- partially_completed
- failed
- cancelled
- reverted
La interfaz debe mostrar estos estados en tiempo real.

32. MANEJO DE ERRORES

Contempla:
- Archivo incompatible.
- Códec no admitido.
- Archivo corrupto.
- Carga interrumpida.
- Fallo de transcripción.
- Fallo de OpenAI.
- Rate limit.
- Créditos insuficientes.
- Worker desconectado.
- Render fallido.
- Recurso eliminado.
- Conflicto de edición.
- Falta de permisos.
- Proyecto demasiado grande.
- Tiempo de espera agotado.
Cada error debe ofrecer:
- Mensaje entendible.
- Código interno.
- Posible solución.
- Acción de reintento.
- Enlace a detalles técnicos cuando proceda.
- Registro para soporte.

33. OBSERVABILIDAD

Implementa:
- Logs JSON.
- Métricas.
- Trazas.
- Alertas.
- Monitoreo de colas.
- Duración de renderizados.
- Tasa de errores.
- Costos de IA.
- Uso de almacenamiento.
- Uso por plan.
- Latencia de transcripción.
- Latencia de herramientas.
- Operaciones deshechas.
- Fallos por códec.
- Auditoría de acciones administrativas.
No almacenes texto sensible completo en logs sin necesidad.

34. PRUEBAS

Incluye:
- Pruebas unitarias.
- Pruebas de integración.
- Pruebas end-to-end.
- Pruebas de permisos.
- Pruebas de funciones de IA.
- Pruebas de esquemas JSON.
- Pruebas de timeline.
- Pruebas de undo y redo.
- Pruebas de sincronización.
- Pruebas de exportación.
- Pruebas con archivos corruptos.
- Pruebas con videos verticales y horizontales.
- Pruebas con distintos FPS.
- Pruebas de accesibilidad.
- Pruebas de carga.
- Pruebas de recuperación tras fallos.
Casos críticos:
  1. Dos usuarios editando el mismo proyecto.
  2. Eliminar y restaurar una región.
  3. Aplicar 100 operaciones de IA.
  4. Cancelar un render.
  5. Perder conexión durante una carga.
  6. Recuperar un proyecto tras cerrar el navegador.
  7. Transcribir un archivo grande por fragmentos.
  8. Exportar subtítulos sincronizados.
  9. Adaptar 16:9 a 9:16.
  10. Deshacer una edición basada en transcripción.

35. DATOS DE DEMOSTRACIÓN

Genera datos iniciales:
- Usuario de demostración.
- Espacio de trabajo.
- Tres proyectos.
- Recursos audiovisuales libres o simulados.
- Plantillas.
- Kit de marca.
- Transcripción.
- Comentarios.
- Render terminado.
- Proyecto educativo.
- Conversación con el asistente de IA.
No dependas de URLs que puedan desaparecer. Documenta cómo reemplazar los recursos.

36. PÁGINAS DE LA APLICACIÓN

Construye:
- Landing page.
- Inicio de sesión.
- Registro.
- Recuperación de contraseña.
- Dashboard.
- Editor.
- Biblioteca de plantillas.
- Kit de marca.
- Espacios de trabajo.
- Invitaciones.
- Compartidos.
- Página de revisión.
- Exportaciones.
- Facturación.
- Configuración.
- Administración.
- Centro educativo.
- Ayuda.
- Política de privacidad.
- Términos.
- Página 404.
- Página de error.
La landing debe mostrar el producto real mediante capturas o componentes funcionales, no mediante promesas genéricas.

37. ENTREGA DEL PROYECTO

Entrega un repositorio organizado con:
/apps/web
/apps/api
/apps/media-worker
/apps/ai-worker
/apps/render-worker
/packages/ui
/packages/types
/packages/timeline
/packages/ffmpeg
/packages/openai
/packages/config
/packages/database
/packages/eslint-config
/packages/tsconfig
/infrastructure
/docs
Incluye:
- Código completo.
- README.
- Arquitectura.
- Diagrama de componentes.
- Diagrama de datos.
- Variables de entorno de ejemplo.
- Docker Compose.
- Migraciones.
- Seeds.
- Scripts de desarrollo.
- Scripts de producción.
- Documentación de API.
- Documentación de las funciones de OpenAI.
- Estrategia de despliegue.
- Pruebas.
- Instrucciones para instalar FFmpeg.
- Instrucciones para configurar almacenamiento S3.
- Instrucciones para configurar OpenAI.
- Explicación del sistema de créditos.

38. VARIABLES DE ENTORNO

Incluye un archivo .env.example parecido a:
NODE_ENV=development
APP_URL=http://localhost:3000
API_URL=http://localhost:4000
DATABASE_URL=postgresql://[TU_USUARIO_POSTGRES]:[TU_CONTRASEÑA_POSTGRES]@localhost:5432/video_ai
REDIS_URL=redis://localhost:6379
S3_ENDPOINT=http://localhost:9000
S3_REGION=us-east-1
S3_BUCKET=video-ai
S3_ACCESS_KEY=
S3_SECRET_KEY=
OPENAI_API_KEY=
AUTH_SECRET=
ENCRYPTION_KEY=
MAX_UPLOAD_SIZE_MB=5120
FREE_PLAN_STORAGE_GB=5
FREE_PLAN_AI_CREDITS=50
FFMPEG_PATH=/usr/bin/ffmpeg
FFPROBE_PATH=/usr/bin/ffprobe
Nunca incluyas credenciales reales.

39. FASES DE DESARROLLO

Fase 1: MVP funcional

Debe incluir:
- Autenticación.
- Dashboard.
- Creación de proyecto.
- Carga multimedia.
- Línea de tiempo.
- Cortar, dividir, mover y recortar.
- Texto.
- Audio básico.
- Subtítulos automáticos.
- Edición mediante transcripción.
- Asistente de IA con al menos diez herramientas reales.
- Exportación 720p y 1080p.
- Autosave.
- Undo y redo.
- Docker Compose.
- Pruebas esenciales.

Fase 2

- Plantillas.
- Kit de marca.
- Colaboración.
- Comentarios.
- Grabación.
- Traducción.
- Voz generada.
- Clips destacados.
- Reencuadre.
- Versiones sociales.

Fase 3

- 4K.
- Educación.
- Elementos interactivos.
- Generación de imágenes y clips.
- Publicación.
- Facturación.
- Analítica.
- Renderizado distribuido.
- Aplicaciones móviles o PWA avanzada.
No simules que las fases futuras están terminadas. Marca claramente qué está implementado y qué está preparado arquitectónicamente.

40. CRITERIOS DE ACEPTACIÓN DEL MVP

El MVP se considera funcional cuando un usuario puede:
  1. Registrarse.
  2. Crear un proyecto.
  3. Subir un video.
  4. Ver su miniatura y forma de onda.
  5. Arrastrarlo a la línea de tiempo.
  6. Cortarlo.
  7. Dividirlo.
  8. Añadir texto.
  9. Modificar volumen.
  10. Generar subtítulos.
  11. Eliminar una frase desde la transcripción.
  12. Escribir “elimina silencios mayores a dos segundos”.
  13. Revisar el plan generado por la IA.
  14. Aplicar la operación.
  15. Deshacerla.
  16. Guardar automáticamente.
  17. Exportar el resultado.
  18. Ver el progreso del renderizado.
  19. Descargar el archivo final.
  20. Recuperar el proyecto después de cerrar la sesión.

41. REGLAS PARA GENERAR EL CÓDIGO

- No entregues únicamente maquetas.
- No uses botones sin funcionalidad.
- No dejes TODO en funciones esenciales.
- No inventes APIs.
- No expongas secretos.
- No uses datos falsos en producción.
- No generes comandos FFmpeg inseguros.
- No mezcles lógica multimedia compleja dentro de componentes React.
- No guardes archivos grandes en PostgreSQL.
- No guardes toda la línea de tiempo como un único JSON sin estrategia de versiones.
- No bloquees solicitudes HTTP mientras se renderiza.
- No ejecutes trabajos pesados en el servidor web.
- No permitas acciones de IA sin validación.
- No apliques operaciones destructivas sin posibilidad de deshacer.
- No uses nombres comerciales ajenos en la interfaz final.
Prioriza código mantenible, tipado, documentado y verificable.
Cuando una función avanzada no pueda implementarse completamente en una sola entrega:
  1. Implementa una versión mínima real.
  2. Diseña la interfaz correcta.
  3. Documenta la limitación.
  4. Evita simular resultados inexistentes.
  5. Deja pruebas y puntos de extensión.

42. PRIMERA ENTREGA SOLICITADA

Comienza produciendo:
  1. Resumen de arquitectura.
  2. Decisiones técnicas y justificación.
  3. Estructura del repositorio.
  4. Modelo de datos.
  5. Flujo completo de carga y procesamiento.
  6. Diseño del motor de línea de tiempo.
  7. Diseño de integración con OpenAI.
  8. Definición inicial de las funciones de IA.
  9. Mockup funcional del editor.
  10. Configuración Docker.
  11. MVP ejecutable localmente.
  12. README con instrucciones exactas.
Después, desarrolla el proyecto módulo por módulo.
Antes de escribir cada módulo:
- Explica brevemente su responsabilidad.
- Define sus interfaces.
- Implementa el código.
- Incluye manejo de errores.
- Incluye pruebas.
- Indica cómo verificarlo.
El resultado final debe ser una aplicación real, funcional, extensible, segura y preparada para crecer como producto SaaS.
```
