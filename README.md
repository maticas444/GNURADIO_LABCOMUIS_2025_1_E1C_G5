# GNURADIO_LABCOMUIS_2025_1_E1C_G5

## Misión 2: El Enlace Crítico

## Objetivo General:
Determinar y cuantificar la atenuación (pérdida de señal) introducida por diferentes cables coaxiales a varias frecuencias, para identificar un componente defectuoso mediante la medición precisa de potencia con un generador de señal y un analizador de espectro.

Para la elaboración de este laboratorio se usaron los siguientes cables:
Cable 1: CAROL C 1178A RG58A A/U Type 50 Ohm coaxial cable 1c 20 awg awm 1354 80c e18621-f de 136 ft
Cable 2: BELDEN 8240 RG-58/Q TYPE 1C20 SHIELDED E108993 AWM 1354 OR (UL) CMX C(UL) NZ de 114 ft

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

CONCLUSION

##Fase 3: Diagnóstico y Análisis
En esta fase se calculó la atenuación práctica de cada cable mediante la siguiente ecuación:
Atenuación (dB) = Potencia de Entrada (P_in) - Potencia de Salida (P_out)

Para la atenuación teórica se hizo uso de la siguiente ecuación:
Atenuación (db) = alfa * Largo del Cable / 100
El valor de alfa es el valor de atenuación por cada 100 ft de cada referencia de cable.


##Resultados Completos

Cable 2 Medio Largo

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

Cable 1 Largo


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
