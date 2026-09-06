# PhysioSentinel Gait · V54 CORREGIDA

## Bug localizado
La corrección inicial solo cambió el valor usado por el `number_input`, pero había dos
bloques anteriores que, al calcular la heurística preliminar, seguían ejecutando:

`sync_offset_user_s = off`

Por eso el valor heurístico `-0.96 s` reaparecía antes de mostrarse el campo.

## Corrección
- Se eliminan las dos escrituras heurística → desfase operativo.
- La heurística solo actualiza `sync_offset_auto_s`.
- Se añade una migración única que pone `sync_offset_user_s = 0.0` al entrar por primera
  vez en V54 corregida, evitando arrastrar el `-0.96` de una sesión Streamlit ya abierta.
- El usuario puede seguir modificando manualmente el desfase operativo después.
- En modo de validación, el ground truth conocido continúa teniendo prioridad.
- No se modifica V47–V53 ni el módulo geométrico pre-3D.
