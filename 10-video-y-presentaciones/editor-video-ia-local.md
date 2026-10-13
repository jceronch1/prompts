# Prompt maestro: editor de video con IA (local)

**Categoría:** [Video y presentaciones](README.md) · **Tecnologías:** Next.js, NestJS/Fastify, PostgreSQL 17, Prisma, pg-boss, FFmpeg, OpenAI

Editor de video web con IA que se ejecuta en Windows sin Docker: línea de tiempo, subtítulos, edición por transcripción y render con FFmpeg.

> **Antes de usarlo, reemplaza:** `[TU_CONTRASEÑA_POSTGRES]`, `[TU_USUARIO_POSTGRES]`

## Prompt

```text
PROMPT MAESTRO: EDITOR DE VIDEO WEB CON IA EJECUTABLE LOCALMENTE Y

Actúa como un equipo senior compuesto por:
- Arquitecto de software especializado en aplicaciones multimedia.
- Ingeniero full stack experto en TypeScript.
- Ingeniero de video especializado en FFmpeg, FFprobe, códecs y procesamiento audiovisual.
- Diseñador UX/UI especializado en herramientas creativas.
- Ingeniero de inteligencia artificial especializado en la API de OpenAI.
- Especialista en aplicaciones colaborativas en tiempo real.
- Ingeniero de bases de datos especializado en PostgreSQL 17.
- Especialista en seguridad, rendimiento y arquitectura local.
- Product Manager de productos SaaS para creadores de contenido.
Tu misión es diseñar y desarrollar desde cero una plataforma web robusta de edición de video llamada provisionalmente:

VIRTUALAB Video AI

La aplicación debe ejecutarse directamente en un computador local con Windows, sin utilizar Docker, máquinas virtuales ni contenedores.
En el equipo local ya se encuentra instalado:
- PostgreSQL 17.
- Usuario de PostgreSQL: [TU_USUARIO_POSTGRES].
- Contraseña de PostgreSQL: [TU_CONTRASEÑA_POSTGRES].
- Host: localhost.
- Puerto: 5432.
La aplicación debe poder instalarse, configurarse y ejecutarse utilizando comandos normales de PowerShell, CMD o terminal integrada de Visual Studio Code.

1. OBJETIVO PRINCIPAL

Construye una plataforma web profesional que permita:
  1. Subir videos, audios e imágenes desde el computador.
  2. Organizar archivos multimedia en una biblioteca.
  3. Editar videos mediante una línea de tiempo multicapa.
  4. Cortar, dividir, mover, duplicar y recortar clips.
  5. Añadir textos, títulos, subtítulos, imágenes, audio y transiciones.
  6. Generar subtítulos automáticos mediante inteligencia artificial.
  7. Editar un video modificando directamente su transcripción.
  8. Eliminar silencios, pausas y muletillas.
  9. Crear narraciones con inteligencia artificial.
  10. Convertir texto o guiones en proyectos de video.
  11. Detectar automáticamente momentos destacados.
  12. Crear versiones para YouTube, TikTok, Instagram, Facebook y LinkedIn.
  13. Controlar el editor mediante órdenes en lenguaje natural.
  14. Renderizar videos localmente con FFmpeg.
  15. Guardar automáticamente todos los cambios en PostgreSQL.
  16. Recuperar proyectos después de cerrar o reiniciar la aplicación.
  17. Deshacer y rehacer operaciones.
  18. Mantener un historial de versiones del proyecto.
La aplicación debe combinar:
- Edición manual mediante herramientas visuales.
- Edición mediante transcripción.
- Edición controlada mediante inteligencia artificial.

2. RESTRICCIÓN PRINCIPAL: EJECUCIÓN LOCAL

La solución debe funcionar completamente de manera local.
No utilizar:
- Docker.
- Docker Compose.
- Kubernetes.
- Contenedores.
- Servicios obligatorios en la nube.
- Almacenamiento S3 obligatorio.
- Redis obligatorio.
- Máquinas virtuales.
- Infraestructura externa para guardar archivos.
- Plataformas externas para renderizar videos.
El usuario debe poder iniciar todo mediante un comando como:
npm run dev
O mediante comandos separados como:
npm run dev:web
npm run dev:api
npm run dev:worker
También debe existir un comando para producción local:
npm run build
npm run start

3. ENTORNO LOCAL OBJETIVO

La aplicación se desarrollará inicialmente para:
- Windows 11.
- Node.js 22 LTS o superior compatible.
- npm o pnpm.
- PostgreSQL 17.
- FFmpeg instalado localmente.
- FFprobe instalado junto con FFmpeg.
- Visual Studio Code.
- Navegadores Chromium modernos.
Debe funcionar también en Linux y macOS con cambios mínimos, pero la documentación principal debe estar orientada a Windows 11.

4. STACK TECNOLÓGICO

Frontend

Utiliza:
- Next.js.
- React.
- TypeScript con modo estricto.
- Tailwind CSS.
- shadcn/ui o Radix UI.
- Zustand para el estado local del editor.
- TanStack Query para comunicación con la API.
- Canvas o WebGL para la previsualización.
- Web Audio API para reproducción y formas de onda.
- WebCodecs cuando esté disponible.
- Web Workers para tareas que no deben bloquear la interfaz.
- Socket.IO o WebSocket para actualizaciones en tiempo real.

Backend

Utiliza:
- Node.js.
- TypeScript.
- NestJS o Fastify con arquitectura modular.
- API REST.
- WebSocket.
- PostgreSQL 17.
- Prisma como ORM.
- FFmpeg.
- FFprobe.
- Sistema de archivos local.
- pg-boss para colas de trabajo basadas en PostgreSQL.
- Sharp para procesamiento de imágenes.
- Zod o class-validator para validación.
- Pino para logs estructurados.

Inteligencia artificial

Integra:
- OpenAI Responses API.
- Function calling.
- Structured Outputs mediante JSON Schema.
- API de transcripción.
- API de texto a voz.
- Modelos con capacidades visuales.
- API de imágenes para miniaturas, fondos e ilustraciones.
- Generación de video como función opcional.
La clave de OpenAI debe permanecer únicamente en el backend.

5. ARQUITECTURA LOCAL

Diseña un monorepositorio con esta estructura:
virtualab-video-ai/
├── apps/
│   ├── web/
│   ├── api/
│   ├── media-worker/
│   └── render-worker/
├── packages/
│   ├── database/
│   ├── timeline/
│   ├── ffmpeg/
│   ├── openai/
│   ├── storage/
│   ├── shared/
│   ├── types/
│   └── ui/
├── local-data/
│   ├── uploads/
│   ├── projects/
│   ├── proxies/
│   ├── thumbnails/
│   ├── waveforms/
│   ├── transcripts/
│   ├── generated/
│   ├── renders/
│   ├── temporary/
│   └── logs/
├── scripts/
├── docs/
├── prisma/
├── package.json
├── pnpm-workspace.yaml
├── .env
├── .env.example
└── README.md
Todos los archivos multimedia deben almacenarse dentro de local-data.
No guardar archivos de video, audio o imagen como datos binarios dentro de PostgreSQL.
PostgreSQL solamente debe guardar:
- Rutas.
- Metadatos.
- Configuración.
- Estados.
- Operaciones.
- Transcripciones.
- Relaciones.
- Historial.
- Usuarios.
- Proyectos.

6. SERVICIOS LOCALES

La aplicación estará formada por procesos locales.

Aplicación web

Responsable de:
- Interfaz.
- Dashboard.
- Editor.
- Línea de tiempo.
- Panel de IA.
- Gestión de proyectos.
- Visualización del progreso.
Puerto sugerido:
http://localhost:3000

API local

Responsable de:
- Autenticación.
- Proyectos.
- Archivos.
- Línea de tiempo.
- Operaciones.
- Inteligencia artificial.
- Base de datos.
- Renderizados.
- Seguridad.
Puerto sugerido:
http://localhost:4000

Media Worker

Responsable de:
- Analizar archivos con FFprobe.
- Generar proxies.
- Crear miniaturas.
- Extraer formas de onda.
- Extraer audio.
- Detectar silencios.
- Preparar archivos para transcripción.

Render Worker

Responsable de:
- Procesar trabajos pendientes.
- Construir comandos seguros de FFmpeg.
- Renderizar proyectos.
- Publicar el progreso.
- Guardar el archivo final.
Todos los procesos deben ejecutarse localmente.

7. CONFIGURACIÓN DE POSTGRESQL 17

Utiliza esta conexión:
Host: localhost
Puerto: 5432
Usuario: [TU_USUARIO_POSTGRES]
Contraseña: [TU_CONTRASEÑA_POSTGRES]
Base de datos: virtualab_video_ai
La cadena de conexión debe ser:
DATABASE_URL="postgresql://[TU_USUARIO_POSTGRES]:[TU_CONTRASEÑA_POSTGRES]@localhost:5432/virtualab_video_ai?schema=public"
La aplicación debe incluir un script que cree la base de datos cuando todavía no exista.
Crear el archivo:
scripts/create-database.ts
Este script debe:
  1. Conectarse a la base de datos postgres.
  2. Verificar si existe virtualab_video_ai.
  3. Crear la base de datos cuando no exista.
  4. Mostrar un mensaje claro.
  5. No eliminar ni sobrescribir bases existentes.
También debe documentarse el comando manual:
CREATE DATABASE virtualab_video_ai;
Y el comando desde PowerShell:
psql -U [TU_USUARIO_POSTGRES] -h localhost -p 5432 -c "CREATE DATABASE virtualab_video_ai;"
La contraseña solicitada será:
[TU_CONTRASEÑA_POSTGRES]

8. CONFIGURACIÓN DE PRISMA

Utiliza Prisma con PostgreSQL.
Debe incluir:
npm run db:create
npm run db:generate
npm run db:migrate
npm run db:seed
npm run db:studio
Equivalencias:
npm run db:create
npx prisma generate
npx prisma migrate dev
npx prisma db seed
npx prisma studio
No ejecutar automáticamente operaciones destructivas.
Nunca utilizar:
prisma migrate reset
sin una confirmación explícita del usuario.
Las migraciones deben conservar los datos existentes.

9. VARIABLES DE ENTORNO

Genera un archivo .env.example con esta configuración:
NODE_ENV=development
APP_NAME=VIRTUALAB Video AI
WEB_URL=http://localhost:3000
API_URL=http://localhost:4000
API_PORT=4000
DATABASE_URL=postgresql://[TU_USUARIO_POSTGRES]:[TU_CONTRASEÑA_POSTGRES]@localhost:5432/virtualab_video_ai?schema=public
OPENAI_API_KEY=
AUTH_SECRET=CAMBIAR_ESTA_CLAVE_EN_PRODUCCION
ENCRYPTION_KEY=CAMBIAR_ESTA_CLAVE_EN_PRODUCCION
LOCAL_STORAGE_ROOT=./local-data
UPLOADS_DIRECTORY=./local-data/uploads
PROJECTS_DIRECTORY=./local-data/projects
PROXIES_DIRECTORY=./local-data/proxies
THUMBNAILS_DIRECTORY=./local-data/thumbnails
WAVEFORMS_DIRECTORY=./local-data/waveforms
TRANSCRIPTS_DIRECTORY=./local-data/transcripts
GENERATED_DIRECTORY=./local-data/generated
RENDERS_DIRECTORY=./local-data/renders
TEMP_DIRECTORY=./local-data/temporary
LOG_DIRECTORY=./local-data/logs
FFMPEG_PATH=ffmpeg
FFPROBE_PATH=ffprobe
MAX_UPLOAD_SIZE_MB=5120
MAX_CONCURRENT_MEDIA_JOBS=2
MAX_CONCURRENT_RENDER_JOBS=1
FREE_PLAN_STORAGE_GB=20
FREE_PLAN_AI_CREDITS=100
ENABLE_OPENAI=true
ENABLE_LOCAL_AUTH=true
ENABLE_REGISTRATION=true
La aplicación debe comprobar durante el inicio:
- Conexión con PostgreSQL.
- Existencia de FFmpeg.
- Existencia de FFprobe.
- Existencia de las carpetas locales.
- Permisos de lectura y escritura.
- Presencia de la clave de OpenAI cuando la IA esté habilitada.

10. ALMACENAMIENTO LOCAL

Crea un adaptador llamado:
LocalStorageAdapter
Debe implementar:
- Guardar archivos.
- Leer archivos.
- Eliminar archivos.
- Mover archivos.
- Copiar archivos.
- Generar rutas seguras.
- Verificar existencia.
- Calcular tamaño.
- Crear streams.
- Limpiar temporales.
- Evitar path traversal.
Organización por proyecto:
local-data/
└── projects/
└── project_<id>/
├── original/
├── proxy/
├── audio/
├── thumbnails/
├── waveform/
├── transcript/
├── generated/
├── autosave/
└── renders/
No utilizar nombres de archivo suministrados directamente por el usuario como nombres físicos definitivos.
Generar nombres internos mediante UUID.
Conservar el nombre original únicamente como metadato.

11. COLA DE TRABAJOS SIN REDIS

No utilizar Redis como requisito obligatorio.
Implementa las colas con:
pg-boss
pg-boss debe utilizar la misma base de datos PostgreSQL.
Colas mínimas:
- asset-analysis
- proxy-generation
- thumbnail-generation
- waveform-generation
- audio-extraction
- transcription
- silence-detection
- ai-operation
- render-project
- temporary-cleanup
Cada trabajo debe tener:
- ID.
- Tipo.
- Estado.
- Progreso.
- Reintentos.
- Fecha de creación.
- Fecha de inicio.
- Fecha de finalización.
- Mensaje de error.
- Proyecto relacionado.
- Usuario relacionado.
Los trabajos deben ser:
- Idempotentes.
- Cancelables cuando sea posible.
- Recuperables después de reiniciar la aplicación.
- Ejecutados con límites de concurrencia.
- Registrados en PostgreSQL.

12. EXPERIENCIA VISUAL DEL EDITOR

Diseña una interfaz original y profesional.
No copies la interfaz exacta de Clipchamp, CapCut, VEED, InVideo, Flixier, Kapwing, FlexClip o WeVideo.

Barra superior

Debe contener:
- Logo.
- Nombre editable del proyecto.
- Estado de guardado.
- Deshacer.
- Rehacer.
- Relación de aspecto.
- Calidad de previsualización.
- Botón exportar.
- Menú de usuario.

Barra lateral izquierda

Debe incluir:
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
- Kit de marca.
- Inteligencia artificial.

Área central

Debe contener:
- Reproductor.
- Timecode.
- Play.
- Pausa.
- Avanzar.
- Retroceder.
- Zoom.
- Guías.
- Márgenes seguros.
- Fondo del lienzo.
- Controles de transformación.

Panel derecho

Debe mostrar propiedades del elemento seleccionado:
- Posición.
- Tamaño.
- Rotación.
- Opacidad.
- Recorte.
- Volumen.
- Velocidad.
- Color.
- Sombras.
- Animación.
- Efectos.
- Fotogramas clave.

Línea de tiempo

Debe incluir:
- Regla temporal.
- Cabezal de reproducción.
- Pistas de video.
- Pistas de audio.
- Pistas de texto.
- Pistas de subtítulos.
- Formas de onda.
- Miniaturas.
- Ajuste magnético.
- Bloqueo.
- Ocultar.
- Silenciar.
- Selección múltiple.
- Zoom.
- Marcadores.

13. MODELO DE LA LÍNEA DE TIEMPO

La edición debe ser no destructiva.
Los archivos originales nunca deben modificarse.
Representa internamente el tiempo mediante microsegundos enteros o ticks enteros.
No utilizar números flotantes como fuente principal del tiempo.
Entidades principales:

Project

id
ownerId
name
description
width
height
frameRateNumerator
frameRateDenominator
durationMicroseconds
backgroundColor
status
createdAt
updatedAt
version

Asset

id
projectId
type
originalName
internalName
originalPath
proxyPath
thumbnailPath
waveformPath
mimeType
codec
width
height
durationMicroseconds
frameRate
fileSize
processingStatus
metadata

Track

id
projectId
type
order
name
locked
hidden
muted
solo

Clip

id
trackId
assetId
startMicroseconds
durationMicroseconds
sourceInMicroseconds
sourceOutMicroseconds
speed
volume
opacity
zIndex
transform
crop
effects
transitions
keyframes
metadata

CaptionSegment

id
projectId
trackId
startMicroseconds
endMicroseconds
text
speaker
confidence
words
style

ProjectOperation

id
projectId
userId
operationType
payload
inversePayload
sequence
createdAt

ProjectSnapshot

id
projectId
sequence
snapshot
createdBy
createdAt
Cada modificación debe registrarse como una operación reversible.

14. HERRAMIENTAS DE EDICIÓN

Implementa de manera funcional:
- Seleccionar.
- Cortar.
- Dividir.
- Recortar inicio.
- Recortar final.
- Eliminar.
- Duplicar.
- Copiar.
- Pegar.
- Mover.
- Edición ripple.
- Cerrar espacios.
- Ajuste magnético.
- Agrupar.
- Desagrupar.
- Bloquear.
- Congelar fotograma.
- Reversa.
- Velocidad.
- Zoom.
- Panorámica.
- Recorte.
- Rotación.
- Volteo.
- Opacidad.
- Picture-in-picture.
- Superposiciones.
- Fotogramas clave.
- Transiciones.
- Fundidos.
- Corrección de color.
- Brillo.
- Contraste.
- Saturación.
- Temperatura.
- Filtros.
- Texto.
- Títulos.
- Lower thirds.
- Formas.
- Imágenes.
- Logos.
- Stickers.
- Fondos.
Incluye atajos de teclado configurables.

15. AUDIO

Implementa:
- Separar audio.
- Silenciar.
- Controlar volumen.
- Normalizar.
- Fade de entrada.
- Fade de salida.
- Reducir ruido.
- Mejorar voz.
- Detectar silencios.
- Eliminar silencios.
- Eliminar muletillas.
- Ducking automático.
- Sincronizar audio y video.
- Mostrar forma de onda.
- Grabar narración.
- Añadir música.
- Añadir efectos de sonido.
- Detectar clipping.
Las acciones pesadas deben ejecutarse mediante el worker local.

16. SUBTÍTULOS Y TRANSCRIPCIÓN

Construye un sistema que permita:
  1. Extraer el audio.
  2. Transcribir mediante OpenAI.
  3. Guardar segmentos.
  4. Guardar marcas temporales.
  5. Mostrar la transcripción.
  6. Buscar palabras.
  7. Saltar al momento exacto.
  8. Editar el texto.
  9. Dividir segmentos.
  10. Combinar segmentos.
  11. Traducir subtítulos.
  12. Exportar SRT.
  13. Exportar VTT.
  14. Exportar TXT.
  15. Incrustar subtítulos durante el renderizado.

Edición basada en transcripción

Cuando el usuario elimine una frase:
  1. Identificar sus marcas temporales.
  2. Crear una operación de edición.
  3. Mostrar qué parte será eliminada.
  4. Aplicar cortes a los clips correspondientes.
  5. Cerrar el espacio cuando se seleccione ripple.
  6. Mantener sincronizados video, audio y subtítulos.
  7. Permitir deshacer la operación.

17. ASISTENTE DE INTELIGENCIA ARTIFICIAL

Añade un panel llamado:

Asistente de edición con IA

Debe contener:
- Historial de conversación.
- Campo de instrucciones.
- Entrada por voz.
- Acciones sugeridas.
- Selector de alcance.
- Proyecto completo.
- Clips seleccionados.
- Intervalo seleccionado.
- Pista activa.
- Vista previa.
- Aplicar.
- Cancelar.
- Deshacer.
- Progreso.
- Costos estimados.
- Explicación de cambios.
Ejemplos:
- “Elimina silencios mayores de dos segundos”.
- “Quita las muletillas”.
- “Genera subtítulos en español”.
- “Traduce los subtítulos al inglés”.
- “Crea un video vertical de 45 segundos”.
- “Busca los cinco mejores momentos”.
- “Agrega un título al inicio”.
- “Cambia el proyecto a formato 9:16”.
- “Genera una narración formal”.
- “Aplica mi kit de marca”.
- “Crea tres Shorts”.
- “Reduce el ruido del audio”.
- “Haz que el ritmo del video sea más dinámico”.
- “Genera una miniatura”.
- “Crea título, descripción, capítulos y etiquetas para YouTube”.

18. ARQUITECTURA DE ACCIONES CON OPENAI

La IA no debe modificar directamente el DOM, la base de datos o los archivos.
Flujo obligatorio:
  1. El usuario escribe una instrucción.
  2. El frontend envía la instrucción al backend.
  3. El backend obtiene el contexto del proyecto.
  4. El backend consulta la Responses API.
  5. OpenAI devuelve llamadas a funciones.
  6. El backend valida los argumentos.
  7. El backend verifica permisos.
  8. El backend calcula costos.
  9. El backend crea un plan.
  10. La interfaz muestra la previsualización.
  11. El usuario confirma las operaciones importantes.
  12. El backend ejecuta las acciones.
  13. Se crea una operación reversible.
  14. Se guarda un snapshot.
  15. La interfaz recibe los cambios.
  16. El usuario puede deshacerlos.
Nunca ejecutar como código una respuesta textual generada por la IA.
Nunca construir comandos de terminal directamente a partir de texto generado por la IA.

19. FUNCIONES DISPONIBLES PARA OPENAI

Implementa herramientas con JSON Schema estricto.

Consulta

- get_project_summary
- get_timeline_state
- get_selected_clips
- get_asset_metadata
- get_transcript_range
- get_brand_kit
- get_available_templates
- estimate_operation_cost

Edición

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
- add_transition
- add_effect
- remove_effect
- add_keyframe
- group_clips
- ungroup_clips

Texto

- add_text_layer
- update_text_layer
- style_text_layer
- animate_text_layer
- add_lower_third

Subtítulos

- transcribe_asset
- generate_captions
- update_caption_segment
- translate_captions
- style_captions
- export_captions
- delete_words_from_transcript

Audio

- detach_audio
- clean_audio
- normalize_audio
- remove_silences
- remove_filler_words
- apply_audio_ducking
- add_music
- generate_voiceover

Creativas

- generate_script
- generate_storyboard
- find_highlights
- create_highlight_reel
- create_social_variants
- suggest_broll
- insert_broll
- generate_image_asset
- generate_thumbnail
- apply_brand_kit
- apply_template

Proyecto

- change_aspect_ratio
- create_project_version
- restore_project_version
- render_project
- cancel_render

20. EJEMPLO DE OPERACIÓN DE IA

{
"summary": "Se eliminarán 8 silencios y la duración se reducirá aproximadamente 31 segundos.",
"scope": "selected_clips",
"estimatedDurationBeforeMicroseconds": 420000000,
"estimatedDurationAfterMicroseconds": 389000000,
"estimatedCostCredits": 2,
"requiresConfirmation": true,
"warnings": [],
"operations": [
{
"tool": "remove_silences",
"arguments": {
"projectId": "project_123",
"clipIds": ["clip_10", "clip_11"],
"minimumSilenceMilliseconds": 2000,
"thresholdDb": -38,
"preservePaddingMilliseconds": 150,
"ripple": true,
"previewOnly": false
}
}
]
}
Cada operación debe tener:
- ID.
- Estado.
- Progreso.
- Resultado.
- Error.
- Operación inversa.
- Usuario.
- Fecha.
- Costo.
- Modelo utilizado.
- Confirmación.

21. IMPORTACIÓN DE ARCHIVOS

Permite importar:
- MP4.
- MOV.
- WebM.
- MKV.
- AVI.
- MP3.
- WAV.
- AAC.
- M4A.
- PNG.
- JPG.
- JPEG.
- WebP.
- GIF.
- SRT.
- VTT.
Proceso:
  1. Seleccionar archivo.
  2. Validar tamaño.
  3. Validar MIME.
  4. Generar UUID.
  5. Copiar archivo a la carpeta del proyecto.
  6. Analizar con FFprobe.
  7. Guardar metadatos.
  8. Crear trabajo de procesamiento.
  9. Generar proxy.
  10. Generar miniaturas.
  11. Generar forma de onda.
  12. Actualizar el estado.
  13. Notificar al frontend.

22. GRABADOR

Incluye:
- Pantalla.
- Cámara.
- Micrófono.
- Pantalla y cámara.
- Selector de dispositivos.
- Cuenta regresiva.
- Pausa.
- Reanudación.
- Nivel del micrófono.
- Vista previa.
- Teleprompter.
- Picture-in-picture.
Las grabaciones deben guardarse por fragmentos para reducir el riesgo de pérdida.
Al finalizar, deben copiarse automáticamente al almacenamiento local del proyecto.

23. RENDERIZADO LOCAL CON FFMPEG

El renderizado debe ejecutarse en el computador local.
Flujo:
  1. Crear snapshot inmutable.
  2. Validar archivos.
  3. Crear el plan de renderizado.
  4. Generar filtros de FFmpeg.
  5. Ejecutar FFmpeg mediante argumentos seguros.
  6. Capturar el progreso.
  7. Enviar el progreso mediante WebSocket.
  8. Guardar el archivo en local-data/renders.
  9. Crear miniatura.
  10. Registrar el resultado.
  11. Limpiar archivos temporales.
Formatos:
- MP4 H.264.
- MP4 H.265 opcional.
- WebM.
- GIF.
- MP3.
- WAV.
- PNG.
- JPG.
Resoluciones:
- 720p.
- 1080p.
- 1440p.
- 4K cuando el equipo lo permita.
- Personalizada.
La aplicación debe advertir cuando una exportación pueda necesitar muchos recursos.
No bloquear el proceso principal de la API durante el renderizado.

24. DETECCIÓN AUTOMÁTICA DE FFMPEG

Al iniciar, ejecutar:
ffmpeg -version
ffprobe -version
Si no están disponibles:
  1. Mostrar un mensaje claro.
  2. Indicar cómo instalar FFmpeg.
  3. Permitir configurar una ruta absoluta.
Ejemplo de configuración:
FFMPEG_PATH=C:/ffmpeg/bin/ffmpeg.exe
FFPROBE_PATH=C:/ffmpeg/bin/ffprobe.exe
No asumir que FFmpeg siempre está registrado en la variable PATH.

25. SCRIPTS DEL PROYECTO

El package.json principal debe incluir:
{
"scripts": {
"dev": "concurrently \"npm:dev:web\" \"npm:dev:api\" \"npm:dev:media-worker\" \"npm:dev:render-worker\"",
"dev:web": "npm --workspace apps/web run dev",
"dev:api": "npm --workspace apps/api run dev",
"dev:media-worker": "npm --workspace apps/media-worker run dev",
"dev:render-worker": "npm --workspace apps/render-worker run dev",
"build": "npm run build --workspaces",
"start": "concurrently \"npm:start:web\" \"npm:start:api\" \"npm:start:media-worker\" \"npm:start:render-worker\"",
"db:create": "tsx scripts/create-database.ts",
"db:generate": "prisma generate",
"db:migrate": "prisma migrate dev",
"db:deploy": "prisma migrate deploy",
"db:seed": "tsx prisma/seed.ts",
"db:studio": "prisma studio",
"check:environment": "tsx scripts/check-environment.ts",
"setup": "npm run check:environment && npm run db:create && npm run db:generate && npm run db:migrate && npm run db:seed",
"test": "vitest run",
"test:e2e": "playwright test",
"lint": "eslint .",
"format": "prettier --write ."
}
}
Adapta correctamente los comandos al administrador de paquetes seleccionado.

26. INSTALACIÓN LOCAL AUTOMATIZADA

Crea un comando:
npm run setup
Debe:
  1. Verificar Node.js.
  2. Verificar PostgreSQL.
  3. Verificar conexión con PostgreSQL.
  4. Crear la base de datos si no existe.
  5. Verificar FFmpeg.
  6. Verificar FFprobe.
  7. Crear carpetas locales.
  8. Instalar o validar Prisma.
  9. Generar Prisma Client.
  10. Ejecutar migraciones.
  11. Crear datos iniciales.
  12. Mostrar las URLs de la aplicación.
No instalar programas del sistema operativo sin autorización.
Si falta FFmpeg, mostrar instrucciones, pero no descargar ejecutables automáticamente.

27. EXPERIENCIA DE PRIMER INICIO

Durante el primer inicio, mostrar un asistente que compruebe:
- PostgreSQL conectado.
- Base de datos creada.
- Migraciones aplicadas.
- FFmpeg disponible.
- FFprobe disponible.
- Carpetas disponibles.
- Clave de OpenAI.
- Espacio libre en disco.
- Permisos de escritura.
Estados:
- Correcto.
- Advertencia.
- Error.
- Función deshabilitada.
La aplicación debe poder iniciar sin clave de OpenAI, pero las funciones de IA deberán aparecer deshabilitadas hasta configurarla.

28. SEGURIDAD LOCAL

Aunque se ejecute localmente, implementar:
- API key solamente en backend.
- Validación de archivos.
- Sanitización.
- Protección contra path traversal.
- Límites de tamaño.
- Autorización por proyecto.
- Hash de contraseñas.
- Sesiones seguras.
- Rate limiting local.
- Auditoría.
- Validación de tool calls.
- Confirmación para operaciones destructivas.
- Protección contra comandos arbitrarios.
- Argumentos seguros para FFmpeg.
- Limpieza de temporales.
- Restricción de rutas permitidas.
No utilizar:
exec(`ffmpeg ${textoGeneradoPorIA}`)
Utilizar procesos con argumentos separados:
spawn(ffmpegPath, safeArguments)
Todos los argumentos deben construirse a partir de estructuras validadas por el backend.

29. BASE DE DATOS

Crea modelos Prisma para:
- User.
- Session.
- Workspace.
- WorkspaceMember.
- Project.
- ProjectMember.
- ProjectSnapshot.
- ProjectOperation.
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
- CreditTransaction.
- AuditLog.
- ApplicationSetting.
Añade:
- Índices.
- Restricciones.
- Relaciones.
- Enums.
- Timestamps.
- Eliminación lógica.
- Control de versiones.
- Transacciones.
- Integridad referencial.

30. ESTADOS

Asset

uploaded
validating
analyzing
proxying
ready
failed
quarantined

Trabajo multimedia

created
queued
running
completed
failed
cancelled

Renderizado

queued
preparing
rendering
finalizing
completed
failed
cancelled

Acción de IA

requested
planning
awaiting_confirmation
queued
executing
completed
partially_completed
failed
cancelled
reverted

31. MANEJO DE ERRORES

Contempla:
- PostgreSQL no iniciado.
- Contraseña incorrecta.
- Base de datos inexistente.
- Migración fallida.
- FFmpeg no instalado.
- FFprobe no encontrado.
- Archivo incompatible.
- Códec no admitido.
- Archivo corrupto.
- Disco sin espacio.
- Permisos insuficientes.
- Transcripción fallida.
- OpenAI no disponible.
- Clave incorrecta.
- Créditos insuficientes.
- Renderizado fallido.
- Proyecto corrupto.
- Conflicto de edición.
- Worker detenido.
Cada error debe mostrar:
- Mensaje entendible.
- Código.
- Detalle técnico opcional.
- Posible solución.
- Botón de reintento.
- Ruta del log correspondiente.

32. LOGS LOCALES

Guardar logs en:
local-data/logs/
Archivos sugeridos:
api.log
media-worker.log
render-worker.log
openai.log
errors.log
Los logs deben:
- Usar JSON estructurado.
- Rotar periódicamente.
- Evitar almacenar claves.
- Evitar almacenar contraseñas.
- Evitar guardar contenido sensible innecesario.
- Incluir ID de proyecto.
- Incluir ID de trabajo.
- Incluir ID de correlación.

33. RESPALDO Y RECUPERACIÓN

Implementa:
- Autosave.
- Snapshots.
- Historial de operaciones.
- Recuperación tras cierres inesperados.
- Copia de seguridad manual del proyecto.
- Exportación de proyecto.
- Importación de proyecto.
Formato de exportación sugerido:
.virtualab-video-project
Puede ser un archivo ZIP que contenga:
project.json
assets/
captions/
thumbnails/
metadata/
No incluir claves de API ni información sensible.

34. PRUEBAS

Incluye:
- Unitarias.
- Integración.
- End-to-end.
- Línea de tiempo.
- Undo y redo.
- Almacenamiento local.
- Acceso a PostgreSQL.
- Colas de pg-boss.
- FFmpeg.
- Renderizado.
- Transcripción.
- Tool calling.
- Validación JSON.
- Seguridad de rutas.
- Archivos corruptos.
- Recuperación de proyectos.
- Reinicio de workers.
Casos críticos:
  1. Cargar un MP4.
  2. Crear proxy.
  3. Generar miniaturas.
  4. Generar forma de onda.
  5. Añadir clip a la línea de tiempo.
  6. Dividir clip.
  7. Deshacer división.
  8. Generar subtítulos.
  9. Eliminar frase desde la transcripción.
  10. Eliminar silencios mediante IA.
  11. Renderizar en 1080p.
  12. Reiniciar el worker durante un trabajo.
  13. Recuperar el trabajo pendiente.
  14. Cerrar y volver a abrir el proyecto.
  15. Exportar e importar un proyecto.

35. MVP LOCAL

La primera versión debe incluir:
- Autenticación local.
- Dashboard.
- Creación de proyectos.
- Carga multimedia.
- Biblioteca local.
- Línea de tiempo.
- Cortar.
- Dividir.
- Recortar.
- Mover.
- Eliminar.
- Duplicar.
- Texto.
- Audio básico.
- Subtítulos automáticos.
- Edición por transcripción.
- Panel de IA.
- Al menos diez herramientas reales de IA.
- Eliminación de silencios.
- Generación de narración.
- Exportación 720p.
- Exportación 1080p.
- Autosave.
- Deshacer.
- Rehacer.
- Historial de operaciones.
- Renderizado local.
- Recuperación tras reinicio.
- Instalación sin Docker.

36. CRITERIOS DE ACEPTACIÓN

El MVP estará listo cuando el usuario pueda:
  1. Ejecutar npm install.
  2. Configurar .env.
  3. Ejecutar npm run setup.
  4. Crear la base de datos local.
  5. Ejecutar npm run dev.
  6. Abrir http://localhost:3000.
  7. Crear un usuario.
  8. Crear un proyecto.
  9. Subir un video.
  10. Generar un proxy.
  11. Ver miniaturas.
  12. Ver forma de onda.
  13. Arrastrar el video a la línea de tiempo.
  14. Cortarlo.
  15. Dividirlo.
  16. Añadir texto.
  17. Modificar volumen.
  18. Generar subtítulos.
  19. Eliminar una frase desde la transcripción.
  20. Pedir a la IA eliminar silencios.
  21. Revisar el plan.
  22. Aplicar la operación.
  23. Deshacerla.
  24. Exportar el video.
  25. Ver el progreso.
  26. Encontrar el archivo en local-data/renders.
  27. Cerrar la aplicación.
  28. Reiniciarla.
  29. Recuperar el proyecto sin pérdida de datos.

37. README OBLIGATORIO

El README debe estar completamente en español e incluir:

Requisitos

- Windows 11.
- Node.js.
- PostgreSQL 17.
- FFmpeg.
- Git.
- Visual Studio Code opcional.

Configuración de PostgreSQL

Usuario: [TU_USUARIO_POSTGRES]
Contraseña: [TU_CONTRASEÑA_POSTGRES]
Host: localhost
Puerto: 5432
Base de datos: virtualab_video_ai

Instalación

git clone URL_DEL_REPOSITORIO
cd virtualab-video-ai
npm install
copy .env.example .env
npm run setup
npm run dev

Acceso

Frontend: http://localhost:3000
API: http://localhost:4000

Comandos

npm run dev
npm run build
npm run start
npm run db:create
npm run db:migrate
npm run db:seed
npm run db:studio
npm run test

Solución de problemas

Debe explicar:
- Cómo iniciar PostgreSQL.
- Cómo verificar PostgreSQL.
- Cómo cambiar la contraseña.
- Cómo instalar FFmpeg.
- Cómo configurar rutas absolutas.
- Cómo borrar archivos temporales.
- Cómo reiniciar los workers.
- Cómo consultar logs.
- Cómo recuperar un proyecto.
- Cómo liberar espacio.

38. PRIMERA ENTREGA SOLICITADA AL AGENTE DE PROGRAMACIÓN

Comienza desarrollando en este orden:

Paso 1

Crear:
- Monorepositorio.
- Configuración de TypeScript.
- Scripts.
- Variables de entorno.
- Estructura de carpetas.
- Verificador del entorno.

Paso 2

Configurar:
- PostgreSQL 17.
- Prisma.
- Creación automática de la base.
- Migraciones.
- Seeds.
- pg-boss.

Paso 3

Crear:
- API.
- Autenticación local.
- Proyectos.
- Assets.
- Almacenamiento local.
- Carga de archivos.

Paso 4

Crear:
- Worker multimedia.
- Integración FFprobe.
- Proxies.
- Miniaturas.
- Formas de onda.

Paso 5

Crear:
- Editor.
- Reproductor.
- Línea de tiempo.
- Pistas.
- Clips.
- Operaciones básicas.
- Undo y redo.

Paso 6

Crear:
- Transcripción.
- Subtítulos.
- Edición basada en texto.

Paso 7

Crear:
- Integración OpenAI.
- Function calling.
- Planificación de operaciones.
- Vista previa.
- Confirmación.
- Herramientas de IA.

Paso 8

Crear:
- Render worker.
- Exportación 720p.
- Exportación 1080p.
- Progreso.
- Cancelación.
- Recuperación de trabajos.

Paso 9

Crear:
- Pruebas.
- README.
- Instalador local.
- Validación completa.
Después de cada paso:
  1. Ejecuta el código.
  2. Corrige errores.
  3. Comprueba tipos.
  4. Ejecuta pruebas.
  5. Verifica PostgreSQL.
  6. Verifica FFmpeg.
  7. Documenta cómo probarlo.
  8. No continúes con errores críticos pendientes.

39. REGLAS PARA EL AGENTE DE PROGRAMACIÓN

- No utilizar Docker.
- No crear archivos Dockerfile.
- No crear docker-compose.yml.
- No exigir Redis.
- No exigir almacenamiento S3.
- No inventar servicios externos.
- No entregar solamente una maqueta.
- No crear botones sin funcionalidad.
- No exponer la clave de OpenAI.
- No guardar videos en PostgreSQL.
- No modificar archivos originales.
- No ejecutar comandos generados libremente por IA.
- No bloquear la API mientras se renderiza.
- No ejecutar FFmpeg en el hilo principal.
- No omitir validaciones.
- No usar rutas inseguras.
- No eliminar datos existentes.
- No usar migraciones destructivas.
- No simular funciones como terminadas cuando no funcionan.
- No continuar a la siguiente fase mientras el proyecto no compile.
- No asumir que PostgreSQL o FFmpeg están disponibles sin verificarlos.
Cuando una función avanzada no pueda completarse:
  1. Implementa una versión mínima real.
  2. Documenta la limitación.
  3. Mantén una interfaz extensible.
  4. Incluye pruebas.
  5. No simules resultados falsos.

40. INSTRUCCIÓN FINAL

Construye una aplicación real, funcional y ejecutable localmente.
La aplicación debe poder instalarse con:
npm install
npm run setup
npm run dev
La base de datos debe utilizar:
DATABASE_URL=postgresql://[TU_USUARIO_POSTGRES]:[TU_CONTRASEÑA_POSTGRES]@localhost:5432/virtualab_video_ai?schema=public
Los archivos deben guardarse en:
./local-data
Los trabajos en segundo plano deben administrarse con PostgreSQL mediante: pg-boss
Los videos deben procesarse y renderizarse localmente mediante:
FFmpeg
FFprobe
No utilices Docker en ninguna etapa.
Entrega primero un MVP completamente funcional y comprobable. Después amplía las características sin romper las funciones existentes.
```
