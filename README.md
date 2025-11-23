# Misión 5: Creando nuestra propia antena

## Contexto
En esta práctica se abordó el diseño, simulación, construcción y validación de una antena tipo **Biquad**, un diseño resonante conocido por su directividad y ganancia moderada. El objetivo central fue pasar de la teoría electromagnética a la implementación física, contrastando los modelos de simulación (MATLAB) con las mediciones reales en laboratorio (VNA y Analizador de Espectro), operando en la banda de frecuencias UHF.

## Fase 1: Diseño y Simulación (La Física detrás de la Forma)

### Fundamentación Matemática
La antena Biquad se compone de dos elementos cuadrados ("quads") alimentados en el centro, colocados frente a un plano reflector. Las dimensiones críticas dependen de la longitud de onda ($\lambda$) de la frecuencia objetivo ($f_c$).

$$\lambda = \frac{c}{f_c}$$

Para el diseño óptimo, se emplearon las siguientes relaciones teóricas:
* **Longitud del lado del Quad ($L$):** $L \approx \frac{\lambda}{4}$
* **Separación al Reflector ($S$):** $S \approx \frac{\lambda}{8}$

### Modelado en MATLAB
Se utilizó la *Antenna Toolbox* de MATLAB para diseñar la estructura geométrica y predecir su comportamiento. Se configuró un barrido de frecuencia para observar el parámetro $S_{11}$ (Coeficiente de Reflexión) y asegurar la resonancia en la banda deseada.

![Diseño MATLAB](imagenes/mision5%20(5).jpg)
Figura 1: Diseño de la antena Biquad en MATLAB Antenna Designer, mostrando la estructura de alambre sobre el plano reflector y los parámetros geométricos de entrada.

## Fase 2: Construcción del Prototipo

Siguiendo las dimensiones obtenidas en la simulación, se procedió a la manufactura de la antena.

### Procedimiento
1.  **Elemento Radiante:** Se moldeó alambre de cobre rígido cuidando la precisión en los ángulos de 90° para formar los dos cuadros.
2.  **Reflector:** Se utilizó una placa cobreada (PCB) como plano de tierra para direccionar la energía.
3.  **Alimentación:** Se instaló un conector SMA en el centro del reflector, soldando el pin central al punto medio del biquad y la masa al cuerpo del conector, garantizando la rigidez mecánica.

![Prototipo Final](imagenes/mision5%20(6).jpg)
Figura 2: Antena Biquad construida. Se observa el elemento radiante sostenido por el conector SMA sobre el plano reflector.

## Fase 3: Medición y Validación

### Caracterización con VNA (Vector Network Analyzer)
Se conectó la antena al analizador de redes Rohde & Schwarz ZVL para medir el parámetro $S_{11}$ (Pérdidas de Retorno). Este parámetro indica qué tanta energía es radiada vs. qué tanta rebota hacia la fuente.

![Medición VNA](imagenes/mision5%20(2).jpg)
Figura 3: Curva de $S_{11}$ medida en el VNA. Se observa un "valle" o dip característico que indica la resonancia de la antena en la banda de operación (centrado en visualización a 775 MHz).

### Prueba Funcional de Directividad (Analizador de Espectro)
Para verificar la ganancia y directividad, se utilizó un Analizador de Espectro FPC1000 recibiendo una señal piloto en 775 MHz. Se realizaron dos mediciones: una apuntando hacia la fuente (Máxima Ganancia) y otra desviando la antena (o polarización cruzada).

![Espectro Maxima Potencia](imagenes/mision5%20(7).jpg)
Figura 4: Medición de la señal recibida apuntando a la fuente.
**Potencia Recibida:** `-69.04 dBm`

![Espectro Minima Potencia](imagenes/mision5%20(1).jpg)
Figura 5: Medición de la señal al desviar la antena (prueba de directividad/polarización).
**Potencia Recibida:** `-90.32 dBm`

![Zoom Espectro](imagenes/mision5%20(3).jpg)
Figura 6: Detalle del ancho de banda de la señal recibida a 775 MHz.

## Análisis y Discusión

### Análisis de Impedancia ($S_{11}$)
En la Figura 3, el VNA muestra una curva de resonancia clara. Aunque el marcador está posicionado en 775 MHz con un valor de **-6.4 dB**, se observa visualmente que el punto de mínima reflexión (mejor acople) se encuentra ligeramente desplazado hacia una frecuencia superior (~785 MHz).
* **Causa del Desplazamiento:** Este *shift* de frecuencia es común y suele deberse a tolerancias de fabricación (longitud de los lados $L$) y, crucialmente, al **factor de velocidad** del material dieléctrico si el alambre tiene recubrimiento o por la permitividad del aire/soporte no siendo idealmente 1.
* **Nivel de Acople:** Un valor de -6.4 dB indica que, aunque la antena irradia, existe una desadaptación de impedancia que podría mejorarse ajustando la distancia al reflector ($S$), ya que la impedancia de entrada de la Biquad varía drásticamente con este parámetro.

### Análisis de Directividad y Ganancia
La prueba más contundente del funcionamiento de la antena se observa en la comparación de potencia recibida:
* Potencia Máxima (Alineada): **-69.04 dBm**
* Potencia Mínima (Desalineada): **-90.32 dBm**

Se obtuvo una diferencia de **21.28 dB**.
Esto confirma que la antena tiene una alta **Relación Frente-Espalda (Front-to-Back Ratio)** o una fuerte discriminación por polarización. Este comportamiento valida el diseño direccional de la Biquad: el reflector está cumpliendo su función de concentrar la energía en un lóbulo principal estrecho, rechazando señales provenientes de otras direcciones o polarizaciones.

## Conclusiones
1.  **Validación de Diseño:** Se logró construir una antena resonante funcional basada en simulación. La estructura física respondió a los principios teóricos de la antena de onda viajera/resonante Biquad.
2.  **Directividad Confirmada:** La diferencia de >20 dB entre la orientación óptima y la desviada demuestra que la antena no es omnidireccional, sino altamente directiva, lo cual es ideal para enlaces punto a punto o para evitar interferencias.
3.  **Mejoras Futuras:** Para optimizar el $S_{11}$ (llevarlo por debajo de -10 dB en 775 MHz), se recomienda implementar un mecanismo de ajuste fino ("tuning") en la distancia del reflector o recortar milimétricamente los elementos radiantes para centrar la resonancia exactamente en la frecuencia portadora.
