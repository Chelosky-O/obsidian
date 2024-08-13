# 09-08
Correo: robertocarlos231@gmail.com

3 unidades c/u evaluación. Promedio simple

1ra unidad → refrescar lo que necesitamos en redes móviles celulares
 evaluacion escrita
 2da unidad → 4g, 90% del trafico en chile es 4g
5g sigue inmadura

Usaremos: RADIO MOBILE → portable, para simulaciones inalambricas.

Link Budget : Presupuesto del enlace

ev2 trabajo practico de diseño con simulaciones: de grupo de 2 o de 3.

---
3ra unidad 5G
diseño y simulación de red 5g
muxo feriao :D

---
nota presentación = promedio simple de las 3 notas
Eximición es con un 4


---
Bibliografía:
Libro 5g
Chris Johnson

Estudiar de ppts, pero complementar con libros si fuera necesario.

---

mejor venir aunque sea tarde :$

Solemnes la definimos entre nosotros

---

## Capitulo 1

### Redes inalámbricas

Red en la que 2 o más terminales se conectan entre si sin la necesidad de un cable.

Se estandarizan, en torres hacen huawei, nokia, samsung, etc...
En cuanto dispositivos: motorola, xiami, huawei, samsung ....

Wifi IEEE 802.11
Redes celulares 3GPP es el ente estandarizador

Se utiliza a través del aire.


Problemas: 
Atenuación
Ruido: interfaz abierta, señales que se pueden acoplar y bajan la prestación del servicio
Fading (desvanecimiento): propagacion multi trayecto

Ventajas de redes inalambricas:
- Movilidad, no confundir entre wifi y movil, wifi no permite desplazamiento
	- Handover: traspaso
- Velocidad y simplicidad de instalación: facil, entre comillas requiere plata, se pone una antena noma o varias
- Flexibilidad
- Costo reducido: en sitios que requieren cambios topologicos frecuentes
- Escalabilidad

Desventajas:
- Alta tasa de errores y menores tasas de transmisión: la fibra va mucho mejor por ej para que vaya asi de bien, muy cerca de antena y pocos dispositivos
- Seguridad: más propenso a ataque, en red celular es imposible. los códigos de encriptacion de redes celulares. en wifi, la clave nomas 
- Potencia de bateria: limitado
- Enfermedades asociadas a la radiofrecuencia: no xd, osea si o no, la radiofrecuencia en si es mala. la señales son debiles, el wifi y horno microondas son más fuerte sobretodo el horno.  los que viven en un edificio muy cerca de la antena quizas deberian preocuparse

### Conceptos generales

#### Ondas y propagación

necesitamos esto para transmitir en los medios.
Como esto se transforma en bits?

Esta onda electromagnetica es una OEM:

se puede propagar por el aire, pero no requiere un medio fisico.
Alcanza un medio de propagacion aprox a la velocidad de la luz
viaja mas rapido que la fibra, por el indice de refracción

la velocidad de una onda depende de cm=co/indice de refraccion, co es 3*10^8
el aire es 1 la fibra 1.5

en chile, para 3g se usa 3,5 ghz
en 4g se usan 2,7 1,4 1,9 ghz
3g 0,85 y 1,9 ghz

wom utiliza 2,1

factores climaticos afectan, sobretodo a frecuencias más altas

refracción se pierde energía pero llega el servicio, por ej cuando pasa por vidrio
reflexion, ahora si pasa por concreto se devuelve la onda
dispersión, se fragmenta

todo esto hace que haya Multitrayecto, muchas señales en muchas direcciones con la misma información.
llegan desfasados, hay señales que llegan antes que otras.

el receptor cuando las señales se desfasen, el receptor las toma todas y provoca interferencia destructiva.

en mundo digital me genera ISI, pierdo bits.

ISI

![[img0908.jpg]]

Se pone un umbral, lo que esta arriba es un 1 y lo que esta abajo de este es un 0w

---
atenuacion
ruido

todo esto es circulito en navegador.

---
#### Modulación
Es acoplar la señal de información al canal.

Quiero hablar con mi mama, esta esta a 15 km , le grito, me va a escuchar? no. pq la señal de voz es de baja frecuencia.

Necesita usar o acoplar una señal

no tiene sentido que emita señales electricas en una señal de fibra, 

Analogas: radio, transportan voz y video analogico, la tv abierta antes usaba analoga.

Digitales o binarias, no me sirve tengo que usar: PAM, PCM analoga a digital o QAM, ASK, FSK, PSK para digital en un medio


1G al inicio era analogo 

---

Para transformar de analogo a digital usamos

PCM : 3 pasos: muestreo, cuantificación y codificación

---

PCM:
Primera etapa muestreo

toma una referencia signiricativa que me permite despues reconstruir la señal de forma inteligente.
se tiene discreto el tiempo solamente (el eje y puede ser continuo)

Segunda etapa Cuantificación
Se toman x en este caso 16 posibles valores cuantos valores tengo, depende de la cantidad de muestras

se debe discretizar, ya que luego se debe binarizar

Tercera etapa codificacion, no es encritpar es tomar un numero y pasarlo a binario

10 en binario 1010
12 en binario 1100

al final se debe analogizar denuevo xd para enviarlo
![[930.jpg]]
---
ASK 1 y 0 diferentes amplitudes

combinaciones de bits = simbolos
a1 00
a2 01
a3 10
a4 11

2^x, x = bits 

---
FSK
mismo principio
desplazamiento de frecuencias
una frecuencia lenta para transportar 0 y rapida para transportar 1
mismo principio 2^x, x = bits

mas frecuencias, mas agrandar el canal, el problema es que las frecuencias deben ser limitadas.

---

PSK
parte de 0 = 1
parte de 1 = 0

mismo principio
2 fases 1 bit
4 fases 2 bits

pero con multi trayecto se desfasa xd se destruye, no se pueden tener tantas fases a mi antojo

---

Ahora se utiliza QAM
es ASK + PSK
amplitud y fase

16QAM son 16 combinaciones amplitud y fase, 4 bits
64QAM 6 bits
256QAM de a 8 bits
4046QAM 12 bits

3g hasta 65qam
4g hasta 256qam
5g 1024

---
Modulación adaptativa
cuando tengo buenas condiciones el sistema me pondra el mejor modulacion
luego va bajando segun 
![[941.jpg]]
# 13-08

