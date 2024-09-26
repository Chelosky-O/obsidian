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


# 16-08
## Configuración básica de sistema VLC/LiFi
![[Pasted image 20240820201726.png]]
Transmisor
- Fuente de datos
- Driver Controlador de lámparas leds

Receptor
- Dongle
	- Fotodetector
	- Todo el sistema de procesamiento de la señal que estamos recibiendo

---
![[Pasted image 20240820202202.png]]

Ciertas etapas o bloques que se parecen mucho a radiofrecuencia.

![[Pasted image 20240820202229.png]]

![[Pasted image 20240820202237.png]]

Se necesita en VLC otros bloques adicionales para ser transmitida por el propio evento físico de la luz y uno de esos es el pre distorsionador que es añadir una pequeña distorsión a la señal modulada para que pueda contrarrestar la propia distorsión que se genera por efectos físicos.

![[Pasted image 20240820202413.png]]

Pulse Shaping: Es la formación de un pulso adecuado para representar el dato digital a señal analógica y pueda ser transmitida por el led ya que el led funciona con corriente y voltaje por lo que son señales analogicas, hay que variar la magnitud de la corriente o voltaje para que varie la potencia luminosa y con eso emular bits o simbolos.

![[Pasted image 20240820202650.png]]

Señal OFDM: en comunicaciones por luz visible necesitamos que la señal sea unipolar positiva y real. Por lo que todas las amplitudes negativas tienen que ser subidas añadiéndole un DC bias (sumar una seña dc a la ac que tenemos como señal de datos).

![[Pasted image 20240820202751.png]]

Modificando el voltaje se aumenta o disminuye la corriente y viseversa.

![[Pasted image 20240820202821.png]]

Hay que tener cuidado en el área DC que se trabaja para no cortar o saturar el led. corriente debe ser manejada con un driver. Los leds suelen tener un driver.

![[Pasted image 20240820203004.png]]

Se usan leds masivamente y no ampolletas, por que? Por la potencia que consumen. mucha deficiencia en consumo de potencia en ampolleta incandescente.

![[Pasted image 20240820203107.png]]

# 20-08

![[Pasted image 20240820203204.png]]

Unidades fotométricas: como medir la luz dependiendo de donde nos encontremos, el punto de vista del observador o de algún área especifica.
Cambia la unidad por el punto de vista que se tome.

hay 4 unidades:

- Candela(cd): unidad en sistema internacional, intensidad luminosa solo en una dirección especifica. es un vector que dice intensidad. Fuente de luz monocromática. 
- Lumen(lm): flujo luminoso en todas las direcciones.
- Lux(lx): 
- Luminancia(L$\alpha$):fuente de luz que irradia en un punto específico o área especifica, pero nos colocamos como observadores, y el área que nosotros observamos que se ilumina es la luminancia. depende del angulo del observador.

![[Pasted image 20240820203738.png]]

1. Intensidad Luminosa (I): flujo que cae en Angulo determinado de apertura.
2. Flujo luminoso($\phi$): no interviene Angulo, si no todo lo que yo irradio con el led en todas las direcciones. medido en lumen
3. Luminaria(L):fuente de luz que irradia en un punto específico o área especifica, pero nos colocamos como observadores, y el área que nosotros observamos que se ilumina es la luminancia. depende del Angulo del observador.
4. Iluminancia(E): la que mas nos sirve. El que se necesita optimizar. es los  rayos de luz que emite en una área especifica o determinada. todo el flujo que puede caer en una área determinada. vista desde el punto del área donde estoy recibiendo la luz. Se mide con lux
	- Flujo en área determinada


- Transmisión regular: pequeña desviación del Angulo con el que iba el rayo.
- Transmisión difusa: muy usada en ambientes indoor con polvo, choca con este y se dispersa.
- Transmisión mixta: algunos rayos tienen una transmisión regular y otros una difusa y esto se combina en ambientes mineros por ejemplos.


Nosotros estudiamos la luz como onda.

![[Pasted image 20240820204840.png]]

Tipos de leds comerciales.

Led es un diodo → Semiconductor : Galio - cilicio - germanio.

Funciona con electroluminiscencia: energizo, doy un voltaje al led y hay 2 tipos de elementos un tipo p que tiene una deficiencia de electrones y un tipo n que tiene una carga de electrones. cuando energizo hay un cambio de energía al pasar electrones del tipo n al tipo p, se van llenando estos espacios y esa energía que se va liberando se libera como una fuente de luz fotones onda luminosa.

El led debe estar polarizado en directa.

Tipos de leds:
- Led basado en fosforo: barato → Luz azul, molestosa a la vista. Para formar la luz blanca se cubre con una capa de fosforo amarillo, con esto la luz va a pasar por esa capa de fosforo y cambia su longitud de onda a blanca.
	- ![[Pasted image 20240820205242.png]]
