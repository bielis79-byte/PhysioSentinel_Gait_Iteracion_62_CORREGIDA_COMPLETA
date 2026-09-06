# PhysioSentinel Gait · Iteración 54

## Corrección temporal
- La heurística preliminar de movimiento ya no rellena automáticamente el campo **Desfase operativo cam02 respecto a cam01 (s)**.
- En uso clínico, el valor operativo parte de **0,00 s** salvo que exista un valor manual previamente elegido en la sesión.
- En modo de validación, el ground truth conocido sigue teniendo prioridad.
- La heurística continúa visible únicamente como referencia diagnóstica.

## Preparación geométrica pre-3D
- Nuevo panel de requisitos previos para calibración y triangulación 3D.
- Se mantienen congeladas V47–V53.
- Se identifican como pendientes:
  - intrínsecos de cam01;
  - intrínsecos de cam02;
  - extrínsecos entre cámaras;
  - verificación del solapamiento simultáneo del campo visual.
- La triangulación 3D permanece desactivada en V54.
- Nueva exportación `06_biplanar_v54` en JSON y CSV.

## Alcance
V54 prepara la arquitectura geométrica. No realiza todavía reconstrucción 3D.
