# Agente web de citas médicas con IA (versión completa)

**Categoría:** [Agentes y chatbots](README.md) · **Tecnologías:** Python, LangGraph, Ollama, PostgreSQL + pgvector, MCP, Streamlit

Proyecto completo y ejecutable de un agente de citas médicas con frontend, backend, RAG y guía de ejecución en Windows 11.

> **Antes de usarlo, reemplaza:** `[TU_CONTRASEÑA_POSTGRES]`, `[TU_USUARIO_POSTGRES]`

## Prompt

```text
Actúa como un Arquitecto de Software Full-Stack Senior, Especialista en IA Agéntica, LangGraph, Ollama, PostgreSQL, pgvector, MCP y desarrollo de aplicaciones web en Python.

MISIÓN PRINCIPAL

Debes construir un proyecto funcional y completo llamado:

Agente Web de Citas Médicas con IA

No quiero una explicación teórica.
No quiero una guía incompleta.
No quiero pseudocódigo.
No quiero fragmentos aislados.

Quiero que generes una aplicación web real, lista para ejecutar en Windows 11, donde cualquier usuario pueda ingresar desde el navegador, conversar con un agente de IA y solicitar una cita médica.

La aplicación debe quedar preparada para:

1. Abrirse en el navegador mediante Streamlit.
2. Mostrar una interfaz web clara y sencilla.
3. Permitir al usuario escribir en un chat.
4. Permitir seleccionar un modelo local de Ollama.
5. Consultar médicos disponibles en PostgreSQL.
6. Orientar al usuario hacia una especialidad según sus síntomas, sin diagnosticar.
7. Solicitar nombre, contacto, especialidad, fecha y hora.
8. Verificar disponibilidad real en la base de datos.
9. Agendar la cita en PostgreSQL.
10. Confirmar la cita al usuario.
11. Generar automáticamente un comprobante PDF.
12. Mostrar la ruta del PDF generado.
13. Funcionar localmente en Windows 11.

CONTEXTO TÉCNICO

Trabajo en Windows 11.

Tengo instalado:

- Python 3.11 o superior.
- PostgreSQL 17.
- Base de datos vacía llamada: citas_m.
- Extensión pgvector habilitada.
- Ollama instalado localmente.
- API local de Ollama en: http://localhost:11434.
- Servidor MCP llamado postgres_codex conectado a PostgreSQL.
- La base de datos citas_m aún está vacía.

La aplicación debe usar Streamlit como frontend principal.

OBJETIVO FINAL DEL PROYECTO

Cuando termine de crear el proyecto, yo debo poder ejecutar:

streamlit run app.py

Y luego ingresar desde el navegador a la AppWeb para pedir una cita médica hablando con el agente de IA.

La experiencia esperada del usuario debe ser similar a esta:

Usuario:
Buenos días, quiero pedir una cita médica.

Agente:
Buenos días. Con gusto le ayudo a solicitar su cita médica. ¿Me puede indicar su nombre completo y un número de contacto?

Usuario:
Me llamo Carlos Pérez y mi contacto es 3101234567.

Agente:
Gracias, Carlos. ¿Desea una cita con alguna especialidad específica o desea contarme de forma general el motivo de la consulta?

Usuario:
Tengo dolor de estómago frecuente.

Agente:
No puedo emitir diagnósticos médicos, pero por la información general que indica, podría orientarlo hacia medicina general o gastroenterología. Voy a consultar disponibilidad real.

Agente:
Tengo disponible al Dr. Juan Martínez, Medicina General, el 2026-05-10 a las 9:00 a.m. ¿Desea confirmar esta cita?

Usuario:
Sí, confirmo.

Agente:
Su cita fue agendada correctamente. He generado el comprobante en PDF.

Ruta del comprobante:
C:\...\comprobantes\cita_1.pdf

REQUISITOS OBLIGATORIOS

Debes generar el proyecto completo con esta estructura:

agente_citas_medicas/
│
├── app.py
├── requirements.txt
├── .env.example
├── README.md
│
├── database/
│   ├── schema.sql
│   └── seed.sql
│
├── agent/
│   ├── graph.py
│   ├── state.py
│   ├── prompts.py
│   └── nodes.py
│
├── tools/
│   ├── mcp_tools.py
│   ├── pdf_tool.py
│   └── ollama_tools.py
│
├── services/
│   ├── db.py
│   └── embeddings.py
│
└── comprobantes/
    └── .gitkeep

Debes entregar el contenido completo de cada archivo.

No omitas código.
No escribas “aquí iría”.
No entregues solo partes.
No entregues solamente arquitectura.
Genera una versión funcional mínima, pero completa.

PASO 1: BASE DE DATOS POSTGRESQL 17 + PGVECTOR

Crea los archivos:

database/schema.sql
database/seed.sql

La base de datos debe incluir las siguientes tablas:

1. pacientes

Campos:

- id
- nombre
- contacto
- fecha_creacion

2. medicos

Campos:

- id
- nombre
- especialidad
- horario_atencion
- activo

3. citas

Campos:

- id
- id_paciente
- id_medico
- fecha
- hora
- estado
- observaciones
- fecha_creacion

4. base_conocimiento

Campos:

- id
- especialidad
- sintomas
- descripcion
- embedding vector

Requisitos SQL:

- Usar CREATE EXTENSION IF NOT EXISTS vector;
- Crear llaves primarias.
- Crear llaves foráneas.
- Crear restricciones básicas.
- Crear índices.
- Crear índice vectorial si aplica.
- Insertar médicos de prueba.
- Insertar pacientes de prueba.
- Insertar registros de conocimiento general sobre especialidades médicas.
- No incluir diagnósticos.
- La tabla base_conocimiento solo debe servir para orientar hacia una especialidad.

IMPORTANTE SOBRE EMBEDDINGS

Si no puedes calcular embeddings reales dentro del SQL, debes dejar preparado el campo vector y explicar cómo se llenará usando services/embeddings.py.

PASO 2: FRONTEND WEB CON STREAMLIT

Crea el archivo:

app.py

La interfaz debe tener:

1. Título:

Agente IA de Citas Médicas

2. Descripción breve:

Sistema local para solicitar citas médicas usando IA, Ollama, PostgreSQL, pgvector y generación automática de comprobantes PDF.

3. Barra lateral con:

- Estado de Ollama.
- Selector de modelo instalado en Ollama.
- Estado de conexión a PostgreSQL.
- Botón para limpiar conversación.

4. Chat principal:

- Entrada de texto del usuario.
- Historial de conversación.
- Respuestas del agente.
- Mensajes de error controlados.
- Visualización de la cita confirmada.
- Visualización de la ruta del PDF generado.

5. Validaciones:

- Si Ollama no está activo, mostrar advertencia clara.
- Si no hay modelos instalados, mostrar mensaje claro.
- Si PostgreSQL no responde, mostrar error controlado.
- Si faltan datos para agendar, el agente debe solicitarlos.

PASO 3: CONEXIÓN CON OLLAMA

Crea el archivo:

tools/ollama_tools.py

Debe incluir funciones funcionales:

1. listar_modelos_ollama()

Debe consultar:

http://localhost:11434/api/tags

Y devolver los modelos instalados.

2. generar_respuesta_ollama(modelo, mensajes)

Debe enviar mensajes al modelo seleccionado usando la API local de Ollama.

3. verificar_ollama()

Debe comprobar si Ollama está activo.

4. Manejo de errores:

- Ollama apagado.
- No hay modelos instalados.
- Modelo no disponible.
- Error de conexión.

PASO 4: SERVICIOS DE BASE DE DATOS

Crea el archivo:

services/db.py

Debe incluir:

- Lectura de variables desde .env.
- Conexión a PostgreSQL.
- Función get_connection().
- Función test_connection().
- Función execute_query().
- Función fetch_all().
- Función fetch_one().
- Cierre seguro de conexiones.
- Manejo básico de errores.

PASO 5: EMBEDDINGS CON OLLAMA

Crea el archivo:

services/embeddings.py

Debe incluir:

1. generar_embedding(texto)

Debe usar la API local de Ollama para generar embeddings.

Modelo recomendado:

nomic-embed-text

Debe leer el modelo desde:

OLLAMA_EMBEDDING_MODEL

También debe permitir usar:

embeddinggemma

Debe manejar errores si el modelo de embeddings no está instalado.

PASO 6: HERRAMIENTAS DEL AGENTE

Crea el archivo:

tools/mcp_tools.py

Este archivo debe permitir dos modos:

1. Modo MCP real.
2. Modo directo con PostgreSQL para pruebas locales.

Debe leer la variable:

USE_MCP=false

Si USE_MCP=false, debe usar psycopg2 directamente contra PostgreSQL.

Si USE_MCP=true, debe dejar preparada la estructura para llamar al servidor MCP postgres_codex.

Debes implementar estas herramientas:

1. buscar_especialista_rag(sintomas_usuario)

Debe:

- Generar embedding del texto del usuario.
- Consultar la tabla base_conocimiento usando pgvector.
- Retornar especialidades sugeridas.
- No diagnosticar.
- Solo orientar.

2. verificar_disponibilidad(especialidad, fecha, hora)

Debe:

- Buscar médicos activos por especialidad.
- Verificar que no tengan cita ocupada en esa fecha y hora.
- Retornar médicos disponibles reales.
- No inventar horarios.
- No inventar médicos.

3. agendar_cita(nombre_paciente, contacto, id_medico, fecha, hora, observaciones)

Debe:

- Crear el paciente si no existe.
- Reutilizar el paciente si ya existe.
- Verificar nuevamente disponibilidad antes de agendar.
- Insertar la cita en la tabla citas.
- Retornar todos los datos completos de la cita:
  - id_cita
  - paciente
  - contacto
  - médico
  - especialidad
  - fecha
  - hora
  - estado
  - observaciones

PASO 7: GENERACIÓN DE PDF

Crea el archivo:

tools/pdf_tool.py

Debe implementar:

generar_comprobante_pdf(datos_cita)

La función debe:

- Crear automáticamente la carpeta comprobantes si no existe.
- Usar fpdf2 o reportlab.
- Generar un PDF claro y ordenado.
- Guardar el PDF con un nombre único.
- Retornar la ruta absoluta del archivo.

El PDF debe incluir:

- Título: Comprobante de Cita Médica.
- Número de cita.
- Nombre del paciente.
- Contacto.
- Médico.
- Especialidad.
- Fecha.
- Hora.
- Estado.
- Observaciones.
- Fecha de generación.
- Nota de seguridad: Este comprobante no representa diagnóstico médico.

PASO 8: ESTADO DEL AGENTE

Crea el archivo:

agent/state.py

Debe definir el estado del agente usando TypedDict o Pydantic.

El estado debe incluir:

- messages
- modelo_seleccionado
- nombre_paciente
- contacto
- sintomas
- especialidad_sugerida
- especialidad_confirmada
- fecha_deseada
- hora_deseada
- medicos_disponibles
- id_medico_seleccionado
- datos_cita
- cita_confirmada
- ruta_pdf
- siguiente_accion
- error

PASO 9: SYSTEM PROMPT Y GUARDARRAÍLES

Crea el archivo:

agent/prompts.py

Debe contener un SYSTEM_PROMPT estricto para el agente.

El prompt debe ordenar:

1. Actuar como recepcionista médico empático, claro y formal.
2. Ayudar únicamente a solicitar y agendar citas médicas.
3. No diagnosticar.
4. No recomendar medicamentos.
5. No formular tratamientos.
6. No reemplazar a un médico.
7. Si hay síntomas graves, recomendar acudir a urgencias.
8. Usar herramientas para consultar médicos y horarios.
9. Nunca inventar disponibilidad.
10. Nunca inventar médicos.
11. Nunca inventar citas.
12. Pedir los datos faltantes de forma ordenada.
13. Antes de agendar, pedir confirmación explícita.
14. Después de agendar, generar PDF obligatoriamente.
15. Responder siempre en español.
16. Mantener privacidad de datos del paciente.

También debe incluir una lista de síntomas de alerta, por ejemplo:

- Dolor fuerte en el pecho.
- Dificultad para respirar.
- Pérdida de conciencia.
- Sangrado abundante.
- Convulsiones.
- Dolor intenso repentino.
- Señales de accidente cerebrovascular.
- Emergencia en embarazo.

PASO 10: NODOS DEL AGENTE

Crea el archivo:

agent/nodes.py

Debe implementar los nodos:

1. recepcion

Responsable de:

- Leer el mensaje del usuario.
- Identificar intención.
- Extraer datos básicos si están presentes.
- Pedir datos faltantes.
- Decidir la siguiente acción.

2. busqueda_rag

Responsable de:

- Usar buscar_especialista_rag.
- Sugerir especialidades.
- Pedir confirmación de especialidad.

3. verificacion_disponibilidad

Responsable de:

- Usar verificar_disponibilidad.
- Mostrar médicos disponibles.
- Pedir confirmación del médico, fecha y hora.

4. agendamiento

Responsable de:

- Confirmar que existen todos los datos.
- Usar agendar_cita.
- Guardar en PostgreSQL.
- Marcar cita_confirmada=True.

5. generacion_pdf

Responsable de:

- Usar generar_comprobante_pdf.
- Guardar ruta_pdf en el estado.

6. respuesta_final

Responsable de:

- Entregar resumen de la cita.
- Entregar ruta del comprobante PDF.
- Finalizar el flujo.

PASO 11: GRAFO CON LANGGRAPH

Crea el archivo:

agent/graph.py

Debe crear la máquina de estados con LangGraph.

Debe incluir:

- StateGraph.
- Nodos definidos.
- Edges condicionales.
- Punto de entrada.
- Punto final.

El flujo debe funcionar así:

1. Usuario escribe en la web.
2. El agente recibe el mensaje.
3. Si faltan nombre o contacto, los solicita.
4. Si el usuario describe síntomas, llama a búsqueda RAG.
5. Si ya hay especialidad, consulta disponibilidad.
6. Si hay disponibilidad, muestra opciones.
7. Si el usuario confirma, agenda la cita.
8. Si la cita se agenda correctamente, genera PDF.
9. Si el PDF se genera, responde con resumen final.
10. Si falta información, vuelve a pedir datos.

PASO 12: ARCHIVOS DE CONFIGURACIÓN

Crea:

requirements.txt

Debe incluir como mínimo:

streamlit
langgraph
langchain
langchain-core
requests
psycopg2-binary
python-dotenv
fpdf2
pydantic

Crea:

.env.example

Debe incluir:

POSTGRES_HOST=localhost
POSTGRES_PORT=5432
POSTGRES_DB=citas_m
POSTGRES_USER=[TU_USUARIO_POSTGRES]
POSTGRES_PASSWORD=[TU_CONTRASEÑA_POSTGRES]
OLLAMA_URL=http://localhost:11434
OLLAMA_EMBEDDING_MODEL=nomic-embed-text
USE_MCP=false
MCP_SERVER_NAME=postgres_codex

PASO 13: README DE EJECUCIÓN EN WINDOWS 11

Crea el archivo:

README.md

Debe explicar paso a paso cómo ejecutar todo en Windows 11.

Incluye comandos exactos:

1. Crear carpeta:

mkdir agente_citas_medicas
cd agente_citas_medicas

2. Crear entorno virtual:

python -m venv venv

3. Activar entorno:

venv\Scripts\activate

4. Instalar dependencias:

pip install -r requirements.txt

5. Copiar variables:

copy .env.example .env

6. Ejecutar scripts SQL:

psql -U [TU_USUARIO_POSTGRES] -d citas_m -f database/schema.sql
psql -U [TU_USUARIO_POSTGRES] -d citas_m -f database/seed.sql

7. Descargar modelos Ollama:

ollama pull qwen2.5:7b
ollama pull nomic-embed-text

8. Verificar Ollama:

ollama list

9. Ejecutar aplicación:

streamlit run app.py

10. Abrir en el navegador:

http://localhost:8501

PASO 14: PRUEBA FUNCIONAL OBLIGATORIA

Incluye una sección llamada:

Prueba rápida del agente

Con este ejemplo:

Usuario:
Buenos días, quiero pedir una cita médica.

Agente:
Solicita nombre y contacto.

Usuario:
Me llamo Ana Rodríguez y mi contacto es 3112223344.

Agente:
Pregunta especialidad o motivo.

Usuario:
Tengo dolor de cabeza frecuente.

Agente:
Aclara que no diagnostica, busca especialidad sugerida y consulta disponibilidad.

Usuario:
Quiero medicina general mañana a las 9.

Agente:
Consulta disponibilidad real.

Usuario:
Confirmo la cita.

Agente:
Agenda en PostgreSQL, genera PDF y entrega ruta del comprobante.

PASO 15: CRITERIOS DE CALIDAD

El proyecto debe cumplir:

- Debe ser ejecutable.
- Debe ser modular.
- Debe tener código real.
- Debe poder abrirse en navegador.
- Debe permitir pedir citas desde la web.
- Debe conectarse a PostgreSQL.
- Debe consultar disponibilidad real.
- Debe guardar citas reales.
- Debe generar PDF real.
- Debe funcionar con Ollama local.
- Debe tener opción preparada para MCP.
- Debe tener modo directo funcional sin MCP.
- Debe tener guardarraíles médicos.
- Debe evitar diagnósticos.
- Debe evitar inventar médicos u horarios.
- Debe manejar errores básicos.

FORMA EXACTA DE RESPUESTA

Entrega la solución en este orden:

1. Explicación breve de la arquitectura.
2. Árbol de carpetas.
3. Código completo de cada archivo.
4. Scripts SQL completos.
5. Archivo requirements.txt.
6. Archivo .env.example.
7. README.md completo.
8. Comandos de ejecución en Windows 11.
9. Prueba rápida del agente.
10. Recomendaciones finales.

IMPORTANTE FINAL

Tu respuesta debe construir el agente de IA de citas médicas completo.

No respondas con una explicación general.
No respondas diciendo que es complejo.
No respondas con recomendaciones solamente.
No omitas archivos.
No uses pseudocódigo.
No dejes funciones vacías.
No dejes “TODO”.
No dependas obligatoriamente de MCP para que funcione.
El proyecto debe poder probarse localmente primero con PostgreSQL directo y después conectarse a MCP.

Construye ahora la primera versión funcional del Agente Web de Citas Médicas con IA.
```
