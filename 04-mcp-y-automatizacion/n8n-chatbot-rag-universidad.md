# Workflow n8n: chatbot RAG para una universidad

**Categoría:** [MCP y automatización](README.md) · **Tecnologías:** n8n, Ollama (qwen3:8b), nomic-embed-text, PostgreSQL + pgvector

Workflow en n8n local con un chatbot que responde sobre carreras, matrículas y horarios a partir de PDFs.

> **Antes de usarlo, reemplaza:** `[RUTA_DE_LA_CARPETA_CON_LOS_PDF]`, `[TU_CONTRASEÑA_POSTGRES]`, `[TU_USUARIO_POSTGRES]`

## Prompt

```text
Crea un Workflow en n8n local de un Chatbot Asistente de la UniPutumayo para responder preguntas sobre las carreas que se ofrecen, Debe ser amable cordial y contestar únicamente sobre las profesiones que ofrece.
Para ello se debe poder realizar una base de conocimiento con PDF en RAG, que servirá para dar respuestas acertadas. Solo podrás responder a temas sobre las carreras, matriculas y horarios de la U.
Los PDF se encuentran en Windows en la ruta:
[RUTA_DE_LA_CARPETA_CON_LOS_PDF]
Tengo en mi instalado Ollama y el modelo qwen3:8b además para la creación del RAG se puede con nomic-embed-text:latest,
Tengo la base de datos vacía llamada “chatrag” en postgresql con pgvector y los datos de usuario son usuario: [TU_USUARIO_POSTGRES] y pass: [TU_CONTRASEÑA_POSTGRES]
```
