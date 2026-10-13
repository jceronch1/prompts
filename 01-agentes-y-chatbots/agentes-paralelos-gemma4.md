# Agentes paralelos con Gemma 4

**Categoría:** [Agentes y chatbots](README.md) · **Tecnologías:** Gemma, llama.cpp, Ollama, FastAPI

App web para ejecutar varios agentes de IA en paralelo con modelos locales en una GPU de 8 GB.

## Prompt

```text
Actúa como arquitecto senior de software especializado en IA local, modelos Gemma, llama.cpp, Ollama, FastAPI y aplicaciones web en Windows 11.

Quiero crear una aplicación web inspirada en el repositorio:
https://github.com/google-gemma/cookbook/tree/main/apps/concurrent

Objetivo:
Construir una app web para ejecutar varios agentes de IA en paralelo usando modelos locales en mi equipo Windows 11 con GPU NVIDIA RTX 4070 Laptop de 8 GB VRAM.

Contexto técnico:
- Sistema operativo: Windows 11
- GPU: NVIDIA RTX 4070 Laptop GPU de 8 GB VRAM
- Modelos locales: Ollama y/o modelos GGUF ejecutados con llama.cpp
- Quiero poder usar modelos como Gemma, Qwen, Llama u otros modelos locales
- La app original del repositorio está pensada para macOS, pero necesito una versión compatible con Windows

Requisitos funcionales:
1. Crear una interfaz web donde el usuario escriba un tema o instrucción principal.
2. Permitir seleccionar el número de agentes concurrentes: 2, 4, 6, 8 o 10.
3. Permitir elegir escenarios:
   - Generar ideas
   - Traducir texto
   - Generar código
   - Crear SVG
   - Resumir documentos
   - Crear publicaciones para redes sociales
   - Debate entre agentes
4. Cada agente debe recibir una instrucción diferente.
5. Un agente orquestador debe organizar, comparar y resumir las respuestas.
6. Mostrar en pantalla el estado de cada agente en tiempo real.
7. Mostrar el resultado final consolidado.
8. Permitir configurar endpoint local:
   - Ollama: http://localhost:11434
   - llama-server: http://localhost:8080

Requisitos técnicos:
- Backend en Python con FastAPI.
- Frontend en React o HTML/CSS/JavaScript.
- Uso de asyncio para ejecutar agentes concurrentes.
- Comunicación en tiempo real con WebSockets o Server-Sent Events.
- Archivo de configuración para modelos, número de agentes, temperatura, contexto y endpoint.
- Código limpio, modular y documentado.
- Compatible con Windows 11.

Estructura esperada:
- backend/
  - main.py
  - agents.py
  - orchestrator.py
  - model_client.py
  - scenarios.py
  - config.py
- frontend/
  - index.html
  - app.js
  - styles.css
- README.md
- requirements.txt

Entrega:
Entrega la app web listar para funcionar.
```
