# PhysioSentinel Gait · V56 CORREGIDA 2

## Corrección temporal crítica
V56 CORREGIDA utilizaba `biplanar_sync_offset_s`, que en el ensayo GPJATK p12s3
contenía el desfase de fase biomecánica V39 (-0.270 s), no el reloj físico.

V56 CORREGIDA 2 usa EXCLUSIVAMENTE:
`biplanar_v46_physical_clock_offset_s`

Para p12s3, el valor esperado es aproximadamente -0.0166667 s.

El desfase biomecánico se sigue mostrando como diagnóstico, pero:
- no gobierna la correspondencia temporal 3D;
- no puede actuar como fallback;
- queda registrado como `phase_offset_used_for_triangulation = false`.

## Exportación robusta
Al finalizar la triangulación se crea un payload serializado persistente:
`v56_export_payload`.

La exportación global puede escribir `08_triangulacion_v56/` desde:
1. los DataFrames V56 vivos; o
2. el payload serializado si hubo reruns.

Además se incorpora una descarga específica:
`PhysioSentinel_V56_triangulacion_3D.zip`
con X/Y/Z y controles de calidad.

## Exportación V56
- resumen_triangulacion_v56.json
- resumen_triangulacion_v56.csv
- puntos_3d_halpe26_v56.csv
- control_calidad_por_frame_v56.csv
- control_calidad_por_landmark_v56.csv

## Capas previas
V47–V55 no se modifican.
