# 09-08

## Comunicaciones por luz visible para industrias inteligente

## Aspectos Formales del curso

- 2 proyectos cuyo promedio es equivalente al 40%.
- 2 solemnes equivalentes a un 30% cada uno.
- Promedio sobre 5 eximido

Muchas veces cambiar 1 solemne por 1 proyecto.

2 solemnes:
	1 proyecto
	2 proyecto reemplaza segunda solemne


proyecto 1 40%
proyecto 2 30%
solemne 1 30%

1ra solemne: teórica
Bases de comunicación de luz visible

2 Proyectos:
	 1 Proyecto de Simulación, en app de matlab.

2do proyecto tiene 3 formas:
	ensayo 2 integrantes
	software: crea un escenario en matlab de escenario y se debe modificar a uno mas industrial, añadir distribucion de particulas o reflexiones, algo que lo haga diferente o no idel. 2 integrantes
	hardware: construir sistema y transmitir usando arduinos o raspberrys 3 integrantes


---

Tx Canal Rx

Tx
Primero se verá como se transmite, el como se procesa o trabaja es lo mismo en radiofrecuencia o luz visible, cambia en la final, proceso de cambio de eléctrico a óptico.

Canal
Modelo de Friis
Modelo Hata
en vacio va perdiendo potencia, estos modelos dan una expresión matemática 

Aquí se utiliza el modelo LoS y mom-LoS(Reflexiones)

Rx
No se usa una antena si no que un photodetector o photoresistor

photodetector es mejor.

---

Revisión literaria de papers
Manejo de MATLAB
Análisis de la tecnología VLC



# 13-08

## Introducción

Distintos tipos de tecnología con luz.

### Motivación:

Por que estamos en continua mejora, innovación, nuevas tecnologías, etc... Por que innovar?
- Limitaciones, toda tecnología incluso vlc tiene limitaciones, ninguna es perfecta, tienen ventajas y desventajas.
	- Las desventajas de una sirven para aprovecharla en otra forma.
- Interferencias, ruido y saturación
- Masificación de equipos. El crecimiento ha sido exponencial, existen millones de equipos por usuarios. → Genera Saturación. (IOT)

Alexander Graham Bell → Fotófono → Cambio en colores al hablar, representaban un sonido. primer teléfono inalámbrico basado en cambios de intensidad de luz.

Harald Hass → LiFi → Light Fidelity 

---

Tecnologia VLC

El principio basico es modular la intensidad de la luz.

Hay muchos parientes de VLC (OWC optical wireless comunication), en redes opticas se transmitia laser o leds en fibra. ese es un medio alambrico, lo que veremos aca es inalambrica.

Como se clasifican: Que usamos como transmisor y receptor
- Led → Fotodetector (quizas panel solar) y ambiente indoor: VLC
- Laser → Fotodetector: FSO[FREE SPACE OPTICAL]
- LED ARRAY → Fotodetector Array o Camera: OCC [OPTICAL CAMERA COMUNICATION]


---
## OWC

### OUTDOOR

Free space optics

V2V/V2l = Vehicle 2 Vehicle Usar comunicación usando los faros para comunicarme con vehículos delante y detrás.

VLC outdoor LiFi

OOC VLC-IoT

VLC-IOT usando camaras ya instaladas en las ciudades que utilizan las luminarias

UWOC: Under Water Optical Communication → La radiofrecuencia bajo el agua es muy dificil

### Indoor

IR WSN: Wireless Sensors Network

VLP OOC VLC-IoT

VLC Indoor LiFi


---

VLC orden de Tera Hz [THz]
VLC trabaja en el rango de la luz visible [380 hasta 730]nm(nanometros)
La frecuencia [411 THz - 789 THzs]

f=c/long de onda


---

## Componentes del Sistema VLC

### MODULADOR
Dispositivo que se coloca al lado de la bombilla LED. Varia la onda de la señal, haciendo que esta viaje en forma de código binario hasta el fotorreceptor
### FOTORECEPTOR
El que transforma luz en electricidad

---

### Velocidades transmisión

En distancias cortas indoor max 1.5 m velocidades de Gbps 
Más distancia menos tasas.

### Interferencia EM
nunca interferirá entre señal de radiofrecuencia (wifi o otra) y la comunicación por luz visible, pueden trabajar a la par.

Las bandas y frecuencias de radiofrecuencia esta regulada a diferencia de vlc

### Seguridad y costo

Con wifi es relativamente fácil interceptar la radiofrecuencia.

Con la luz no traspasa paredes, no puede venir alguien afuera xd
da mas seguridad sin agregar nada.

En costo, es mas costoso crear algo desde 0, mano de obra, pruebas, equipos. La idea de VLC es añadir pequeños circuitos a la luminaria ya existente.

---
## Aplicaciones en entornos industriales

- Aplicaciones Medicas: Disminuir la interferencia electromagnética
- UnderWater: Radiofrecuencia bajo el agua no es tan optima
- Aviones: Ya no apagar celulares o dispositivos al no interferir en radiofrecuencias.
- Visible Light Positioning:
- High speed internet
- IoT and Smarts Infraestructures
- VLC en entornos mineros subterráneos
- VLC en Invernaderos