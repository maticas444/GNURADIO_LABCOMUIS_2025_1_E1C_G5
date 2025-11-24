# Misión 3: Modulación en Amplitud (AM) con SDR

## Contexto
En esta misión se realizó la transición de la recepción a la **transmisión (TX)**. El objetivo principal fue configurar el Radio Definido por Software (SDR) como un transmisor de Amplitud Modulada (AM). Se diseñó un flujo de procesamiento en GNU Radio para generar una señal portadora y modularla con diferentes fuentes de información (señales periódicas y audio), validando el resultado físico y espectral mediante instrumentación de laboratorio.

## Fase 1: Diseño y Configuración del Modulador

### Arquitectura del Transmisor
Se diseñó un diagrama de flujo (*flowgraph*) en GNU Radio que implementa la ecuación matemática de la AM de doble banda lateral con portadora:

$$s(t) = A_c [1 + k_a \cdot m(t)] \cos(2\pi f_c t)$$

El sistema permite controlar en tiempo real la señal mensaje $m(t)$ (Seno, Cuadrada, Sierra), el índice de modulación ($k_a$) y la frecuencia portadora ($f_c$).

![Diagrama de Bloques](imagenes/mision3.png)
Figura 1: Diagrama de flujo completo en GNU Radio.

### Código Fuente
El flujo diseñado en GNU Radio fue compilado a Python para su ejecución y control.
Puede consultar el código fuente completo en el siguiente enlace:
👉 **[INSERTE LINK DEL GIST AQUÍ]**

---

## Fase 2: Generación y Análisis de Señales

A continuación se presenta el análisis detallado para cada tipo de señal moduladora, contrastando la configuración de software con la medición física en el osciloscopio.

### 1. Modulación Senoidal (Tono Puro)

Se configuró el sistema para transmitir un tono puro. Esta es la prueba base para verificar la limpieza espectral y la correcta configuración del índice de modulación.

#### Configuración y Espectro
![Configuracion Mensaje Seno](imagenes/mensaje_gnu_seno.jpg)
Figura 2: Visualización en tiempo real del mensaje senoidal en GNU Radio.

![Espectro Seno](imagenes/gnu_seno.jpg)
Figura 3: Espectro de la señal modulada. Se observa la portadora central y dos bandas laterales únicas, lo que confirma una modulación limpia sin armónicos indeseados.

#### Medición Física (Osciloscopio)
Primero validamos la portadora pura sin modulación y luego aplicamos el mensaje.

![Portadora Seno Amplitud](imagenes/amplitud_portadora_seno.jpg)
![Portadora Seno Frecuencia](imagenes/frecuencia_portadora_seno.jpg)
Figura 4 y 5: **Señal Portadora sin Modular ($k_a = 0$).** Vistas de amplitud y detalle de frecuencia. Se confirma una onda continua constante.

![Modulada Seno](imagenes/amplitud_modulada_seno.jpg)
Figura 6: **Señal Modulada (AM).** Envolvente suave y sinusoidal.

**Análisis de Sobremodulación:**
Al forzar un índice $k_a > 1$, se evidencia la distorsión de fase.
![Sobremodulacion](imagenes/frecuencia_modulada_seno_coeficiente1,09.jpg)
Figura 7: Sobremodulación (Coeficiente 1.09). Nótese el cruce por cero en la envolvente, lo que genera inversión de fase.

---

### 2. Modulación con Onda Cuadrada

Esta prueba simula una transmisión de pulsos digitales. La onda cuadrada representa un reto para el transmisor debido a sus transiciones abruptas.

#### Configuración y Espectro
![Configuracion Mensaje Cuadrada](imagenes/mensaje_gnu.jpg)
Figura 8: Configuración del entorno para señal cuadrada.

![Espectro Cuadrada](imagenes/gnu_cuadrada.jpg)
Figura 9: Espectro AM con onda cuadrada. A diferencia del seno, aparecen múltiples bandas laterales ($f_c \pm n \cdot f_m$) que se extienden a lo largo del ancho de banda, validando la presencia de armónicos impares infinitos.

#### Medición Física
Se analizó la portadora base y el efecto de la modulación con diferentes coeficientes.

