# PhysioSentinel Gait · V56 CORREGIDA 3

## Objetivo
Corregir únicamente la prioridad de exportación del ZIP global.

## Problema
V56 CORREGIDA 2 triangulaba correctamente con el reloj físico maestro
(~ -0.0167 s en GPJATK p12s3), pero el ZIP global podía recuperar una
estructura V56 viva obsoleta correspondiente a una triangulación previa
con -0.270 s.

El ZIP específico de respaldo V56 sí contenía el resultado correcto.

## Corrección
- El ZIP global prioriza SIEMPRE `v56_export_payload`.
- Ese payload se crea exactamente al finalizar la triangulación más reciente.
- `v56_triangulation` queda únicamente como fallback si no existe payload.
- El payload incorpora:
  - `payload_version = 56-corregida-3`
  - `source = generado en el momento de triangular`
- El resumen V56 pasa a:
  - `version = 56-corregida-3`

## No modificado
- Reloj físico V47/V38.
- Separación de fase biomecánica.
- DLT 3D.
- Corrección de distorsión Tsai.
- Reproyección.
- QC por punto/frame/landmark.
- V47–V55.

## Resultado esperado
Tras triangular y exportar, el ZIP global y el ZIP específico V56 deben
contener la misma ejecución:
- physical_clock_offset_s ~ -0.0166667 s
- biomechanical_phase_offset_s ~ -0.270 s
- phase_offset_used_for_triangulation = false
- 08_triangulacion_v56/ presente en el ZIP global
