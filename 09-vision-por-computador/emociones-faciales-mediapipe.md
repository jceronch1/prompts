# Detector de emociones faciales en tiempo real

**Categoría:** [Visión por computador](README.md) · **Tecnologías:** MediaPipe, Three.js

App web que estima emociones con la cámara usando landmarks faciales 3D.

## Prompt

```text
Claude Opus 4.6 Vs gpt-5.3-codex xhigh

Actúa como un desarrollador web senior en visión por computador y gráficos 3D.

Quiero que construyas una aplicación web que estime emociones faciales en tiempo real usando la cámara frontal del ordenador. La app debe detectar y mostrar emociones como: alegría, tristeza, enojo, miedo, sorpresa, aburrimiento, llorando, neutral (y otras relevantes).

## Requisitos técnicos obligatorios
1. Usar **MediaPipe** para:
   - Captura del rostro.
   - Extracción de **facial landmarks 3D** en tiempo real.
2. Usar **Three.js** para:
   - Renderizar un efecto visual sobre el rostro (máscara/filtro/mesh/partículas) alineado con los landmarks.
   - Mantener seguimiento fluido del rostro en movimiento.
3. Usar la **cámara frontal** del equipo (`getUserMedia`).

## Funcionalidades de la interfaz
1. Mostrar el video en vivo de la cámara.
2. Superponer el efecto 3D sobre el rostro en tiempo real.
3. Mostrar en pantalla la **emoción predominante** en tiempo real, con lenguaje inclusivo y no estigmatizante (ejemplo: “Emoción estimada: Alegría”).
4. Mostrar una **tabla en tiempo real** con todas las emociones detectadas y su porcentaje de confianza:
   - Columnas: Emoción | Porcentaje (%)
   - Orden descendente por porcentaje
   - Actualización continua (sin recargar página)

## Requisitos de calidad
1. Rendimiento fluido (objetivo: ~20–30 FPS si el hardware lo permite).
2. Manejo de errores:
   - Sin permisos de cámara
   - Sin rostro detectado
   - Cámara no disponible
3. Privacidad:
   - Todo el procesamiento debe ejecutarse localmente en el navegador.
   - No subir imágenes/video a servidores.
4. Código limpio, modular y comentado.

## Entregables
1. Código completo en **HTML + CSS + JavaScript** (ejecutable en navegador moderno).
2. Instrucciones de ejecución paso a paso.
3. Explicación breve de:
   - Cómo se calcula la emoción predominante.
   - Cómo se normalizan los porcentajes.
   - Cómo se alinea el efecto de Three.js con los landmarks de MediaPipe.

Si alguna librería requiere CDN o instalación local, inclúyela explícitamente.
```
