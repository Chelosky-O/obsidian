# Red Troncal (Network Backbone) Clase 1
Parte de la infraestructura de red informática que interconecta diferentes redes, lo que les permite comunicarse entre sí, y proporciona una ruta para el intercambio de datos entre estas diferentes redes.

## Red Troncal - Point of Presence (POP)
Es la infraestructura que permite a los usuarios remotos conectarse a INTERNET.
Es un punto de acceso bien a grande escala.
### Características:
- Un POP generalmente está presente en todo proveedor de servicios de Internet (ISP) o en  
el proveedor de servicios de telecomunicaciones.  
- Puede consistir en un enrutador, conmutadores, servidores y otros dispositivos de  
comunicación de datos.  
- Un ISP o proveedor de telecomunicaciones puede mantener más de un POP en diferentes  
ubicaciones, cada uno de los cuales atiende a una base de usuarios distinta.  
- POP admite la conversión de datos analógicos a digitales y viceversa para complementar  
diferentes tecnologías de comunicación de datos y dispositivos de recepción.

---
## Red Troncal - Consideraciones
Las redes discretas tienen varias formas de «hablar» entre sí. Si tiene dos redes  
separadas, digamos entre dos ubicaciones de «Puntos de presencia» (PoP),  
pueden enviar tráfico a través de Internet pública, establecer túneles encriptados a  
través de Internet pública o conectarse a través de un circuito físico dedicado que  
solo se conecta entre ellos.

### Objetivo General:
Las redes troncales conectan redes de área local (LAN) y redes de área amplia (WAN)  
juntas. Las redes troncales de red están diseñadas para maximizar la confiabilidad y  
el rendimiento de las comunicaciones de datos a gran escala y a larga distancia.  

Las redes troncales más conocidas son las que se utilizan en Internet.

---

## ¿Cómo funciona una Red Troncal ?
- Cada PoP tiene una red local conmutada que es independiente y discreta de  
la otra.  
 - La red troncal de la red es un circuito físico que conecta los PoP discretos  
entre sí, permitiendo que la red local de un PoP se comunique con la red  
local de un segundo PoP, y viceversa.  
- La tabla de routing controla qué tráfico utiliza la red troncal de la red.

---

## Tipos de BackBone
### BackBone en serie
La red troncal en serie está formada por dos o más dispositivos que están conectados en una cadena. Es un tipo de Backbone más simple.

- Al diseñar la red troncal, se debe considerar el límite de los dispositivos que se pueden conectar a la red troncal de manera repetitiva.  
- Exceder el límite daría lugar a errores inesperados y pérdida de datos en la red.  
- Las redes troncales seriales no son muy tolerantes a fallas y no son muy escalables, lo que las hace menos utilizadas que la red troncal distribuida.

Falla 1 y chao

### Backbone distribuido
La red troncal distribuida utiliza un diseño jerárquico de la red, donde la cantidad de dispositivos intermedios están conectados a dispositivos de conectividad únicos o múltiples.

- Este tipo de red troncal es fácilmente escalable ya que se pueden agregar nuevas capas de dispositivos sin problemas.  
- La red troncal distribuida permite una administración simple de la red debido a su segregación. 
- Este tipo de red puede tener dispositivos conectados en cadena para la red troncal, sin embargo, el diseñador debe considerar las mismas limitaciones que para la red troncal serie.

En general, es barato, fácil y rápido implementar la red troncal distribuida.

falla el router y chao

### Backbone colapsada
Este tipo de red troncal utiliza un router potente y único como punto de conexión central para múltiples subredes.  
- El dispositivo central es el nivel más alto de la Backbone.  
- Debería tener una potencia computacional poderosa para administrar el tráfico entrante.  
- Solución muy arriesgada, ya que si el dispositivo central falla, toda la red estaría inactiva.  
- Sin embargo, este tipo de red troncal es útil para quien desea interconectar dos tipos de  
subredes, con la capacidad de administrarlas y solucionarlas.

### Backbone parelela
La red troncal paralela es una variación de la red troncal colapsada, donde los dispositivos tienen más de una conexión entre ellos.

- Existen múltiples conexiones entre los routers de alto nivel y los segmentos de red.  
- Las conexiones duplicadas aseguran la disponibilidad de las redes en cualquier momento, velocidades más altas y alta tolerancia a fallas.  
- El inconveniente lógico de estas soluciones es el aumento del precio, ya que la cantidad de cableado requerido aumenta considerablemente.  
- No es obligatorio tener conexiones duplicadas entre todos los dispositivos, la implementación selectiva de la estructura paralela reduciría significativamente el precio general y haría que los puertos adicionales de los dispositivos estén disponibles

---


# High Availability (Alta disponibilidad) Clase 2-4
Un sistema, componente o aplicación de TI puede funcionar a un alto nivel, de forma continua, sin intervención, durante un período de tiempo determinado.  

La infraestructura de alta disponibilidad está configurada para brindar un rendimiento de calidad y manejar diferentes cargas y fallas con un tiempo de inactividad mínimo o nulo.

## Objetivos y Beneficios
- Evitar tiempos de inactividad no planificados
- Minimizar el impacto de Fallas.  
- Mejorar la confiabilidad y la satisfacción del usuario.  
- Mantener la continuidad del negocio.  

La infraestructura de alta disponibilidad está configurada para brindar un rendimiento de calidad y manejar diferentes cargas y fallas con un tiempo de inactividad mínimo o nulo.

## Clasificación de fallas
Los Fallas son situaciones no deseadas que pueden ocurrir en un sistema y afectar su funcionamiento normal. La clasificación de Fallas es importante para identificar los tipos de problemas que pueden surgir y para implementar estrategias de alta disponibilidad adecuadas. A continuación, se describen algunos tipos de Fallas comunes:  


