# Juego de resortera con física 2D

**Categoría:** [Juegos](README.md) · **Tecnologías:** Canvas, Web Audio API

Puzzle de física con resortera inspirado en Angry Birds, sin recursos protegidos.

## Prompt

```text
Actúa como un desarrollador senior de videojuegos web y un ingeniero de física 2D.

Tu tarea es generar el código completo de un videojuego web 2D tipo “slingshot physics puzzle” inspirado en Angry Birds, pero sin usar nombres, logos, tipografías ni recursos protegidos (no escribir “Angry Birds”, no usar su logo). Debe verse y sentirse como en las imágenes: estilo caricatura brillante, fondo cielo azul con nubes suaves, colinas verdes, pasto en primer plano, suelo con textura rocosa azul oscuro, resortera a la izquierda, estructuras de madera/piedra/vidrio a la derecha y cerditos verdes dentro.

ENTREGABLE ÚNICO: Un solo archivo HTML autocontenido con CSS + JavaScript embebidos. Sin dependencias externas. Sin imágenes externas. Sin audio externo. Todo debe dibujarse con Canvas (vectorial/geométrico) y sonidos generados con WebAudio.
1) Estética y composición (debe coincidir con las imágenes)
•	Vista lateral 2D, cámara horizontal.
•	Resortera (madera con horquilla en “Y”) en el extremo izquierdo, clavada en el suelo.
•	Cola de pájaros en el suelo cerca de la resortera (dos o tres visibles) como en la imagen.
•	Trayectoria punteada (puntos blancos) al apuntar/disparar.
•	Estructuras a la derecha: marcos de madera (rectángulos color miel), bloques de piedra (gris con puntitos), y vidrio (azul claro translúcido).
•	Cerditos verdes redondos con hocico y orejitas (caricatura), colocados dentro de la estructura (arriba, centro, y laterales) como objetivos.
•	Efectos de destrucción: astillas de madera, polvo gris, fragmentos y vibración leve de cámara al impacto fuerte.
•	HUD como en las imágenes:
o	Arriba izquierda: botones circulares (pausa, reinicio/volver, energía/poder).
o	Barra superior con iconos de pájaros y contador (ej. “5”) estilo burbuja.
o	Arriba derecha: texto “SCORE” grande y el número debajo (blanco con borde oscuro).
•	Pantalla de inicio/carga opcional con ilustración simple genérica (sin marcas registradas), manteniendo el estilo.
________________________________________
2) Jugabilidad (core loop exacto)
•	El jugador arrastra el pájaro desde la resortera:
o	Click/touch sobre el pájaro cargado.
o	Drag hacia atrás para tensar.
o	Muestra banda elástica (dos líneas) y trayectoria punteada.
o	Al soltar: lanzamiento con velocidad proporcional a la tensión.
•	La cámara sigue al pájaro durante el vuelo (suavemente), y luego vuelve a la resortera cuando se detiene o tras unos segundos.
•	Objetivo: derribar estructuras y eliminar cerditos.
•	Fin de nivel: cuando no queden cerditos → victoria, estrellas según puntaje y botón “Siguiente”.
•	Si se acaban los pájaros y quedan cerditos → derrota con botón “Reintentar”.
•	Teclas/controles:
o	Mouse + táctil (imprescindible).
o	Tecla R reinicia nivel.
o	Tecla N siguiente nivel (solo si ganó).
o	Botón de pausa funcional.
________________________________________
3) Física (obligatorio: consistente, divertida y “tipo Angry Birds”)
Implementa un motor de física 2D propio (sin librerías):
•	Cuerpos rígidos simples: círculos (pájaros/cerdos) y rectángulos (madera/piedra/vidrio).
•	Gravedad constante, integración con fixed timestep (por ejemplo 1/60).
•	Colisiones:
o	círculo-círculo, círculo-rectángulo, rectángulo-rectángulo (AABB o SAT simplificado).
o	Respuesta con impulso (restitución), fricción mínima y amortiguación.
•	Estabilidad:
o	Iteraciones de resolución (solver iterativo) para evitar que la torre “explote”.
o	“Sleeping” para cuerpos casi quietos.
•	Materiales con propiedades distintas:
o	Madera: resistencia media, se rompe con impactos moderados, genera astillas.
o	Vidrio: frágil, se quiebra con impactos menores, genera fragmentos “cristal” azul claro.
o	Piedra: muy resistente, casi no se rompe salvo golpes fuertes.
•	Daño por impacto:
o	Calcula “impulso/energía” del choque y resta vida al bloque.
o	Cuando la vida llega a 0: bloque se destruye y genera partículas.
•	Cerditos:
o	Tienen vida baja; se eliminan con golpes o aplastamiento por bloques.
o	Al eliminar: “pop” visual + puntos + sonido.
________________________________________
4) Puntuación, UI y feedback
•	Puntaje:
o	Bloque destruido: madera +100, vidrio +150, piedra +200.
o	Cerdito eliminado: +500.
o	Bonus por pájaros restantes al ganar.
o	Multiplicador por combos (destrucciones en cadena).
•	Mostrar “floating text” (ej: “+500”) cerca del evento.
•	HUD:
o	Score en esquina superior derecha como en las imágenes.
o	Barra superior con iconos circulares y contadores de pájaros.
o	Indicador de pájaros restantes en cola (visual).
•	Pausa:
o	Congela física y animaciones, muestra overlay semitransparente con botones: Continuar / Reiniciar / Menú.
________________________________________
5) Pájaros (mínimo 3 tipos, estilo caricatura)
Sin usar diseños exactos protegidos; crea variantes genéricas “pájaro rojo/amarillo/negro”:
1.	Rojo básico: solo golpe.
2.	Amarillo acelerador: al tocar/click en el aire, aumenta velocidad hacia adelante (dash).
3.	Negro explosivo: al tocar/click en el aire, explota con onda expansiva que empuja bloques (sin gore).
•	En la barra superior deben verse sus iconos con contador.
________________________________________
6) Niveles (mínimo 5, inspirados en las imágenes)
•	Define niveles en un array JSON dentro del JS:
o	Posiciones (x,y), tamaño (w,h), rotación opcional, material, y cerditos.
•	Niveles con torres de:
o	Marcos de madera verticales + losas horizontales.
o	Bloques de piedra arriba.
o	Vidrios en el centro como “ventanas”.
o	Algún bloque inclinado como en la imagen (madera diagonal).
•	Botones: Reiniciar, Siguiente, Seleccionar nivel (mini lista).
________________________________________
7) Sonido (sin archivos, solo WebAudio)
•	Sonidos generados proceduralmente:
o	Estirar resortera (tono que sube).
o	Lanzamiento (click + whoosh).
o	Impacto madera/piedra/vidrio (timbres distintos).
o	Eliminación cerdito (pop).
o	Victoria/derrota (jingle simple).
•	Control de volumen en UI (on/off).
________________________________________
8) Rendimiento, responsive y calidad de código
•	Canvas full-screen y escalado responsivo (mantener proporción, adaptar cámara).
•	requestAnimationFrame + fixed physics step con acumulador.
•	Código modular con clases:
o	Game, Renderer, Camera, PhysicsWorld, Body, Collider, ConstraintSlingshot, LevelManager, UIManager, AudioManager, ParticleSystem.
•	Comentarios claros y variables legibles.
•	Debe ejecutarse al abrir el HTML en el navegador sin configuración extra.
________________________________________
9) Restricciones finales (muy importantes)
•	No usar nombres, marcas, logos ni tipografías del juego original.
•	No usar imágenes, audios, sprites o assets externos.
•	Todo debe estar generado por código (formas, gradientes, sombras suaves, partículas).

El resultado debe ser la app-web lista para jugar y parecerse visualmente a las escenas: cielo con nubes, torre de madera/piedra/vidrio, cerditos verdes, trayectoria punteada, HUD superior y score.

Observaciones generales
•	El juego debe ser responsive
•	Se debe poder ocultar los menús
•	Se debe poder activar y desactivar el sonido
•	Aumentar una opción para que pueda jugar automático
```
