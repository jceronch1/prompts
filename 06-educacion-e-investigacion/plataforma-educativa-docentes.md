# Plataforma educativa con IA para docentes

**Categoría:** [Educación e investigación](README.md) · **Tecnologías:** MySQL o PostgreSQL, Ollama, OpenAI, Gemini

Plataforma para generar actividades educativas con IA, con sistema de créditos y exportación a Word o Excel.

## Prompt

```text
Crea una plataforma web educativa con las siguientes condiciones
1. Crear una base de datos en MySQL o PostgreSQL donde maneje los usuarios(Docente o Estudiante o Admin) y guarde el histórico de las actividades porque esa actividad que hace un docente le puede servir a otro de la misma área.
2. Debe funcionar tanto con Ollama como una api de OpenAI o Gemini
3. Datos generales
   a. Dar 500 créditos que se vaya descontado. Se descuenta siempre y cuando sea con la API sino seria gratis
   b. Que todas las actividades se puedan exportar a Microsoft Word o Excel según sea el caso.
   c. Cuando el docente genere la actividad poder escoger entre si lo publica en forma general para que puedan ver los demás docentes o de forma privada donde solo lo miraría en docente que lo ha creado.
4. Las actividades y opciones que debe tener la plataforma educativa son:
   a. Exámenes de cualquier tema teniendo en cuenta si son preguntas F/V, selección múltiple con única respuesta y respuesta corta.
   b. Que se puedan crear resúmenes a partir de un texto largo o documento anexo
   c. Poder crear actividades de clase
   d. Crear rubricar de evaluación según el tema, carrera, semestre, objetivos
   e. Corrección de escritura. Se pueda subir un texto y se le pueda corregir a ese texto, la sintaxis, ortografía etc.
   f. Creación de diapositivas de un tema
   g. Poder crear los textos para un correo electrónico
   h. Crear una encuesta.
   i. Creación de Chatbot de diferentes áreas
Sección de juegos
a. Poder crear cuentos, fabulas, aventuras de forma personalizada
b. Crucigrama
c. Sopa de letras
```
