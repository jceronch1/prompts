# Editor LEGO 3D

**Categoría:** [Apps 3D e interactivas](README.md) · **Tecnologías:** Three.js

Editor de construcción con piezas tipo LEGO en un único index.html.

## Prompt

```text
Actúa como un Ingeniero Senior de gráficos 3D y UX interactiva.

Tu tarea es generar un editor LEGO 3D de calidad profesional en un único archivo `index.html` completamente autónomo, ejecutable al abrirse en navegador moderno, usando exclusivamente Three.js y sus módulos oficiales desde CDN (incluyendo `examples/jsm` si es necesario).
No uses frameworks adicionales, no build tools, no backends, no recursos externos (imágenes, audios, fuentes, modelos, APIs) fuera de Three.js.

========================
OBJETIVO DEL PRODUCTO
========================
Construir una experiencia premium de creación LEGO 3D: precisa, fluida, visualmente atractiva, intuitiva para mouse/táctil y con sensación “mágica” de juguete físico.

========================
RESTRICCIONES TÉCNICAS
========================
1) Entrega:
- Responde SOLO con el HTML responsive completo final (sin explicaciones, sin markdown, sin texto extra).
- Debe funcionar de inmediato al guardar como `index.html` y abrir en navegador.
- Sin TODOs, placeholders, bloques incompletos ni funciones vacías.

2) Dependencias:
- Solo módulos CDN de Three.js (core + addons oficiales de Three.js).
- Prohibido usar librerías externas distintas a Three.js.

3) Rendimiento:
- Interacción suave en equipos de gama media.
- Reutilización de geometrías/materiales cuando sea posible.
- Raycasting eficiente y actualización incremental de escena/UI.

========================
FUNCIONALIDAD OBLIGATORIA
========================
A) Sistema de construcción y física lógica
- Rejilla de studs precisa en X/Z + niveles de altura por “plate/layer”.
- Colocación por “snap” exacto.
- Validación de soporte real stud↔tube al apilar.
- Detección de colisiones sólida (no interpenetración).
- Vista fantasma (ghost piece) antes de colocar, con color de estado válido/inválido.
- Que se puedan colocar una pieza encima de otra y encajen según la pieza para poder construir cosas.
B) Biblioteca de piezas
- Catálogo amplio con categorías:
  - Ladrillos, placas, mosaicos (tiles) de 1x1 a 16x16
  - Pendientes/slope
  - Technic básico
  - Piezas de minifigura
- Mínimo 20+ colores tipo LEGO (paleta auténtica aproximada).
- Paleta lateral con búsqueda/filtro por categoría y tamaño.
- Arrastrar desde paleta a escena + clic para colocar.

C) Transformación y edición
- Rotación con Q/E (pasos de ángulo configurables).
- Arrastre con botón derecho para mover en plano.
- Recoloración instantánea por ladrillo seleccionado.
- Selección simple y multiselección:
  - Shift + arrastrar para caja de selección.
- Acciones sobre selección:
  - Copiar, pegar, eliminar.
- Deshacer/rehacer ilimitado (historial robusto de operaciones).

D) Escena y base
- Tamaños de baseplate conmutables (varios presets).
- Acción “Clear Scene” con confirmación.
- Toggle de ajuste de rejilla (snap on/off).
- Toggle de incremento angular (ej. 15°/45°/90°).

E) Cámara e interacción
- Cámara de órbita suave con soporte mouse + táctil.
- Controles cómodos de zoom/pan/orbit.
- Enfoque automático opcional al seleccionar.

F) Persistencia y archivos
- Guardar/cargar proyectos en localStorage.
- Miniatura automática al guardar (captura de canvas).
- Importar/exportar JSON de proyecto.
- Manejo de errores y validación de formato JSON.

G) Calidad visual y sensorial
- Materiales PBR realistas.
- Sombras suaves.
- Brillo/transparencia sutil tipo capa en studs.
- Microinteracciones pulidas:
  - caída breve al colocar, tambaleo suave, partículas al eliminar.
- Sonido de colocación sutil generado localmente (WebAudio, sin archivos externos).
- Vibración háptica cuando esté disponible (`navigator.vibrate`).

H) UI/UX premium
- Panel lateral plegable, limpio y moderno. (Que se pueda ocultar)
- Barra superior con herramientas clave. (Que se pueda ocultar)
- Galería de plantillas listas para cargar:
  - coche, castillo, nave espacial, robot (mínimo 4).
- Atajos visibles y ayuda rápida.
- Diseño responsivo.

I) Ejemplos
-  Que venga con ejemplos predeterminados de animales (Gato, perro) y cosas (carro, Robot) y que se puedan ir armando paso a paso.
========================
ARQUITECTURA Y CALIDAD DE CÓDIGO
========================
- Código organizado por módulos lógicos dentro del mismo HTML:
  - estado global, motor de rejilla, catálogo de piezas, render, input, historial, persistencia, UI.
- Nombres claros, comentarios breves de alto valor.
- Sin duplicación innecesaria.
- Manejo defensivo de errores.
- Consistencia en unidades y convenciones de coordenadas.

========================
CRITERIOS DE ACEPTACIÓN
========================
Se considera correcto solo si:
1) Permite construir estructuras válidas por snap stud/tube sin colisiones.
2) Incluye biblioteca amplia de piezas y 20+ colores.
3) Implementa selección múltiple, copiar/pegar/eliminar y undo/redo ilimitado.
4) Guarda/carga con miniatura en localStorage y soporta JSON import/export.
5) Provee UX fluida con cámara orbit, ghost placement y panel plegable.
6) Entrega un `index.html` único, totalmente funcional, sin dependencias externas fuera de Three.js CDN.

Devuelve únicamente el código HTML final completo.
```