### 1. Fallas de Hardware:  
- **Fallo de Disco Duro:** Un disco duro defectuoso puede provocar la pérdida de datos y afectar la operación del sistema. La redundancia, como la configuración RAID, puede ayudar a mitigar este tipo de fallo.  
- **Fallo de Memoria:** La pérdida o corrupción de datos en la memoria RAM puede causar bloqueos del sistema o errores en la ejecución de programas. La redundancia de memoria y la detección de errores son enfoques para abordar este tipo de fallo.

### 2. Fallas de Software:
- **Errores de Aplicación:** Los errores en el código de las aplicaciones pueden provocar bloqueos o un comportamiento impredecible. La implementación de pruebas exhaustivas y el monitoreo constante pueden ayudar a detectar y mitigar estos fallos.
- **Parches y Actualizaciones defectuosas:** La instalación de parches o actualizaciones de software incorrectos puede causar conflictos y fallos en el sistema. Las políticas de gestión de cambios y las pruebas rigurosas son fundamentales para evitar estos problemas.

### 3. Fallas de Red:
- **Fallo del Enlace de Red:** La desconexión de un enlace de red puede aislar una parte del sistema y afectar la conectividad. La configuración de enlaces redundantes y la conmutación por error pueden ayudar a mantener la conectividad en caso de fallo de un enlace.  
- **Congestión de la Red:** Un exceso de tráfico puede sobrecargar la red y afectar la latencia o la disponibilidad de los servicios. El balanceo de carga y la expansión de la capacidad de red pueden abordar este tipo de problema.

### 3. Fallas Humanas:
- **Errores de configuración:** Configuraciones incorrectas o cambios mal realizados pueden provocar fallas en el sistema. La automatización de la configuración y las revisiones rigurosas pueden ayudar a prevenir estos errores.
- **Accidentes Operativos:** Acciones humanas accidentales, como eliminar archivos críticos, pueden causar interrupciones en los servicios. Las copias de seguridad regulares y la formación adecuada del personal son importantes para mitigar estos riesgos.

### Solución:
La redundancia, la detección automática de Fallas, la conmutación por error, las pruebas de  recuperación y otras técnicas son esenciales para garantizar que los servicios sigan funcionando incluso cuando ocurran fallas.



## Arquitecturas de Alta Disponibilidad

### 1. Clustering (Agrupación o Clústeres):
#### Definición:
Un clúster es un grupo de dos o más servidores o nodos que trabajan juntos como una sola entidad. Se distribuye la carga de trabajo entre los nodos y, si uno de ellos falla, los demás pueden asumir la carga.  
#### Tipos de Clústeres:
Clústeres activo-activo (todos los nodos comparten la carga) y clústeres activo-pasivo (un nodo principal maneja la carga y un nodo secundario toma el control si el principal falla).
#### Ejemplo: 
Clúster de bases de datos en el que varios nodos almacenan los mismos datos y mantienen la coherencia para garantizar la disponibilidad de la base de datos.

Configura base de datos para que sea un espejo de la otra. Importa la geografia.
### 2. Replicación:  
#### Definición:
La replicación implica la creación de copias idénticas de datos o servicios en diferentes ubicaciones. Si  una copia falla, las otras pueden continuar proporcionando el servicio.  
#### Tipos de Replicación:
Replicación síncrona (los datos se replican en tiempo real) y replicación asíncrona (los datos se  
replican en intervalos).  
#### Ejemplo:
Replicación de bases de datos en tiempo real entre un servidor principal y un servidor secundario para garantizar la disponibilidad y la recuperación en caso de fallo.

Son 2 bases de datos descontextualizados, donde mediante un script , toda las transacciones hechas en 1 se repiten en la replica.

Ventajas: Datos iguales en primario y secundario
Debilidades: Fuerte impacto en rendimiento, Escrituras penalizadas por la latencia, latencia afecta al commit.

### 3. Balanceo de Carga:
#### Definición: 
Distribuye el tráfico de red y la carga de trabajo entre varios servidores para evitar sobrecargas  
en un solo punto y mejorar el rendimiento.
#### Algoritmos de Balanceo de Carga:
Round-robin, balanceo ponderado, basado en la carga, basado en la geolocalización, entre otros.

- Balanceo Ponderado: Dependiendo de la conexión se selecciona, se pondera o asigna mas pega a servidor con mayor ancho de banda y proporcionalmente al que tiene menos.
- Basado en la carga: Servidores cdn, por carga de cada servidor.
- Basado en geolocalización: Selecciona por cercanía geográfica.

#### Ejemplo:
Un servidor de aplicaciones que distribuye las solicitudes de los usuarios entre varios servidores backend para garantizar una distribución equitativa de la carga.

Códigos http 400 error, 500 error servidor, 200 ok, 300 redirección.

### 4. Conmutación por Error (Failover) y Conmutación por Recuperación (Failback):

#### Definición:  
• La conmutación por error implica cambiar automáticamente a un recurso de respaldo cuando el recurso principal falla.  
• La conmutación por recuperación implica volver al recurso principal una vez que se ha  
recuperado.  
#### Ejemplo:
Un servidor web que cambia automáticamente a un servidor de respaldo si el servidor principal se vuelve inaccesible.

### 5. División de Zona y Geoclusterización
#### Definición:
Divide los sistemas en zonas geográficas separadas y aisladas para evitar que un desastre local afecte a todas las áreas.
#### Ejemplo:
Distribución de servidores en diferentes centros de datos para evitar interrupciones en caso de un desastre en una ubicación.
### 6. Virtualización y Contenedores
#### Definición: 
La virtualización y los contenedores permiten ejecutar múltiples instancias de sistemas operativos y aplicaciones en una sola máquina física, lo que puede mejorar la utilización de recursos y facilitar la migración y recuperación en caso de fallos.

---

