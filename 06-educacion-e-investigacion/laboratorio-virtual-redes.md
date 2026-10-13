# Laboratorio virtual de redes (topología estrella)

**Categoría:** [Educación e investigación](README.md) · **Tecnologías:** Three.js r128, JavaScript

Simulación 3D interactiva de una red en estrella con configuración de IP y pruebas de conectividad.

## Prompt

```text
Actúa como un Desarrollador Senior de Simulaciones Web 3D y UI/UX.

OBJETIVO
Crea un “Laboratorio Virtual de Redes — Topología Estrella” en un SOLO archivo HTML (index.html) con CSS y JavaScript embebidos. Debe funcionar al abrirlo en el navegador sin build tools.

STACK / RESTRICCIONES
- Usar Three.js desde CDN (three.min.js) versión r128.
- JavaScript vanilla (sin frameworks).
- Todo en un único archivo HTML.
- Idioma: Español.
- Estética: paneles modernos tipo “glass”, tipografía Inter + JetBrains Mono, botones con emojis, sombras suaves, bordes redondeados.
- Debe ser RESPONSIVE (resize del canvas y de la cámara).

FUNCIONALIDADES PRINCIPALES (UI)
1) Barra superior fija (“top-bar”) con botones:
   - 🖥️ Agregar PC
   - 🔀 Agregar Switch
   - 🗄️ Agregar Servidor
   - 🔗 Conectar
   - 🗑️ Eliminar
   - 📡 Ping (abre modal)
   - 📝 Quiz (panel de preguntas)
   - ⭐ Auto Estrella (genera red estrella automáticamente)
   - ↺ Reiniciar (resetea todo)
   Cada botón cambia el “modo” de interacción.

2) Panel lateral izquierdo con:
   - Título “📡 Dispositivos de Red” + badge con el conteo de nodos.
   - Sección “Agregar dispositivos” con botones (PC, Switch, Servidor) con descripción corta.
   - Sección “Nodos en la red” (lista clicable de nodos mostrando ícono, nombre, IP, y estado).
   - Sección de estadísticas: Nodos, Conexiones, Topología detectada, Paquetes enviados.

3) Panel informativo (abajo derecha) visible al seleccionar un nodo:
   - Ícono, nombre, tipo.
   - Descripción educativa del dispositivo.
   - Specs: IP, Máscara, MAC, cantidad de conexiones, estado “Online”.

4) Panel de instrucciones (arriba derecha) con controles:
   - Clic izq: agregar/seleccionar
   - Clic der: rotar cámara
   - Scroll: zoom
   - Supr: eliminar seleccionado
   - ESC: cancelar modo
   - R: resetear cámara

5) Indicador de modo (parte inferior centrada) que aparece cuando el modo está activo (texto tipo “Haz clic en el plano para colocar…”).

6) Notificaciones tipo toast (arriba) para éxito/error/info.

MODALES
7) Modal de configuración IP (al crear un nodo):
   - Campos: Nombre, Dirección IP, Máscara (por defecto 255.255.255.0)
   - Validar IP IPv4.
   - Evitar IP duplicada.
   - Botones: Cancelar / Confirmar.
   - Autogenerar IPs: 192.168.1.X incremental.
   - Autogenerar nombre sugerido (ej: PC-01 / SW-01 / SV-01).

8) Modal “📡 Simulación de Ping”:
   - Select de nodo origen y destino.
   - Terminal estilo consola para imprimir el resultado.
   - Botón “▶ Enviar Ping”.
   - Si no hay ruta: mostrar “Host de destino inalcanzable” con explicación.
   - Si hay ruta: simular 4 respuestas con latencias aleatorias, TTL=64, y mostrar estadísticas finales.

QUIZ
9) Panel “📝 Pregunta de Redes” con preguntas tipo test (opciones clicables).
   - Al responder: marcar correcto en verde, incorrecto en rojo, bloquear clics y pasar a la siguiente pregunta en 2s.
   - Preguntas mínimas: nodo central en estrella, capa OSI del switch, ICMP, MAC, máscara /24, DHCP, etc.

ESCENA 3D (THREE.JS)
10) Escena con:
   - Fondo claro + niebla suave.
   - Piso grande (plane) con material estándar y grid helper.
   - Iluminación: Hemisphere + Ambient + Directional con sombras suaves (PCFSoftShadowMap).
   - Cámara perspective con OrbitControls (si no puedes importar OrbitControls, implementa una versión compacta en el mismo archivo).

MODELOS 3D (con primitivas)
11) Modelos 3D estilizados:
   - PC: monitor + base + soporte + “pantalla” con material emissive, teclado y LED.
   - Switch: caja rectangular, 8 puertos al frente, 8 LEDs, LED de power.
   - Servidor: torre/rack vertical, líneas frontales, 3 LEDs (verde/azul/naranja).
   - Cada nodo debe tener:
     - Anillo de selección (ring) en el piso que se ilumine al seleccionar.
     - Etiqueta flotante (Sprite) generada con CanvasTexture que muestre nombre e IP (IP en verde, usando JetBrains Mono).

DATOS Y LÓGICA
12) Estructuras:
   - nodes[] con: id, type (pc/switch/server), name, ip, mask, mac, mesh, ring, label, pos, connections[].
   - links[] con: from, to, mesh (cable).
   - Generar MAC tipo AA:BB:CC:XX:YY:ZZ.

13) Colocación de nodos:
   - En modo agregar: al mover mouse mostrar “ghost preview” semitransparente del dispositivo.
   - Al clic en el piso: abrir modal de IP y crear nodo.
   - Snap a grilla de 0.5 unidades.
   - Restringir el área de colocación (ej: |x|<18, |z|<18).

14) Conectar nodos:
   - En modo conectar: clic en nodo ORIGEN y luego en DESTINO.
   - Evitar conectar nodo consigo mismo.
   - Evitar conexiones duplicadas.
   - Crear cable curvo entre nodos usando CatmullRomCurve3 + TubeGeometry.
   - Actualizar conexiones en ambos nodos.

15) Eliminar:
   - En modo eliminar: clic en un nodo lo borra y elimina sus cables.
   - Tecla Delete elimina el nodo seleccionado.

16) Detección de topología (para mostrar en stats):
   - Si hay un solo switch y todos los enlaces van al switch y el número de enlaces coincide con hosts => “⭐ Estrella”.
   - Si todos van al switch pero faltan enlaces => “⭐ Estrella (parcial)”.
   - Si hay varios switches => “🔀 Multi-Switch”.
   - Si hay enlaces sin switch => “📏 Punto a punto”.
   - Si no hay enlaces => “📍 Sin conexión”.

PING + ANIMACIÓN DE PAQUETES
17) Para ping:
   - Encontrar ruta con BFS sobre links[].
   - Si hay ruta: animar esferas (paquetes) que viajen nodo a nodo.
   - Resaltar temporalmente el cable activo (material verde/emissive).
   - Hacer también “viaje de retorno” simplificado.
   - Contabilizar “paquetes enviados” y actualizar stats.

AUTO-ESTRELLA
18) Botón “⭐ Auto Estrella”:
   - Resetear.
   - Crear un switch central en (0,0,0) con IP 192.168.1.1.
   - Crear 6 nodos alrededor en círculo (radio ~8): 1 servidor + 5 PCs, con IPs 192.168.1.10+.
   - Conectar todos al switch con una pequeña animación/retardo secuencial.
   - Notificar “Red estrella generada automáticamente”.

ANIMACIÓN GENERAL
19) Animation loop:
   - requestAnimationFrame
   - controls.update()
   - Animar paquetes (interpolación + salto en Y con sin()).
   - Animar etiqueta flotante (levitar suave).
   - Pulsar el anillo del nodo seleccionado.
   - renderer.render()

ENTREGABLE
Devuélveme el HTML completo, con secciones comentadas (UI/CSS/Three.js/State/Handlers), y listo para ejecutar.
```
