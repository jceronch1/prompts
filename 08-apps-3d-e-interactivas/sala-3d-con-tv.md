# Sala 3D con televisor

**Categoría:** [Apps 3D e interactivas](README.md) · **Tecnologías:** Three.js

Escena 3D de una sala con un televisor que muestra una animación procedimental.

## Prompt

```text
Actúa como un desarrollador senior de gráficos 3D en la web. Tu tarea es crear una escena 3D de una sala (living room) en Three.js con un televisor/pantalla grande que muestre contenido animado sin copyright (preferiblemente una animación procedimental renderizada en un <canvas> y aplicada como VideoTexture, o un “clip” simulado con cambios de color/formas).

Requisitos técnicos

Entrega un único archivo index.html autónomo con CSS y JS embebidos.

Usa Three.js desde CDN (módulos ES) y no dependas de frameworks.

No uses assets externos obligatorios (texturas/modelos); si agregas algo, debe ser procedural o embebido.

Escena y ambientación

Construye una sala creíble con geometrías simples: piso, paredes, sofá, mesa de centro, alfombra, lámpara, mueble del TV, y algunos detalles decorativos.

Materiales simples pero agradables (tipo PBR básico con MeshStandardMaterial).

Iluminación: AmbientLight + DirectionalLight (con sombras) + 1–2 luces de acento suaves (por ejemplo PointLight cerca de la lámpara).

Sombras suaves si es posible (activar renderer.shadowMap, configurar bias, y calidad razonable).

Televisor con “contenido animado”

El televisor debe tener:

Bisel/carcasa + pantalla (un plano).

La pantalla debe reproducir una animación simulada (por ejemplo: personajes/figuras abstractas moviéndose, cortes, subtítulos falsos tipo “beep”, etc.) generada en canvas y actualizada por frame.

Emite un leve “glow” (por ejemplo usando un material más brillante o una luz tenue cerca de la pantalla).

Interacción y controles

Implementa controles FPS:

Caminar: WASD

Mirar: mouse con Pointer Lock (clic para capturar el mouse, Esc para liberar).

Opcional: Shift correr, Space subir ligeramente (o salto simple).

Zoom hacia el televisor:

Al presionar una tecla (por ejemplo Z) o con rueda del mouse, realiza un zoom suave (cambio de FOV o dolly controlado).

Incluye un modo “enfocar TV” (tecla F): acerca la cámara y la orienta hacia la pantalla con interpolación suave; volver a la posición anterior con la misma tecla.

UI mínima

Superposición HTML pequeña con instrucciones: “Click para capturar mouse, WASD para moverte, Z zoom, F enfocar TV, Esc liberar”.

Un crosshair centrado opcional.

Calidad y rendimiento

Código comentado y ordenado: init(), createRoom(), createFurniture(), createTV(), setupLights(), animate().

Usa requestAnimationFrame, resize handler, y limita geometrías pesadas.

Debe tener una barra para poder aumentar o disminuir la luz. con la letra "p" para ir subiendo la luz y la letra "o" para ir bajando

Debe correr en Chrome/Edge moderno en escritorio.

Entregable final: devuelve únicamente el contenido completo del index.html listo para copiar y ejecutar.
```
