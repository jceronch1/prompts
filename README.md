# Prompts

Colección de 47 prompts en español para construir aplicaciones con inteligencia artificial: agentes, chatbots, RAG, MCP, plataformas web, juegos, escenas 3D, visión por computador, video y más.

Están pensados para pegarse en asistentes de programación como Claude, ChatGPT, Gemini, Codex o Cursor.

## Cómo usarlos

1. Busca el prompt en el índice de abajo o dentro de la carpeta de cada categoría.
2. Copia el bloque **Prompt** con el botón de copiar de GitHub.
3. Reemplaza los marcadores `[ENTRE_CORCHETES]` con tus propios datos.
4. Ajusta modelos, rutas y tecnologías a tu entorno y pégalo en tu asistente.

## Marcadores para tus datos

Ningún prompt incluye claves, contraseñas ni rutas personales. En su lugar hay marcadores que debes reemplazar:

| Marcador | Qué debes poner |
| --- | --- |
| `[TU_API_KEY_DE_OPENAI]` | Tu API key de OpenAI. |
| `[TU_API_KEY_DE_GOOGLE]` | Tu API key de Google AI Studio (Gemini). |
| `[TU_API_KEY_DE_GRADIUM]` | Tu API key de Gradium (síntesis de voz). |
| `[TU_VOICE_ID_DE_GRADIUM]` | El ID de la voz que elijas en Gradium. |
| `[TU_USUARIO_POSTGRES]` / `[TU_CONTRASEÑA_POSTGRES]` | Usuario y contraseña de tu PostgreSQL. |
| `[TU_USUARIO_MYSQL]` / `[TU_CONTRASEÑA_MYSQL]` | Usuario y contraseña de tu MySQL. |
| `[CONTRASEÑA_DE_PRUEBA]` | La contraseña que quieras para los usuarios de prueba que creará la app. |
| `[RUTA_...]` | Una carpeta o archivo de tu equipo, por ejemplo `C:\proyectos\mi-app`. |

> **Seguridad:** no pegues claves reales en archivos que vayas a subir a un repositorio. Guárdalas en un archivo `.env` que esté en tu `.gitignore`. Si una clave se publica por error, revócala y genera una nueva en el panel del proveedor.

## Índice

### [Agentes y chatbots](01-agentes-y-chatbots/)

Agentes conversacionales, multiagente y chatbots con modelos locales (Ollama) o en la nube.

| Prompt | Descripción | Tecnologías |
| --- | --- | --- |
| [Agente de IA para candidato político](01-agentes-y-chatbots/agente-ia-candidato-politico.md) | Agente conversacional multimodal (texto y voz) que responde a la ciudadanía sobre la propuesta de campaña y la hoja de vida de un candidato. | Ollama, Gemma 4, RAG, PostgreSQL + pgvector, WhisperX, VibeVoice |
| [Agente de citas médicas (LangGraph + MCP)](01-agentes-y-chatbots/agente-citas-medicas-langgraph.md) | Arquitectura paso a paso de un agente autónomo de citas médicas con base de conocimiento vectorial. | LangGraph, Ollama, MCP, PostgreSQL + pgvector, Python |
| [Agente web de citas médicas con IA (versión completa)](01-agentes-y-chatbots/agente-citas-medicas-completo.md) | Proyecto completo y ejecutable de un agente de citas médicas con frontend, backend, RAG y guía de ejecución en Windows 11. | Python, LangGraph, Ollama, PostgreSQL + pgvector, MCP, Streamlit |
| [Agentes paralelos con Gemma 4](01-agentes-y-chatbots/agentes-paralelos-gemma4.md) | App web para ejecutar varios agentes de IA en paralelo con modelos locales en una GPU de 8 GB. | Gemma, llama.cpp, Ollama, FastAPI |
| [Chatbot de debate automático](01-agentes-y-chatbots/chatbot-debate-automatico.md) | Debate automático entre dos personajes de IA con posturas opuestas y un moderador, cada uno con su propia voz. | Ollama (qwen3:8b), síntesis de voz |

### [Voz y audio](02-voz-y-audio/)

Síntesis de voz (TTS), clonación de voz, reconocimiento de voz (ASR) y agentes que hablan.