**Portadora Base (Referencia):**
![Portadora Cuadrada Ref](imagenes/portadora_cuadrada_coeficiente0_amplitud.jpg)
![Portadora Cuadrada Ref Zoom](imagenes/portadora_cuadrada_coeficiente0_frecuencia.jpg)
Figura 10 y 11: Portadora pura antes de aplicar la onda cuadrada.

**Señal Modulada:**
![Modulada Cuadrada Amplitud](imagenes/amplitud_modulada_cuadrada.jpg)
![Modulada Cuadrada Frecuencia](imagenes/frecuencia_modulada_cuadrada.jpg)
Figura 12 y 13: Envolvente de la señal AM Cuadrada. La potencia conmuta entre dos niveles. Los flancos de subida y bajada muestran la respuesta del sistema.

**Detalle de la Portadora bajo Modulación ($k_a = 0.51$):**
![Portadora Modulada Zoom 1](imagenes/portadora_cuadrada_coeficiente0,51_amplitud.jpg)
![Portadora Modulada Zoom 2](imagenes/portadora_cuadrada_coeficiente0,51_frecuencia.jpg)
Figura 14 y 15: Zoom a la señal portadora mientras es modulada. Se aprecia cómo la onda de alta frecuencia "dibuja" la forma de la onda cuadrada.

---

### 3. Modulación Diente de Sierra (Rampa)

Se utilizó esta señal para verificar la **linealidad** del sistema. Si el amplificador fuera no-lineal, la rampa se vería curvada.

#### Espectro
![Espectro Sierra](imagenes/gnu_sierra.jpg)
Figura 16: Espectro de la señal modulada con diente de sierra. Los armónicos decaen suavemente en amplitud.

#### Medición Física
**Portadora Base:**
![Portadora Sierra Ref](imagenes/portadora_sierra_amplitud.jpg)
![Portadora Sierra Ref Zoom](imagenes/portadora_sierra_frecuencia.jpg)
Figura 17 y 18: Referencia de la portadora.

**Señal Modulada:**
![Modulada Sierra Amplitud](imagenes/modulada_sierra_amplitud.jpg)
![Modulada Sierra Frecuencia](imagenes/modulada_sierra_frecuencia.jpg)
Figura 19 y 20: Envolvente de la señal AM Sierra. El crecimiento lineal y la caída abrupta demuestran que el SDR opera en su zona lineal, reproduciendo fielmente la rampa sin distorsión por saturación.

---

## Fase 3: Análisis Comparativo y Conclusiones

### Tabla de Comportamiento

| Tipo de Señal | Dominio del Tiempo (Osciloscopio) | Dominio de la Frecuencia (Espectro) | Impacto en el Sistema |
| :--- | :--- | :--- | :--- |
| **Senoidal** | Envolvente suave. | Ancho de banda mínimo (Portadora + 2 laterales). | Máxima eficiencia espectral. Ideal para calibración. |
| **Cuadrada** | Cambios bruscos de nivel. | **Ancho de banda extenso.** Múltiples armónicos significativos. | Requiere mayor ancho de banda de canal. Si se filtra, los bordes se redondean (Fenómeno de Gibbs). |
| **Sierra** | Crecimiento lineal. | Armónicos decrecientes ($1/n$). | Prueba crítica de linealidad para amplificadores de potencia (PA). |

### Conclusiones
1.  **Validación de Teoría:** Las capturas del osciloscopio validan la teoría de AM: la información (mensaje) viaja contenida en las variaciones de amplitud de la portadora de alta frecuencia.
2.  **Ancho de Banda vs. Forma de Onda:** Al comparar las Figuras 3 (Seno) y 9 (Cuadrada), se demuestra experimentalmente que transmitir señales con transiciones rápidas (digitales/cuadradas) "contamina" el espectro con armónicos, exigiendo filtros más estrictos o mayor separación entre canales.
3.  **Linealidad del SDR:** La prueba de diente de sierra (Figura 19) confirmó que el hardware mantiene una respuesta lineal, lo cual es crucial para evitar distorsión armónica en transmisiones de audio real.
4.  **Control de Modulación:** Se evidenció (Figura 7) la importancia de mantener $k_a \le 1$. La sobremodulación destruye la información de la envolvente en los cruces por cero, haciendo imposible una demodulación coherente en un receptor estándar.
