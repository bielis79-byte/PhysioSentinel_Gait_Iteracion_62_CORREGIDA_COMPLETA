# PhysioSentinel Gait · V58 CORREGIDA

## Corrección
La exportación global ahora incorpora explícitamente:

- `08_triangulacion_v56/`
  - prioriza `v56_export_payload` de V56 CORREGIDA 3;
  - solo usa `v56_triangulation` como fallback;
  - no recalcula ni modifica Tsai, DLT, sincronización o QC.

- `09_calibracion_estereo_v58/`
  - `perfil_calibracion_v58.json`
  - `resumen_calibracion_v58.json` cuando existe calibración calculada
  - `qc_detecciones_charuco_v58.csv` cuando existe
  - `manifiesto_exportacion_v58.json` siempre

El perfil V58 activo cargado desde JSON también se conserva aunque no se haya recalibrado en esa sesión.

V55/V56 permanecen congeladas.