| Prompt | Descripción | Tecnologías |
| --- | --- | --- |
| [Agente de ventas de ropa por voz](02-voz-y-audio/agente-ventas-ropa-por-voz.md) | Agente web de ventas que consulta un inventario en Excel y responde por audio. | Ollama (qwen3.5:4b), VibeVoice-Realtime-0.5B, PostgreSQL, Excel |
| [Audio a texto con Qwen3-ASR](02-voz-y-audio/audio-a-texto-qwen3-asr.md) | Interfaz web para transcribir audio a texto con un modelo Qwen3-ASR local. | Qwen3-ASR, Python |
| [Chatbot que responde por voz](02-voz-y-audio/chatbot-responde-por-voz.md) | Chatbot web que recibe preguntas por texto y contesta con voz sintetizada. | Ollama (ministral-3:8b), API de Gradium (TTS) |
| [Clonar voz con Qwen3-TTS](02-voz-y-audio/clonar-voz-qwen3-tts.md) | App web para clonar voz a partir del modelo base Qwen3-TTS, ejecutable en CPU o GPU. | Qwen3-TTS, Python |

### [RAG y chat con documentos](03-rag-y-chat-con-documentos/)

Aplicaciones para conversar con PDFs y bases de conocimiento usando RAG y embeddings.

| Prompt | Descripción | Tecnologías |
| --- | --- | --- |
| [Cambiar la fuente de datos de una LLM Wiki (Karpathy)](03-rag-y-chat-con-documentos/llm-wiki-karpathy.md) | Ajusta una LLM Wiki basada en la propuesta de Andrej Karpathy para que lea los documentos desde otra carpeta. | LLM Wiki, Claude |
| [Chat con PDFs usando RAG-Anything](03-rag-y-chat-con-documentos/chat-pdfs-rag-anything.md) | App web en PHP para chatear con PDFs (con imágenes, tablas y figuras) organizados por categorías, con historial. | PHP, RAG-Anything, PostgreSQL + pgvector, Ollama, OpenAI, Gemini |
| [Chatbot para preguntar sobre un PDF](03-rag-y-chat-con-documentos/chatbot-pdf-ollama.md) | Chatbot en HTML, CSS y JS que vectoriza un PDF y responde solo sobre su contenido. | Ollama (qwen3:8b), nomic-embed-text, SQLite |
| [Clon de ChatPDF con citas](03-rag-y-chat-con-documentos/clon-chatpdf-con-citas.md) | App web tipo ChatPDF que muestra las citas de origen de cada respuesta y navega hasta ellas en el documento. | RAG, visor de PDF |

### [MCP y automatización](04-mcp-y-automatizacion/)

Servidores MCP, flujos en n8n, OpenClaw y automatizaciones conectadas a aplicaciones.

| Prompt | Descripción | Tecnologías |
| --- | --- | --- |
| [App web para controlar Photoshop con MCP y Ollama](04-mcp-y-automatizacion/app-web-photoshop-mcp-ollama.md) | Interfaz web que envía instrucciones en lenguaje natural a modelos locales para operar Photoshop mediante un servidor MCP. | MCP, Ollama, Adobe Photoshop |
| [Chatbot de WhatsApp para venta de ropa](04-mcp-y-automatizacion/chatbot-whatsapp-venta-ropa.md) | Chatbot de ventas que funciona dentro de WhatsApp Web con un modelo local. Incluye un segundo prompt para convertirlo en un sistema de citas médicas. | MCP de WhatsApp, Go, Ollama (ministral-3:8b), SQLite |
| [MCP para conectar Claude Desktop con n8n](04-mcp-y-automatizacion/mcp-claude-desktop-n8n.md) | Servidor MCP para crear, buscar y editar workflows y nodos de n8n local desde Claude Desktop. | MCP, n8n, Claude Desktop |
| [OpenClaw: inventario y reportes de una tienda](04-mcp-y-automatizacion/openclaw-inventario-tienda.md) | Automatización con OpenClaw: app de inventario, gráficas de ventas, alertas diarias de stock y resumen por audio. | OpenClaw, SQLite |
| [Workflow n8n: chatbot RAG para una universidad](04-mcp-y-automatizacion/n8n-chatbot-rag-universidad.md) | Workflow en n8n local con un chatbot que responde sobre carreras, matrículas y horarios a partir de PDFs. | n8n, Ollama (qwen3:8b), nomic-embed-text, PostgreSQL + pgvector |

### [Plataformas web](05-plataformas-web/)

Plataformas full-stack completas: portales, gestión de clubes, pollas, SaaS y landing pages.

