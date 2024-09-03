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

## Modulación Adaptativa

  

![[Pasted image 20240814100300.png]]

  

La modulación adaptativa quiero el mejor esquema de modulación, el que me de mas bits.

  

1024 ya lo usa la fibra óptica hasta 4096.

  

El problema es que no puedo dar ese esquema siempre, hay un problema en las comunicaciones inalámbricas, si me alejo del ente que me da la conectividad, mi nivel de señal disminuye.

  

La diferencia de señal vs el ruido presente en el ambiente genera que no pueda ser capaz de decodificar bien la comunicación.

Esto se adapta a la condición del canal.

  

---

  

Como se hace él cambio en la modulación adaptativa?

  

El esquema de modulación se negocia en función de la condición del canal, eso se llama MCS

Modulation uncoding skill → una tabla del 1 al 32 referenciado a SNR signal noise relation.

  

Se ponen de acuerdo y usan 16qam, ambos usan el esquema de fases y amplitudes para tomar la info.

  

---

  

## Conversión de Potencia

  

### Decibel

  

La razon de lo que sale vs lo que entra en una cajita x

  

Es una medida de variación donde su unidad es el decibelio (dB). Se utiliza en redes de radiofrecuencia, microondas, cobre y fibra óptica, como una medida absoluta a causa de su capacidad para expresar valores muy pequeños y muy grandes.  

  

Un aumento de 3 dB representa el doble de algo, lo que significa que -3 dB representa  

la mitad de algo.

  

![[Pasted image 20240814103151.png]]

  

![[Pasted image 20240814103143.png]]

  

---

#### Ejemplos:

1)

![[Pasted image 20240814103212.png]]

![[Pasted image 20240814103223.png]]

![[Pasted image 20240814103228.png]]

  

La perdida que tuve ahí fue de -1,2 dB. Esto no representa ninguna unidad, lo usamos a conveniencia con potencia.

  

---

  
  

A alguien se le ocurrió llevar el concepto de dB a potencias

dB → Variación

EL dBm → POTENCIA

  

Se pueden combinar dB con dBm? Si por que son variaciones de potencia.

  

---

  

2)

  

![[Pasted image 20240814103608.png]]

La potencia en dBm es

$$

10 \cdot log_{10}(Potencia\, en\, mW)

$$

Si tengo la potencia en W, o micro watts o nano watts debo llevarlo a mili para usarlo en la formula.

  

![[Pasted image 20240814103614.png]]

![[Pasted image 20240814104016.png]]

  

y para volver de dBm a mW se hace:

  

$$

10^{\frac{dBm}{10}}

$$

  

##### Recordar:

$$

m=10^{-3}, \mu = 10^{-6}, n=10^{-9}

$$

  

---

  

Tengo

  

![[Pasted image 20240814105213.png]]

  

Potencia transmisión + ganancia + atenuación + ganancia

10 dBm + 10 dB + (- 15dB) + 3dB = 8 dBm

  

$$

10^{\frac{8}{10}} = 10^{0,8}= 6,3 mW

$$

  

balance teleco: Lo que llega del receptor es lo que sale del transmisor + todas las ganancias y atenuaciones.

  

---

  

Ejercicio con servicio

\*#0011#

PLMN 730 es chile 01 ENTEL

  

RSRP NIVEL DE SEÑAL -97 → -97 dBm

RSRQ es como la snr , diferencia nvl de señal vs interferencia de ruido

  
  

Movistar (5G):

- - 83 dBm

- S24+

SpeedTest → tasa velocidad del servicio:

- DL = 191 Mbps

- UL = 51 Mbps

  

$$

P[W] = \frac{10^{\frac{-83}{10}}}{1000}

$$

$$

P[W] = 10^{-11,3}[W] = 5 \cdot 10^{-12}[W] = 5 pW

$$

  

Con esta poca potencia tenemos casi 200 Mbps de descarga y 50 subida

  

---

2g aguanta hasta -102 dBm para mantener un enlace estable

3g -112 dBm -115 aprox

4g -122 dBm aprox

  

---

  
  
  
  

Entel (5G)

- -86 dBm

- A52

- DL = 66 Mbps

