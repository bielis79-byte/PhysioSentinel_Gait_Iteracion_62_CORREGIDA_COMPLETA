# PhysioSentinel Gait · V57

## V57 · Esqueleto 3D dinámico e interactivo

V57 se construye sobre la triangulación ya validada de V56 CORREGIDA 3.
No modifica el reloj físico, la fase biomecánica, la calibración Tsai,
la triangulación DLT ni los controles de calidad.

### Funciones
- Animación completa del ciclo 3D a partir de los X/Y/Z de V56.
- Rotación libre 360° con ratón.
- Zoom interactivo con rueda.
- Pan/desplazamiento de cámara.
- Slider de fase 0–100 %.
- Reproducir y pausa.
- Velocidades 0,25× / 0,5× / 1× / 2×.
- Vistas rápidas: 3D oblicua, frontal, posterior, lateral A/B y superior.
- Etiquetas opcionales de landmarks.
- Trayectoria 3D opcional de cualquier landmark.
- Hover con X/Y/Z, error de reproyección y ángulo de triangulación.
- Rangos espaciales fijos durante toda la animación para evitar cambios de zoom.
- `uirevision` para favorecer la conservación de la cámara durante interacción.

### Dependencia nueva
`plotly>=6.0,<7`

### Capas congeladas
V47–V56 CORREGIDA 3 no se modifican intencionadamente.
