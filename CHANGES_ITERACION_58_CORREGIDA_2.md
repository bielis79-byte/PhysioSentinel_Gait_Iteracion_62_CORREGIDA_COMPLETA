# PhysioSentinel Gait · V58 CORREGIDA 2

Corrige el `NameError: _v58c_export_v56_v58_to_zip is not defined`.

Causa: la función auxiliar de exportación V56/V58 estaba definida al final
del script, después de que Streamlit pudiera ejecutar `build_export_zip()`.

Corrección:
- `_v58c_export_v56_v58_to_zip()` y sus auxiliares se definen antes de
  `build_export_zip()`.
- Se conserva la exportación de `08_triangulacion_v56/`.
- Se conserva la exportación de `09_calibracion_estereo_v58/`.
- Se actualiza el pie visible a Versión 58 CORREGIDA 2.
- V56 CORREGIDA 3 permanece congelada: no se modifican Tsai, DLT,
  sincronización, triangulación ni QC.
