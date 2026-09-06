# PhysioSentinel Gait · Versión 62 CORREGIDA

## Corrección del visor 3D estimado/no métrico

- Se corrige la correspondencia entre las etiquetas de las vistas rápidas y la cámara virtual del 3D estimado V60.
- Convención explícita del 3D estimado: X = horizontal frontal, Y = vertical corporal, Z = profundidad aproximada derivada de la cámara lateral.
- Frontal/Posterior miran ahora a lo largo de Z.
- Lateral A/Lateral B miran ahora a lo largo de X.
- Superior mira ahora a lo largo de Y.
- La vista 3D oblicua usa Y como eje vertical.
- Los presets específicos se aplican solo al 3D estimado/no métrico.
- El visor 3D calibrado V56/V57 conserva sus presets originales y no se modifica la triangulación, sincronización, QC ni los cálculos biomecánicos.