- UL = 12 Mbps

  

Aquí hay una diferencia de 3dBm, o sea es el doble o la mitad del anterior, en este caso la mitad.

  

$$

P[W] = 2,5 \cdot 10^{-12}[W] = 2,5 pW

$$

  

---

  

## Antenas

  

Sin antenas no hay comunicación inalámbrica, es fundamental.

un material de metal con cierta estructura q recepción y transmite señales en cierto rango de frecuencias.

  

No todas las antenas sirven para todos los rangos de frecuencia.

  

Las antenas tienen diferentes tipos y aplicaciones.

  

Su parámetro mas importante es la ganancia, es una amplificación, o sea gane cierto nivel de señal.

  

Amplificación se asocia a un dispositivo electrónico, pero como puedo amplificar algo si es un pedazo de metal?

  

las antenas pasivas son pedazos de metal.

  

la ganancia esta relacionada con la capacidad de irradiar.

  
  

Unidad de ganancia dBi = es un dB, no tiene diferencia.

  

Por que se llama dBi? por que es la diferencia para una antena Isotrópica que es una antena ideal vs una antena real que no tiene esas condiciones.

  

---

### Tipos de antena

  

![[Pasted image 20240814112142.png]]

  

Antena isotrópica: Irradia en todas direcciones de forma equivalente. Básicamente corresponde a una antena ideal.

Esto no se puede construir, lo mas cercano es la omnidireccional.

  

Antenas omnidireccionales: son buenas para cubrir áreas grandes, donde se intenta que la radiación sea pareja en todas las direcciones, es decir cubre 360°.  

  

Antenas direccionales: son las mejores en una conexión punto a punto, permitiendo acoplar edificios a través de una red inalámbrica.  

  

Antenas sectoriales: intermedio entre omnidireccional y direccional. ni tan omnidireccional ni tan directiva.

  
  

El telefono es una omnidireccional.

  
  
  

![[Pasted image 20240814112406.png]]

  
  

---

  

![[Pasted image 20240814112433.png]]

![[Pasted image 20240814112357.png]]

  

---

### ANCHO DE BANDA DE OPERACIÓN

Es el rango de frecuencias en el cual la antena es capaz de radiar energía de forma eficiente y sin perdidas considerables.

  

![[Pasted image 20240814112602.png]]

  

---

![[Pasted image 20240814112627.png]]

  

Directividad: capacidad de enviar la radiacion a un punto en particular.

La de la derecha es mas directiva.

  

Ganancia: se define la ganancia de potencia en la dirección máxima, cuando por efecto de la directividad se concentra la potencia en las zonas indicadas en el diagrama de radiación.

  

Eficiencia: es la relación entre la potencia radiada y la potencia entregada a la antena.  

También se puede definir como la relación entre ganancia y directividad.

  

Eficiencia = Ganancia/Directividad

  

---

  

una antena omnidireccional mas parecida a una esfera tiene menos ganancia.

  

Como se hace la omnidireccionalidad, se sectoriza:

  

![[Pasted image 20240814113109.png]]

  

Si bien no es una esfera perfecta, se sigue una estructura celular, se pone otra que complementa las zonas muertas de mis antenas.

  

---

  

![[Pasted image 20240814113333.png]]

  

Antena de baja ganancia pero mucho rango de frecuencia.

  

![[Pasted image 20240814113350.png]]

  

antenas muy comunes en radio, por que son frecuencias bajas, ganancias buenas pq maximiza zona de impacto, es la que antiguamente tenían los celulares.

Los autos igual, pero ahora ya no.

  

![[Pasted image 20240814113439.png]]

Antes estaban en todos los techos de las casas, apunta antena hacia tv abierta. hoy es todo digital así que xd. sirve la dipolo, un alambre sirve para digital xD

  

Al ser directiva tiene mucha ganancia y puede operar a altas frecuencias y bajas muy adaptable.

  

---

  

![[Pasted image 20240814113556.png]]

  

Antena directiva por excelencia.

![[Pasted image 20240814113616.png]]

  

La antena es el pitutito y la parabola es donde rebotan señales.

  

ma grande el plato maximizo la zona de impacto.

  
  

---