| Prompt | Descripción | Tecnologías |
| --- | --- | --- |
| [Landing page para venta de celulares](05-plataformas-web/landing-page-venta-celulares.md) | Landing page moderna y orientada a conversión para una tienda de celulares en Colombia. | HTML, CSS, JavaScript |
| [Plataforma colaborativa de mapas mentales con IA](05-plataformas-web/plataforma-mapas-mentales-ia.md) | SaaS de mapas mentales, diagramas y pizarra colaborativa en tiempo real con asistente de IA. | Next.js, NestJS, PostgreSQL, Redis, Yjs, OpenAI |
| [Plataforma de gestión de un club deportivo](05-plataformas-web/plataforma-club-deportivo.md) | Gestión integral de un club: socios, categorías, equipos, eventos, membresías, asistencia y documentos. | NestJS, React + Vite, PostgreSQL + pgvector, MCP |
| [Polla futbolera del Mundial 2026](05-plataformas-web/polla-futbolera-mundial-2026.md) | Plataforma de pronósticos del Mundial 2026 con puntuación, ranking, premios y análisis con IA. | NestJS, React + Vite, PostgreSQL + pgvector |
| [Portal web del ciclo de vida de mascotas](05-plataformas-web/portal-ciclo-de-vida-mascotas.md) | Portal para gestionar la vida de un perro (vacunas, salud, crecimiento, seguros, memorial). Incluye la idea original y 3 prompts encadenados. | MySQL, MCP, full-stack |

### [Educación e investigación](06-educacion-e-investigacion/)

Plataformas educativas, laboratorios virtuales, recursos para docentes y redacción académica.

| Prompt | Descripción | Tecnologías |
| --- | --- | --- |
| [GPT para crear syllabus por competencias](06-educacion-e-investigacion/gpt-creador-de-syllabus.md) | Instrucciones para un GPT personalizado que construye syllabus de 16 semanas basados en competencias. | GPT personalizado (ChatGPT) |
| [Laboratorio virtual de redes (topología estrella)](06-educacion-e-investigacion/laboratorio-virtual-redes.md) | Simulación 3D interactiva de una red en estrella con configuración de IP y pruebas de conectividad. | Three.js r128, JavaScript |
| [Pizarra interactiva para explicar IA](06-educacion-e-investigacion/pizarra-ia-interactiva.md) | Pizarra tipo canvas para construir diagramas sobre LLM, RAG, agentes, MCP y más, arrastrando y conectando objetos. | HTML, CSS, JavaScript |
| [Plantilla para un proyecto de investigación (paper)](06-educacion-e-investigacion/plantilla-paper-investigacion.md) | Plantilla (en inglés) para un proyecto de investigación en varias fases, adaptable a cualquier área. | Cualquier LLM |
| [Plataforma de cursos virtuales (LMS)](06-educacion-e-investigacion/plataforma-cursos-virtuales.md) | LMS completo inspirado en Platzi, Coursera, edX y Udemy, con búsqueda semántica y recomendaciones. | PostgreSQL + pgvector, MCP, full-stack |
| [Plataforma educativa con IA para docentes](06-educacion-e-investigacion/plataforma-educativa-docentes.md) | Plataforma para generar actividades educativas con IA, con sistema de créditos y exportación a Word o Excel. | MySQL o PostgreSQL, Ollama, OpenAI, Gemini |
| [Simulador 3D para ensamblar un PC](06-educacion-e-investigacion/ensamble-pc-3d.md) | App educativa 3D para aprender a identificar y ensamblar los componentes de un computador. | Three.js |

### [Juegos](07-juegos/)

Videojuegos web 2D y 3D en un solo archivo HTML.

| Prompt | Descripción | Tecnologías |
| --- | --- | --- |
| [Carrera de Fórmula 1 en 3D](07-juegos/carreras-f1-3d.md) | Simulación 3D de una carrera de F1 con conducción manual o automática y tres cámaras. | Three.js r182 |
| [Juego de plataformas 2D estilo Mario](07-juegos/plataformas-2d-estilo-mario.md) | Juego de plataformas retro de 8 bits en un solo archivo HTML. | HTML, CSS, JavaScript |
| [Juego de resortera con física 2D](07-juegos/juego-resortera-fisica-2d.md) | Puzzle de física con resortera inspirado en Angry Birds, sin recursos protegidos. | Canvas, Web Audio API |
| [Space Invaders 3D](07-juegos/space-invaders-3d.md) | Versión 3D de Space Invaders con gráficos de primitivas y audio sintético. | Three.js r182, Web Audio API |

