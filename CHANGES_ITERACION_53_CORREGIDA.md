# PhysioSentinel Gait · V53 CORREGIDA

## Corrección principal
La interpretación V53 queda conectada directamente al generador del ZIP.

## Nuevos archivos de exportación
- `06_biplanar_v53/resumen_interpretacion_v53.json`
- `06_biplanar_v53/informe_interpretacion_v53.txt`
- `06_biplanar_v53/medicion_observada_variables_v53.csv`
- `06_biplanar_v53/eventos_referencia_v53.csv`

La exportación se genera desde los resultados V52/V51 ya calculados, por lo que no depende
del orden de renderizado de Streamlit ni de que el panel V53 se haya ejecutado antes del botón de descarga.

## Alcance
No se modifican sincronización, IC, TO, ciclo homólogo ni segmentación apoyo/oscilación.
No se introducen umbrales automáticos de normalidad/patología.
