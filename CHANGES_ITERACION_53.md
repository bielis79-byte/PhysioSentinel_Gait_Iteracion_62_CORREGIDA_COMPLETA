# PhysioSentinel Gait · Iteración 53

## Objetivo
Añadir una capa de interpretación biomecánica biplanar explicable sobre el ciclo clínico V52.

## Cambios
- Mantiene congeladas las capas V47–V52: no modifica reloj físico, sincronización, IC, TO ni segmentación del ciclo.
- Añade panel V53 de interpretación biomecánica biplanar 2D.
- Separa explícitamente **medición observada** de **interpretación clínica**.
- Resume IC→apoyo→TO→oscilación→IC y conserva la calidad/incertidumbre heredada.
- Integra conceptualmente las variables frontal/posteriores y sagitales sobre el mismo ciclo 0–100 %.
- Cuando las métricas V52 están disponibles en `session_state`, genera descripciones cuantitativas por variable: cambio IC→TO, ROM en apoyo, ROM en oscilación y cierre IC→IC.
- No etiqueta automáticamente valores como normales, patológicos, diagnósticos o pronósticos.
- Persiste `v53_interpretation` para su inclusión por exportadores compatibles.

## Alcance
Análisis 2D (Bidimensional) multiplanar. No equivale a reconstrucción 3D (Tridimensional), plataforma de fuerzas ni dinámica inversa.