![[Pasted image 20240814113723.png]]

  

Muchas aplicaciones, da wifi.

se pueden usar para conexion con microondas punto a punto

  

---

  
  

![[Pasted image 20240814113730.png]]

igual que monopolo, mismo largo pero enrollado en superficie, permite optar a rangos de frecuencia elevados y mejores ganancias, pero en superficie minimizo el tamaño.

  

![[Pasted image 20240814113736.png]]

Estas son las que se utilizan hoy en celulares, computadores, radio, etc...

Es una antena, dibujada a través de pistas de cobre.

  

Muchas ventajas pero tiene mala eficiencia o ganancias.

  

Ventajas: económica, bajo perfil se adapta a cualquier forma.

Conectada directamente a circuitería que toma la info.

  

Funciona a rangos de frecuencia que yo desee.

  

Problema baja potencia.

por norma un teléfono celular 23 dBm es lo máximo que puede irradear.

  

wifi por ej 100 mW → ← 20 dBm

un dispositivo celular 23 dBm→ ← 200mW

  

en los dispositivos modernos costados por atrás.

  

### DIVERSIDAD ESPACIAL

  

![[Pasted image 20240814141116.png]]

  

DIVERSIDAD DE ANTENA (DIVERSIDAD ESPACIAL)  

Mas costosa que la diversidad de frecuencia en cuanto a equipamiento, pero mas eficiente en lo que es la congestión del espectro de frecuencias.  

  

Si las antenas se instalan lo suficientemente apartadas entre sí, las señales sufrirán desvanecimientos independientes, por lo tanto se crean caminos diferenciados.  

  

Puede ser utilizada para enviar la misma información y seleccionar la señal mas robusta frente a la interferencia o enviar la información de forma segmentada aumentando las velocidades de transmisión de forma considerable. A esto último se le conoce como MIMO (multiplexación espacial).

  

DIVERSIDAD DE ANTENA (DIVERSIDAD ESPACIAL)

  

5G tiene 32 Tx Rx 64 se quiere llegar a 128

  
  

SISO: single input – single output. (sistema básico)

![[Pasted image 20240814142027.png]]

  
  
  

a) SIMO: single input – multiple output.  

  
  
  

b) MISO: multiple input – single output.  

  
  
  

c) MIMO: multiple input – multiple output.

![[Pasted image 20240814142036.png]]

  
  

x
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
- ITU TERRAIN MODEL: modelo para desnivel geográfico, montañas, mesetas, etc... obstrucciones con perdidas adicionales. Tampoco tiene la perdida en espacio libre, se tiene que sumar.
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
2 ESTANDARES -> CDMA GRINGO Y GSM EUROPEO MÁS ADOPTADO

3G → 3G
3,5G → H
3,7G → H+

4G → 4G
4,5G → 4G+

5G → 5G



---

# 20-08

## Historia y Evolución de la redes móviles
![[Pasted image 20240820085217.png]]

FDMA → Muchos canales FM.


---
![[Pasted image 20240820085322.png]]

La ITU le puso orden. en 1G todos los países tenían un standard propio.

GSM se adopto más.

Se pasó de analógico a digital. Comienzan a aparecer SMS.

Se crea a 3GPP que standariza las redes móviles
3GPP2 para CDMA
después 3GPP2 desaparece.

Canales dedicados a voz y a datos.

---
![[Pasted image 20240820085547.png]]
salió como 2005

GSM evoluciona a → UMTS ahora las 3g son UMTS

Aquí hasta 64QAM en cuanto a modulación digital.

También hay canales dedicados a voz y datos. para voz esta bien asegurar conexión, pero datos era ineficiente.

crearon HSPA, tengo un poll de recursos y existe una disposición.

---
![[Pasted image 20240820085833.png]]
desplego 2014 y 5g 2023

quiebre con predecesores, volvemos a tener segmentación en frecuencia y tiempo como en 2g pero más eficiente.

Todos los sistemas de teleco tienen OFDMA como método de acceso.

Postularon LTE+ y WIMAX2, pero gano LTE+, ya que LTE queda standarizado a nivel mundial.

