---
titulo: Vision 101
fecha: 2-10-2026
autor: "David"
estado: completa
---

# Sesión 5 — vision 101
## Qué debía lograr hoy

1. Objetivos de la Sesión 
Entender los fundamentos de la visión por computadora mediante OpenCV.

Capturar y procesar flujo de video en tiempo real.

Aplicar técnicas de filtrado por color y superposición gráfica sobre fotogramas.

2. Resumen de ActividadesConcepto de Imagen DigitalComprensión de imágenes como matrices de datos con estructura ALTO x ANCHO x CANALES.

Manejo de espacios de color BGR y HSV.
Captura de Video 

Conexión con la cámara web integrada.

Procesamiento cuadro por cuadro mediante un bucle continuo.
```cpp
import cv2
import numpy as np

# 1. Inicialización de cámara
cap = cv2.VideoCapture(0)

if not cap.isOpened():
    raise RuntimeError("No se pudo abrir la cámara")

# Configurar resolución (opcional)
cap.set(cv2.CAP_PROP_FRAME_WIDTH, 1280)
cap.set(cv2.CAP_PROP_FRAME_HEIGHT, 720)

# Bucle principal de procesamiento
while True:
    ok, frame = cap.read()
    if not ok:
        break

    # Conversión a espacio HSV
    hsv = cv2.cvtColor(frame, cv2.COLOR_BGR2HSV)

    # Rango de color a segmentar (verde)
    low = np.array([35, 60, 60], dtype=np.uint8)
    high = np.array([85, 255, 255], dtype=np.uint8)

    # Aplicación de máscara binaria
    filtro = cv2.inRange(hsv, low, high)
    filtrada = cv2.bitwise_and(frame, frame, mask=filtro)

    # Dibujo de formas geométricas
    cv2.line(frame, (0, 0), (280, 80), (0, 255, 0), 2)
    cv2.circle(frame, (230, 180), 20, (0, 0, 255), 2)
    cv2.ellipse(frame, (290, 315), (80, 35), 0, 0, 360, (255, 0, 0), 2)
    cv2.rectangle(frame, (310, 160), (380, 200), (0, 255, 255), 2)
    cv2.putText(frame, "Hola Mundo!", (20, 450), 
                cv2.FONT_HERSHEY_SIMPLEX, 1.0, (255, 255, 255), 2)

    # Salida visual
    cv2.imshow("Original", frame)
    cv2.imshow("Mascara", filtro)
    cv2.imshow("Filtrada", filtrada)

    # Condición de cierre
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```

Explicación línea por línea del código
A. Captura y Bucle de Video
cv2.VideoCapture(0): Abre la cámara web principal del equipo.

cap.set(...): Configura el ancho (1280px) y alto (720px) de la transmisión.

while True: y cap.read(): Lee el fotograma actual del flujo de la cámara de manera continua.

B. Segmentación HSV y Filtrado
cv2.cvtColor(frame, cv2.COLOR_BGR2HSV): Transforma la imagen de BGR a HSV para aislar el tono del color de las sombras.

cv2.inRange(hsv, low, high): Genera una máscara binaria (blanco donde el color está dentro del rango, negro fuera de él).

cv2.bitwise_and(...): Filtra el área de interés combinando el fotograma original con la máscara.

C. Dibujo de Formas Geométricas y Texto
cv2.line(...): Dibuja una línea indicando punto inicial, final, color BGR y grosor.

cv2.circle(...): Crea un círculo especificando su centro y radio.

Durante la sesion vimos estas herramientas y fue bastante interesante la sesion, pudimos verlos filtros y hacer codigo y usamos python. 
