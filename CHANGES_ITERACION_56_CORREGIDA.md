# PhysioSentinel Gait · V56 CORREGIDA

Corrige el requisito HALPE26 de V56.

La V56 original dependía solo de `analysis_df` y `analysis_df2`, pero la app
los elimina después de calcular resultados. El análisis biplanar conserva las
copias ligeras realmente usadas:
- `biplanar_seg_front`
- `biplanar_seg_lateral`
- `biplanar_fps_front`
- `biplanar_fps_lateral`
- `biplanar_sync_offset_s`

V56 CORREGIDA usa primero los DataFrames vivos si existen y, si ya fueron
eliminados, usa automáticamente esos segmentos preservados. También conserva
el mismo reloj físico del pipeline biplanar que produjo V48.

No se modifica V47–V55 ni se fuerza ningún requisito a OK.
