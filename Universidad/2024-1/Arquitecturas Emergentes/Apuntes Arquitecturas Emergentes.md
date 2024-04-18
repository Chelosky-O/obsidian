# 07-03

GNS3 Como cisco packet tracer
Mini net -> Simula Delay, Paquetes fallidos y Perdidos

High availability (HA)
# 11-03
## Red Troncal (BackBone)
Point of Presence (PoP), es un punto de acceso bien a grande escala

### Tipos de BackBone

- BackBone en serie: falla 1 y chao
- BackBone distribuido: falla el router y chao
- BackBone distribuido
- BackBone colapsada
- BackBone paralela



---
En una red no deberían existir loops ya que se haría un loop de STP

---
Alta disponibilidad (High Availability)

Los sistemas fallan, pero su objetivo es:
- Evitar tiempos de inactividad
- Minimizar impacto fallos
- Mejorar confiabilidad
- Mantener continuidad del negocio

Clasificación de fallos:

- Hardware
	- Disco Duro
	- Memoria
- Software
	- Aplicación
	- Parches, actualizaciones defectuosas
- Red
	- Enlace de red
	- Congestión de la red
- Fallas Humanos (Capa 8)
	- Configuración
	- Accidentes


SOLUCION: REDUNDANCIA

# 14-03
## Arquitecturas de Alta disponibilidad

### 1. Clustering

- Definición: Un clúster es un grupo dedos o mas servidores o nodos que trabajan juntos como una sola entidad. Se distribuye la carga de trabajo entré los nodos y, si uno de ellos falla, los demás pueden asumir la carga.

Configura base de datos para que sea un espejo de la otra. Importa la geografia.
### 2. Replicación



Son 2 bases de datos descontextualizados, donde mediante un script , toda las transacciones hechas en 1 se repiten en la replica.
En tiempo real.
Genera un trafico de red para mandar entre servidores. Penalización de latencia, esta afecta el commit.

### 3. Balanceo de Carga 

- Round Robin Si tengo un trafico de red que viene...

- Balanceo Ponderado: Dependiendo de la conexión se selecciona, se pondera o asigna mas pega a servidor con mayor ancho de banda y proporcionalmente al que tiene menos.

- Basado en la carga: Servidores cdn, por carga de cada servidor.
- Basado en geolocalización: Selecciona por cercania geografica.
Códigos http 400 error, 500 error servidor, 200 ok, 300 redirección.

### 4. Conmutación por Error (Fail Over) y Conmutación por Recuperación (Fail Back)

Conmutación por error implica cambiar automáticamente a un recurso de respaldo cuando el recurso principal falla.

La conmutación por recuperación implica volver al recurso principal una vez que se ha recuperado.

Ej: Si un sv web que cambia automáticamente a un servidor de respaldo si el servidor principal se vuelve inaccesible.

### 5. División de Zona y Geoclusterización

Divide los sistemas en zonas geográficas separadas y aisladas para evitar que un desastre local afecte todas las áreas.

Para desastres evitando interrupciones.

### 6. Virtualización y Contenedores
Contenedores.



---
---

# 28-03

## Desafios IoT

### Escala

Una red típica soporta del orden de miles de nodos
Una red IoT debe soportar millones de dispositivos

Una cosa puede ser sensor y otra actuador. 
Sensor → 
Actuador → Se ejerce una acción a propósito de lo que se sensó.

---
### Big data y Analítica
- Generación de un diluvio de datos de diferentes fuentes de información.
- Debe manejarse o administrarse de manera eficiente.
-  Datos proveen información crítica y hallazgos importantes.

---

### Privacidad

- El uso de dispositivos IoT es cada vez más masivo.
- Capturan y recolectan datos asociados a individuos y a sus actividades o comportamientos.

---
### Interoperabilidad

- Proceso de estandarización de protocolos y arquitecturas
- Basados en tecnología abierta y/o propietaria.
- Incorporar sistemas o dispositivos heredados (legacy).

---

### Seguridad

- Riesgo transversal a todo nivel de una red IoT
- Dispositivos o nodos están físicamente expuestos.

---

### oneM2M
Es un proyecto de asociacion






# 01-04

Entidad de Aplicación:

- Representa la lógica del servicio de aplicación 
- Cada lógica de servicio de aplicación puede residir en varios nodos y/o más de una vez en un solo nodo.

Entidad de Servicios comunes:

- Representa la instancia de un conjunto de funciones de servicios comunes (CSF)
- Un CSE es en realidad la entidad que contiene la colección de funciones de servicio comunes especificadas por oneM2M que los AE pueden usar.

Pub - Sub : 1 dispositivo iot no necesita tener dirección ip asignada, se conecta a una capa de red tal que es capaz de conectarse con una especie de aforo virtual y ahí se publican y leen avisos.

Entidad de Servicios de red
- Una entidad de servicios de red proporciona servicios de la red subyacente a los CSEs


# 18-04

Solemne entre hasta HOY PPT 12 - PARTE 4

Sabado ZOOM 2 ejercicios tipo problema

calculo de ppt en inicio 
equipo 2 fuentes de poder 2 tarjeas madre y varias tarjetas de red

---
