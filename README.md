# Misión 4

## Fase 1:  Inteligencia y Preparación (Investigación Regulatoria)
1. Obtención de Datos Oficiales: Navegue en al sitio web oficial de la ANE o del MinTIC de Colombia.

2. Búsqueda del Registro: Busque el documento oficial que contiene los parámetros de las estaciones de radiodifusión sonora en FM. Generalmente se llama "Cuadro Nacional de Atribución de Bandas de Frecuencias (CNABF)" o puedes encontrar los datos en el "Sistema de Gestión de Espectro (SGE)".

3. Creación de la Lista Oficial: Filtra la información para la ciudad de Bucaramanga y su área metropolitana. Cree una tabla con todas las emisoras FM legalmente registradas.

[EmisorasFMLegalmenteRegistradas.pdf](https://github.com/user-attachments/files/23434039/EmisorasFMLegalmenteRegistradas.pdf)

Tabla 1. Emisoras FM legalmente registrada de Bucaramanga y el área metropolitana

## Fase 2: Monitoreo de Campo (Escaneo del Espectro)
1. Configuración del Equipo: Conecta tu antena al SDR.

2. Barrido del Espectro: Realice un barrido completo de la banda de FM, desde 88.0 MHz hasta 108.0 MHz.

3. Registro de Señales Detectadas: Por cada señal que detectes claramente, crea una nueva lista. Para cada una, debes:

#### Anotar la frecuencia exacta en la que la encuentras.

#### Estimar su potencia relativa o calidad de la señal.

Identificar la emisora: Escuche la transmisión para capturar su nombre comercial o cualquier pista que te permita identificarla.

| Frecuencia | Emisora | Potencia relativa (dB) |
|---|---|---|
| 90.7 | W RADIO | -33,45 |
| 91.7 | POLICIA NACIONAL DE BUCARAMANGA | -32,7 |
| 92.3 | RADIONICA | -56,44 |
| 92.9 | COLOMBIA ESTEREO | -42,84 |
| 93.4 | EMISORA COMUNITARIA LA BRUJULA | -50,19 |
| 94.7 | NO IDENTIFICADA | -55,87 |
| 95.7 | TROPICANA | -37,21 |
| 96.2 | SANTO TOMAS ESTEREO | -61,37 |
| 96.9 | UIS FM | -33,55 |
| 97.7 | OLIMPICA ESTEREO | -60,63 |
| 98.5 | La Exitosa | -54,41 |
| 99.2 | CARACOL | -47,94 |
| 99.7 | LA FM | -44,72 |
| 100.7 | EMISORA CULTURAL LUIS CARLOS GALAN SARMIENTO | -45,84 |
| 101.7 | UTS - TU RADIO ESTEREO | -62,94 |
| 102.5 | LA MEGA ESTEREO | -65,88 |
| 103.7 | RUMBA ESTEREO | -41,84 |
| 104.7 | BESAME | -58,6 |
| 105.1 | LA GUAPACHOSA | -65,71 |
| 106.7 | RADIO UNO | -49,99 |

Tabla 2. Emisoras FM registradas y medidas en la práctica

## Fase 3: Análisis y Cruce de Datos

1. Creación de la Tabla Maestra: Combine las dos listas (la oficial de la Fase 1 y la de campo de la Fase 2) en una única tabla comparativa.

2. Clasificación de Hallazgos: Para cada emisora que encontraste en tu barrido, clasifíquela:

##### Coincidencia Legal: La frecuencia y el nombre coinciden con un registro oficial.

##### Posible Desviación: La frecuencia está ligeramente desviada del registro oficial, pero el nombre coincide.

##### Transmisión No Identificada: usted ha Encontrado una señal en una frecuencia que NO está en la lista oficial, o no pudiste identificar el nombre de una emisora en una frecuencia registrada.

| Frecuencia | Emisora | Potencia relativa (dB) | Registro | Desviación |
| :--- | :--- | :--- | :--- | :--- |
| 90.7 | W RADIO | -33,45 | SI | NO |
| 91.7 | POLICIA NACIONAL DE BUCARAMANGA | -32,7 | SI | NO |
| 92.3 | RADIONICA | -56,44 | SI | NO |
| 92.9 | COLOMBIA ESTEREO | -42,84 | SI | NO |
| 93.4 | EMISORA COMUNITARIA LA BRUJULA | -50,19 | SI | NO |
| 94.7 | NO IDENTIFICADA | -55,87 | NO | NO |
| 95.7 | TROPICANA | -37,21 | SI | NO |
| 96.2 | SANTO TOMAS ESTEREO | -61,37 | SI | NO |
| 96.9 | UIS FM | -33,55 | NO | NO |
| 97.7 | OLIMPICA ESTEREO | -60,63 | SI | NO |
| 98.5 | La Exitosa | -54,41 | NO | NO |
| 99.2 | CARACOL | -47,94 | SI | NO |
| 99.7 | LA FM | -44,72 | SI | NO |
| 100.7 | EMISORA CULTURAL LUIS CARLOS GALAN SARMIENTO | -45,84 | SI | NO |
| 101.7 | UTS - TU RADIO ESTEREO | -62,94 | SI | NO |
| 102.5 | LA MEGA ESTEREO | -65,88 | SI | NO |
| 103.7 | RUMBA ESTEREO | -41,84 | SI | NO |
| 104.7 | BESAME | -58,6 | SI | NO |
| 105.1 | LA GUAPACHOSA | -65,71 | SI | NO |
| 106.7 | RADIO UNO | -49,99 | SI | NO |

Tabla 3. Emisoras FM clasificadas, registradas y medidas en la práctica

## Entregables y Análisis del Reporte:
Prepara un reporte de misión como si fueras a entregarlo a tu superior en la ANE.

### Resultados y Hallazgos:
Presenta una Tabla Maestra comparando los datos oficiales con los datos de campo. Esta es la evidencia principal de tu trabajo
Incluya una captura de pantalla panorámica del espectro FM de Bucaramanga, señalando algunas de las emisoras que identificaste.
#### Análisis y Discusión:

##### Lista de Anomalías: Presenta una lista clara y concisa de todas las "Transmisiones No Identificadas" o con desviaciones. Estas son tus principales pistas para una investigación más profunda.

Solo se encontró transmisión no identificada ubicada en la frecuencia 94.7 MHz.

##### Análisis de Discrepancias: ¿Por qué podría existir una emisora en el aire que no está en los registros? Propón al menos dos hipótesis (ej. transmisión sin licencia, una licencia de un municipio cercano cuya señal llega a la ciudad, etc.).

Mientras nos encontrabamos verificando las emisoras que no se encontraban en los registros, encontramos que la emisora "La Inolvidable o La Exitosa" 98.5 MHz continuaba funcionando a pesar que había sido sancionada en septiembre del año pasado, y habían sido ecomisados sus equipos, todo esto debido a presunto uso no autorizado del espector radioeléctrico, como también que esta frecuencia no está proyectada ni asignada para el referido municipio. Por lo que postulamos esta misma causa como la principal por la que una emisora que esté al aire no se encuentra en los registros.

Por otro lado, encontramos que la emisora no identificada en 94.7 MHz podría tratarse de Olimpica Estereo Cúcuta, ya que a esta misma frecuencia se transmite en ese sector, por lo que asumimos como segunda hipótesis que otra razón por la cual una emisora no se encuentre en los registros y esté funcionando es debido a que la emisora sí cuenta con una licencia de operación válida, pero esta fue asignada para un municipio o área de servicio diferente. Sin embargo, debido a la potencia de su transmisor, la ubicación de su antena o condiciones favorables de propagación, su señal alcanza a cubrir esta localidad. Esto explicaría su presencia en nuestras mediciones, a pesar de no estar en los registros oficiales de Bucaramanga.

##### Retos de la Misión: Describe las dificultades que enfrentaste. ¿Fue difícil identificar todas las emisoras? ¿Había señales muy débiles o mucho ruido?

Si, mientras algunas señales presentaban potencias altas y totalmente audibles, nos encontramos con algunas que eran bastante débiles, como por ejemplo lo son "La Mega Estereo" y "La Guapachosa" que presentaron potencias de -65,88 y -67,71 dB respectivamente, las cuales fue difícil encontrar al estar con bastante ruido. Lo cual es un comportamiento esperado, ya que las señales débiles con altas pérdidas por atenuación y obstáculos pueden ser difíciles de sintonizar.