### [Apps 3D e interactivas](08-apps-3d-e-interactivas/)

Escenas y aplicaciones interactivas con Three.js y simuladores en el navegador.

| Prompt | Descripción | Tecnologías |
| --- | --- | --- |
| [Clon de Excel con Three.js](08-apps-3d-e-interactivas/clon-excel-threejs.md) | Hoja de cálculo tipo Excel renderizada con WebGL en un único archivo HTML. | Three.js, JavaScript |
| [Editor LEGO 3D](08-apps-3d-e-interactivas/editor-lego-3d.md) | Editor de construcción con piezas tipo LEGO en un único index.html. | Three.js |
| [Sala 3D con televisor](08-apps-3d-e-interactivas/sala-3d-con-tv.md) | Escena 3D de una sala con un televisor que muestra una animación procedimental. | Three.js |
| [Simulador de Windows 11](08-apps-3d-e-interactivas/simulador-windows-11.md) | Escritorio de Windows 11 funcional en el navegador: barra de tareas, menú inicio y ventanas. | HTML, CSS, JavaScript |
| [Sistema solar 3D de empresas](08-apps-3d-e-interactivas/sistema-solar-empresas-3d.md) | Sistema solar en 3D donde cada planeta es una de las empresas más valiosas, con vista alternativa de gráfico de torta. | Three.js r182 |

### [Visión por computador](09-vision-por-computador/)

Detección de rostro, manos y movimiento con MediaPipe, OpenCV y YOLO.

| Prompt | Descripción | Tecnologías |
| --- | --- | --- |
| [Detector de emociones faciales en tiempo real](09-vision-por-computador/emociones-faciales-mediapipe.md) | App web que estima emociones con la cámara usando landmarks faciales 3D. | MediaPipe, Three.js |
| [Monitor de ejercicios con YOLO](09-vision-por-computador/monitor-ejercicios-yolo.md) | Analiza un video y cuenta en tiempo real sentadillas, flexiones y dominadas. | Ultralytics YOLO, PHP, Python, CUDA |
| [Navegar en la web con la mano](09-vision-por-computador/navegar-web-con-la-mano.md) | Control del navegador con gestos de la mano: scroll, clic, doble clic y clic derecho. | Python, OpenCV, MediaPipe, PyAutoGUI |

### [Video y presentaciones](10-video-y-presentaciones/)

Editores de video con IA y generadores de diapositivas.

| Prompt | Descripción | Tecnologías |
| --- | --- | --- |
| [Generador de diapositivas estilo Gamma](10-video-y-presentaciones/generador-diapositivas.md) | Programa para crear presentaciones a partir de un tema o un PDF, con imágenes generadas o buscadas en internet. | Google AI Studio, Gemini API, Nano Banana Pro |
| [Prompt maestro: editor de video con IA (local)](10-video-y-presentaciones/editor-video-ia-local.md) | Editor de video web con IA que se ejecuta en Windows sin Docker: línea de tiempo, subtítulos, edición por transcripción y render con FFmpeg. | Next.js, NestJS/Fastify, PostgreSQL 17, Prisma, pg-boss, FFmpeg, OpenAI |
| [Prompt maestro: plataforma SaaS de edición de video con IA](10-video-y-presentaciones/plataforma-edicion-video-ia.md) | Plataforma profesional de edición de video con IA para la nube: colaboración, almacenamiento S3, colas y planes con créditos. | Next.js, NestJS, PostgreSQL, Redis, S3, FFmpeg, OpenAI |

### [Generación de imágenes](11-generacion-de-imagenes/)

Prompts y recursos para generar imágenes con IA.

| Prompt | Descripción | Tecnologías |
| --- | --- | --- |
| [Prompts para crear imágenes](11-generacion-de-imagenes/prompts-para-imagenes.md) | Colección de prompts descriptivos para generar imágenes fotorrealistas y artísticas. | Cualquier generador de imágenes |
| [Recursos: repositorios de prompts de imágenes](11-generacion-de-imagenes/recursos-prompts-imagenes.md) | Enlace a una colección pública de prompts para generar imágenes. | Referencia |

## Licencia

Distribuido bajo la licencia [MIT](LICENSE).
