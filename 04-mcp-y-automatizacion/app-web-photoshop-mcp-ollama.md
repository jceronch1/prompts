# App web para controlar Photoshop con MCP y Ollama

**Categoría:** [MCP y automatización](README.md) · **Tecnologías:** MCP, Ollama, Adobe Photoshop

Interfaz web que envía instrucciones en lenguaje natural a modelos locales para operar Photoshop mediante un servidor MCP.

> **Antes de usarlo, reemplaza:** `[RUTA_DEL_MCP_DE_PHOTOSHOP]`

## Prompt

```text
Actúa como un arquitecto de software senior, experto en desarrollo web, integración de MCP Server, Ollama, modelos locales de IA y automatización de Adobe Photoshop.

CONTEXTO:
Quiero construir una aplicación web que permita conectar un MCP Server personalizado para Adobe Photoshop versión 27. El MCP ya fue construido y se encuentra en la siguiente ruta local de Windows:

[RUTA_DEL_MCP_DE_PHOTOSHOP]

También tengo instalado Ollama en mi computador, con varios modelos locales disponibles, y quiero que la aplicación web permita conectar esos modelos con Photoshop 27 a través del MCP.

OBJETIVO GENERAL:
Crear una app web que funcione como una interfaz de control para enviar instrucciones en lenguaje natural a modelos locales ejecutados con Ollama, y que estos modelos puedan interactuar con Photoshop 27 mediante el MCP Server ubicado en la ruta indicada.

REQUERIMIENTOS FUNCIONALES:
1. Crear una aplicación web moderna, clara y fácil de usar.
2. Permitir configurar la ruta del MCP:
   [RUTA_DEL_MCP_DE_PHOTOSHOP]
3. Detectar o permitir seleccionar modelos locales instalados en Ollama.
4. Permitir escribir prompts en lenguaje natural para controlar Photoshop 27.
5. Conectar la app web con Ollama para enviar instrucciones al modelo seleccionado.
6. Conectar la respuesta del modelo con el MCP Server de Photoshop 27.
7. Permitir ejecutar todas las acciones que tiene el MCP

REQUERIMIENTOS TÉCNICOS:
Propón la mejor arquitectura posible para Windows local, usando tecnologías web modernas. Puedes sugerir una de estas opciones:

Opción A:
Frontend: HTML, CSS y JavaScript
Backend: Node.js con Express
Comunicación con Ollama: API local de Ollama
Comunicación con MCP: ejecución o conexión con el servidor MCP local

Opción B:
Frontend: React
Backend: Node.js con Express
Comunicación con Ollama y MCP desde el backend

Opción C:
Frontend: HTML, CSS y JavaScript
Backend: Python con FastAPI
Comunicación con Ollama y MCP desde Python

Debes recomendar cuál opción es mejor y explicar por qué.

TAREAS QUE DEBES REALIZAR:
1. Analizar la arquitectura ideal para conectar:
   App Web → Backend → Ollama → MCP Photoshop 27 → Adobe Photoshop 27

2. Explicar cómo debe funcionar el flujo de comunicación.

3. Proponer la estructura de carpetas del proyecto.

4. Crear el código base completo de la aplicación.

5. Incluir:
   - Frontend.
   - Backend.
   - Archivo de configuración.
   - Servicio para conectarse a Ollama.
   - Servicio para conectarse al MCP de Photoshop.
   - Controlador para procesar prompts.
   - Manejo de errores.
   - Instrucciones de instalación.
   - Comandos para ejecutar el proyecto.

6. El sistema debe permitir seleccionar el modelo de Ollama desde la interfaz.

7. El sistema debe permitir probar la conexión con:
   - Ollama.
   - MCP Photoshop 27.
   - Photoshop 27.

8. Crear un ejemplo de prompt de prueba como:
   “Abre Photoshop, crea un documento de 1080x1080 píxeles, agrega un fondo azul oscuro, coloca el texto ‘Curso MCP Photoshop 27’ en el centro y exporta la imagen como PNG”.

9. Explicar cómo adaptar el sistema si el MCP usa:
   - STDIO.
   - HTTP.
   - WebSocket.

10. Incluir recomendaciones de seguridad para ejecutar comandos locales desde una app web.

11. Entrega
Debes entregar una appweb funcional lista para solicitar imágenes u objetos para que se realicen el Photoshop
```