Estas arquitecturas y estrategias pueden combinarse y adaptarse según las necesidades específicas de un sistema o servicio. La elección de la arquitectura de alta disponibilidad adecuada dependerá de varios factores, como la criticidad del servicio, el presupuesto, la complejidad y las restricciones técnicas.

## High availability versus IT disaster recovery
- Los sistemas y servicios de TI de alta disponibilidad están diseñados para estar disponibles el 99,999 % del tiempo durante las interrupciones planificadas y no planificadas. Conocido como confiabilidad de cinco nueves, el sistema está esencialmente siempre encendido.
- Si la infraestructura de TI crítica falla, pero es compatible con una arquitectura de alta disponibilidad, el sistema o componente de respaldo se hace cargo.
- Esto permite que los usuarios y las aplicaciones sigan trabajando sin interrupciones y accedan a los mismos datos disponibles antes de que ocurriera la falla.

La recuperación ante desastres de TI se refiere a las políticas, herramientas y procedimientos que las organizaciones de TI deben adoptar para que los componentes y servicios de TI críticos vuelvan a estar en línea después de una catástrofe. Un ejemplo de un desastre de TI es la destrucción de un centro de datos debido a un evento natural como un gran terremoto.

High Availability  
Piense en la alta disponibilidad como una estrategia para administrar fallas pequeñas pero críticas en los componentes de la infraestructura de TI que se pueden restaurar fácilmente.

VS

IT Disaster Recovery  
La recuperación ante desastres de TI es un proceso para superar eventos importantes que pueden dejar de lado infraestructuras de TI completas.

## Resumen de Elementos de una infraestructura de HA

### Redundancia
- La infraestructura de TI de alta disponibilidad cuenta con redundancia de hardware, redundancia de software y aplicaciones, y redundancia de datos. Redundancia significa que los componentes de TI en un clúster de alta disponibilidad, como servidores o bases de datos, pueden realizar las mismas tareas.  
- La redundancia también es esencial para la tolerancia a fallas, que complementa la alta disponibilidad y la recuperación ante desastres de TI.

### Replicación
- La replicación de datos es esencial para lograr una alta disponibilidad. Los datos deben replicarse y compartirse con los mismos nodos en un clúster. Los nodos deben comunicarse entre sí y compartir la misma información, de modo que cualquiera de ellos pueda intervenir para brindar un servicio óptimo cuando falla el servidor o el dispositivo de red al que están dando soporte.  
- Los datos también se pueden replicar entre clústeres para ayudar a garantizar tanto la alta disponibilidad como la continuidad del negocio en caso de que falle un centro de datos.

### Failover
- Una conmutación por error ocurre cuando un proceso realizado por el componente principal fallido se mueve a un componente de respaldo en un clúster de alta disponibilidad. Una mejor práctica para la alta disponibilidad y la recuperación ante desastres es mantener un sistema de conmutación por error que esté ubicado fuera de las instalaciones.  
- Los administradores de TI que supervisan el estado de los sistemas primarios críticos pueden cambiar rápidamente el tráfico al sistema de conmutación por error cuando los sistemas primarios se sobrecargan o fallan.
### Fault Tolerance
- La tolerancia a fallas tiene como objetivo el tiempo de inactividad cero, mientras que la alta disponibilidad se enfoca en brindar un tiempo de inactividad mínimo.  
- Un sistema de alta disponibilidad diseñado para proporcionar un tiempo de actividad operativo del 99,999 %, o cinco nueves, espera ver 5,26 minutos de tiempo de inactividad al año.  
- A diferencia de la alta disponibilidad, la entrega de un rendimiento de alta calidad no es una prioridad para la tolerancia a fallas. El propósito del diseño de tolerancia a fallas en la infraestructura de TI es evitar que una aplicación de misión crítica experimente tiempo de inactividad.  
- Es un enfoque más costoso para garantizar el tiempo de actividad que la alta disponibilidad porque puede implicar la copia de seguridad de sistemas completos de hardware y software y fuentes de alimentación. Los sistemas de alta disponibilidad no requieren la replicación de componentes físicos.

## Descripción de métricas de sistemas de HA
Hay dos formas principales de establecer la disponibilidad de una red:  
El método porcentual y el método de defectos por millón.

Ambos métodos utilizan métricas como :
MTBF (Mean Time Between Failure = Tiempo medio entre fallas) y
MTTR (Mean Time To Repair -  Tiempo medio de reparación).

### Método porcentual
En análisis previos se mencionó el término cinco 9 en relación con la disponibilidad de una red. Esto significa que el dispositivo o la red están disponibles en un 99,999 por ciento del tiempo. 

El uso esencial del porcentaje de disponibilidad es calcular cuánto tiempo de inactividad tendrá durante un período de un año.  

El **tiempo de inactividad** se determina multiplicando la cantidad de minutos en un año por el porcentaje de disponibilidad. Esto le da los minutos por año que estará operativo. 
El saldo es el tiempo de inactividad que puede esperar.

#### Métricas que se ocupan
Generalmente se toman las siguientes referencias de tiempo:

- 365 días al año, 24 horas por día y 60 minutos a la hora.  
- Hay 525.600 minutos al año. Sin embargo, esto no tiene en cuenta los años bisiestos.  
- Para tomar en cuenta el día extra se agrega un cuarto de un día a cada año. Esto da como resultado **525.960 minutos por año**, que es el número que se utiliza en todos los cálculos.  

**Definición: Confiabilidad Anual** → La confiabilidad anual es la cantidad de veces al año que un dispositivo falla.  

Cuando conoce el MTBF de un dispositivo, puede dividir ese MTBF por la **cantidad de horas en un año (8766)** para predecir la cantidad promedio de fallas por año.

Number of 9s; Uptime and Downtime:

