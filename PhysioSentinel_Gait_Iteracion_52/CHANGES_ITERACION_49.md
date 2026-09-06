# PhysioSentinel Gait · Iteración 49

## Objetivo
Corregir la capa biomecánica biplanar de V48 sin modificar el reloj físico ni el emparejamiento temporal consolidados en V47.

## Cambios principales

- Recuperación explícita de variables cinemáticas derivadas a partir de landmarks HALPE26 antes de normalizar el ciclo. Esto corrige el caso V48 en el que el perfil exportaba 0 variables frontales pese a existir tracking frontal válido.
- El ciclo homólogo sigue anclado por IC→IC (Initial Contact / Contacto Inicial a siguiente IC) y se normaliza a 0–100 %.
- Nuevo control de concordancia del TO (Toe Off / Despegue del Pie) entre frontal/posterior y lateral:
  - Δ ≤ 8 puntos porcentuales del ciclo: TO biplanar concordante y se informa un TO confirmado medio.
  - Δ > 8 y ≤ 15: concordancia limitada; se muestran ambos detectores, pero no se confirma un TO biplanar.
  - Δ > 15: discrepante; el TO no se usa como evento biplanar confirmado.
- Nuevas métricas exportadas de discrepancia TO, TO biplanar confirmado y número de variables integradas por plano.
- El panel V49 muestra de forma explícita cuántas curvas frontales y laterales se han integrado.
- Corrección de textos visibles residuales que mostraban “Versión 33”.
- Sin cambios deliberados en el estimador de reloj V47 ni en los criterios de emparejamiento físico de ciclos.

## Alcance
La integración continúa siendo 2D (Bidimensional) multiplanar. No realiza triangulación 3D (Tridimensional) ni cinética/inversa dinámica.