Chile usa mucho su red celular. agresivos >:(

Se acabo la conmutación de circuitos, todo es paquetizado hasta la voz.


## Estación base móvil

![[Pasted image 20240820090550.png]]

1RO se necesita montar una estructura y abajo un gabinete ojala protegido.

Monoposte para ciudades.

Autosoportada ciudades o rurales.

![[Pasted image 20240820090759.png]]

Arriba esta el amplificador y la antena.

Puede ser alimentado con fibra óptica o cable coaxial.

Abajo todo el sistema de procesamiento digital y permite comunicarme al núcleo de la red a través de micro ondas etc...

---

Ejemplo pasivo con RRU's
![[Imagen de WhatsApp 2024-08-20 a las 09.16.37_1f6d16b9.jpg]]

---

5G TODAS ACTIVAS.
4G PUEDE SER ACTIVAS PERO DE NORMAL SON PASIVAS.

---

![[Pasted image 20240820092117.png]]


baseband digital unit, de ahi sale las fibras q llega a unidad de radio o antena activa.

![[Pasted image 20240820092338.png]]
![[Pasted image 20240820092357.png]]

![[Pasted image 20240820092412.png]]

![[Pasted image 20240820092424.png]]
![[Pasted image 20240820092451.png]]
Funcionan con corriente continua

También se utiliza climatización para mantener una temperatura dentro de esto.

---

# 23-08
## Estructura celular de una red móvil

![[Pasted image 20240820092545.png]]



![[Pasted image 20240820092609.png]]

Las celdas se separan por tecnología, con cada portadora diferente
Pero varias celdas pueden ser parte de un mismo sector.

2 Portadoras 3G (2 Celdas)
3 Portadoras 4G (3 celdas)
1 portadora 5G (1 Celda)

1 Sector → 6 Celdas

---
![[Pasted image 20240823083721.png]]

Comúnmente se bajan datos. En general, el trafico de subida es el 10% del trafico de bajada.

Duplexación no es lo mismo que una multiplexación. Es como administro el enlace descendente y ascendente de un usuario. de 2 formas:
Tengo FDD, 1 canal dedicado solo a subida y un canal dedicado solo para la bajada. Permite comunicación sin colisión
Distribución por distribución de tiempo se usa cuando tengo un solo canal y tengo que administrarlo para bajada y subida. Por cierto tiempo esto es bajada cierto tiempo subida. Como se baja más se designa mas tiempo bajada que subida.

En 2G se usa FDD
3G FDD
4G FDD pero empieza el concepto de TDD muy poco explotado
5G TDD


![[Pasted image 20240823084904.png]]

Estado IDLE: modo dormido, el teléfono puede estar en modo conectado o IDLE. Cuando no estoy haciendo nada estoy en modo IDLE.

Como el teléfono despierta? Existe un mensaje llamado mensaje de paging, le dice al teléfono oye tienes algo. El mensaje de paging se coordina cuando el teléfono hace este ping.


![[Pasted image 20240823085055.png]]
CC es 56 es Chile
NDC Numero que sigue (nosotros usamos el 9) pero aveces aparecen unos 8 o 7. Depende del pais que numero utilice
Subcriber Number son los 8 digitos que componen el numero


![[Pasted image 20240823085115.png]]
dificil de clonar
IMSI: 3 CAMPOS
MCC: país 730 esto se usa bastante para la ubicación de cada usuario en un país. se usa para roaming.
MCN: identifica proveedor del país.
MSIN: Codigo de simcard, identifica del resto


![[Pasted image 20240823085522.png]]

Identificador de dispositivo movil. es facil de clonar

---
![[Pasted image 20240823085552.png]]
En edge 200kbs max 
![[Imagen de WhatsApp 2024-08-27 a las 08.36.22_ebc84575.jpg]]


![[Pasted image 20240823085603.png]]



![[Pasted image 20240823085613.png]]

frecuencia en downlink es mayor que el uplink. por que no al reves? 

![[Pasted image 20240823091018.png]]

las operadoras tienen su frecuencia propia no la comparten con nadie.
BCCH → la primera frecuencia Broadcasting control channel, indicador que el usuario ve para identificar la celda. Eso va alojado en el primer slot de la primera frecuencia.

Los primeros slots son para control y señalización, todo el resto trafico.

![[Pasted image 20240823091056.png]]


# 27-08

![[Pasted image 20240823091955.png]]

Núcleo de red hace todas las funciones básicas que hace una red móvil.

Torre celular : BTS

Interfaz UM: la que va en el aire.

En 2g las estaciones celulares no se manejan solas tienen un administrador. Se llama BSC y tiene una interfaz que se llama Abis.

Cada BSC tiene un U definido para administrar Q cosas.

Estos administradores llegan al MSC (conmutador de circuitos) que hace las transiciones para distribuir x entre 2 entes que quieren comunicarse.






![[Pasted image 20240823092729.png]]

En su momento habían 40 bsc una por región y en Santiago 10.



prueba martes 10

---



![[Pasted image 20240827082659.png]]

Cuantos BSC yo tenga necesito una x cantidad MSC

Ahora tenemos unos 6 MSC a nivel nacional, hay de redundancia entre estos ya que se cae y chao.


Todos los msc tienen un GMSC que es un gateway hacia otros operadores móviles o fijos.









![[Pasted image 20240827082711.png]]

Hay bases de datos

HLR estan nuestros datos, el plan el rut etc..

Cuando tengo un servicio paso por todo y la red conoce lo que yo tengo a traves de una consulta a través de desta db

EIR otra db que tiene 3 listas, blanca, negra y gris. Los lista blanca pueden traficar en la red, los lista negra estan bloqueados y gris son los que están intervenidos, por ej la pdi necesita seguir un nro y chao.

![[Pasted image 20240827082725.png]]

La SIMCAR tiene una IMCI , el HLR sabe las 3 variables del IMCI, cada imci tiene una tripleta única. 


![[Pasted image 20240827082738.png]]

VLR: Lo mismo que el HLR, base de datos de los abonados, el vlr es como una ram. se consulta primero al hlr y luego se la pasa al vlr.
cada msc tiene un vlr.

Este sirve para localizar al cliente cuando tiene un servicio. Con el LAC (location area code). es un codigo que le asigno a las celdas.



![[Pasted image 20240827082752.png]]

Para ubicar desde afuera se usa el LAI, lo mismo que LAC pero + pais y red.


![[Pasted image 20240827082904.png]]

Usa QPSK


![[Pasted image 20240827082918.png]]

GPRS VS EDGE es que pasamos de QPSK A 8PSK ya no son 2 bits si no que 3.

![[Pasted image 20240827082938.png]]

Lo mismo que antes pero para paquetes.

Msc con vlr para vos
y sgsn con su gateway para datos, salidas a internet.

Es lo único que se adicionó.

En 3g es igual solo cambia el controlador y la torre.


![[Pasted image 20240827082949.png]]

8 SLOTS DE TIEMPO 4 FRECUENCIAS.

Stand Alone SD asignan recursos para tráficos 

en 5g es igual el dar recursos.

tch T trafico
PDCH P trafico pero datos, 

rojo datos
amarillo voz
los demás control.

Best efford ocurre hoy en dia en 5g.

---

![[Pasted image 20240827091821.png]]

3G cambia completamente el tipo de acceso al medio

De fdma y tdma a algo que depende de una visión mas lógica de la 
cdma acceso múltiple por división de código.

![[Pasted image 20240827092041.png]]

hoy en dia 3g aguanta hasta 64qam 6 bits.

GSM pedacito de tiempo y de frecuencia.

En 3g, todo el tiempo y toda la frecuencia a los usuarios.  como se segmenta? por que se crea un tercer plano de códigos, código 1 a un usuario 2 a otro 3 a otro y así.

3G 64 usuarios simultaneos, para voz no problem, pero para datos es poco.

En sus inicios 388 kbps por segundo.


el 80% del trafico se sigue cursando en 4g. un 15% 5g y remanente en 5% en 3g. 

Sin embargo 3g sigue siendo poderoso por que la gran parte del trafico de voz se usa en 3g.

2G Muere este año. 

![[Pasted image 20240827092414.png]]

![[Pasted image 20240827092449.png]]
el código es único para cada usuario. 

recibo la señal de todos pero solo recupero lo que viene asociado a mi código.
Es como una especie de broadcasting.

Cada codigo se llama Spread Factor (SF) → Este es el recurso de 3G.

En GSM (2G) el recurso es el Time Slot.
![[Pasted image 20240827092801.png]]
Usa FDD

5 Mhz Downlink y 5 Mhz Uplink

10 MHZ efectivos.

Tiene un código para los canales en frecuencia en 2g era ARFCN ahora es UARFCN.

En chile la GSM las mantuvimos hacia 3g, se apagan gsm para meter 3g.

![[Pasted image 20240827093215.png]]

Aquí no hay plan de frecuencias, entonces como se a que celda esta conectada? hace plan de celdas. ese código es Scrambling code vendría siendo el análogo al BCCH.

![[Pasted image 20240827093341.png]]

Si se esta completamente seguro de que se va a cambiar, me tiro, antes era mas brusco aquí no.
En 3g siempre tengo una segunda opción. si no me funciona la segunda opción me quedo.

# 30-08

![[Pasted image 20240827093722.png]]

3G tiene una ventaja, y es que se puede agregar mas dispositivos, no celulares, tablet, etc...



![[Pasted image 20240830090103.png]]

![[Pasted image 20240830090115.png]]
![[Imagen de WhatsApp 2024-08-30 a las 09.00.02_6d1283f6.jpg]]


Estoy en una celda 1 y me muevo a una celda 2, no se cambia por magia.
Para poder hacerlo necesito definir una vecindad.
Tenemos celda 1 y 2 y debemos decir en la configuración, tu puede moverte a la celda 2, celda 5, celda 10... etc, y si me voy moviendo a qui y empiezo a detectar la celda 2 y si la tiene se mueve, pero si no estuviera se cae.


Esta definición se llama adyacencia o vecindad.

![[Imagen de WhatsApp 2024-08-30 a las 09.05.59_822242a8 1.jpg]]


![[Pasted image 20240830090129.png]]
R99 canal dedicado, se usaba para voz y datos.
Antes si no había voz agarraba menos datos y si había agarraba más.

Con esta tecnología, mala eficiencia para datos.




![[Pasted image 20240830090143.png]]
EN HSPA TOPE 16QAM Y EN HSPA+ 64QAM, Es la unica diferencia entre los 2, nada más.



![[Pasted image 20240830090156.png]]

Es como una piscina, mientras más personas mas te puedes mover. llegaran tantas personas que no podre hacer nada.
R99 ahora solo se usa para voz. todo lo que queda disponible para datos, estos si estoy solito buena, si no ... 

Lo ideal es que nadie usara voz para poder usar todo ese canal.


![[Pasted image 20240830090209.png]]
con r99 siempre tendria el downlink de 384


![[Pasted image 20240830090220.png]]
buena cobertura mejora la velocidad, siempre y cuando tuviera pocos usuarios de voz obviamente.
Si estoy en mala cobertura tendré menos velocidad.


![[Pasted image 20240830090231.png]]

Ahora no se usa eso hoy en dia, hoy seria high speed noma XD pq se utilizan mucho espacio los R99.


# 03-09

## Ejercicios Solemne No 1


1)
HM altura en metro terminal
Ht altura en metros base celular


