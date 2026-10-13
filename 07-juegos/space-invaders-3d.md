# Space Invaders 3D

**Categoría:** [Juegos](README.md) · **Tecnologías:** Three.js r182, Web Audio API

Versión 3D de Space Invaders con gráficos de primitivas y audio sintético.

## Prompt

```text
Rol: Actúa como un Desarrollador Senior de Videojuegos Web experto en JavaScript y la librería Three.js.  (https://github.com/mrdoob/three.js/releases/tag/r182?s=08)
Objetivo: Tu tarea es escribir el código completo para un juego tipo "Space Invaders" en 3D llamado "Space Invaders 3D".
Requisitos Técnicos Estrictos:
1.	Sin Assets Externos: No uses imágenes, modelos 3D (.glb/.obj) ni archivos de audio (.mp3/.wav).
o	Todos los gráficos deben construirse usando primitivas de Three.js (BoxGeometry, ConeGeometry, SphereGeometry, etc.).
o	Todo el audio debe generarse sintéticamente en tiempo real usando la Web Audio API (osciladores para efectos y melodías simples).
2.	Arquitectura Modular: El código debe estar separado en archivos ES6 Classes distintos para facilitar el mantenimiento.
3.	Librería: Usa Three.js (versión https://github.com/mrdoob/three.js/releases/tag/r182?s=08) vía CDN.
Estructura de Archivos Solicitada: Genera el código para los siguientes archivos y carpetas:
1.	index.html: Contenedor del juego, UI (Puntaje, Vidas, Nivel) y menús superpuestos (Inicio, Game Over, Nivel Completado). Importa los scripts en orden.
2.	css/style.css: Estilos para la UI superpuesta, fuente tipo arcade, manejo de estados "oculto" para los menús.
3.	js/game.js: Clase Game. Maneja la escena, cámara, renderizador, requestAnimationFrame, luces y el bucle principal (update y draw). Gestiona los arrays de entidades.
4.	js/player.js: Clase Player.
o	Nave construida con múltiples geometrías agrupadas.
o	Movimiento con flechas del teclado.
o	Disparo con Espacio.
o	Sistema de invulnerabilidad temporal al recibir daño (con efecto de parpadeo).
5.	js/enemy.js: Clase Enemy.
o	Tipos de enemigos: Basic (cono), Scout (rápido), Tank (resistente, cubo), Bomber (cilindro) y Boss (complejo).
o	Patrones de movimiento: Lineal, Zigzag, Picado (swooping) y Complejo (para el jefe).
o	Atributos parametrizables: Salud, velocidad, puntos, cadencia de disparo.
6.	js/projectile.js: Clase Projectile. Maneja disparos del jugador (azules) y de enemigos (rojos). Detección de límites de pantalla.
7.	js/level.js: Clase LevelManager.
o	Define un array de niveles.
o	Cada nivel tiene una configuración de oleadas y formaciones (Grid, Línea, V-Shape, Flanking).
o	Cambio de color de fondo/ambiente según el nivel.
8.	js/sound.js: Clase SoundManager.
o	Debe contener métodos play(soundId) que creen un AudioContext, un oscilador y un nodo de ganancia para simular sonidos (disparo, explosión, power-up).
o	Incluir secuencias de notas simples para "Música de fondo" usando setTimeout o bucles de osciladores.
9.	js/main.js: Punto de entrada. Instancia el juego al cargar el DOM y conecta los botones de la UI.
Detalles de Jugabilidad:
•	El jugador tiene 3 vidas.
•	Al eliminar todos los enemigos, se avanza al siguiente nivel.
•	Implementar detección de colisiones simple (AABB o Box3).
•	Sistema de partículas simple para el fondo (campo de estrellas).
Por favor, entrégame el código completo de cada archivo por separado.
Observaciones finales
•	La nave debe poder moverse en todo la pantalla
•	El juego debe tener sonido y poderlo desactivar
•	Se debe poder ocultar y mostrar los menús
•	El juego debe ser responsive
```