| Number of Nines | Availability Percentage | Minutes of Uptime per Year (Percentage * 525,960) | Minutes of Downtime per Year (525,960 - Uptime) | Annual Downtime |
| --------------- | ----------------------- | ------------------------------------------------- | ----------------------------------------------- | --------------- |
| 1               | 90.000%                 | 473,364                                           | 52,596                                          | 36.5 days       |
| 2               | 99.000%                 | 520,700.4                                         | 5259.6                                          | 3.5 days        |
| 3               | 99.900%                 | 525,434.0                                         | 525.96                                          | 8.5 hours       |
| 4               | 99.990%                 | 525,907.4                                         | 52.596                                          | 1 hour          |
| 5               | 99.999%                 | 525,954.7                                         | 5.2596                                          | 5 minutes       |
| 6               | 99.9999%                | 525,959.5                                         | 0.5296                                          | 32 seconds      |

---
### Método de defectos por millón (DPM)

- Describe la cantidad de fallas que han ocurrido durante un millón de horas de funcionamiento de un dispositivo o una red.  
- Es común ver este método utilizado para grandes redes existentes.  
- Con el método DPM, podemos informar problemas de confiabilidad que el método de porcentaje tendría dificultades para rastrear.  
- Debido a que DPM se usa a menudo para redes existentes, podemos usarlo para medir interrupciones parciales y completas de la red.  
- También podemos medir el millón de horas en términos de horas de operación de la red, las horas de operación de los dispositivos (sumados) que componen la red, o quizás incluso las horas de uso que los usuarios obtienen de la red.

#### Ejemplo 1 DPM:
Una red consta de 1000 concentradores (hubs), Switches y Routers. Suponga que cuenta cualquier degradación en el rendimiento como una interrupción. Suponga también que se basa el cálculo en 8766 horas al año (teniendo en cuenta los años bisiestos) y se sabe que el informes de errores se realiza mensualmente y para un mes específico se reportaron 2 fallas.

##### Solución:
$Ha = 8766$
$N = 1000$
$Ha\_totales = Ha \cdot N = 8766 \cdot 1000 = 8.766.000\ horas$ (Para todos los dispositivos)
$Horas\_acum\_mes = \frac{Ha\_totales}{12} = \frac{8.766.000}{12} = 730.500\ horas$
Cálculo del DPM = $(\frac{1.000.000}{Horas\_acum\_mes})\cdot Nfallas = (\frac{1.000.000}{730.500})\cdot 2 = 2.74\ DMP$

#### Ejemplo 2 DPM:
Otra forma de informar fallas con el método DPM sería basar el millón de horas en el uso de la red. Supongamos que nuestra red es grande y está en constante crecimiento. Supongamos también que facturamos a nuestros clientes por cada hora que utilizan la red. Digamos que tenemos varios miles de clientes y que a lo largo de un mes acumulan 1.200.000 horas de funcionamiento. En esta red, si tuviéramos dos fallas, entonces el DPM resultante sería:

##### Solución:
$Total\_horas\_operación = 1.200.000$
$Nfallas = 2$
Cálculo del DPM = $(\frac{1.000.000}{Total\_horas\_operación})\cdot Nfallas = (\frac{1.000.000}{1.200.000})\cdot 2 = 1.67\ DMP$

## MTBF, MTTR y Disponibilidad

- **MTBF (Mean Time Between Failure = Tiempo medio entre fallas):** Describe el número de horas entre fallas para un dispositivo particular.  
- **MTTF (Mean Time to Failure = Tiempo medio hasta el fallo):** Describe la cantidad de tiempo desde que se pone en servicio un dispositivo hasta que falla.  
- **MTTR (Mean Time To Repair):** Es la cantidad de tiempo (en promedio) que transcurre entre la falla de una red y la restauración de la red para que funcione correctamente. En la mayoría de los casos, MTTR incluye tiempos  
	para:  
	-  notar que la red ha fallado.  
	-  diagnosticar el problema.  
	-  realizar la acción apropiada para arreglar la falla  
	-  ejecutar las reparaciones adicionales para que la red funcione correctamente.

- El punto clave aquí es recordar que hay tres fases para solucionar un problema de red:
	- Detección  
	- Diagnóstico  
	- Reparación
- Puede calcular el porcentaje de disponibilidad directamente si tiene los números MTBF y MTTR para un dispositivo en particular, como se muestra a continuación:

$$Disponibilidad = \frac{MTBF}{MTBF + MTTR}$$

#### Ejemplo:
Supongamos que un dispositivo cuya disponibilidad queremos medir tiene un MTTF de 200.000 horas. Supongamos también que tiene un MTTR de seis horas. Supongamos además que el MTBF sería de 200.006 horas.

##### Solución:
$$Disponibilidad = \frac{MTBF}{MTBF + MTTR}$$

$Disponibilidad = \frac{200.006}{200.006 + 6} = 0,99997$ (usando el MTBF como corresponde)
$Disponibilidad = \frac{200.000}{200.000 + 6} = 0,99997$ (usando el MTTF como MTBF)

----
## Conversión entre método de porcentaje y DPM
- Conocidos el MTBF y el MTTR, es posible convertir entre los métodos de porcentaje y DPM.  
- Dado que la disponibilidad es un porcentaje y DPM no lo es, necesitamos MTTR para realizar la conversión.  
- El MTBF ayudará porque lo usamos para llegar al número de porcentaje de disponibilidad.

#### Ejemplo:
Supongamos que tenemos una red donde todos los routers y switches tienen el mismo MTBF de 200.000 horas. El MTTR para estos dispositivos es de seis horas porque un contrato de soporte garantiza el reemplazo de cualquier dispositivo defectuoso en seis horas o menos.

