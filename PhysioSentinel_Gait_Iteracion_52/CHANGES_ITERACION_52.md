# PhysioSentinel Gait · Iteración 52

## Objetivo
Convertir el ciclo físico homólogo ya estabilizado en V47–V51 en un ciclo biomecánico biplanar clínico completo IC→apoyo→TO→oscilación→IC, sin modificar sincronización ni detectores previos.

## Cambios
- Mantiene congelados reloj físico V47, emparejamiento IC→IC y detector TO jerárquico V51.
- Usa `v51_selected_to_pct` como frontera clínica entre apoyo y oscilación.
- Calcula porcentaje y duración de apoyo y oscilación.
- Etiqueta cada punto del ciclo normalizado 0–100 % como Apoyo u Oscilación.
- Resume las curvas frontales y laterales por fase: media, mínimo, máximo y ROM.
- Añade una línea temporal clínica IC→TO→IC en la interfaz.
- Exporta carpeta `06_biplanar_v52` con resumen, eventos, curvas y métricas por fase.
- Sigue siendo integración 2D multiplanar; no triangula 3D ni estima fuerzas/momentos.