- Multi-chip: arreglo de leds
- Organic LEDs: oleds, mayor investigación.
	- ![[Pasted image 20240820205255.png]]
	- Muchos televisores tienen este tipo de pantallas. basados en cristales o polímeros.
	- Ventajas: flexibles, delgados, se pueden reconstituir y tienen cierta inteligencia para saber cuanto transmitir a mas o menos intensidad.
	- Con esto puedo aumentar el ancho de banda y se puede enviar mas datos que con un led. por su material flexibilidad y su adecuación a una estructura de transmisión.

---

![[Pasted image 20240820205514.png]]

Si se quiere transmitir o usar una modulación para poder transmitir mas dígitos o bits, necesito modulaciones que permitan transmitir símbolos o conjuntos de bits.
Se deben considerar 2 cosas:
- Que la modulación o la energía que necesito para modular el dato este justo en el rango de funcionamiento lineal del led.


![[Pasted image 20240820205741.png]]

En términos de la señal se necesitan 2 características:
- Que la señal sea positiva
- Que la señal a transmitir sea real.
Si no es alguna de esta se debe forzar a ser positiva y real

Lo recomendable es usar modulaciones que usen cambios en intensidad.

No se pueden usar constelaciones para representar una señal, como en 2d en radiofrecuencia
y los valores negativos se deben hacer positivos usando aumentos de corriente.

Modulaciones:
OOK
PAM
PWM
PPT
OFDM → modificada:  a+jb(parte real y una parte imaginaria) se usa la real

---
![[Pasted image 20240820210032.png]]

![[Pasted image 20240820210514.png]]
modulación pasabanda

---

![[Pasted image 20240820210707.png]]

A este circuito se pueden añadir cambios en intensidad con alguna señal de datos que cambie intensidad (apagando o prendiéndose) se pueden transmitir cosas básicas pero a poca distancia.

![[Pasted image 20240820210754.png]]

Por ejemplo un modulador, da una señal mas adecuada modulada para que sea transmitido por el led.
Opamp para poner señal de comunicación.

![[Pasted image 20240820210931.png]]

Raspberry ya tiene todo para transmitir señales.

![[Pasted image 20240820210951.png]]

Los lasers tienen un mayor consumo de potencia, son mas dirigidos. se puede modular con mas frecuencia pero el ancho espectral óptico usado es muy bajo comparado con el led. no sirve mucho en indoor.

---


# 27-08

## Recepción óptica
- VLC Receiver: Se tiene un elemento que hace la transformación Optico a eléctrico, TIA (Trans-impedance amplifier) (Amplificación), DSP.
	- Una vez que la señal sale del transmisor y llega al receptor.
	- Factores a considerar en el transmisor:
		- Ruido (Ruido térmico, ocurre cuando la señal está ya en el receptor)
			- AWGN (Ruido ideal, gaussiana)
		- Interferencia (Se produce en el canal de transmision)
		- Luego de que llega la señal al receptor una vez se le añaden los ruidos se debe **sincronizar**. De esta manera se saben los tiempos de muestreo y poder muestrearla correctamente
		- **Matched filter:** Importante en entornos donde hay mucho ruido, asi se puede eliminar gran cantidad de ruido.
		- Una vez está lo más limpia posible la señal se realiza la conversion Analógica/Digital
		- Luego se utiliza un **Equalizador**, aumenta o disminuye la amplitud de la señal. Ayuda para reducir la ISI que se produce a altas velocidades, por lo que a velocidades bajas es practicamente inútil usarlo.
		- Demodulación y decodificación, respocto a la modulación y codificación usada. Se utilizan métricas para saber si llegó bien la señal. BER (Bit error rate) y SER (Symbol error rate).
	- Elementos que incluyen al receptor:
		- Optical filter and concetrator:
			- Filtro óptico:
				- Capa traslucida que permite pasar ciertos rangos de longitudes de onda.
				- La onda que atraviesa el filtro depende del angulo de incidencia
			- Concentrador:
				- Su funcion es concentrar la luz a un punto específico sin importar como llega o en que angulo llegue. Sin el concentrador no todas las ondas llegarian al foto receptor
		- Photo-diode:
			- Semiconductor de tipo P-I-N
			- Material: Silicon, Germanium, InGaAs. Cada material tiene su responsividad.
			- Tiene un AP (Area activa)
		- TIA
		- Procesamiento
	-




# 03-09

## Modelo de canal
- Alámbrico
	- Deterministico
	- Medio físico
		- Líneas de fuga
		- Fibra óptica
		- Cobre
		- Semi-conductores
	- El canal se modela con modelos matemáticos probabilísticos o estadísticos.
	- distancia → atenuaciones → pathloss
- Inalámbrico
	- No determinístico
	- Medio físico
		- aire/vacío/agua o estados del agua
			- Mucha más atenuacion que alambricamente
			- shadowing
			- scattering
		- LoS
		- Hokumura
		- Friss
		- Fresnel

---

## Link Configuration

![[Pasted image 20240903162143.png]]

Linea de vista (LoS)
De los 4 los lineal de vista son: a) 


d) usa Tracking Los(Line of Sight), es lo más optimo pero tambien lo más caro.
angulo de irradencia 

b) escenario de reflexion(non LoS) y linea de vista indirecta.

