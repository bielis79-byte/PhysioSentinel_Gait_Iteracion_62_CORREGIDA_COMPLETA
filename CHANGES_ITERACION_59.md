# PhysioSentinel Gait · Iteración 59

- Interfaz reorganizada en tres niveles de análisis:
  1. Nivel 1 · 2D una cámara.
  2. Nivel 2 · Biplanar 2D frontal/posterior + lateral, sin calibración 3D obligatoria.
  3. Nivel 3 · 3D calibrado frontal/posterior + lateral.
- Se mantiene disponible el análisis 2D/biplanar cuando no existe calibración 3D válida.
- Corrección del gestor de borrado de registros longitudinales en Supabase:
  - elimina métricas y sesión;
  - verifica posteriormente que la sesión ya no exista;
  - solo informa éxito cuando el borrado queda confirmado;
  - limpia la selección tras el borrado;
  - corrige etiquetas que mostraban representaciones internas de pandas como `<bound method Series.view ...>`.
- Se conservan sin cambios los algoritmos congelados de sincronización, calibración Tsai y triangulación V56, así como el módulo ChArUco/OpenCV de V58 salvo integración de interfaz.
