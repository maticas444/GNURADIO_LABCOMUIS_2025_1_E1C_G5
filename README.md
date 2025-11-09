# Misión 6

## Fase 1:

* **Objetivo Específico 1.1:** Diseñar un guion para un bloque de programación de 60 a 90 segundos que incluya una introducción (jingle), un segmento de voz y una pieza musical.
* **Objetivo Específico 1.2:** Grabar y/o seleccionar los elementos de audio definidos en el guion.
* **Objetivo Específico 1.3:** Utilizar un software de edición de audio (ej. Audacity) para ensamblar, mezclar y masterizar los elementos en un único archivo de audio. El producto final debe ser un archivo estéreo (dos canales: Izquierdo y Derecho) en formato `.wav` para preservar la máxima calidad.

[Audio Transmitido.wav](https://github.com/user-attachments/files/23442709/Audio.Transmitido.wav)

## Fase 2:

Esta es la fase crítica del procesamiento de la señal, donde se construye la estructura de la señal que modulará la portadora de RF.

* **Objetivo Específico 2.1:** Cargar el archivo de audio estéreo en el entorno de desarrollo (GNU Radio).
* **Objetivo Específico 2.2:** Implementar los bloques o el código necesario para generar los componentes de la señal MPX:
    * Crear la señal de suma **(L+R)** para compatibilidad monofónica.
    * Generar el **tono piloto de 19 kHz**, que es la referencia de fase para la demodulación estéreo.
    * Crear la señal de diferencia **(L-R)** y modularla en una subportadora de 38 kHz mediante AM de Doble Banda Lateral con Portadora Suprimida (AM-DSB-SC).
* **Objetivo Específico 2.3:** Combinar (sumar) las tres señales anteriores para formar la señal MPX final.
* **Objetivo Específico 2.4:** Analizar el espectro de la señal MPX resultante y verificar la correcta ubicación y amplitud relativa de cada uno de sus componentes.
