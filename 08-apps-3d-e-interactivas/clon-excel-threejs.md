# Clon de Excel con Three.js

**Categoría:** [Apps 3D e interactivas](README.md) · **Tecnologías:** Three.js, JavaScript

Hoja de cálculo tipo Excel renderizada con WebGL en un único archivo HTML.

## Prompt

```text
Actúa como un desarrollador senior de aplicaciones web. Construye un clon funcional tipo Excel usando solo HTML, CSS y JavaScript, y renderiza la grilla con Three.js (WebGL) para alto rendimiento.

Entregable

Un único archivo index.html autónomo (CSS y JS embebidos).

Sin frameworks (React/Vue/etc).

Puedes usar Three.js desde CDN (módulos). No uses assets externos (imágenes/fuentes) salvo Three.js.

Objetivo de la app

Una hoja de cálculo con experiencia “tipo Excel/Google Sheets”:

Grilla con filas/columnas, encabezados (A, B, C… y 1,2,3…).

Selección de celda con mouse y teclado.

Edición in-cell (doble clic o Enter) con cursor y selección de texto.

Scroll vertical/horizontal suave con “inercia” y soporte para trackpad.

Zoom (Ctrl + rueda) con límites razonables.

Requisitos de UI/UX

Barra superior con:

Cuadro de referencia (ej: B3)

Barra de fórmulas

Botones: Nuevo, Guardar, Cargar, Exportar CSV, Importar CSV

Resaltado de fila/columna de la celda activa.

Rejilla con líneas finas, fondo claro, selección con borde visible.

Autofill handle (cuadrito en esquina) para arrastrar y rellenar series simples.

Redimensionar columnas/filas arrastrando el borde del encabezado.

Freeze opcional de primera fila y primera columna (toggle).

Requisitos funcionales mínimos

Datos

Modelo interno tipo Map o matriz dinámica para celdas.

Cada celda soporta: raw (texto ingresado), value (resultado), type (text/number), format (básico).

Fórmulas

Si el usuario escribe = entonces es fórmula.

Implementa: SUM, AVERAGE, MIN, MAX, y referencias tipo A1, rangos A1:B10.

Recalcula dependencias básicas (sin ciclos; si hay ciclo, mostrar #CYCLE!).

Edición y atajos

Flechas para moverse, Tab/Shift+Tab, Enter/Shift+Enter.

Copy/Cut/Paste (Ctrl+C/X/V) con soporte de pegado de tablas TSV (desde Excel real).

Delete limpia celdas.

Undo/Redo (Ctrl+Z / Ctrl+Y) con historial.

Persistencia

Guardar/cargar en localStorage como JSON.

Exportar/Importar CSV (descarga/subida usando input file).

Uso de Three.js (obligatorio)

Renderiza la hoja como una escena 2D con cámara ortográfica.

La grilla debe ser eficiente:

Renderiza celdas visibles (virtualización) y evita dibujar miles fuera del viewport.

Usa InstancedMesh o geometrías reutilizables para rendimiento.

El texto de celdas:

Usa canvas 2D para generar texturas (atlas) o sprites de texto, pero optimiza (solo visible).

Maneja picking:

Convierte coordenadas del mouse a celda (raycast o cálculo 2D preciso).

Calidad y robustez

Código modular dentro del mismo HTML (clases o módulos internos).

Comentarios breves en partes complejas (render, virtualización, fórmulas).

Debe correr fluido con al menos 1000 filas x 200 columnas (aunque solo renderice visible).

Manejo de errores: mostrar #ERROR, #REF!, #VALUE! donde aplique.

Resultado esperado

Al abrir index.html, debo poder:

Escribir valores y fórmulas, copiar/pegar, deshacer/rehacer,

Desplazarme y hacer zoom,

Redimensionar columnas/filas,

Guardar/cargar, e importar/exportar CSV,
todo con una experiencia similar a una hoja de cálculo real.
```
