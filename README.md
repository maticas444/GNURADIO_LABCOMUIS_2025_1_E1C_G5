# Misión 2: El Enlace Crítico

## Objetivo General:
Determinar y cuantificar la atenuación (pérdida de señal) introducida por diferentes cables coaxiales a varias frecuencias, para identificar un componente defectuoso mediante la medición precisa de potencia con un generador de señal y un analizador de espectro.

Para la elaboración de este laboratorio se usaron los siguientes cables:
#### Cable 1: CAROL C 1178A RG58A A/U Type 50 Ohm coaxial cable 1c 20 awg awm 1354 80c e18621-f de 136 ft
#### Cable 2: BELDEN 8240 RG-58/Q TYPE 1C20 SHIELDED E108993 AWM 1354 OR (UL) CMX C(UL) NZ de 114 ft

## Fase 1: Establecimiento de la Línea Base (Calibración)l
En esta fase inicial, el objetivo principal fue establecer la línea base de potencia o calibración del sistema1. Este valor de referencia, conocido como Potencia de Entrada ($P_{in}$), es crucial, ya que sirve como el punto de comparación para todas las mediciones de atenuación posteriores.

Se realizó la medición de la potencia de referencia y se obtuvo: -61.05 dBm.

![Potencia de Entrada (Cable Corto)](https://github.com/maticas444/GNURADIO_LABCOMUIS_2025_1_E1C_G5/blob/mision2/Imagenes/Potencia%20de%20Entrada%20(Cable%20Corto).jpg)

Figura 1: Medición potencia de entrada con cable corto en 500 MHz.
## Fase 2: Pruebas de Campo (Medición de Componentes)
Durante esta fase se volvió a medir la potencia de salida, usando los otros 2 cables a la misma frecuencia que en la fase 1 (500 MHz).

![Potencia de Entrada (Cable 1)](https://github.com/maticas444/GNURADIO_LABCOMUIS_2025_1_E1C_G5/blob/mision2/Imagenes/Cable%201%20500MHz.jpg)

Figura 2: Medición de potencia de entrada con Cable 1 en 500 MHz.

![Potencia de Entrada (Cable 2)](https://github.com/maticas444/GNURADIO_LABCOMUIS_2025_1_E1C_G5/blob/mision2/Imagenes/Cable%202%20500MHz.jpg)

Figura 3: Medición de potencia de entrada con Cable 2 en 500 MHz.

### CONCLUSION

## Fase 3: Diagnóstico y Análisis
En esta fase se calculó la atenuación práctica de cada cable mediante la siguiente ecuación:
##### Atenuación (dB) = Potencia de Entrada (P_in) - Potencia de Salida (P_out)

Para la atenuación teórica se hizo uso de la siguiente ecuación:
##### Atenuación (db) = alfa * Largo del Cable / 100
El valor de alfa es el valor de atenuación por cada 100 ft de cada referencia de cable.


## Resultados Completos

### Cable 1: 136 ft


| Frecuencia (MHz) | Pin (dBm) | Pout (dBm) | Atenuación teórica (dB) | Atenuación práctica (dB) |
|------------------:|-----------:|------------:|-------------------------:|--------------------------:|
|       100        |  -61,05   |  -72,81    |           7,344           |          11,76           |
|       200        |  -61,05   |  -75,61    |           11,016           |          14,56           |
|       300        |  -61,05   |  -79,09    |           13,668           |          18,04           |
|       400        |  -61,05   |  -82,44    |           16,336           |          21,39           |
|       500        |  -61,05   |  -83,26    |           18,9856           |          22,21           |
|       600        |  -61,05   |  -84,66    |           21,3928           |          23,61           |
|       700        |  -61,05   |  -87,51    |           23,8           |          26,46           |
|       800        |  -61,05   |  -87,79    |           26,1936           |          26,74           |
|       900        |  -61,05   |  -91,25    |           28,6008           |          30,2            |


### Cable 2: 114 ft

| Frecuencia (MHz) | Pin (dBm) | Pout (dBm) | Atenuación teórica (dB) | Atenuación práctica (dB) |
|-----------------:|----------:|-----------:|-------------------------:|--------------------------:|
| 100 | -61,05 | -64,3 | 3,8 | 3,25 |
| 200 | -61,05 | -65,0 | 5,6 | 3,95 |
| 300 | -61,05 | -64,95 | 7 | 3,9 |
| 400 | -61,05 | -63,78 | 8,4 | 2,73 |
| 500 | -61,05 | -63,52 | 9,5 | 2,47 |
| 600 | -61,05 | -64,26 | 10,6 | 3,21 |
| 700 | -61,05 | -63,5 | 11,7 | 2,45 |
| 800 | -61,05 | -64,52 | 12,7 | 3,47 |
| 900 | -61,05 | -64,58 | 13,7 | 3,53 |


### Análisis y Discusión:
Identificación de anomalias: Basado en la tabla de resultados, identifique claramente cuál es el cable "que mayor atenuación presenta" y justifique por qué su atenuación es significativamente mayor.

El Cable 1 (CAROL C 1178A) el de 136 ft es el que presenta una atenuación significativamente mayor, esto se debe a que la atenuación total (en dB) es el producto de la constante de atenuación del material ($\alpha_{dB}$) multiplicada por la longitud total ($l$).Atenuación Total (dB) = $\alpha_{dB}$ [dB/m] $\cdot$ $l$ [m], por lo que la atenuación total (medida en dB) es directamente proporcional a la longitud (distancia) del cable.

### Análisis Causa-Raíz: ¿Qué posibles fallas físicas en un cable o conector podrían causar una atenuación tan alta?

Existen diversas razones por las cuales pueden presentarse atenuaciones altas en cables o conectores, las más comúnes son las filtraciones de agua, daños físicos (como pisotones, dobleces bruscos), también afecta la atenuación cualquier afectación a los conoectores como corrosión u oxidación. 

(Si se realizó el reto avanzado): Analiza cómo cambió la atenuación de los cables al aumentar la frecuencia. ¿Es un comportamiento esperado? ¿Por qué?

Al aumentar la frecuencia, observamos que la atenuación de los cables también aumentaba, lo cuál es un comprotamiento totalmente esperado, esto es debido a 2 fenómenos físicos, al efecto piel y a las pérdidas dieléctricas.

### Resume tus hallazgos y la importancia de medir la pérdida en las líneas de transmisión para garantizar la integridad de un enlace de comunicaciones
## Conclusiones y Discusión

Tras realizar la caracterización espectral de los componentes utilizando el generador de señales y el analizador de espectro, se destacan los siguientes puntos clave derivados de las mediciones:

* **Comportamiento del Cable 1 (CAROL C 1178A - 136 ft):** Este medio de transmisión demostró ser el elemento limitante del sistema. [cite_start]Se observó una correlación directa y proporcional entre el aumento de la frecuencia y el incremento de la atenuación, pasando de **11.76 dB a 100 MHz** hasta alcanzar **30.2 dB a 900 MHz**[cite: 167]. Este comportamiento valida el modelo teórico donde las pérdidas aumentan con la frecuencia, pero identifica a este cable como el componente defectuoso debido a su magnitud de pérdida.
* **Comportamiento del Cable 2 (BELDEN 8240 - 114 ft):** A diferencia del primero, este cable presentó un comportamiento de "baja pérdida" con una respuesta más plana y atenuaciones significativamente menores a las teóricas calculadas. [cite_start]En todo el rango medido (100-900 MHz), la atenuación se mantuvo estable, oscilando mayoritariamente entre **2.4 dB y 3.9 dB**[cite: 169].
* [cite_start]**Identificación de Anomalías:** Al comparar ambas líneas de transmisión a una frecuencia central de 500 MHz, el Cable 1 presenta una atenuación de **22.21 dB** frente a los **2.47 dB** del Cable 2[cite: 167, 169]. Esto confirma que el Cable 1 introduce una pérdida de potencia drástica, convirtiéndose en el "enlace crítico" que comprometería la eficiencia energética del diseño.

### Importancia de la Medición en la Integridad del Enlace
[cite_start]La medición precisa de las pérdidas en las líneas de transmisión ($P_{in} - P_{out}$) [cite: 162] es un pilar fundamental para garantizar la operatividad de cualquier sistema de telecomunicaciones por las siguientes razones:

1.  **Presupuesto de Enlace (Link Budget):** Conocer la atenuación exacta permite calcular si la señal que llega al receptor tendrá suficiente potencia para superar la sensibilidad del equipo. [cite_start]En este laboratorio, ignorar los **~30 dB** de pérdida del Cable 1 a altas frecuencias resultaría en una caída total del enlace, ya que la potencia recibida caería drásticamente (ej. -91.25 dBm a 900 MHz)[cite: 167].
2.  **Relación Señal a Ruido (SNR):** La atenuación afecta directamente la SNR. Si la señal se atenúa excesivamente antes de llegar al receptor, se acerca al piso de ruido térmico, lo que en sistemas digitales incrementa la tasa de bits errados (BER) y degrada la integridad de los datos.
3.  [cite_start]**Validación de Modelos Teóricos:** Los resultados del Cable 2 demostraron que los cálculos teóricos no siempre reflejan con exactitud la realidad del componente físico (la práctica arrojó valores menores a la teoría en este caso)[cite: 169]. Esto subraya la necesidad obligatoria de realizar mediciones de campo para certificar la infraestructura antes del despliegue.
