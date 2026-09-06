# PhysioSentinel Gait · V58

## V58 · Calibración clínica estéreo ChArUco

Objetivo: eliminar la dependencia práctica de XML externos para futuros vídeos clínicos.

### Funcionalidad
- Generador de tablero ChArUco descargable en PNG.
- Parámetros configurables:
  - número de cuadrados X/Y;
  - tamaño físico de cuadrado y marcador;
  - diccionario ArUco.
- Entrada de dos vídeos de calibración simultáneos:
  - cam01 frontal;
  - cam02 lateral.
- Muestreo temporal uniforme.
- Detección ChArUco por cámara.
- Calibración intrínseca independiente de ambas cámaras.
- Calibración estéreo con intrínsecos fijados.
- Cálculo de:
  - K y distorsión Brown-Conrady/radtan;
  - R y T cam01→cam02;
  - centros de cámara;
  - baseline en mm;
  - E y F;
  - RMS intrínseco;
  - RMS estéreo;
  - error epipolar medio y P95.
- Control de detecciones por muestra.
- Guardado de perfil JSON reutilizable.
- Recarga/activación de perfil guardado.
- Condiciones explícitas para reutilizar calibración.

### Decisión metodológica
V55/V56 Tsai de GPJATK permanecen congeladas.
V58 NO convierte silenciosamente Brown-Conrady a Tsai.
El perfil V58 queda preparado para una futura ruta clínica de triangulación OpenCV.

### Dependencia
Se reemplaza:
`opencv-python-headless`
por:
`opencv-contrib-python-headless>=4.10,<5`

Esto es necesario para ArUco/ChArUco.
