---
titulo: Vision 101
fecha: 2-10-2026
autor: "David"
estado: completa
---

# Sesión 5 — vision 101
## Qué debía lograr hoy
Objetivo: Entender cómo funciona la vision por computadora haciendo codigo en visual studio code.
1. Resumen de lo realizado en la sesiónDurante esta sesión trabajamos con la librería OpenCV en Python dentro de Visual Studio Code para procesar imágenes y video en tiempo real:Concepto de Imagen Digital: Comprensión de las imágenes como matrices tridimensionales ($ALTO \times ANCHO \times CANALES$) en espacios BGR y HSV.Captura de Video en Vivo: Acceso a la cámara web mediante un bucle principal de procesamiento marco por marco.Segmentación y Filtrado por Color: Conversión al espacio HSV y aplicación de rangos de color mediante máscaras binarias (inRange).Dibujo de Formas y Texto: Superposición de geometrías (líneas, círculos, elipses, rectángulos) y texto en tiempo real sobre la transmisión de la cámara.


A. Inicialización y Captura de Video
cv2.VideoCapture(0): Inicia la transmisión de video desde la cámara web integrada o conectada (0).
cap.set(...): Establece la resolución horizontal y vertical a $1280 \times 720$ píxeles.while True: y cap.read(): Mantiene la cámara capturando imagen tras imagen de manera continua.

B. Filtrado y Espacio de Color HSVcv2.cvtColor(..., cv2.COLOR_BGR2HSV): Cambia el formato de color de BGR a HSV. El formato HSV permite aislar el color real sin importar las variaciones de sombra o luz en la habitación.cv2.inRange(...): Filtra los píxeles que están entre el rango de valores low y high, creando una máscara donde lo que coincide con el color es blanco y lo demás negro.cv2.bitwise_and(...): Recorta el color original aplicando la máscara.

C. Formas Geométricas y Textocv2.line(...): Traza una línea recta especificando coordenada inicial, final, color BGR y grosor.cv2.circle(...): Dibuja un círculo definiendo su centro y su radio.cv2.ellipse(...) y cv2.rectangle(...): Dibujan elipses y rectángulos sobre la pantalla.cv2.putText(...): Escribe texto directamente en el video de la cámara.

D. Salida y Cierrecv2.imshow(...): Abre las ventanas para ver la imagen original, la máscara en blanco y negro, y la imagen filtrada.cv2.waitKey(1): Detecta cuando presionas la tecla q en el teclado para finalizar el programa y cerrar las 

