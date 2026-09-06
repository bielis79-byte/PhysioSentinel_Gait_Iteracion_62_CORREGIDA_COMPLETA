# PhysioSentinel Gait · Iteración 51

## Objetivo
Introducir un detector de TO (Toe Off / Despegue del Pie) jerárquico y dependiente de la perspectiva, manteniendo congelado el reloj físico y el emparejamiento temporal de V47.

## Cambios principales
- La vista lateral/sagital pasa a ser la fuente primaria para localizar TO.
- La vista frontal/posterior actúa como evidencia secundaria de compatibilidad y ya no tiene el mismo peso geométrico que la lateral.
- Si los candidatos frontal y lateral coinciden dentro de la tolerancia temporal, V51 clasifica el evento como `Confirmado biplanar directo`.
- Si no coinciden, V51 evalúa la activación frontal exactamente en el instante TO propuesto por la lateral. Si existe respaldo suficiente, clasifica `Confirmado jerárquico` sin promediar ambos candidatos.
- Si la frontal es débil o no concluyente, el TO lateral puede conservarse como probable, pero no se etiqueta como confirmado biplanar.
- El TO seleccionado conserva una resolución práctica de ±1 frame de la cámara lateral; no se presenta como intervalo de confianza estadístico.
- V51 no modifica IC (Initial Contact / Contacto Inicial), IC→IC, reloj V47, offset físico ni emparejamiento de ciclos.
- Se mantienen los resultados y la auditoría V50 para trazabilidad.

## Nuevas salidas
Carpeta `06_biplanar_v51`:
- `resumen_to_jerarquico_v51.json`
- `resumen_to_jerarquico_v51.csv`
- `auditoria_to_jerarquico.csv`

Nuevas métricas principales:
- `v51_selected_to_pct`
- `v51_to_confirmed`
- `v51_front_support_at_lateral_to`
- `v51_selected_to_uncertainty_ms`
- `v51_to_status`
- `v51_to_quality`

## Alcance metodológico
El detector sigue siendo experimental y basado en cinemática 2D (Bidimensional). La jerarquía dependiente de perspectiva evita forzar una equivalencia entre cámaras con distinta sensibilidad geométrica al despegue. No equivale a una plataforma de fuerzas, GRF (Ground Reaction Force / Fuerza de Reacción del Suelo) ni validación cinética.
