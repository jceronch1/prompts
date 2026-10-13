# Agente de IA para candidato político

**Categoría:** [Agentes y chatbots](README.md) · **Tecnologías:** Ollama, Gemma 4, RAG, PostgreSQL + pgvector, WhisperX, VibeVoice

Agente conversacional multimodal (texto y voz) que responde a la ciudadanía sobre la propuesta de campaña y la hoja de vida de un candidato.

> **Antes de usarlo, reemplaza:** `[RUTA_DEL_MODELO_VIBEVOICE]`, `[RUTA_DE_LOS_DOCUMENTOS_DEL_CANDIDATO]`

## Prompt

```text
Actúa como un Arquitecto Senior de Software, experto en IA conversacional, RAG, PostgreSQL, pgvector, Ollama, WhisperX, Microsoft VibeVoice y desarrollo de aplicaciones web en Windows.

Quiero que construyas una aplicación web completa de un agente de IA para un candidato político a la Alcaldía de una Ciudad X.

OBJETIVO GENERAL
Crear un agente conversacional multimodal capaz de responder preguntas de los ciudadanos sobre:
1. La propuesta de campaña del candidato.
2. La hoja de vida del candidato.
3. Dudas frecuentes relacionadas con su trayectoria, experiencia, visión, plan de gobierno y perfil profesional.

El agente debe responder por texto y por voz, escuchar por micrófono y contestar de forma natural, amable, respetuosa, propositiva, clara y positiva.

IMPORTANTE
El agente debe ser estrictamente informativo y basado en evidencia documental.
No debe inventar datos.
No debe asumir posiciones no contenidas en los documentos.
No debe responder con información no verificada como si fuera cierta.
Si una respuesta no está en la base documental, debe decirlo claramente y sugerir una forma correcta de consultar o ampliar la información.

STACK TECNOLÓGICO OBLIGATORIO
- Backend: el más adecuado para integrar Ollama, PostgreSQL, pgvector, WhisperX y VibeVoice.
- Frontend web moderno, limpio, responsivo y fácil de usar.
- Base de datos PostgreSQL ya existente con nombre: candidato
- Extensión vectorial: pgvector
- Conexión y operaciones sobre PostgreSQL usando el MCP de Postgres
- LLM local mediante Ollama
- Modelo de embeddings ya instalado en Ollama: embeddinggemma:latest
- Modelo por defecto del chat: gemma4:e4b
- El frontend debe permitir seleccionar dinámicamente otros modelos locales instalados en Ollama
- STT: WhisperX ya instalado en Windows por consola
- TTS: Microsoft VibeVoice usando el modelo local ubicado en:
  [RUTA_DEL_MODELO_VIBEVOICE]

RUTAS IMPORTANTES
- Carpeta de documentos fuente para ingesta RAG:
  [RUTA_DE_LOS_DOCUMENTOS_DEL_CANDIDATO]
- Modelo TTS:
  [RUTA_DEL_MODELO_VIBEVOICE]
- STT:
  WhisperX ya instalado y accesible desde consola en Windows

REQUERIMIENTOS FUNCIONALES
1. Crear una aplicación web donde el ciudadano pueda:
   - Escribir preguntas.
   - Hablar por micrófono.
   - Escuchar la respuesta en audio.
   - Ver el texto de la respuesta.
   - Ver las fuentes documentales usadas para responder.
   - Ver el modelo LLM activo.
   - Cambiar el modelo desde el frontend, dejando gemma4:e4b por defecto.

2. Implementar un sistema RAG sobre PostgreSQL + pgvector que:
   - Ingeste automáticamente la propuesta de campaña y la hoja de vida del candidato desde la carpeta:
     [RUTA_DE_LOS_DOCUMENTOS_DEL_CANDIDATO]
   - Divida los documentos en chunks adecuados.
   - Genere embeddings con embeddinggemma:latest usando Ollama.
   - Almacene documentos, metadatos, chunks y embeddings en PostgreSQL.
   - Recupere contexto relevante antes de responder.
   - Cite la fuente usada en cada respuesta.

3. El agente debe responder preguntas como:
   - ¿Cuál es la propuesta del candidato en seguridad?
   - ¿Qué propone para empleo, educación, salud, movilidad o medio ambiente?
   - ¿Qué experiencia profesional tiene?
   - ¿Cuál es su formación académica?
   - ¿Qué cargos ha ocupado?
   - ¿Qué logros tiene?
   - ¿Cuál es su visión para la ciudad?
   - ¿Qué dice su hoja de vida sobre su experiencia pública o privada?

4. El agente debe manejar correctamente:
   - Preguntas cortas y largas.
   - Preguntas ambiguas.
   - Seguimiento conversacional.
   - Historial de conversación.
   - Respuestas con contexto.
   - Casos donde no exista información suficiente.

COMPORTAMIENTO DEL AGENTE
- Tono cordial, amable, profesional, cercano y respetuoso.
- Debe explicar con claridad.
- Debe evitar respuestas agresivas, sesgadas o confusas.
- Debe responder siempre con base en los documentos cargados.
- Debe indicar cuando algo no aparece en la propuesta o en la hoja de vida.
- Debe evitar alucinaciones.
- Debe ser útil, organizado y transparente.
- Debe diferenciar claramente entre:
  a) información encontrada en la propuesta,
  b) información encontrada en la hoja de vida,
  c) información no encontrada.

REGLAS DE RESPUESTA
- Si la respuesta está en los documentos, responder de forma clara y resumida.
- Luego mostrar una sección “Fuente consultada” con el documento y, si es posible, el fragmento o sección.
- Si la información no está disponible, responder:
  “No encontré esa información de forma explícita en los documentos cargados del candidato.”
- No inventar propuestas, cargos, títulos, logros o datos personales.
- No mezclar información de la hoja de vida con la propuesta sin indicarlo.
- Priorizar precisión sobre creatividad.

BASE DE DATOS
Usar la base de datos PostgreSQL existente llamada:
- candidato

Debes crear todas las tablas necesarias para soportar:
1. documentos
2. chunks_documentales
3. embeddings_vectoriales
4. conversaciones
5. mensajes
6. configuracion_modelos
7. auditoria_consultas
8. sesiones_usuario
9. fuentes_respuesta

Diseña el esquema completo con buenas prácticas.
Incluye:
- claves primarias
- claves foráneas
- índices normales
- índices vectoriales apropiados para pgvector
- timestamps
- campos de metadatos
- campos para tipo_documento (propuesta, hoja_vida, otro)
- campos para nombre_archivo, ruta_origen, hash_documento y estado_ingesta

También genera:
- scripts SQL completos
- creación de extensión pgvector si aplica
- inserciones iniciales mínimas de configuración
- consultas ejemplo para recuperación semántica

INGESTA DOCUMENTAL
Construye el proceso para:
1. Leer archivos desde:
   [RUTA_DE_LOS_DOCUMENTOS_DEL_CANDIDATO]
2. Detectar documentos compatibles
3. Extraer el texto
4. Limpiar y normalizar contenido
5. Dividir en chunks
6. Generar embeddings con embeddinggemma:latest
7. Guardar todo en PostgreSQL con pgvector
8. Registrar logs de ingesta y errores

AUDIO
Implementa:
1. Entrada de voz con WhisperX
   - Capturar audio del micrófono
   - Enviar a transcripción
   - Mostrar el texto transcrito antes o durante la consulta
2. Salida de voz con VibeVoice
   - Convertir la respuesta textual a audio
   - Reproducirla en el frontend
   - Permitir activar o desactivar audio
   - Mantener baja latencia y buena experiencia de usuario

FRONTEND
Construir una interfaz moderna y limpia con:
- caja de chat
- botón para enviar texto
- botón para grabar audio
- botón para escuchar o detener audio
- selector de modelos Ollama
- panel para mostrar fuentes recuperadas
- indicador de estado del sistema
- historial conversacional
- diseño responsivo
- estilo profesional y agradable

El frontend debe mostrar claramente:
- modelo activo
- si la respuesta vino de RAG
- documentos fuente usados
- estado de escucha, transcripción y síntesis de voz

BACKEND
Construye toda la lógica necesaria para:
- conexión con PostgreSQL
- uso de MCP de Postgres
- lectura de documentos
- generación de embeddings con Ollama
- recuperación vectorial con pgvector
- llamada al LLM seleccionado
- integración con WhisperX
- integración con VibeVoice
- manejo de errores
- logs técnicos
- configuración por archivos .env

CONFIGURACIÓN DEL MODELO
Debes dejar:
- modelo por defecto: gemma4:e4b
- opción para listar modelos locales disponibles en Ollama
- opción para cambiar el modelo desde el frontend
- persistencia del último modelo seleccionado por el usuario o sesión

SEGURIDAD Y CALIDAD
Implementa:
- validación de entradas
- manejo de errores robusto
- sanitización básica
- separación por capas
- código limpio y modular
- comentarios útiles
- estructura escalable
- buenas prácticas de seguridad
- registros de auditoría de consultas

SALIDA ESPERADA
Quiero que entregues:
1. Arquitectura completa del sistema
2. Estructura de carpetas del proyecto
3. Script SQL completo para PostgreSQL + pgvector
4. Backend completo
5. Frontend completo
6. Módulo de ingesta documental
7. Integración con WhisperX
8. Integración con VibeVoice
9. Integración con Ollama
10. Selector de modelos en frontend
11. Archivo .env.example
12. Instrucciones de instalación y ejecución en Windows
13. Flujo completo de funcionamiento
14. Código listo para probar localmente

MUY IMPORTANTE
- No dejes secciones incompletas.
- No uses pseudocódigo si puedes entregar código funcional.
- Todo debe quedar orientado a ejecución local en Windows.
- Usa nombres claros y consistentes.
- Si necesitas decidir un framework o lenguaje, elige el más conveniente para integrar todo localmente y justifica brevemente la elección.
- La respuesta debe estar pensada para construir un prototipo funcional real, mantenible y ampliable.
```
