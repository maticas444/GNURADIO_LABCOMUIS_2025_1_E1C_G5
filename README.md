# Misión 1: Reconocimiento de Equipos y Espectro

## Contexto
En esta primera misión, el objetivo fundamental fue familiarizarse con la instrumentación básica de un laboratorio de telecomunicaciones, comprendiendo las fortalezas y limitaciones de cada herramienta al analizar el espectro radioeléctrico.
La práctica se dividió en tres fases estratégicas: exploración masiva usando Radio Definido por Software (SDR), medición de precisión mediante Analizador de Espectro y visualización temporal con Osciloscopio.

## Fase 1: Exploración y Descubrimiento (El Ojo Panorámico del SDR)

### Mapeo del Terreno
Utilizando un dispositivo SDR y un software de visualización, se realizó un barrido espectral amplio entre 50 MHz y 2200 MHz para identificar la actividad radioeléctrica en el entorno del laboratorio. El SDR actuó como una herramienta de "visión amplia", permitiendo observar múltiples bandas simultáneamente mediante el diagrama de cascada.

### Identificación de Objetivos
Durante el barrido se identificaron claramente tres bandas de servicios principales:

1. **Radiodifusión FM Comercial:** Se observaron múltiples portadoras de alta potencia entre 88 y 108 MHz.
2. **Banda UHF:** Se exploró el rango cercano a los 470 MHz, observando un piso de ruido distinto y señales esporádicas.
3. **Telefonía Móvil:** Se detectó actividad significativa en la banda de 1900 MHz.

![Espectro FM](https://github.com/maticas444/GNURADIO_LABCOMUIS_2025_1_E1C_G5/blob/mision1/imagenes/Captura%20desde%202025-08-13%2017-34-51.png)
Figura 1: Visualización del espectro en la banda comercial FM (88-108 MHz). Se aprecian las portadoras de alta potencia.

![Espectro UHF](https://github.com/maticas444/GNURADIO_LABCOMUIS_2025_1_E1C_G5/blob/mision1/imagenes/Captura%20desde%202025-08-15%2017-52-25.png)
Figura 2: Exploración en la banda UHF centrada en 476 MHz.

![Espectro Movil](https://github.com/maticas444/GNURADIO_LABCOMUIS_2025_1_E1C_G5/blob/mision1/imagenes/Captura%20desde%202025-08-15%2017-55-22.png)
Figura 3: Detección de señales de comunicaciones móviles cerca de 1.9 GHz (1908 MHz).


## Fase 2: Análisis de Precisión (La Lupa del Analizador)

Para esta fase, se seleccionó una de las señales identificadas para realizar una caracterización precisa utilizando el Analizador de Espectro.

### Configuración Fina
Se ajustó el **SPAN** para visualizar únicamente el canal de interés ("Zoom espectral") y se redujo el **RBW (Resolution Bandwidth)** para disminuir el piso de ruido y distinguir la forma exacta de la portadora.

#### Datos Recolectados (Ejemplo basado en señal de 1908 MHz)
* **Frecuencia Central:** 1908.2 MHz
* **Ancho de Banda:** Se utilizaron los marcadores para medir el ancho de banda ocupado.
* **Resolución (RBW):** Se seleccionó un RBW bajo para separar las componentes espectrales del ruido de fondo.

## Fase 3: Visualización de la Onda (Dominio del Tiempo)

### Captura de la Forma de Onda
Esta fase representó el mayor desafío técnico. Se conectó la antena directamente al osciloscopio para intentar capturar la señal en el dominio del tiempo.

#### Desafíos y Ajustes
Se ajustó la escala vertical (Volts/div) y la base de tiempo (s/div) al mínimo posible. Sin embargo, debido a la naturaleza modulada de las señales de RF y las limitaciones de ancho de banda del osciloscopio, la visualización de la portadora pura es compleja y requiere un ajuste preciso del **Trigger** para estabilizar la onda.

## Resultados y Hallazgos

### Comparativa de Equipos
Al comparar los tres instrumentos, se evidenció lo siguiente:

* **SDR (El Explorador):** Fue la herramienta más eficiente para encontrar señales rápidamente gracias a su visualización en cascada (Waterfall). Ideal para búsqueda inicial.
* **Analizador de Espectro (El Agrimensor):** Ofreció la medida de frecuencia más confiable y precisa. Permite medir potencia (dBm) y ancho de banda con exactitud que el SDR no alcanza debido a la falta de calibración rigurosa.
* **Osciloscopio (El Cronista):** Resultó ser el menos eficaz para esta tarea específica de RF. Aunque permite ver el voltaje pico a pico (Vpp), carece de la sensibilidad y las herramientas de frecuencia necesarias para analizar espectro radioeléctrico complejo.

### La Conexión Tiempo-Frecuencia
Lo observado confirma la relación teórica: el "pico" estacionario observado en el Analizador de Espectro a una frecuencia $f_c$ corresponde a la componente sinusoidal principal que se intenta visualizar en el osciloscopio. Mientras el osciloscopio muestra la suma de todas las señales en el tiempo, el analizador las descompone en sus frecuencias individuales.

### Conclusión General
La práctica demostró el rol estratégico de cada equipo: el SDR para explorar, el Analizador para medir y el Osciloscopio para caracterizar temporalmente. Para tareas de ingeniería de RF precisas, el Analizador de Espectro es el instrumento insustituible.
