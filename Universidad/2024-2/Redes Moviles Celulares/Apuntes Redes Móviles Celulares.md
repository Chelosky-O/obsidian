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

# 16-08

## Arreglo de antenas
Cuando pongo mas de una antena, lineal o matricial.
Cada antena tiene su patrón de radiación en particular.

### Antena inteligente
Mover el patrón de radiación.

en 5G tengo distintas antenas y al final se combinan las respuestas en amplitud y fase.

el usuario reporta hacia arriba y puede direccionar el patrón de radiación. puede seguirlo mientras reporta su nivel de señal
![[Imagen de WhatsApp 2024-08-16 a las 08.40.21_b3070d0c.jpg]]

5g nace con antenas inteligentes 32 a 64 tx y rx

---

#### BeamForming

##### Dinámico
El ejemplo de aparatos, defensa antiaérea, antimisiles, se va ajustando a la trayectoria del misil o avión

##### Estático
Significa:

![[Imagen de WhatsApp 2024-08-16 a las 08.45.54_3cec9b19.jpg]]

Alojando a los diferentes usuarios, eso queda quieto, no sigue solo pasa al siguiente.

---

#### Massive MIMO

Combinar los 2 anteriores.

4G a lo más tiene 4 receptores y transmisores.

Los celulares más modernos tienen 2 transmisores y 4 receptores.

El problema es que si se agrega otro celu perdió esas 4 recepciones.

---

Ahora si hay 16 en la antena como se muestra en el ejemplo.

![[Imagen de WhatsApp 2024-08-16 a las 08.50.13_5a805bff.jpg]]

Se tiene un celular 2Tx/4Rx y un 1Tx/2Rx, todos tienen sus rx ocupados

ahora si aparece un tercero se puede distribuir el arreglo de antenas.

---

3G 3.7 es H+.
4G+ es 4.5

---

## Zonas de Fresnel

Sirve par Diseño, Simulación, 

Aire medio no ideal. obstruccion → perdida en espacio libre

ademas hay obstrucciones que no tienen que ver con el aire como edificio montañas etc...

Se puede modelar con Fresnel

Lobulo de cobertura que se genera entre transmisor y receptor.

Todo el calculo se hace para la primera por que tiene linea de vista.

### Calculo de Enlace

Elipsoide (elipse 3d)

El radio de este es r = 17,32\*sqrt((d1\*\d2)/(d\*f))


### Perdida espacio libre

Esto no da negativo, pero cuando se ocupa para calcular le pongo el menos
por que es una perdida.
![[Pasted image 20240816090707.png]]



---



PIRE O EIRP Presupuesto para salir hacia el aire.

![[Pasted image 20240816090152.png]]

---

![[Pasted image 20240816090055.png]]

![[Imagen de WhatsApp 2024-08-16 a las 09.03.22_59950c96.jpg]]

---




![[Imagen de WhatsApp 2024-08-16 a las 09.06.14_f60fec31.jpg]]

Ahora el ejercicio con fre

![[Imagen de WhatsApp 2024-08-16 a las 09.09.54_8c8f92d5.jpg]]

mas frecuencia menos radio osea soy mas resiliente a obstrucciones
mientras mas grande el radio mas choque.

no creo que se pregunte esto en la prueba pero si lo siguiente.

---

## Modelos de propagación

Cuando se invierte se debe definir un diseño apalancado por cálculos.

Simulación previa.

- Terrestrial path with one terminal in woodland: En bosque no considera espacio libre, solo vejetacion a eso se debe sumar la perdida de espacio libre.
- ITU TERRAIN MODEL: modelo para desnivel geografico, montañas, mecetas, etc... obstrucciones con perdidas adicionales. Tampoco tiene la perdida en espacio libre, se tiene que sumar.
- HATA MODEL: Este se utiliza en redes moviles celulares. Ecuaciones para suburbanos rurales, abiertas, ciudades. Tiene restricciones. Pero funciona para 3G. Toma todo el fenomeno de problemas que hay
- HATA EXTENDIDO → COST 231: Este si que si se usa ahora. Ahora añade una constante para acoplarse a las ciudades que uno va a simular

Tanto hata como cost321 depende de 4 elementos, 
- distancia de los 2 elementos en KM.
- Frecuencia de operación en MHZ
- ht Altura estación base, depende de la zona, desde 10m hasta 60m zona ma rurale, medida comun 30-36m y
- HT altura dispositivo celular, se usa 1.5 metros en promedio. 1.6 si quisiera

---
En el software se usara longly raise usa itu terrain model osea Fresnel.
Por perdidas adicionales por condición climatológica.

Por aquí termina lo de antes.

---

## Redes móviles

Problemas:
- Espectro disponible limitado (ancho del canal en frecuencia)
	- Eficiencia espectral: bits/Hz/Seg cuanto bits puedo enviar por hertz por segundo.
		- El segundo no puedo manipularlo, los bits depende de la tecnologia. pero si hay algo manipulable a mi antojo, los hz. la frecuencia. si yo agrando mi BW añado ma
		- 2G el ancho del canal son 200 KHZ
		- 3G 5 MHZ
		- 4G 20 MHZ
		- 5G 100MHZ
		- puede ser menos? si, la subtel licito 50 MHZ para cada operador en 5G, estas son maximas, pero se puede tener menos
		- Mayor generacion mas ancho de canal osea mas informacion puedo mandar. El problema es que es un recurso limitado.
		- Hay que distribuir para evitar congestión

Una torre celular esta compuesta por 2 partes:
	El sistema radiante, el que da potencia a señal
	Y sistema de bandabase o procesamiento digital, de aqui va al nucleo de la red.
Estructura de celdas:
	El concepto de movilidad entre celdas lo da el HANDOVER
		El handover es: el terminal reporta a que antena le va mejor, la señal de una torre es mayor a otra dependiendo de distancias, hay un punto donde las 2 se equilibran, hay un delta para hacer el traspaso, hasta que se llega a el margen, y como esta mejor se cambia.


---

### Tópicos observados en redes móviles

- Cobertura: tener un buen nivel de señal y mínimo nivel de interferencia para tener cobertura eficiente
- Calidad: congestión en servicio, cortes de llamadas, que no se pueda usar el servicio. Aquí se despoja la integridad del servicio
- Capacidad: Relacionado a cantidad de usuarios en una celda, si tengo muchos usaros todos van a pedir recursos, habrá muy poquito para mi, me va mal.

---

SOLO VOZ
2G → 2G
2,5G → GPRS
2,7G → E (Edge)
2 ESTANDARES CDMA GRINGO Y GSM EUROPEO MA ADOPTADO

3G → 3G
3,5G → H
3,7G → H+

4G → 4G
4,5G → 4G+

5G → 5G





























