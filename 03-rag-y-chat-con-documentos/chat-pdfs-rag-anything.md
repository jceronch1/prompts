# Chat con PDFs usando RAG-Anything

**Categoría:** [RAG y chat con documentos](README.md) · **Tecnologías:** PHP, RAG-Anything, PostgreSQL + pgvector, Ollama, OpenAI, Gemini

App web en PHP para chatear con PDFs (con imágenes, tablas y figuras) organizados por categorías, con historial.

> **Antes de usarlo, reemplaza:** `[RUTA_DEL_PROYECTO]`, `[TU_API_KEY_DE_GOOGLE]`, `[TU_API_KEY_DE_OPENAI]`, `[TU_CONTRASEÑA_POSTGRES]`, `[TU_USUARIO_POSTGRES]`

## Prompt

```text
carpeta chat-pdf-kiro

Crea una app web para chatear con PDFs. La app debe ser en web php y debe poder

 Subir varios pdfs donde se puedan crear varias categorías y que se pueda chatear directamente con el PDF o con una categoría donde existen varios PDFs
 Las preguntas que se realicen se deben guardar en un histórico tanto la pregunta como la respuesta. Se debe guarda en la base de datos tanto la pregunta como la respuesta.

El sistema se debe crear con

RAG-Anything para todo el manejo de la indexación de los PDfs que tienen imágenes, tablas y texto.
Se coloca en la carpeta rag-any todos los archivos y ejemplos necesarios de RAG-Anything para que busques todo lo que necesites.
se encuentra en la ruta [RUTA_DEL_PROYECTO]\rag-any
Debe obligatoriamente funcionar con RAG-Anything ya que con este sistema se puede chatear con PDFs que tenga imágenes, tablas, figuras.

Ojo aunque RAG-Anything está en Python recuerda que la app debe ser en web php.

PostgreSQL/PGVector. para la base de datos vectorial

también en la base de datos debe haber roles donde puedan acceder usuarios normales donde pueda crear categorías subir sus PDFs y Chatear con ellos, únicamente con los suyo Y también usuario administrador donde tendrá derecho a toda la administración y configuración de las categorías, PDFs. Poder configurar todo lo relacionado con los LLM tanto locales como en la nube, tanto par emebdings, chat, y visión con sus configuraciones.

Mi computador cuenta con los siguientes requisitos
Windows 11
Tiene instalado Ollama
Tiene instalado LLM locales que son:
C:\>ollama list
NAME                          ID              SIZE      MODIFIED
qwen2.5vl:3b                  fb90415cde1e    3.2 GB    6 days ago
qwen3-embedding:4b            df5bd2e3c74c    2.5 GB    6 days ago
qwen2.5:7b                    845dbda0ea48    4.7 GB    2 months ago
qwen3:8b                      500a1f067a9f    5.2 GB    2 months ago
qwen2.5vl:7b                  5ced39dfa4ba    6.0 GB    3 months ago

también debe funcionar con el modelo de Google y el modelo de OpenAI por medio de la apikey.

Ya esta instalado en mi PC  PostregSQL y PG-Vector. base de datos llamada "chat-pdf-kiro"
La conexión a la base de datos PostgreSQL es :
GOOGLE_API_KEY="[TU_API_KEY_DE_GOOGLE]"
OPENAI_API_KEY="[TU_API_KEY_DE_OPENAI]"
DB_HOST="localhost"
DB_PORT="5432"
DB_NAME="chat-pdf-kiro"
DB_USER="[TU_USUARIO_POSTGRES]"
DB_PASSWORD="[TU_CONTRASEÑA_POSTGRES]"

También se tienen instalado Laragon y
la carpeta donde vamos a crear la app esta en la ruta
[RUTA_DEL_PROYECTO]

Debe obligatoriamente funcionar con RAG-Anything ya que con este sistema se puede chatear con PDFs que tenga imágenes, tablas, figuras.

Ojo aunque RAG-Anything está en Python recuerda que la app debe ser en web php.
```