puede dar la perdida y nosotros calculamos la distancia.

en okumura nos dan constantes. la frecuencia va en MHz

La altura de la estación celular va en metros
en okumura son:
distancias en km
alturas en metros
frecuencias en MHz

no solo considera perdida en espacio libre si no la demografía. las estructuras.

---
en fresnel la frecuencia es en GHz.
y distancia en km.

considera perdida en espacio libre

---
3 4 preguntas, la 1 va siosi pero de distinta forma quizas?

---

la 1 de cost231

cost231 es para ciudad y el itu para nivel geográfico.

estudiar si o si la 1 y la 1 de ambas solemnes.

puede pedir la distancia en lugar de lo que pide.

---


## CAPITULO 2

### Redes Móviles 4G

#### LTE (Long Terminal Evolution)

Al inicio habían 2 postulantes LTE → EEUU y UE.
WIMAX ma asiáticos :P 

Caracteristicas mas significativas:
- 4G 200 MB por segundo a 1 GB/s
- 4G llega a 20 MHz pero se usan 20 para subida y 20 para bajada, en teoria son 40 los que necesita.
- Lo bueno es que es una ancho de espectro variable.
Pueden ser 20 15 5 10 5 ....
Menos frecuencia, menos capacidad de transporte de información tengo.

max velocidades 100 mbs en bajada y 50 en subida.
Puede usar MIMO, tiene mas antenas en el transmisor para multiplexar y multiple streams. con esto se llega a 200 mbs de bajada y 100 de subida.