##### Solución:
- Usando la ecuación de disponibilidad, podemos llegar fácilmente a la misma respuesta que obtuvimos para estas cifras en la sección anterior: una disponibilidad del 99,997 por ciento.  
- Si tomamos el 99,997 % y lo multiplicamos por la cantidad de minutos en un año, obtenemos la respuesta:

$Tiempo\_inactividad\_dispositivo = (1-0,99997)\cdot8776\cdot60=15,79\ minutos$ (al año)

$DPM=\frac{1.000.000}{MTBF}=\frac{1.000.000}{200.000}=5$

Downtime(por millón de horas) = $DPM\cdot MTTR=5\cdot 6=30$$

Fallas(por año) = $\frac{8766}{1.000.000}=0,008766$


Downtime(por año) = $Fallas(por\ año)\cdot Downtime(por\ millón\ de\ horas)$
Downtime(por año) = $0,008766\cdot30=0,26\ horas = 15,79\ minutos$

---

## Calculo de la disponibilidad en arquitecturas de red Clase 

## Disponibilidad de componentes múltiples
Para calcular la disponibilidad de varios componentes, se requiere definir los siguientes términos:  
- **Disponibilidad Serial:** En un sistema en serie, si algún componente falla, todo el sistema falla. Por ejemplo, si un producto consta de una fuente de alimentación y una placa de circuito, tiene un sistema en serie. Si falla la fuente de alimentación, entonces falla el sistema, y si falla la placa de circuito única, entonces falla el sistema.

$$SerialAvailability = \prod_{i=1}^{n} ComponentAvailability_i$$

i: Número que identifica un componente especifico
n: Número total de componentes

- **Disponibilidad Paralela:** Cuando los componentes de un sistema están en  paralelo o son redundantes. Aunque hay varios diseños paralelos diferentes, a continuación se muestra una ecuación paralela básica. Esta ecuación se aplica a la situación en la que dos dispositivos están en paralelo entre sí.

$$ParallelAvailability = 1 - [\prod_{i=1}^{n} (1-ComponentAvailability_i)]$$

i: Número que identifica un componente especifico
n: Número total de componentes

  
- En un sistema paralelo, se combinan dos o más componentes de manera que el sistema funcionará mientras cualquiera de los componentes paralelos siga funcionando.  
- Si tiene dos componentes paralelos y uno de ellos falla, el sistema continúa (o al menos debería continuar) ejecutándose sin fallas.  
- La mayoría de los sistemas que incluyen componentes paralelos también incluyen componentes en serie.

### Ejemplo Disponibilidad Serial:
Se tiene un sistema que consta de una tarjeta madre y una fuente de poder. Sus disponibilidades son 99.994% y 99.999% respectivamente. ¿Cuál es la disponibilidad del sistema en conjunto?

$$SerialAvailability = \prod_{i=1}^{n} ComponentAvailability_i$$
$Disponibilidad\_Sistema=0.99994\cdot0.99999=0.99993$


### Ejemplo Disponibilidad Paralela Simple:
Suponga que tiene un sistema y que dentro del sistema hay dos componentes en paralelo. Los dos componentes son idénticos y ambos tienen una disponibilidad del 99,9%.

$$ParallelAvailability = 1 - [\prod_{i=1}^{n} (1-ComponentAvailability_i)]$$
$Disponibilidad\_Sistema=1-[(1-0.999)(1-0.999)]=0.999999$

---
- **Disponibilidad Paralela N+1**
	- Hemos discutido cómo calcular la disponibilidad cuando los dispositivos están en arreglos paralelos simples.  
	- En otras palabras, si tenemos cualquier cantidad de dispositivos en paralelo, ahora sabemos cómo calcular la disponibilidad siempre que un solo dispositivo permanezca operativo.  
	- Este método se implementa con mayor frecuencia en la vida real al tener dos dispositivos cuando solo necesita uno.
	- Un ejemplo es cuando necesitamos al menos dos fuentes de alimentación en un router grande para suministrar suficiente energía.  
	- En esa situación, podríamos optar por tener una sola fuente de alimentación de respaldo en lugar de dos fuentes de alimentación de respaldo.

Generalizando:
- Este método de redundancia se llama N + M.
- N representa el número requerido y M representa el número instalado

---
### Ejemplo Disponibilidad Serial/Paralela:
Considere un sistema que tiene una tarjeta madre y dos fuentes de alimentación  
redundantes. La tarjeta madre está disponible en un 99,994 por ciento y cada  
una de las fuentes de alimentación está disponible en un 99,95 por ciento.

#### Solución:
En estos casos, aplique los criterios aprendidos en la teoría de circuitos sobre series y paralelos y el respectivo orden a ser resueltas.

- Paso 1: Cálculo del paralelo de las fuentes
$Disp\_fuentes=1-[(1-0.9995)(1-0.9995)]=0.99999975$

- Paso 2: Cálculo de la serie entre la tarjeta madre y las fuentes redundantes
$Disponibilidad\_sistema=0.99994\cdot0.99999975)=0.99993975$

---
## Diagramas de bloques de confiabilidad para el análisis de rutas
Para realizar un análisis de ruta, suele ser una buena idea crear un diagrama de bloques de disponibilidad.

Por ahora, consideraremos un ejemplo muy simple de conexión en red, usando un enrutador grande con componentes que no son cruciales para nuestros cálculos.

Necesitamos eliminarlos de nuestros cálculos y realizar el análisis de disponibilidad para algo que nos importa. En la figura, un dispositivo de red grande está conectado a tres redes.

