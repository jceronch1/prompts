# Simulador 3D para ensamblar un PC

**Categoría:** [Educación e investigación](README.md) · **Tecnologías:** Three.js

App educativa 3D para aprender a identificar y ensamblar los componentes de un computador.

## Prompt

```text
Desarrolla una aplicación web educativa e interactiva en 3D para estudiantes de primer semestre del Técnico en Reparación de Computadores, cuyo objetivo es aprender a identificar, nombrar y ensamblar correctamente los componentes internos y externos de un computador de escritorio. Usa Three.js como motor de renderizado 3D con JavaScript ES6+.

🎓 Propósito pedagógico
La aplicación debe funcionar como una herramienta didáctica de aprendizaje activo, donde el estudiante:

Reconoce visualmente cada componente de hardware
Comprende la función de cada pieza dentro del sistema
Practica el proceso correcto de ensamblaje en un entorno seguro y sin riesgo físico
Recibe retroalimentación inmediata sobre sus acciones
Evalúa su progreso al finalizar el ensamblaje

🖥️ Componentes a incluir
Internos (dentro del gabinete/case):

Gabinete ATX con panel lateral removible
Tarjeta Madre (Motherboard) con slots y puertos visibles y etiquetados
Microprocesador (CPU) con socket indicado
Disipador térmico (Cooler) con ventilador
Módulos de Memoria RAM (slots DIMM)
Tarjeta Gráfica (GPU)
Disco Duro HDD y unidad SSD
Fuente de Alimentación (PSU)

Externos (periféricos):

Monitor
Teclado
Mouse
Parlantes

⚙️ Funcionalidades requeridas
Interacción 3D completa:

Cámara orbital libre con OrbitControls: rotar, hacer zoom y desplazarse libremente por toda la escena con mouse o touch.
Agarre y movimiento real de piezas: el estudiante puede hacer clic y mantener presionado sobre cualquier componente para tomarlo, moverlo libremente por el espacio 3D y soltarlo donde desee, simulando el manejo físico real de las piezas.
Snapping guiado: al acercar una pieza a su ranura correcta, encaja automáticamente con una animación suave acompañada de un efecto visual de confirmación.
Resaltado de compatibilidad: al tomar una pieza, los slots donde puede ir se iluminan en verde; los incompatibles se marcan en rojo.
Validación con feedback inmediato: si se suelta una pieza en lugar incorrecto, vibra visualmente y muestra mensaje educativo explicando por qué no va ahí.

Herramientas de iluminación y visualización:

Barra deslizante de iluminación (slider) ubicada en la interfaz, que permite al estudiante regular la intensidad de luz de la escena entre muy oscuro y muy brillante, para examinar detalles de los componentes con comodidad. La iluminación por defecto debe ser clara y bien visible.
Modo linterna / foco: botón que activa una luz puntual que sigue al cursor, permitiendo iluminar zonas específicas del interior del gabinete como si fuera una linterna real, útil para ver piezas en el interior.
Panel de zoom de componente: doble clic sobre cualquier pieza para verla aislada en primer plano con rotación libre y mayor detalle, antes de volver a la escena principal.

Contenido educativo integrado:

Etiquetas flotantes (labels 3D): cada componente tiene su nombre visible en todo momento sobre él, con tipografía clara y legible.
Ficha técnica didáctica: al hacer clic en cualquier pieza aparece un panel lateral con nombre oficial, función dentro del sistema, características técnicas básicas (en lenguaje accesible para primer semestre) y una curiosidad o dato práctico relevante para un técnico.
Guía de ensamblaje paso a paso: modo tutorial que indica al estudiante cuál pieza debe colocar a continuación, en qué orden lógico y por qué, con flechas animadas que señalan la posición correcta.
Panel de progreso académico: barra de avance que muestra cuántos componentes han sido ensamblados correctamente (ej. "6 de 12 componentes instalados — 50% completado"), con nombre de cada pieza pendiente.
Evaluación final: al completar el ensamblaje, la aplicación presenta un resumen con puntaje, tiempo empleado, número de intentos fallidos y un mensaje de retroalimentación personalizado.
Animación de encendido como recompensa: al lograr el ensamblaje correcto, el PC "enciende" con animación de LEDs, ventiladores girando y monitor activándose, como celebración del logro.

🎨 Estilo visual académico

Modelos 3D low-poly limpios y bien diferenciados por color, fáciles de identificar para un estudiante sin experiencia previa.
Fondo claro o neutro (gris claro tipo laboratorio técnico), que no compita visualmente con las piezas.
Iluminación por defecto: alta y uniforme, garantizando que todos los componentes sean perfectamente visibles desde el inicio sin necesidad de ajustes.
UI con panel lateral translúcido que lista los componentes disponibles con íconos representativos.
Tipografía clara, botones grandes y colores accesibles pensados para pantallas de aula.
Esquema de color: fondo claro con acentos en azul técnico y verde confirmación.
La carcasa debe ser transparente para poder ver los componentes internos.

🧱 Stack tecnológico

Three.js (r150+) — renderizado 3D
GSAP — animaciones de ensamblaje y transiciones
HTML5 + CSS3 — interfaz de usuario
JavaScript ES6+ modular
OrbitControls + DragControls + TransformControls de Three.js para la interacción completa con las piezas

📦 Entregable
Archivo index.html autocontenido, ejecutable directamente en el navegador sin backend ni archivos externos, con todos los modelos construidos proceduralmente mediante geometrías nativas de Three.js. Debe funcionar correctamente en los navegadores de las salas de cómputo institucionales (Chrome / Firefox actualizados).
```
