# PhysioSentinel Gait · V55 CORREGIDA

## Problema corregido
V55 podía conservar `homologous_cycle_available=false` si la calibración XML se
había cargado antes de que V48/V54 reconstruyera el ciclo homólogo en la misma
ejecución de Streamlit.

Esto producía una inconsistencia:
- V48/V54: ciclo homólogo válido.
- V55: ciclo homólogo pendiente.
- `v56_triangulation_ready=false`.

## Corrección
- V55 usa `st.session_state["biplanar_v48_profile"]` como fuente de verdad viva.
- La pantalla recalcula el estado del ciclo homólogo en cada rerun.
- El exportador vuelve a leer V48 EN EL MOMENTO DE EXPORTAR.
- Se recalculan:
  - homologous_cycle_available
  - homologous_pair_index
  - front_side
  - lateral_side
  - integration_confidence
  - ic_alignment_delta_ms
  - front_cycle_s
  - lateral_cycle_s
  - v56_triangulation_ready
- La calibración Tsai K/R/t/P no se modifica.
- V47–V54 no se modifican.
- La triangulación 3D continúa desactivada en V55; solo se declara preparada para V56.

## Resultado esperado con GPJATK p12s3
- ciclo homólogo: OK
- par: #4
- lado: L/L
- confianza: Alta
- ΔIC: ~ -10 ms
- ciclo frontal/lateral: 1.16 / 1.16 s
- cam01 C2: válida
- cam02 C3: válida
- geometría relativa: válida
- P1/P2: listas
- V56 triangulation ready: true
