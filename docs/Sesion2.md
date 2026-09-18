---
titulo: MCU
fecha: 4-09-2026
autor: "David"
estado: completa
---

# Sesión 2— MCU

## Qué debía lograr hoy
- Configurar el entorno de desarrollo del ESP32, controlar entradas y salidas digitales (LED, botón con pull-up y antirrebote) y establecer comunicación Bluetooth con un protocolo de comandos.

## Qué usé
- Tarjeta: ESP32 DevKit V1 (WROOM-32). Importante: debe ser ESP32 “clásico”; las variantes S3/C3 no tienen Bluetooth Classic y los ejemplos de BluetoothSerial no compilan en ellas.
- Cable: USB de datos.
- Breadboard: + jumpers.
- LED: 1 + 1 resistor 220 Ω.
- Botón: 1 (push button).
- Resistor: (Opcional) 1 10 kΩ si no usamos pull-up interno.
Software:

- Arduino IDE + Paquete de tarjetas ESP32.
(Opcional) VS Code + Extensión Arduino.

## Qué hice y qué pasó (evidencia)

![Código en Arduino IDE](recursos/imgs/MCU_Sesion_2.png)

![Circuito físico en el protoboard](recursos/imgs/MCU_Sesion_2_(2).png)

## Qué falló y cómo lo resolví
- **Síntoma:** El circuito y el código estaban bien, pero el Bluetooth de la ESP32 (con nombre "pes") no aparecía en la lista de dispositivos del celular.
- **Cómo lo encontré:** Al abrir la aplicación de terminal Bluetooth en el teléfono y escanear los dispositivos cercanos, la placa no figuraba.
- **Solución:** En la clase no funciono.No pudimos resolverlo al momento porque el tiempo de la clase se termino, por lo que el LED no prendió.



## Qué aprendí
*Aprendi como usar el software de "arduino IDE" y hacer codigo con ese programa tambien el como conectarlo con el arduino que teniamos*