DL-> 200Mbps
UL → 100 Mbps
ESTO ESTA EN 64QAM


Luego sale MIMO 4X4 y serian 400 y 200.


4G disminuye la latencia en la interfaz de aire, no es el end to end (depende de la red de transporte, etc...) es la de radio y disminuya a 20ms (0.02s)

OFDMA → Acceso multiple por division de frecuencia ortogonales (perpendicular) → Esta es una de las grandes impulsoras para que la tecnología sea eficiente.

Red IP → La voz es paquetizada 
No hay controlador de estaciones celulares.
La estacion celular se conecta directamente al core.

EN 2G USA ARFCN
3G UARFCN
4G EARFCN

---
IGUAL QUE EN 3G las celdas se definen por codigo

PCI physical cell identity
no tienen que quedar adyacentes los pci

PSS → primario 
SSS → secundario

nunca primarios contiguos

![[Imagen de WhatsApp 2024-09-03 a las 09.03.24_f9c7cf29.jpg]]

![[Imagen de WhatsApp 2024-09-03 a las 09.03.46_6aff0207.jpg]]

---

Acceso al medio

Resource block

Matriz tiempo frecuencia vuelve a aparecer.

prb se entrega par servicio

15x12 en frecuencia son 180 khz
un rb dura 0.5 ms

