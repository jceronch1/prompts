# Agente de citas médicas (LangGraph + MCP)

**Categoría:** [Agentes y chatbots](README.md) · **Tecnologías:** LangGraph, Ollama, MCP, PostgreSQL + pgvector, Python

Arquitectura paso a paso de un agente autónomo de citas médicas con base de conocimiento vectorial.

## Prompt

```text
Actúa como un Arquitecto de Software de IA especializado en el sector salud, sistemas multiagente (LangGraph), modelos locales (Ollama) y el estándar Model Context Protocol (MCP).

Mi objetivo es construir una appweb desde cero el fronted y backend de un Agente de Citas Médicas autónomo y seguro. Actualmente, tengo un servidor MCP llamado postgres_codex ya conectado a una base de datos PostgreSQL vacía llamada citasmedicas (que tiene la extensión pgvector habilitada).

Por favor, genera el código y la arquitectura detallada dividida en los siguientes pasos:

PASO 1: Diseño de la Base de Datos (PostgreSQL + pgvector) Escribe los scripts SQL (DDL) para crear toda la estructura de la base de datos citasmedicas. La clínica necesita al menos las siguientes tablas:

pacientes (datos básicos y DNI).
medicos (nombre, especialidad, horario de atención).
citas (id_paciente, id_medico, fecha, hora, estado).
base_conocimiento (tabla vectorial usando pgvector para almacenar las políticas de la clínica, preparación para exámenes y qué especialidad trata qué síntomas, con una columna de embeddings). Asegúrate de incluir datos de prueba (INSERTs) para poder probar el agente.

PASO 2: Integración de Herramientas vía MCP Sabiendo que el agente se comunicará con la base de datos a través del MCP postgres_codex, redacta el código en Python que define las herramientas (Tools) que el agente usará a través de este MCP. Las herramientas necesarias son:

verificar_disponibilidad: Consulta horarios libres de un médico.
agendar_cita: Inserta un nuevo registro en la tabla citas.
buscar_politicas_rag: Realiza una búsqueda de similitud vectorial (Semantic Search) en la tabla base_conocimiento basada en los síntomas o dudas del usuario.

PASO 3: Orquestación con LangGraph Crea el código de Python utilizando LangGraph para definir la máquina de estados del agente. El flujo debe incluir:
Definición del Estado (AgentState): Utiliza TypedDict o Pydantic para definir el estado (mensajes, contexto del paciente, paso actual).
Nodos (Nodes): Crea las funciones para los nodos principales:
recepcion_triaje: Analiza la solicitud.
recuperacion_rag: Usa la herramienta del MCP para buscar a qué especialista derivar.
gestion_calendario: Usa la herramienta del MCP para ver/agendar la cita.
ejecutor_herramientas: Nodo que ejecuta la llamada al MCP.
Aristas y Enrutamiento Condicional (Edges): Define la lógica para mover el flujo de un nodo a otro (ej. si el agente decide llamar a una herramienta del MCP, debe ir al nodo ejecutor).
Usa un modelo local a través de Ollama (ej. llama3 o qwen) como el motor de razonamiento (LLM) del agente.

PASO 4: Guardarraíles Médicos y Prompt del Sistema Genera el System Prompt exacto que debe usar el modelo local. Este prompt debe incluir restricciones críticas de salud:
Cero Diagnósticos: El agente tiene estrictamente prohibido diagnosticar o medicar.
Derivación de Emergencias: Si detecta una emergencia vital, debe interrumpir el flujo y sugerir ir a urgencias.
Dependencia estricta de la BD: Solo puede ofrecer horarios y médicos que le devuelva el MCP postgres_codex; no puede inventar (alucinar) información.
```
