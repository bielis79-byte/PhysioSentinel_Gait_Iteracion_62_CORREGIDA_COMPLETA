# PhysioSentinel Gait · Iteración 60

## Dos rutas 3D claramente diferenciadas
- Nivel 1: 2D monocámara, sin calibración.
- Nivel 2: biplanar frontal/posterior + lateral con visor 3D estimado/no métrico.
- Nivel 3: 3D calibrado cuantitativo; si falta calibración conserva el 3D estimado como respaldo visual.

## 3D estimado/no métrico
- Fusiona landmarks HALPE26 sincronizados en tiempo físico.
- Usa X-Y normalizado de frontal/posterior y Z-Y normalizado de lateral.
- Normaliza cada vista por escala corporal aparente para no mezclar directamente píxeles de cámaras distintas.
- Reutiliza el visor Plotly interactivo: rotación, zoom, animación, slider, vistas y trayectorias.
- Etiquetado explícito NO MÉTRICO: no se usa para cm/mm, distancias, desplazamientos o ángulos 3D cuantitativos.

## 3D calibrado
- Conserva sin cambios la ruta validada V55/V56 Tsai + DLT y el visor V57.
- V56/V57 calibrados se muestran en Nivel 3.
- La ausencia de calibración nunca genera falsas coordenadas métricas.

## Persistencia
- Se mantienen las correcciones V59 de eliminación verificada de registros Supabase.
