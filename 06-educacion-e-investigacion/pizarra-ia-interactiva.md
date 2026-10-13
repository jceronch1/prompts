# Pizarra interactiva para explicar IA

**Categoría:** [Educación e investigación](README.md) · **Tecnologías:** HTML, CSS, JavaScript

Pizarra tipo canvas para construir diagramas sobre LLM, RAG, agentes, MCP y más, arrastrando y conectando objetos.

## Prompt

```text
Actúa como un desarrollador senior especializado en aplicaciones web educativas, diagramación visual, interfaces interactivas y herramientas de apoyo para la enseñanza de Inteligencia Artificial.

Quiero construir una pizarra digital interactiva para explicar conceptos de Inteligencia Artificial mediante diagramas, objetos, logos, imágenes, conectores y flujos visuales.

La aplicación debe funcionar como una pizarra tipo “canvas” donde el usuario pueda arrastrar elementos desde una barra lateral de objetos hacia el área de trabajo, organizarlos, conectarlos con líneas y construir diagramas explicativos sobre temas de IA.

Objetivo principal:
Crear una herramienta visual para docentes, estudiantes e investigadores que permita explicar temas como tokens, agentes de IA, LLM, SLM, RAG, bases vectoriales, automatización, MCP, empresas de IA y flujos de funcionamiento de sistemas inteligentes.

Características principales de la pizarra:

1. Área de trabajo
- Crear una pizarra amplia e interactiva.
- Permitir arrastrar y soltar objetos.
- Permitir mover, redimensionar, duplicar y eliminar elementos.
- Permitir hacer zoom y desplazamiento dentro de la pizarra.
- Agregar cuadrícula de fondo para facilitar la organización.
- Permitir alinear objetos automáticamente.
- Permitir guardar y cargar diagramas.

2. Barra lateral de objetos
Debe existir una barra lateral con categorías de elementos relacionados con Inteligencia Artificial. Cada elemento debe poder arrastrarse hacia la pizarra.

Categorías y objetos:

A. Fundamentos y estructura de IA
- Agente de IA: entidad autónoma capaz de ejecutar tareas complejas.
- Chatbot: interfaz básica de conversación.
- Asistente virtual: herramienta de apoyo interactiva.
- Lógica de funcionamiento: razonamiento detrás de la acción del agente.
- Flujo general: entrada, procesamiento y salida de información.
- Token: unidad mínima de texto procesada por un modelo.
- Prompt: instrucción dada a un modelo de IA.
- Contexto: información que el modelo usa para responder.
- Memoria: almacenamiento de información relevante para futuras interacciones.

B. Componentes tecnológicos
- Prompt Engineering: diseño de instrucciones precisas para guiar a la IA.
- SLM, Small Language Models: modelos de lenguaje compactos y eficientes.
- LLM, Large Language Models: modelos de lenguaje de gran escala.
- RAG, Retrieval-Augmented Generation: generación aumentada mediante recuperación de información externa.
- TTS, Text-to-Speech: conversión de texto a voz.
- STT, Speech-to-Text: conversión de voz a texto.
- Embeddings: representación numérica del significado de textos, imágenes o datos.
- Base de datos vectorial: almacenamiento especializado para búsqueda semántica.
- API: interfaz para conectar servicios y aplicaciones.
- MCP, Model Context Protocol: protocolo para conectar modelos de IA con herramientas externas.
- Herramientas: recursos externos usados por los agentes.
- Orquestador: componente que coordina modelos, herramientas y memoria.

C. Aplicaciones y herramientas avanzadas
- Agentes especializados: ventas, atención al cliente, citas, educación, soporte técnico e investigación.
- Automatización: integración de flujos de trabajo sin intervención humana.
- OpenClaw: framework para crear y coordinar agentes.
- Hermes Agent: herramienta para agentes dentro del ecosistema actual.
- Ollama: ejecución local de modelos de IA.
- n8n: automatización de flujos.
- LangChain: construcción de aplicaciones con LLM.
- LlamaIndex: indexación y recuperación de información para IA.
- CrewAI: coordinación de agentes colaborativos.
- AutoGen: creación de sistemas multiagente.

D. Empresas y modelos de IA
Agregar objetos visuales tipo logo, tarjeta o ícono para representar:

Empresas internacionales:
- OpenAI
- Anthropic
- Google
- Google DeepMind
- Meta AI
- Microsoft AI
- NVIDIA
- Mistral AI
- Hugging Face
- Cohere
- xAI

IA y modelos chinos:
- Alibaba Qwen
- Moonshot AI Kimi
- DeepSeek
- Baidu ERNIE
- Tencent Hunyuan
- Zhipu AI GLM
- MiniMax
- SenseTime

Modelos y ecosistemas locales:
- LLaMA
- Gemma
- Mistral
- Qwen
- DeepSeek
- Phi
- Ollama
- LM Studio

3. Sistema de conexión mediante líneas
La pizarra debe permitir crear líneas y conectores entre objetos.

Tipos de líneas:
- Línea recta.
- Línea con flecha.
- Línea curva.
- Conector tipo flujo.
- Conector punteado.
- Conector con etiqueta.

Funciones de las líneas:
- Conectar objetos para crear diagramas de flujo.
- Explicar procesos como:
  - Usuario → Prompt → LLM → Respuesta.
  - Usuario → Chatbot → RAG → Base vectorial → Respuesta.
  - Agente → Herramientas → MCP → Aplicación externa.
  - Voz → STT → LLM → TTS → Respuesta hablada.
- Permitir editar el color, grosor y tipo de línea.
- Permitir agregar texto encima de las conexiones.

4. Diagramas que debe poder construir la aplicación
La pizarra debe facilitar la creación de diagramas como:

- Diagrama de funcionamiento de un LLM.
- Diagrama de tokens y contexto.
- Diagrama de arquitectura RAG.
- Diagrama de agente de IA.
- Diagrama de automatización con n8n.
- Diagrama de MCP: Host, Client y Server.
- Diagrama de flujo de un chatbot.
- Diagrama de asistente virtual con voz.
- Diagrama comparativo entre LLM y SLM.
- Diagrama de ecosistemas de empresas de IA.
- Diagrama de agentes especializados para ventas, citas y atención al cliente.

5. Diseño visual
La interfaz debe ser moderna, limpia, educativa y profesional.

Estilo recomendado:
- Diseño tipo dashboard.
- Colores relacionados con tecnología e IA.
- Íconos claros y fáciles de identificar.
- Tarjetas visuales para cada objeto.
- Texto legible.
- Botones grandes y comprensibles.
- Modo claro y modo oscuro.
- Estilo adecuado para usar en clase, conferencias o videos educativos.

6. Funciones adicionales
Agregar las siguientes opciones:

- Botón para limpiar la pizarra.
- Botón para exportar como imagen PNG.
- Botón para exportar como PDF.
- Botón para guardar el proyecto en JSON.
- Botón para cargar un proyecto guardado.
- Panel de propiedades para editar cada objeto.
- Opción para cambiar color, tamaño, texto e ícono.
- Opción para agregar texto libre.
- Opción para agregar notas explicativas.
- Opción para crear grupos de objetos.
- Opción para bloquear elementos.
- Opción para enviar objetos al frente o al fondo.

7. Requisitos técnicos
Construir la aplicación en HTML, CSS y JavaScript puro, sin depender de backend.

El archivo debe incluir:
- HTML.
- CSS.
- JavaScript.
- Canvas o SVG para la zona de trabajo.
- Funciones de drag and drop.
- Sistema de conexión entre objetos.
- Sistema de exportación.
- Código limpio, comentado y organizado.

Si se usan logos oficiales de empresas, dejar espacios o tarjetas representativas con el nombre de cada empresa. Si no se tienen los archivos de logos, usar íconos, iniciales, tarjetas SVG o representaciones visuales no oficiales.

8. Resultado esperado
Entregar una aplicación web funcional que permita construir visualmente diagramas sobre Inteligencia Artificial, arrastrando objetos desde una barra lateral hacia una pizarra, conectándolos con líneas y explicando conceptos como agentes de IA, tokens, LLM, SLM, RAG, MCP, Ollama, OpenClaw, Hermes Agent y empresas líderes de IA.

El resultado debe ser educativo, visualmente atractivo, fácil de usar y útil para clases, conferencias, talleres y videos explicativos.
```
