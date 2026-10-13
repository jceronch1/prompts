# Agente de ventas de ropa por voz

**Categoría:** [Voz y audio](README.md) · **Tecnologías:** Ollama (qwen3.5:4b), VibeVoice-Realtime-0.5B, PostgreSQL, Excel

Agente web de ventas que consulta un inventario en Excel y responde por audio.

> **Antes de usarlo, reemplaza:** `[RUTA_DEL_EXCEL_DE_INVENTARIO]`, `[RUTA_DEL_MODELO_VIBEVOICE]`

## Prompt

```text
Crear un agente web de venta de ropa llamado “Ruby”. Para chatear usar el modelo qwen3.5:4b que lo tengo instalado en mi computador con Ollama como puedes ver en la imagen adjunta, además se debe crear las tablas y registros necesarios en la base de datos “prueba” que está en PostgreSQL usando su MCP.  Para crear esta base de datos se debe tener en cuenta la información del archivo de Excel que está en la ruta:
"[RUTA_DEL_EXCEL_DE_INVENTARIO]"
además, quiero que el agente me conteste por audio con el modelo VibeVoice-Realtime-0.5B que ya este descargado en la ruta:
[RUTA_DEL_MODELO_VIBEVOICE]
```
