# PhysioSentinel Gait · V56

## Objetivo
Primera reconstrucción tridimensional real de landmarks HALPE26 a partir de
cam01 + cam02 calibradas y sincronizadas.

## Pipeline V56
1. Usa el reloj físico V47; NO alinea cámaras por fase biomecánica.
2. Restringe la reconstrucción al ciclo físico homólogo V48.
3. Interpola ambas detecciones 2D al mismo instante físico.
4. Si V48 detectó intercambio L/R entre vistas, corrige la correspondencia semántica.
5. Corrige la distorsión radial del modelo Tsai:
   xu = xd(1 + kappa1 r_d²), yu = yd(1 + kappa1 r_d²).
6. Convierte a coordenadas pinhole normalizadas.
7. Triangula con DLT de dos vistas usando [R|t].
8. Reproyecta el punto 3D a ambas cámaras con el modelo Tsai.
9. Calcula:
   - error de reproyección por cámara;
   - error medio;
   - profundidad en cada cámara;
   - ángulo entre rayos;
   - aceptación/rechazo por QC.
10. Conserva también los puntos rechazados para auditoría.

## Exportación
`08_triangulacion_v56/`
- resumen_triangulacion_v56.json
- resumen_triangulacion_v56.csv
- puntos_3d_halpe26_v56.csv
- control_calidad_por_frame_v56.csv
- control_calidad_por_landmark_v56.csv

## Alcance
- V56 sí genera X/Y/Z.
- V56 NO calcula todavía ángulos articulares 3D.
- V56 NO realiza cinética/inversa dinámica.
- La figura 3D es estática y de control; la animación se reserva para la etapa posterior.
- Los umbrales de confianza/reproyección/ángulo son controles internos experimentales,
  no umbrales clínicos validados.

## Capas previas
V47–V55 se mantienen sin cambios intencionados.