[![Foo](https://i.imgur.com/xZrTojl.png)]

Solo queremos saber la disponibilidad de la Red 1 a la Red 2. Por lo tanto, el hardware que admite la conexión a la Red 3 puede eliminarse de nuestros cálculos.

Como puede ver en la figura, nuestro dispositivo incluye dos fuentes de alimentación redundantes denominadas Power 1 y Power 2.

Se requieren varios pasos para calcular la disponibilidad de un dispositivo (o red) que tiene  
componentes paralelos y seriales.  
En este caso nuestros pasos son:  
- Paso 1: Determinar la disponibilidad de cada componente  
- Paso 2: Calcule la disponibilidad de las fuentes de alimentación duales.  
- Paso 3: Multiplique la disponibilidad de todos los componentes con el resultado del Paso 2.

#### Ejemplo

[![Foo](https://i.imgur.com/xZrTojl.png)]

Disp_fuentes = 99.9%
Disp_MainBoard = 99.994%  
Disp_Interface_cards = 99.95%

##### Solución
- Paso 1:
$Disp\_power = 1-[(1-0.999)(1-0.999)] = 0.999999$

- Paso 2:
$Disp\_sistema = 0.999999 \cdot 0.99994 \cdot 0.9995 \cdot 0.9995$
$Disp\_sistema = 0.998939$ → 99.8939%

# Arquitecturas IOT Clase 6-12

## Arquitecturas y Estándares

### Desafíos de IOT

- **Escala:
	- Una red típica soporta del orden de miles de nodos
	- Una red IoT debe soportar millones de dispositivos
- **Datos/Analítica:
	- Generación de un diluvio de datos de diferentes fuentes de información.
	- Debe manejarse o administrarse de manera eficiente.
	- Datos proveen información crítica y hallazgos importantes.
- **Privacidad**
	- El uso de dispositivos IoT es cada vez más masivo.
	- Capturan y recolectan datos asociados a individuos y a sus actividades o comportamientos.
- **Inter-Operabilidad**
	- Proceso de estandarización de protocolos y arquitecturas.
	- Basados en tecnología abierta y/o propietaria.
	- Incorporar sistemas o dispositivos heredados (legacy).
- **Seguridad**
	- Riesgo transversal a todo nivel de una red IoT
	- Dispositivos o nodos están físicamente expuestos.

### oneM2M
Es un proyecto de Asociación entre 8 Organizaciones líderes de Desarrollo de Estándares:

- ICT (CCSA China Communications Standards Association)
- TTA (Telecommunications Technology Association) 
- ARIB (Association of Radio Industries and Business) 
- TTC (Telecommunication Technology Committee of Japan) 
- ETSI (European Telecommunications Standards Institute) 
- ATIS (Alliance for Telecommunications Industry Solutions) 
- TIA (Telecommunications Industry Association) 
- TSDSI (India)
Se han unido para lanzar una nueva organización para asegurar el despliegue de sistemas de comunicación M2M de una manera más eficiente.

El objetivo de la organización es crear un estándar técnico global para la interoperabilidad con respecto a la arquitectura, las especificaciones de API y la seguridad para las tecnologías de máquina a máquina e IoT en función de los requisitos aportados por sus miembros.

#### Arquitectura de oneM2M
El modelo arquitectónico de oneM2M consiste en un modelo de 3 capas:
- Aplicación 
	- Representa la lógica del servicio de aplicación.
	- Cada lógica de servicio de aplicación puede residir en varios nodos y/o más de una vez en un solo nodo.
- Servicios Comunes
	- Representa la instancia de un conjunto de Funciones de Servicios Comunes (CSF).
	- Un CSE es en realidad la entidad que contiene la colección de funciones de servicio comunes especificadas por oneM2M que los AE pueden usar.
- Servicios de Red
	- Una entidad de Servicios de red proporciona servicios de la red subyacente a los CSEs.

### Paradigma de Silos
- Mercado muy fragmentado con aplicaciones específicas de proveedores limitadas 
- Reinventando la rueda: los mismos servicios desarrollados una y otra vez 
- Cada silo contiene sus propias tecnologías sin interoperabilidad

### Capa de Servicio M2M
- Plataforma de extremo a extremo: capa de capacidades de servicio común o common service capabilities layer (CSCL) 
- Interoperabilidad a nivel de intercambios de datos y control a través de API estándar 
- Interacción perfecta entre aplicaciones y dispositivos heterogéneos

Middleware que permite el intercambio seguro de datos de extremo a extremo entre dispositivos M2M y aplicaciones de clientes, al proporcionar funciones para el aprovisionamiento y activación remotos, autenticación, cifrado, configuración de conectividad, almacenamiento en búfer, sincronización, agregación y administración de dispositivos.

- Es una capa de software 
- Se encuentra entre las aplicaciones M2M y la comunicación HW/SW que proporciona transporte de datos 
- Normalmente se monta sobre IP 
- Proporciona funciones que las aplicaciones M2M en diferentes segmentos de la industria comúnmente necesitan capa horizontal

---
### Arquitecturas IOT

- OneM2M
- IoT World Forum
- Industrial Internet Reference Architecture
- Microsoft Azure
- Amazon Web Services
- Google Cloud Platform
- IBM

## Arquitectura IoT Simplificada

- Existen diferencias considerables entre cada modelo, a veces orientadas a la industria donde son implementadas. 
- Todos tienen un enfoque basado en capas. 
- Permite el desarrollo de tecnologías y estándares de manera independiente entre niveles o dominios. 
- Interconexión de dispositivos o nodos a una red de transporte de datos que son utilizados por aplicaciones. 
- Procesamiento o computación distribuida en las capas.}

### Objetivo:

- Definición de bloques constructivos que sean:
	- Fundamentales.
	- Comunes entre distintas arquitecturas de referencia.
	- Asistan al diseño de una red IoT.
	- Agnósticos a la industria objetivo.

### IoT Stacks o Pilas
[![Foo](https://i.imgur.com/w6p25lk.png)]

#### Capa Cosas:
● Compuesta por objetos o cosas que necesitan ser conectadas. 
● Variedad de objetos conectados o inteligentes según forma, necesidades influyen en el diseño de una arquitectura. 
● Dispositivos físicos requieren cumplir con las restricciones del entorno donde operan y del objeto o cosa a la cual están asociados

##### Clasificación de Cosas
● Suministro de energía: batería o externa. 
● Movilidad: móvil o estática. 
● Reportabilidad: baja o alta frecuencia. 
● Datos: simple o complejo, una variable o muchas variables. 
● Rango de reportabilidad: distancia entre el objeto y el gateway de comunicación. 
● Densidad: cantidad de objetos en un área común

#### Capa Red de Comunicaciones:
- Subcapa de acceso a la red: se clasifican según el rango entre el objeto y el colector de datos
	- PAN (personal area network): rango de los metros, espacio alrededor de una persona. Bluetooth.
	- HAN (home area network): decenas de metros. ZigBee, Bluetooth Low Energy (BLE).
	- NAN (neighborhood area network): cientos de metros. Grupo de casas.
- Subcapa de acceso a la red: se clasifican según el rango entre el objeto y el colector de datos
	- FAN (field area network): rango de las decenas a cientos de metros, espacio abierto. WirelessHart.
	- LAN (local area network): hasta 100 metros. Ethernet, IEEE 802.11 (WiFi). 
	- WAN (wide area network): orden de kilómetros. LTE, NB-IoT, LPWA.
- Topología: se clasifican según la estructura de conectividad entre el objeto y el colector de datos.
	- Punto a punto
	- Punto a multipunto}

#### Capa Aplicaciones y Analítica
- Aplicación de Analítica
	- Recopila datos de múltiples objetos, procesa la data y visualiza la información resultante.
	- Reportes históricos, estadísticas, tendencia de un sistema, etc.
	- Aspecto relevante es que esta aplicación entrega una vista de la red que no se puede obtener considerando la información de un solo objeto inteligente.
- Aplicación de Control
	- Controla el comportamiento de un objeto u otro objeto relacionado con el mismo. Ejemplo, controlar la velocidad de una bomba.
	- Responde a los cambios de parámetros de la red, configuraciones o comportamientos.
	- Aspecto relevante es que esta aplicación permite controlar una red IoT compleja cuya lógica no puede programarse en un solo dispositivo u objeto.

---

### Modelo tradicional red TI

- Modelo cliente / servidor.
- Endpoints: laptops, impresoras, teléfonos IP, teléfonos inteligentes, etc.
- Acceso a la red de alto ancho de banda.
- Datos son almacenados en el data center o cloud.

### Cloud Computing: “la nube”
- Modelo cloud es simple.
- Objetos se conectan a la nube y el procesamiento es centralizado.
- Dispositivos IoT son considerados restringidos (constrained devices):
	- Baja capacidad de procesamiento (CPU).
	- Memoria limitada (RAM/ROM/FLASH).
	- Bajo consumo de energía
#### Modelo red IoT: Cloud Computing
Qué pasa cuando se requiere un análisis de condiciones críticas:
- Latencia: en sistemas industriales se requiere una respuesta del orden de los milisegundos. 
- Ancho de banda: no es práctico enviar data de miles de dispositivos a la nube. 
- Eficiencia local: no es útil recolectar y almacenar data entre condiciones ambientales muy diferentes

### Edge Computing: “el borde"
- Nuevos dispositivos IoT no son tan “limitados”.
- Capacidad de procesamiento permite:
	- Analítica de bajo nivel. 
	- Filtrar los datos localmente. 
	- Tomar decisiones básicas.
- Se trasladan las aplicaciones de analítica y/o control al objeto mismo: entorno local.
#### Beneficios:
- Tiempo de respuesta mucho más rápido.
- Operación más confiable ante intermitencias de la red de comunicaciones.
- Optimización de conectividad: alivio del ancho de banda.
- Solución más económica.
- Aumento de seguridad y privacidad: data es manejada localmente.

### Fog Computing: “la niebla”
Estructura de red descentralizada en la que los recursos, incluyendo datos y aplicaciones, se sitúan en algún lugar lógico entre la nube y la fuente que genera los datos.

#### Beneficios:
- Crear una red con menor latencia y con menor carga de datos hacia la Nube. 
- Genera una “conciencia de contexto” de los dispositivos que gestiona debido a la proximidad geográfica. 
- Capacidad de filtrar los datos hacia la nube. 
- Distribución geográfica de servicios y aplicaciones, la nube es centralizada. 
- Interacciones a tiempo real entre dispositivos.
---
### Modelo Cliente/Servidor
● Modelo de diseño de software. 
● Tareas distribuidas: 
	○ Servidores: proveedores de recursos y/o servicios. 
	○ Clientes: demandantes. 
● Cliente inicia solicitudes o peticiones, tiene un papel activo en la comunicación (dispositivo maestro). 
● Servidor al iniciarse espera a que lleguen las solicitudes de los clientes, desempeña un papel pasivo en la comunicación (dispositivo esclavo).

Ejemplo Cliente / Servidor SMTP

### API (Application Programming Interface)

● Interfaz de Programación de Aplicaciones. 
● Mecanismo que permite a dos componentes de software comunicarse entre sí. 
● Se utiliza un conjunto de definiciones y protocolos comunes. 
● La arquitectura de las API suele explicarse en términos de cliente y servidor. 
● Tipos de API: 
	○ SOAP: protocolo simple de acceso a objetos. 
	○ RPC: llamadas a procedimientos remotos. 
	○ WebSocket: comunicación bidireccional entre las aplicaciones cliente y el servidor (sesión interactiva).

### API REST

● REST significa Transferencia de Estado Representacional. 
● REST define un conjunto de funciones para acceder a los datos del servidor: 
	○ GET, POST, PUT, DELETE, etc. 
● Clientes y los servidores intercambian datos mediante HTTP distintos formatos: 
	○ HTML, XML, texto sin formato y JSON. 
● Principal característica es la ausencia de estado, los servidores no guardan datos del cliente entre las solicitudes.

#### Beneficios:
● Integración 
	○ Nuevas aplicaciones utilizando servicios existentes. 
● Innovación 
	○ Implementaciones más rápidas. 
● Ampliación 
	○ Soporte multiplataforma: web, Android, iOS, etc. 
● Mantenimiento 
	○ Cambios internos de una API no afectará a la otra.

### Postman

● Herramienta que permite crear peticiones sobre APIs de una forma muy sencilla: 
	○ Probar las APIs. 
● Crear Peticiones. 
● Definir Colecciones. 
● Entorno Colaborativo. 
● Gestionar la Documentación. 
● Crear mockups de Servidores.

### Webhooks
• En el desarrollo web tradicional, un botón activa una acción. 
• Para lograr esto, se programa un “escuchador” del botón, que maneja eventos: 
```
handler(event):
	print(“Apretaste el botón”)
```
• Esto se conoce como “programación basada en eventos” (event-driven programming)

Pero ¿qué pasa si no hay nadie que presione el botón?

• Una forma – ineficiente - es hacer un código que esté continuamente consultando si el botón ha sido presionado (“polling”). 
• Otra forma – más eficiente – es lograr que la porción de código se ejecute “cuando corresponda” (eventos basados en ciclos de vida). 
• Esto también se conoce como “inversión del control” o “Hollywood Principle” 
• Y para esto se utilizan los Webhooks

#### Definición:
• Callbacks HTTP definidos por el usuario, que se disparan automáticamente ante la ocurrencia de eventos predefinidos (triggers). 
• Cuando ocurre un trigger, el webhook: 
	• Capta el evento 
	• Captura los datos asociados al evento. 
	• Envía la data a las URL especificadas en formato HTTP Request. También pueden especificarse acciones.

#### Eventos soportados 
• Delivered: Datos entregados. 
• Dropped: Trigger cancelado o interrumpido (o alguna condición incompleta) 
• Invalid: Proceso inválido 
• Bounced: Data “rebotó” (p.e. por problemas de conectividad u otro error) 
• Opened: Data abierta/consumida. 
• Unsubscribed: Cancelación de suscripción (por ejemplo, de un tópico) 
• Abused: Warning de detección de uso malicioso de un webhook (por ejemplo, con payloads muy altos, o con triggers muy frecuentes, u otra condición de riesgo)

---

## Contexto de seguridad IoT
● Objetos que se han ido IoTizando: 
	○ Refrigerador smart Linux-embedded 
	○ Lavadoras conectadas 
	○ Automóviles 
	○ Dispositivos médicos implantables 
	○ Sistemas robóticos de fábricas 
	○ etc 
● Históricamente, muchas de estas industrias nunca tuvieron que preocuparse por la seguridad. 
● Con nuevos productos y características comercializables, se encuentran en un territorio peligroso, sin saber cómo desarrollar, implementar y operar de manera segura.
## Ciberseguridad vs Seguridad IoT
● Recordemos que un dispositivo IoT: 
	○ Conectado directa o indirectamente a Internet. 
	○ Monitorea y/o manipula objetos físicos. 
● Seguridad en IoT es una fusión de ciberseguridad tradicional con otras disciplinas de la ingeniería. 
● Ciberseguridad se preocupa de la data, servidores, infraestructura de red y seguridad de la información. 
● Seguridad IoT además incluye el monitoreo y/o control directo o distribuido del estado de sistemas físicos conectados vía Internet.

## Conceptos Seguridad IoT
● Exploit 
	○ Cualquier ataque que aprovecha vulnerabilidades en aplicaciones, redes, sistemas operativos o hardware. Generalmente son códigos que tienen como objetivo tomar el control de las computadoras o robar datos de la red.
● Threats 
	○ La amenaza es el potencial para que se lleve a cabo el daño, o más generalmente representa el potencial de explotación.
● Vulnerability 
	○ Vulnerabilidad es el término que usamos para identificar una debilidad, ya sea en el diseño, integración u operación de un sistema o dispositivo. Las vulnerabilidades están siempre presentes y se descubren todos los días. 
● Risks 
	○ El riesgo es la exposición a la pérdida de confidencialidad, integridad o disponibilidad de información, datos o sistemas de información (o control) y reflejan los posibles impactos adversos en las operaciones de la organización.

## Relaciones entre conceptos

Threat → Vulnerability → Attack → Compromise

## Ataques IoT

● Radio frequency Jamming 
	○ Interferir las señales de radio con el objetivo que los dispositivos IoT se comuniquen. 
	○ Jammer celular, WiFi, GPS, etc. 
● Mapeo y reconocimiento inalámbrico 
	○ Similar al escaneo de redes con herramientas como Nmap para recopilar información sobre hosts, subredes, puertos y protocolos en las redes. 
	○ CatSniffer: objetivo son dispositivos IoT, cosas que pueden abrir la puerta del garage, cerrar la puerta de su casa, enciender y apagar luces, etc. 
	○ El reconocimiento inalámbrico a menudo precederá a los ataques de dispositivos a gran escala.
● Physical attacks 
	○ Simplemente conectar un USB a un dispositivo IoT puede ser suficiente para propagar malware a una red o espiar las comunicaciones. 
	○ USB Rubber Ducky. 
● Firmware exploits / hijacking 
	○ Utilizar vulnerabilidades conocidas. A menudo, estas vulnerabilidades tienen parches disponibles del desarrollador, pero el usuario no los ha descargado, dejándolos abiertos al hackeo. 
	○ Cada dispositivo tiene software, actualizaciones y modificaciones. Se puede sacar ventaja de este entorno agregando actualizaciones falsas o controladores para descargar software malicioso.