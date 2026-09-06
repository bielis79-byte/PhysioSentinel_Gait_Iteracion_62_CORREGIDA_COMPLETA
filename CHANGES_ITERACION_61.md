# PhysioSentinel Gait · Versión 61

## Informe integrado y anexo maestro

- La pestaña 6 incorpora **Visión integrada de los resultados**, un bloque editable que reúne en una sola lectura:
  - parámetros espaciotemporales disponibles;
  - hallazgos 2D frontal/posterior;
  - hallazgos 2D lateral/sagital;
  - integración biplanar sobre el ciclo físico homólogo;
  - estado del 3D estimado/no métrico;
  - estado y QC del 3D calibrado cuando existe.
- La síntesis distingue explícitamente qué información es 2D, biplanar, 3D estimada y 3D calibrada, evitando convertir automáticamente los resultados en diagnóstico.
- La exportación TXT incorpora la nueva visión integrada.
- La pestaña 11 pasa a usar un **diccionario maestro de variables**: añade a las métricas principales los parámetros escalares biplanares, las métricas V52 por fase disponibles y las variables/QC de V60/V56 cuando existen.
- El 3D estimado se etiqueta siempre como no métrico; X/Y/Z normalizadas no se presentan como cm/mm.
- El 3D calibrado conserva los controles geométricos V56 (aceptación, reproyección y ángulo de triangulación) sin modificar su algoritmo.
- Se mantienen las correcciones V59 de borrado verificado de registros y los dos modos 3D de V60.