c) Reflexión →  solo non-Los

![[Pasted image 20240903162952.png]]


todos receptores y transmisores están en el suelo (mismo nivel)

![[Pasted image 20240903163428.png]]


![[Pasted image 20240903163442.png]]

a) hay 2 canales UL y DL.
b) mas facilito pq se sabe donde estarán los equipos.


## Indoor Optical Wireless Communication Channel

![[Pasted image 20240903163650.png]]

![[Pasted image 20240903164345.png]]














# 06-09

## LOS propagation model
- Linea de vista directa.
- No hay obstrucciones.
- Escenario ideal
### Light Source Model
![[Pasted image 20240906161521.png]]
(1) El ángulo de irradiancia es con respecto a la normal en el led, si el angulo del haz de luz está en 0° con respecto a la normal se alcanza el máximo de intensidad.
(2)
El semiángulo de la mitad de potencia va entre [60°-90°)]
Siendo 90°el peor
A medida que se amplía el angulo más se dispersa la luz, mientras que con menos angulo, mas concentrada está la potencia.

### Light Detectors
![[Pasted image 20240906162547.png]](3) Ángulo de incidencia, lo ideal es que sea 0°
(4) n es el coeficiente de reflexión

Todo se une en la siguiente formula:
![[Pasted image 20240906163656.png]]

Pauta Solemne 1 2022-2
Calcular y graficar la respuesta al impulso ( magnitud vs tiempo) de la componente de canal LoS de un sistema 
Angulo de incidencia = 30°
Angulo de irradiancia = 45°
Posición del led = (2, 4, 4)
Posición del PD = (1, 4, 1)
Área efectiva del PD = 12 mm^2
Asumir ganancia unitaria y modo lambertiano de 1
distancia se saca con los puntos = raiz(1+0+9) = raiz(10)
Aeff = Ap x cos(ang_inc)
Ap = 12 / cos(30°) = 10,39 mm^2
Ap = 1,39 x 10^-3
m se asume como 1
H_LoS = (1+1) x 1,39 x 10^-3  x cos(45) x cos (30) x 1 /(2 x pi x 10)
H_LoS = 2 x 1,39 x 10^-3  x 0,707106 x 0,866025 / (20 x pi)
**H_LoS = 2,71 x 10 ^-5**

tiempo que va a demorar en llegar al receptor
d/c = raiz(10) / (3x10^8) = **1,05 x 10^-8 segundos** = 0,105 nanosegundos
Ahora graficar eje X tiempo(ns) y eje Y (adimensional) se dibuja un pulso en los 0,105 ns con una altura de 2,71 x10^-5

# 10-09
Solemne 1

![[Imagen de WhatsApp 2024-09-10 a las 16.15.31_eb9ba556.jpg]]
1)
B) 430um A 770um

2)
B) Real y positiva

3)
C) Dependencia de condiciones del entorno

4)
C) Modificar la intensidad o la fase de la señal óptica para llevar información.

![[Imagen de WhatsApp 2024-09-10 a las 16.17.15_c4d50302.jpg]]
5)
c) Filtro Optico

![[Imagen de WhatsApp 2024-09-10 a las 16.20.15_e3088b4a.jpg]]
6)
b) La disminución de la intensidad de la señal a medida que viaja a través del canal debido a la disperción y absorción de la luz

La distancia es lo más critico para la atenuacion de la comunicacion de LOS

![[Imagen de WhatsApp 2024-09-10 a las 16.23.51_c657c4bf.jpg]]
7)
b) A medida que las

en el transmisor

![[Imagen de WhatsApp 2024-09-10 a las 16.24.04_100da505.jpg]]
8)
no se representa en frecuencia, en tiempo, frecuencia o peaks

b)

![[Imagen de WhatsApp 2024-09-10 a las 16.24.14_7930e863.jpg]]
![[Imagen de WhatsApp 2024-09-10 a las 16.26.37_c6c8e234.jpg]]
9)

los siempre sera la que llega mas rapido por que es directa, el peak de la foto en todas las graficas
lo demas es non los, disperciones, reflexiones, etc...

el mejor desempeño es el a,b o c? depende del contexto, los 3 tienen la misma amplitud, en termino de llegadas en tiempo, el a llega más rapido, pero sin conteto no puedo decir que b es correcta.

los 3 tienen el mismo desempeño?

correcta d) tienen la misma cant de reflexiones.

e) no se puede concluir sobre el desempeño de los sistemas con esta información

f)
Dispercion temporal: el ancho que ocupa la señal en el tiempo.
es buena o mala? depende



Problema 1:
![[Imagen de WhatsApp 2024-09-10 a las 16.30.34_642b229c.jpg]]
preguntan calcular distancia aprox 

forma extensa y facil.

extensa es la formula de h.


la forma rapida es con:
v=d/t → t=d/v


delta representa impulso, va a multiplicar
![[Imagen de WhatsApp 2024-09-10 a las 16.33.58_e97e2d16.jpg]]

---

## Proyecto:
APP EN CANVAS




