cada cuadrito se llama resource element y se modula bajo un esquema de modulacion diferente 64qam por ej.

![[Imagen de WhatsApp 2024-09-03 a las 09.11.50_579431bf.jpg]]

---

sync → fourier → escalon
escalon → fourier → sync

aumenta la capacidad del sistema con ofdma, se cumple con la ortogonalidad. con fourier los separa.

doopler le pega mucho a esto...

pero hay tecnicas para mitigar este fenomeno.
tambien el multitrayecto

![[Imagen de WhatsApp 2024-09-03 a las 09.17.22_0c5a2d63.jpg]]

---

En 4G:

OFDMA → DL
SC-FDMA → UL

---

HARQ - HYBRID AUTOMATIC REPEAT REQUEST

Retransmisiones
envía una paquete de datos, espero el ack o el no ack.

transmito el siguiente si llego ack
vuelvo a enviar si llego no ack


que hace harq? los paquetes que llegan mal, no los descarta, los almacena.
envió paquete llega mal
envió de nuevo llega mal de nuevo
que hace? con los guardados ve si se puede recuperar y si lo hace pide el siguiente.


---

Calculo velocidad máxima en DOWNLINK
![[Imagen de WhatsApp 2024-09-03 a las 09.26.20_20534fe5.jpg]]


20MHz(100PRB) 64QAM(6bits) MIMO2x2(MULTIPLICA X2)

14 slots de tiempo x 12 subcarriers = 168 RE

1 prb dura 1 ms, un rb dura la mitad 0.5 ms

(168 RE x 6 bits )/ 0.001 seg = 1Mbps

---
en teoria con 20MHz, 64QAM y mimo2x2 se obtendrian
200 Mbps DL
100 Bps UL


En realidad se obtienen aprox:
150 Mbps DL
75 Mbps UL

---

mas actualmente se usan 20 MHz 256 QAM(8bits) y mimo4x4(x2)

200 Mbps x 2 x 1,33 = 532 Mbps teórico DL
%25 control
400 Mbps DL realidad

en subida me quedo casi igual, 256QAM no se usa en subida.

---

estudiar core 3g y 2g, interfaz 2g 3g mimo diversidad espacial, binforming, fading, nose xd.


# 06-09


# 10-09


# 13-09




























