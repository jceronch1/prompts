# Cambiar la fuente de datos de una LLM Wiki (Karpathy)

**Categoría:** [RAG y chat con documentos](README.md) · **Tecnologías:** LLM Wiki, Claude

Ajusta una LLM Wiki basada en la propuesta de Andrej Karpathy para que lea los documentos desde otra carpeta.

> **Antes de usarlo, reemplaza:** `[RUTA_DE_TU_LLM_WIKI]`

## Prompt

```text
He construido una LLM Wiki según lo propuso Andrej Karpathy en su publicación que está en la ruta
https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
Lo que quiero es que hagas los cambios necesarios en todos los archivos y configuraciones para que no tome los datos de la ruta
[RUTA_DE_TU_LLM_WIKI]\Documentos
Sino que tome ahora los datos de la ruta
[RUTA_DE_TU_LLM_WIKI]\papers
```
