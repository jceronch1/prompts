# Chatbot de WhatsApp para venta de ropa

**Categoría:** [MCP y automatización](README.md) · **Tecnologías:** MCP de WhatsApp, Go, Ollama (ministral-3:8b), SQLite

Chatbot de ventas que funciona dentro de WhatsApp Web con un modelo local. Incluye un segundo prompt para convertirlo en un sistema de citas médicas.

> **Antes de usarlo, reemplaza:** `[RUTA_DEL_PROYECTO]`

## Prompt

```text
Crear un Chatbot para WhatsApp para venta de Ropa a partir de un MCP que construí que está en un video de YouTube Claude Desktop + MCP + WhatsApp
A partir de todo ese contenido, quiero que crees un Chatbot de venta de ropa para que funcione directamente dentro de WhatsApp web directamente.
Para esto ten en cuenta que debe funcional con las siguientes herramientas
1.	Tengo instalado Ollama en Windows 11 en mi PC
2.	Tengo instalado el llm ministral-3:8b en mi PC
3.	Tengo instalado go
4.	Tengo instado gcc.exe en la ruta C:\msys64\ucrt64\bin
5.	No quiero trabajar con Claude Desktop
6.	Debes trabajar con la base de datos SQLite
Nota: hice un directorio en blanco para que crees todo lo necesario para que funcione en la ruta
[RUTA_DEL_PROYECTO]

citas medicas
Crea solo el sistema robusto de citas Médicas, quita todas las demás profesiones.
además, realiza una pagina web donde salga el calendario y el médico pueda seleccionar días y horas que puede atender, para que esto este conectado con la base de datos SQLite de las citas, para que cuando alguien pida la cita en WhatsApp, salga esa cita en la web y se pueda ver.
Para la cita se debe pedir los siguientes datos del paciente: Nombres y apellidos, cedula, celular y correo.
```
