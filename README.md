# Misión 6

## Fase 1:

* **Objetivo Específico 1.1:** Diseñar un guion para un bloque de programación de 60 a 90 segundos que incluya una introducción (jingle), un segmento de voz y una pieza musical.

El guión fue generado con inteligencia artificial obteniendo el siguiente segmento de voz:
"Sintoniza la voz de los estudiantes, somos UIS y estamos en el aire. UIS Radio, la voz que conecta tu futuro.

Bienvenidos de nuevo a tu emisora estudiantil de la UIS. En esta edición te contamos lo más relevante de esta semana en la universidad. La Universidad Industrial de Santander ha lanzado una nueva convocatoria de becas para estudiantes de pregrado y posgrado con el objetivo de fomentar la investigación y la innovación. La convocatoria incluye becas completas para estudiantes que deseen realizar proyectos de impacto social y científico. Las inscripciones estarán abiertas hasta el 31 de octubre y podrás encontrar toda la información detallada en el sitio web oficial de la universidad. Recuerda que si quieres más detalles sobre esta y otras noticias, puedes seguirnos en nuestras redes sociales. ¡No te lo pierdas!
Y ahora, para seguir acompañándote con lo mejor de la música, aquí tienes una canción que no te puedes perder. Sigue disfrutando de la programación en UIS Radio."
La melodía elegida fue un segmento de la canción "Corazón Partio" de Alejandro Sanz.


* **Objetivo Específico 1.2:** Grabar y/o seleccionar los elementos de audio definidos en el guion.

Se usó el uso de la IA "Elevenlabs" para pasar el guión escrito a un audio narrado por un locutor. De igual manera se descargó el segmento musical mediante la página "https://www-y2mate.com/es36/" usando el link de Youtube de la canción.

* **Objetivo Específico 1.3:** Utilizar un software de edición de audio (ej. Audacity) para ensamblar, mezclar y masterizar los elementos en un único archivo de audio. El producto final debe ser un archivo estéreo (dos canales: Izquierdo y Derecho) en formato `.wav` para preservar la máxima calidad.

<img width="1891" height="621" alt="image" src="https://github.com/user-attachments/assets/55946a2f-dbd5-49db-a959-39d42731c309" />

Se hizo la mezcla de los audios en Audacity, se configuró para que el jingle inicial suene solo por el canal izquierdo, el speech por el canal derecho, y la canción por ambos canales, resultando en un archivo wav estéreo mezclado.

[AudioMezclado.wav](https://github.com/user-attachments/files/23464810/Audio.Transmitido.wav)
Este fue el audio final obtenido que se va a transmitir en las siguientes fases.

## Fase 2:

Esta es la fase crítica del procesamiento de la señal, donde se construye la estructura de la señal que modulará la portadora de RF.

* **Objetivo Específico 2.1:** Cargar el archivo de audio estéreo en el entorno de desarrollo (GNU Radio).

<img width="401" height="281" alt="image" src="https://github.com/user-attachments/assets/70014530-41e1-4b9a-8261-03018f11ed97" />

* **Objetivo Específico 2.2:** Implementar los bloques o el código necesario para generar los componentes de la señal MPX:
    * Crear la señal de suma **(L+R)** para compatibilidad monofónica.
    * Generar el **tono piloto de 19 kHz**, que es la referencia de fase para la demodulación estéreo.
    * Crear la señal de diferencia **(L-R)** y modularla en una subportadora de 38 kHz mediante AM de Doble Banda Lateral con Portadora Suprimida (AM-DSB-SC).

<img width="1114" height="862" alt="image" src="https://github.com/user-attachments/assets/cafe3502-ced7-423b-b0aa-e7123d805157" />
 
* **Objetivo Específico 2.3:** Combinar (sumar) las tres señales anteriores para formar la señal MPX final.

<img width="596" height="264" alt="image" src="https://github.com/user-attachments/assets/d4ac2ca9-3923-4a80-af2b-8c81daaeba34" />


* **Objetivo Específico 2.4:** Analizar el espectro de la señal MPX resultante y verificar la correcta ubicación y amplitud relativa de cada uno de sus componentes.

<img width="1919" height="1017" alt="image" src="https://github.com/user-attachments/assets/43048d13-6151-4367-8a45-b48e78eea5eb" />

<img width="1919" height="1016" alt="image" src="https://github.com/user-attachments/assets/354f6fb3-b30b-4a47-a2dc-a0d7496426a0" />

<img width="1919" height="1018" alt="image" src="https://github.com/user-attachments/assets/3d612995-fbfc-439a-a127-d7944a5f9d58" />

## Fase 3:

En esta fase final, la señal procesada se lleva al dominio de radiofrecuencia para su emisión y se comprueba su correcta recepción.

* **Objetivo Específico 3.1:** Configurar el bloque de modulación FM, utilizando la señal MPX generada como entrada. Se debe ajustar la desviación de frecuencia para cumplir con el estándar de radiodifusión (típicamente ±75 kHz).
* **Objetivo Específico 3.2:** Configurar los parámetros del USRP (frecuencia central de transmisión, ganancia, tasa de muestreo) para emitir la señal en una frecuencia libre dentro de la banda FM comercial (88-108 MHz).
* **Objetivo Específico 3.3:** Iniciar la transmisión y utilizar un receptor de radio FM comercial para sintonizar la señal.
* **Objetivo Específico 3.4:** Validar cualitativamente la calidad del audio recibido y confirmar que el indicador "Stereo" del receptor se activa, lo que prueba la correcta generación y detección del piloto de 19 kHz.

