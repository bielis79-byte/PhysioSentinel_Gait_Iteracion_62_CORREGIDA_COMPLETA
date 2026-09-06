# PhysioSentinel Gait · V55

## Objetivo
Primera capa geométrica real previa a reconstrucción 3D.

## Implementado
- Importación independiente de XML Tsai para cam01 y cam02.
- Parser tolerante a variantes habituales de etiquetas/atributos XML.
- Lectura de Geometry / Intrinsic / Extrinsic.
- Derivación de dpx = dx·ncx/nfx y dpy = dy cuando faltan.
- Construcción de:
  - K (matriz intrínseca pinhole equivalente)
  - R (rotación mundo→cámara)
  - t (traslación mundo→cámara)
  - P = K[R|t]
  - centro óptico de cada cámara en coordenadas mundo
- Control de det(R) y ortogonalidad.
- Transformación relativa cam01→cam02.
- Cálculo de baseline entre centros ópticos.
- Persistencia en session_state.
- Exportación completa en `07_calibracion_v55/`.
- V56 solo se declara preparada cuando:
  - V54 confirma ciclo homólogo;
  - ambas calibraciones son válidas;
  - la geometría relativa es válida.
- V55 NO triangula X,Y,Z.
- Se conserva el coeficiente kappa1 del modelo Tsai para que V56 trate correctamente la distorsión.

## GPJATK
Para el ensayo de control p12s3:
- cam01 = C2 frontal/anterior
- cam02 = C3 lateral

El dataset declara calibración en XML con modelo Tsai. La unidad angular se elige
explícitamente en la interfaz para evitar inferencias silenciosas.
