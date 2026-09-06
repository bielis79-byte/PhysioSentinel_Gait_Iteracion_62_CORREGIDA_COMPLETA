# PhysioSentinel Gait · Iteración 50

## Objetivo
Auditar y resolver de forma conservadora la discrepancia del TO (Toe Off / Despegue del Pie) detectada en V49, sin modificar el reloj físico V47 ni los ciclos IC→IC ya aceptados.

## Cambios
- Mantiene congelada la sincronización física V47.
- Añade detector V50 de onset distal multiseñal por cada vista.
- Lateral: combina avance del pie respecto a pelvis, ascenso distal y velocidad del pie.
- Frontal/posterior: usa velocidad distal y ascenso como evidencia secundaria, con confianza conservadora por geometría.
- Busca el inicio persistente de activación dentro de 35–82% del ciclo, evitando confundir TO con el máximo tardío de velocidad de oscilación.
- Solo confirma TO biplanar si ambos candidatos convergen ≤8 puntos porcentuales y superan calidad mínima.
- Si el lateral es internamente consistente pero el frontal no converge, lo etiqueta como respaldo lateral, no como confirmación biplanar.
- Exporta resumen V50 y auditoría de señales a `06_biplanar_v50/`.
- No triangula 3D ni estima fuerzas/GRF.

## Seguridad metodológica
V50 no promedia detectores discrepantes, no desplaza el reloj y no altera IC. El TO continúa siendo una inferencia cinemática markerless 2D y no un evento cinético validado por plataforma de fuerzas.
