# Juego de plataformas 2D estilo Mario

**Categoría:** [Juegos](README.md) · **Tecnologías:** HTML, CSS, JavaScript

Juego de plataformas retro de 8 bits en un solo archivo HTML.

## Prompt

```text
Actúa como un Desarrollador Senior de Videojuegos especializado en mecánicas de Plataformas 2D tipo retro NES.

Tu objetivo es construir un juego web completo de plataformas 2D, inspirado en los clásicos juegos de 8 bits, utilizando únicamente:

- HTML
- CSS
- JavaScript puro

No uses frameworks externos ni librerías. Todo debe estar en un solo archivo HTML autocontenido, con CSS y JavaScript incluidos dentro del mismo archivo.

El juego debe funcionar directamente en el navegador.

==================================================
1. OBJETIVO GENERAL DEL JUEGO
==================================================

Crea un juego de plataformas 2D estilo retro donde el jugador controle a un personaje que debe avanzar por escenarios con scroll lateral, saltar plataformas, evitar enemigos y completar tres niveles.

El juego debe tener:

- Tres niveles jugables.
- Física de plataformas fluida.
- Enemigos básicos.
- Sistema de colisiones.
- Cámara con desplazamiento lateral.
- Sonidos activables y desactivables.
- Menú ocultable.
- Modo automático donde la IA controle al personaje.
- Diseño responsive para computador, tablet y celular.

==================================================
2. ESTILO VISUAL
==================================================

El estilo debe ser retro tipo NES de 8 bits.

Usa gráficos generados con rectángulos, colores planos y formas simples mediante Canvas 2D.

No uses imágenes externas.

Elementos visuales requeridos:

- Personaje principal original.
- Suelo con bloques.
- Plataformas flotantes.
- Enemigos simples tipo criatura caminante.
- Fondo con cielo, nubes y montañas simples.
- Indicadores de nivel, vidas, puntuación y estado del sonido.
- Pantalla de inicio.
- Pantalla de pausa.
- Pantalla de victoria.
- Pantalla de derrota.

==================================================
3. TECNOLOGÍA
==================================================

El juego debe implementarse con:

- HTML para la estructura.
- CSS para diseño responsive y estilo del menú.
- JavaScript para toda la lógica del juego.
- Canvas 2D para renderizar el mundo.

Debe incluir:

- Game loop con requestAnimationFrame.
- Separación clara de clases o módulos internos:
  - Player
  - Enemy
  - Tile
  - Level
  - Camera
  - Game
  - InputManager
  - SoundManager
  - AutoPlayer

==================================================
4. FÍSICA DEL JUGADOR
==================================================

Implementa un Player Controller con física de plataformas.

Movimiento horizontal:

- El jugador debe moverse a la izquierda y derecha.
- Debe tener aceleración progresiva.
- Debe tener fricción o desaceleración.
- No debe detenerse de forma inmediata.
- Debe sentirse una ligera inercia.

Salto variable:

- Si el jugador mantiene presionado el botón de salto, debe alcanzar mayor altura.
- Si el jugador suelta rápido el botón de salto, debe hacer un salto corto.
- Evita saltos infinitos.
- Solo puede saltar cuando está tocando el suelo o una plataforma.

Gravedad:

- La gravedad debe sentirse pesada.
- La caída debe ser rápida y satisfactoria.
- Debe existir una velocidad máxima de caída.

Estados del jugador:

- Idle
- Running
- Jumping
- Falling
- Hit
- Dead

Controles:

- Teclado:
  - Flecha izquierda o A: mover izquierda.
  - Flecha derecha o D: mover derecha.
  - Espacio, W o flecha arriba: saltar.
  - P: pausar.
  - M: mostrar u ocultar menú.
  - S: activar o desactivar sonido.
  - O: activar o desactivar modo automático.

- Controles táctiles para celular:
  - Botón izquierda.
  - Botón derecha.
  - Botón salto.
  - Botón pausa.

==================================================
5. COLISIONES
==================================================

Implementa colisiones AABB, Axis-Aligned Bounding Box.

Debe haber colisiones con:

- Suelo.
- Plataformas.
- Paredes.
- Techos.
- Enemigos.

Reglas de colisión:

- El jugador no debe atravesar bloques sólidos.
- Si golpea una plataforma desde arriba, debe quedar encima.
- Si golpea un techo desde abajo, debe detener el salto.
- Si choca lateralmente con un bloque, debe detener el movimiento horizontal.
- El sistema debe resolver las colisiones por separado en los ejes X y Y para evitar errores.

==================================================
6. CÁMARA Y SCROLL LATERAL
==================================================

Implementa una cámara lateral.

Comportamiento requerido:

- La cámara debe seguir al jugador cuando avanza hacia la derecha.
- El jugador no puede retroceder más allá del borde izquierdo visible de la pantalla.
- La cámara no debe mostrar zonas fuera del nivel.
- El nivel debe ser más ancho que la pantalla.
- El scroll debe ser suave.

==================================================
7. GENERACIÓN DE NIVELES
==================================================

Usa un tilemap representado por arrays o listas.

Ejemplo de estructura:

- 0 = vacío
- 1 = suelo
- 2 = bloque sólido
- 3 = plataforma
- 4 = moneda o punto
- 5 = enemigo
- 6 = meta

Crea tres niveles diferentes:

Nivel 1:
- Fácil.
- Suelo continuo.
- Algunas plataformas bajas.
- Pocos enemigos.

Nivel 2:
- Dificultad media.
- Más huecos.
- Plataformas más altas.
- Más enemigos.

Nivel 3:
- Más difícil.
- Saltos más precisos.
- Enemigos mejor ubicados.
- Mayor longitud del nivel.

Cada nivel debe tener:

- Punto inicial del jugador.
- Distribución de plataformas.
- Enemigos.
- Meta final.
- Fondo visual diferente o variación de color.

==================================================
8. ENEMIGOS
==================================================

Crea un enemigo básico original, no llamado Goomba.

Características:

- Debe caminar de izquierda a derecha.
- Debe cambiar de dirección al chocar contra una pared o borde.
- Debe tener colisión AABB.
- Debe poder ser derrotado si el jugador cae sobre su cabeza.

Lógica de daño:

- Si el jugador cae encima del enemigo:
  - El enemigo desaparece o queda aplastado.
  - El jugador rebota ligeramente hacia arriba.
  - Se suma puntuación.

- Si el enemigo toca al jugador por un lado:
  - El jugador pierde una vida.
  - Si no tiene vidas, se reinicia el nivel o aparece pantalla de derrota.
  - Debe haber animación o efecto visual simple de daño.

==================================================
9. SISTEMA DE VIDAS, PUNTOS Y META
==================================================

Incluye:

- Sistema de vidas.
- Puntuación.
- Nivel actual.
- Tiempo opcional.
- Meta al final del nivel.

Reglas:

- El jugador inicia con 3 vidas.
- Al tocar un enemigo por el lado pierde una vida.
- Si cae al vacío pierde una vida.
- Si pierde todas las vidas, aparece pantalla de Game Over.
- Si llega a la meta, pasa al siguiente nivel.
- Si completa el nivel 3, aparece pantalla de victoria.

==================================================
10. SONIDO
==================================================

Incluye sonidos simples generados con Web Audio API.

No uses archivos externos.

Sonidos requeridos:

- Salto.
- Derrotar enemigo.
- Daño.
- Pasar de nivel.
- Victoria.
- Game Over.

Debe existir una opción para:

- Activar sonido.
- Desactivar sonido.

El estado del sonido debe mostrarse en pantalla.

==================================================
11. MENÚ DEL JUEGO
==================================================

Crea un menú lateral o superior con las siguientes opciones:

- Iniciar juego.
- Reiniciar nivel.
- Pausar / continuar.
- Activar / desactivar sonido.
- Activar / desactivar modo automático.
- Mostrar controles.
- Ocultar menú.

El menú debe poder ocultarse y mostrarse con una tecla o botón.

==================================================
12. MODO AUTOMÁTICO
==================================================

Implementa un modo automático donde el personaje juegue solo.

El modo automático debe:

- Mover al jugador hacia la derecha.
- Saltar cuando detecte un hueco.
- Saltar cuando detecte una plataforma necesaria.
- Saltar sobre enemigos cercanos.
- Evitar chocar lateralmente con enemigos.
- No debe quedarse atascado fácilmente.
- Debe poder completar los niveles en condiciones normales.

La lógica del modo automático puede ser sencilla, basada en detección hacia adelante:

- Revisar tiles frente al jugador.
- Revisar enemigos cercanos.
- Revisar si hay suelo adelante.
- Decidir cuándo saltar.
- Ajustar movimiento horizontal.

Debe existir un indicador visual que diga:

"MODO AUTOMÁTICO ACTIVADO"

==================================================
13. RESPONSIVE DESIGN
==================================================

El juego debe adaptarse a:

- Pantallas de escritorio.
- Portátiles.
- Tablets.
- Celulares.

Requisitos:

- El Canvas debe escalar manteniendo proporción.
- Los controles táctiles deben aparecer en pantallas pequeñas.
- El menú debe ser legible en móvil.
- No debe romperse el diseño al cambiar el tamaño de la ventana.

==================================================
14. CALIDAD DEL CÓDIGO
==================================================

El código debe estar bien organizado y comentado.

Requisitos técnicos:

- Usar clases de JavaScript.
- Evitar código repetido.
- Separar claramente renderizado, física, entradas, sonidos y lógica del juego.
- Usar constantes para gravedad, velocidad, salto, tamaño de tile y escala.
- Incluir comentarios explicando las partes principales.
- Evitar dependencias externas.
- Todo debe estar en un único archivo HTML funcional.

==================================================
15. ENTREGABLE FINAL
==================================================

Entrega como resultado un único archivo HTML completo, listo para copiar, guardar y ejecutar.

El archivo debe contener:

- HTML
- CSS
- JavaScript
- Canvas
- Física del jugador
- Tilemap
- Tres niveles
- Enemigos
- Sonidos
- Menú
- Modo automático
- Responsive design

El juego debe ejecutarse abriendo el archivo en cualquier navegador moderno.
```
