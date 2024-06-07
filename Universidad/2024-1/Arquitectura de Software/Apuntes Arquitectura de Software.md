# 08-03

Juan Giadach

#### Objetivo del curso
###### Contenidos
1. Intro.
2. Propiedades no funcionales.
3. Arquitecturas de Software Genéricas.
4. Patrones de Arquitectura. 
5. Pruebas, medición y validación de la arquitectura en base a atributos de calidad

###### Evaluación

Nota presentación = Solemne(2) 60% + Controles(2) 10% + Proyecto(4 Informes 20% y Presentación Final 10%) 30%

$$
Ns_i \geq 4\; \&\; NCo \geq 4  \;\& \; NPr \geq 4 \;\&\; NP \geq 5
$$

###### Fechas
- Solemnes 24/04 - 30/04 y 24/06 - 28/06
- Controles 03/04 y 29/05
- Proyecto Curso
	- Informes
		22/03 - 12/04 - 24/05 - 14/06
	- Presentación Final
		21/06 - 05/07

###### Apuntes
Arquitectura Proyecto: SOA

Bibliografía los 2 primeros son los más importantes.

Arquitectura de Software: Componentes, su relación entre ellos y su ambiente.

# 12-03

## Proyecto
Para un área de una empresa.
Se utiliza SOA
Correo con integrantes de grupo (decimas si enviamos antes de que termine la semana)

1 Funcionalidad a unos Datos, Funcionalidades grandes no

Consultar, eliminar modificar un tipo de datos es 1 Funcionalidad

Presentación final, mientras antes mejor.

## Arquitecto de Software

- Administra Riesgos ⇒ Tecnológicos, de negocios, de operación, riesgo del desarrollo.
- Conocimiento de la tecnología ⇒ Ver lo que se está utilizando actualmente, la moda.
- Diseñar.
- Interfaz entre Cliente y Equipo Técnico.
- Promoción de buenas practicas de desarrollo.
- Puente de comunicación entre los equipos de desarrollo.

## Requerimientos no funcionales
(O atributos de calidad del software)

- Performance:
	- Throughput → Flujo
	- Tiempo de respuesta
	- Plazos → En consultas que toma horas por ejemplo

Los bancos dejan de atender los usuarios, tienen un proceso donde hacen la cuadratura de depósitos, cuentas, etc... Los plazos se extendían tanto que no alcanzaba el tiempo disponible, pq a las 9 tiene que atender de nuevo. Aparece cartelito "No tenemos sistema". Ahora ya no hay estos espacios, ahora hacen procesos de cuadratura y conciliación 

- Escalabilidad:
	- Carga (tps) → Transacciones x segundo (En requerimiento → respuesta)
	- Conexiones simultaneas
	- Volumen de datos
	- Despliegue → Facilidad o complejidad de instalar una nueva instancia del sistema

- Mantenibilidad: (Cuando decimos que le hacemos mantención al software que hacen? No es corregir errores, es poder incluir nuevos requerimientos, dependiendo de la arquitectura y modificar estos. )
	- Modificable → 
	- Nuevos requerimientos funcionales → 

- Seguridad:
	- Autenticación → Identificar al usuario frente al sistema
	- Autorización → Definir funciones que un usuario puede tener en un sistema
	- Encriptación → 
	- Integridad → Que el mensaje que salió llegue integro al destino. Garantizar
	- No repudio → Mecanismo que nos permita verificar que quien hizo la transacción es quien la hizo. Pero esto baja la velocidad de hacer cosas al agregar más claves, correos etc... Mientras más seguro menos rendimiento
- Confiabilidad: Que este disponible no que los resultados sean correctos
	- Disponibilidad → Que este disponible el mayor porcentaje del tiempo posible
	- Recuperable → En caso de que falle que se recupere rápido
	- Regla de los cinco nueves → Es un porcentaje 99.999%
- Integrabilidad: 
	- Agregación → 
	- Interoperable → 
	- API'S → Poder usar otros sistemas a través de las funcionalidades
- Portabilidad: NO existe, el sistema que corra en mac y si lo tomo tal cual a linux y va a correr sin ningún problema, luego en otra windows y va a correr sin problemas, eso no es cierto. 
	- Independencia de plataforma → 
- Verificabilidad: Autochekeo que hace el sistema, los nuevos autos tienen sensores que te avisan de todas, es verificable. Que tenga elementos de auto
	- Testeable → 
- Soportabilidad:
	- Diagnosticar 
	- Corrección de incidencias


# 19-03


Componentes, relaciones entre ellos, ambiente.

Rellene clase pasada.
# 22-03

## Frases celebres

Simple → no problem
Complicado → Errores imposibles de encontrar?

#presentacion2

### Diseño de Software

- Fase 0 → Analizar el contexto
	- Donde se va a instalar
- Fase 1 → Estructuración
	- Identificar componentes y sus relaciones
- Fase 2 → Modelo de control
	- Comportamiento de los componentes
- Fase 3 → Descomposición 
	- Diseño detallado

Estructuración:
	Descompone el sistema en un conjunto de subsistemas.
	Utiliza un diagrama de bloques que muestra la estructura del sistema.
	Indica el flujo de datos entre los componentes del sistema.
	Muestra las interfaces que provee el sistema.

Ej de modelos: SOA (Arquitectura orientada a servicios), Modelo de repositorio, Cliente/Servidor, Modelo de Capas, Objetos distribuidos, Arquitectura Cloud.

---
## Modelo de Repositorio:

Cuando hay grandes cantidades de datos que necesitan ser compartidos
- Gestión centralizada de datos
- Almacenamiento Centralizado / Distribuido

Modelo Pasivo → Almacena esto, relaciona esto
Modelo Proactivo → El modelo le avisa a sus usuarios cuando hay modificaciones en los datos.

Componentes aparte de bdd, modulos que controlan el acceso a los datos y que permiten manejar la bdd, los S1, 2 o 3 se conectan a los modulos.

Ej: Registro civil, sistema de cedula de identidad, pasaporte etc...
Canvas
Github

- Ventajas:
	- Modo eficiente de compartir datos
	- Administración centralizada de los datos
	- Seguridad, Escalabilidad, Mantenibilidad
- Desventajas:
	- Fuerza un modelo de datos → La mas terrible
	- Difícil cambio del modelo de datos
	- Política centralizada de administración
	- Punto único de falla → El mas critico
# 26-03

**Control Viernes 5**


Los sistemas de electricidad y celulares están diseñados parra los 5 9´s

El mes pasado, AT&T la red celular tuvo 11 horas caído.


# 02-04

**Preguntas tipo control:**
Analice el siguiente parrafo indicando y corrigiendo los errors:
- El objetivo del requerimiento funcional de mantenibilidad es mantener operativo el sistema el mayor tiempo posible. **R:// esta definición es de confiabilidad**
- El optimo a alcanzar es que opere al 99,999% del tiempo, regla conocida como la de los cinco nueves. **R:// Verdadero**
- Para lograr los cinco nueves, un sistema debe diseñarse con componen redundantes que puedan tomar el control de la operación del sistema en el caso que uno de ellos falle. **R:// Verdadero, porque tener componentes redundantes es una de las soluciones**
- Si esto ocurre, utilizando los procesos definidos al incluir el requerimiento de mantenibilidad se podra corregir el error y restaurar el sistema a su estado normal del procesamiento. **R:// falso, eso lo realiza soportabilidad**

- Continuación modelos de estructuración
	- Cliente/Servidor:
		- Estructurado en base a:
			- Servidores que ofrecen servicios especificos
			- Clientes que requieren serviios
			- Redes de comunicacion que conectan ambos
		- Es un modelo parcialmente distribuido (el procesamiento está dividido tanto en el cliente como en el servidor)
		- Ventajas
			- Procesamiento distribuido
			- Datos distribuidos
			- Escalable (definir más instancias de los servidor)
		- Desventajas
			- Datos no compartidos (cada servidor tiene sus propios datos)
			- Administración de datos en cada servidor
			- Performance deteriorada (ya que existe un medio de comunicacipon entre cliente y servidor, el cuello de botella es la red)
			- No hay registro centralizado de servicios (No se que servicios están operativos y cuales no, tampoco se donde estan. Todo es en base a prueba y error)
	- Modelo de capas:
		- Conjunto de capas de software que ofrecen servicios especificos
		- Cada capa tiene una interfaz claramente definida
		- Desarrollo independiente de las capas
	- Objetos distribuidos
	- Arquitectura orientada a servicios
	- Arquitectura Cloud 


# 09-04

Que componente tiene SOA : BUS y Servicios

En SOA se pueden reutilizar los servicios
SOA tiene un bus donde se comunican todos sus servicios





# 12-04
## Arquitectura SOA
**Ejercicio -SOA**:
Un banco requiere un sistema para manejar las cuentas corrientes de sus clientes el que debe comtemplar las siguientes operaciones:
- Consulta del saldo de una cuenta
- Deposito en una cuenta
- Giro desde una cuenta
- Transferencia entre cuentas
Se pide definir este sistema utilizando la arquitectura SOA.

1. Paso 1: Identificar los servicios. Por lo menos son 4 servicios, ya que se puede incluir un servicio de base de datos(este servicio se conecta directamente a la base de datos) o servicios que son utilizados por los 4 servicios principales (recordar que si un servicio quiere solicitar a otro servicio debe pasar por el Bus)
	1. Servicio de transferencias
	2. Servicio de Giros
	3. Servicio de Depósitos
	4. Servicio de consulta saldo
2. Paso 2: Definir las transacciones que se procesarán cada uno de los servicios:
	1. Servicio de consulta de saldos:
		1. INPUT
			1. COSAL
			2. Cuenta destino
		2. OUTPUT
			1. COSAL
			2. Monto Saldo
			3. Resultado Consulta Saldo
	2. Servicio de Depositos
		1. INPUT
			1. DEPOS
			2. Cuenta Origen
			3. Monto
		2. OUTPUT
			1. DEPOS
			2. Monto Nuevo Saldo
			3. Resultado Deposito
	3. Servicio de giros: debe hacer uso del servicio de consulta de saldo mediante el bus para saber si es posible hacer un giro, luego realiza el giro
	4. Servicio de transferencias: Debe realizar un giro y el giro a su vez debe hacer una consulta de saldo y luego debe hacer un deposito y para esto debe hacer uso del servicio de deposito todo esto mediante el bus
		1. INPUT:
			1. TRANS
			2. Cuenta Origen
			3. Cuenta Destino
			4. Monto a Transferir
		2. OUTPUT:
			1. TRANS
			2. Monto Nuevo Saldo Cuenta Origen
			3. Resultado Transferencia
3. Paso 3: Especificar las interacciones entre los servicios
	1. Servicio de giros
		1. Servicio de consulta de saldos
	2. Servicio de deposito
		1. Servicio de consulta de saldos
	3. Servicio de transferencias
		1. Servicio de consulta de saldos
		2. Servicio de giros
		3. Servicio de depositos
4. Paso 4: Definir el modelo de datos
5. Paso 5: Especificar el funcionamiento de cada servicio
6. Paso 6: Definir la interfaz de usuario
7. Pasos siguientes: Codificar, Probar, etc.
# 16-04

 CONTROL REVISION
2 
 1ra mas importante → Capacidad de diseño
 2da → Buena comunicación cliente y equipo técnico
 3ra → Tecnologia
3
confiabilidad pq hay que tener mecanismo o redundancia en caso de caida
Seguridad
soportabilidad
portabilidad
verificabilidad


---

## SOA

Cada servicio implementa 1 funcionalidad

Cada vez que identificamos sus servicios vemos la interfaz del servicio
la transacción que in y out

BUS esta en docker que acepta conexion en puerto 5000, con protocolo TCP/IP

Para una transaccion de hola mundo

Deberia ser

#### TX in: transaccion de requerimiento

| LARGO | SERVI | DATOS DEL REQUERIMIENTO |
| ----- | ----- | ----------------------- |

En el caso de hola mundo seria:

| 00017 | HOLAS | HOLA MUNDO!! |
| ----- | ----- | ------------ |

#### TX out: transacción de respuesta del servicio

| LARGO | SERVI | DATOS DE LA RESPUESTA |
| ----- | ----- | --------------------- |

#### TX out: transaccion de respuesta del bus

| LARGO | SERVI | ST  | DATOS DE LA RESPUESTA |
| ----- | ----- | --- | --------------------- |
ST : STATUS DE LA TRANSACCION OK:CORRECTA NK:ERRONEA

---
## Servicio

Servicio no tiene idea de los clientes, su unico contacto es con el BUS

Como sabe el bus si un programa es un servicio? por que debe enviar una transaccion sinit → Service init


El programa sumar le dice hola soy el servicio sumar

Sumar envía a BUS 00010sinitsumar (se queda esperando) → Bus recibe y luego responde en el BUS 00012sinitOKsumar y lo toma sumar

TCP connect - TCP send - TCP recv ⇒ sinit

TCP recv - x - TCP send

calc es el programa que ve el cliente

bg → background → deja a lo stopeado con (ctrl + z) y queda por detras

ps → procesos

kill PID mata a los procesos

# 19-04-24
## Modelo de capas
- Conjunto de capas de software que ofrecen servicios específicos
- Cada capa tiene una interfaz claramente definida
- Desarrollo independiente de las capas
- Ventajas:
	- Desarrollo incremental
	- Flexible
	- Mantenible
- Desventajas
	- Díficil estructuración
	- Dependencias cruzadas
	- Baja performance
## Objetos distribuidos
- Cada componente (objeto) define los datos y metodos que pueden ser invocados
- Cada objeto puede proveer y recibir servicios
- Objetos se comunican a través del sistea ORB (Object Request Broker)
- Arquitectura compleja
- Ventajas
	- Diseño flexible(yo defino las clases que yo quiera)
	- Facil agregar objetos
	- Configuración dinámica
	- Escalabilidad, mantenibilidad
- Desventajas
	- Compleja construcción
	- Bajo rendimiento
## Arquitectura Cloud
- Externalización de servicios computacionales
	- Infraestructura - IaaS
	- Plataforma - PaaS
	- Aplicación - SaaS
- Recursos elásticos (pay what you use)
- Ventajas
	- Servicios ubicuos
	- Reducción de costos
	- Disponibilidad, escalabilidad, elasticidad
	- Flexibilidad, movilidad
- Desventajas
	- Dependencia de ente externo
		- Seguridad
		- Confidencialidad
		- Conectividad
## **Fase 2: Modelo de Control**
- Control del flujo entre componentes
- Control Centralizado:
	- Un componente controla la ejecucion del sistema
	- Modelo Call-Return
		- Simple 
		- Predecible
		- Rigido
		- Testeable
		- Bloqueante
		- Complejo manejo de excepciones
	- Modelo Administrador
		- No bloqueante
		- Coordinación de procesos
		- Lógica centralizada
		- Posible cuello de botella
- Control Basado en Eventos
	- Control descentralizado
	- Control no bloqueante
	- Manejan eventos generados externamente
		- Transmisión Múltiple (Broadcast)
		- Manejador de Interrupciones
	- Usan modelo Publicador-Suscriptor
		- Componentes distribuidos
			- Publican servicios
			- Gatillan eventos
			- Suscriben eventos
	- Manejo de Interrupciones
		- Sistemas en tiempo de real
		- Manejador para cada tipo de interrupción
		- Respuesta inmediata
		- No bloqueante
		- Procesamiento paralelo
## **Fase 3: Descomposición Modular**
- Componentes divididos en módulos
- Posibilita visualizar 
### Modelo de Objetos
- Conjunto de clases bien definidas
- Identifica atributos y métodos
- Objetos creados a partir de las clases
- Coordinación de operaciones entre objetos
### Modelo de Flujo de Datos
- Descomposición en procesos funcionales
- Transformación de entradas en salidas
- Dependencia entre procesos
- Flujo predeterminado
- Adecuado para procesos batch
---
			FIN DE ARQUITECTURAS GENÉRICAS
--
# 23-04-24
## Arquitecturas de Dominio Específico
- Modelos específicos para algún dominio
- Arquitecturas genéricas
	- Generalización de sistemas reales
	- Análisis de sistemas existentes
- Arquitecturas de referencia
	- Idealización de una arquitectura específica
	- Estudio del dominio de una aplicación
	- Estándar de facto en su dominio
- Diferencia entre estas arquitecturas: La generica dice, esta es la arquitectura, implementala.. la deja lista. La de referencia es similar pero no es aplicable a la realidad, es lo que deberias tener pero no necesariamente lo tendrás, ejemplo de arquitectura de referencia puede ser



# 10-05

PROBLEMA = REQUERIMIENTO

Descripción general.
Decir lo que debe resolver. necesitamos balanceador de carga, replicas de bdd etc..
Fueras presentes en el contexto
	propiedades
	requisitos
	restricciones

# 14-05-24
#### Clasificación de patrones
##### Patrones simples
- **Capas**
	- Estructura aplicaciones descomponiendolas en tareas con diferentes niveles de abstracción
	- **Contexto**: Sistemas estructurados con diversos niveles de acción
	- **Requerimiento**: Organización inadecuada genera problemas de escalabilidad y mantenibilidad.
	- **Solución**: Estructuración en esquema multi-capa
		- Capa base con nivel de abstracción más bajo
		- Avanzar capa a capa utilizando los servicios de la capa inmediatamente anterior.
		- Componentes estructurados en módulos relacionados
		- Características:
			- La capa K se relaciona solamente con la capa K-1.
			- No hay otras dependencias entre capas.
			- Cada capa puede estar integrada por distintos componentes.
			- Los componentes pueden interactuar entre sí, pero quedan acoplados.
			- Cada capa expone una interfaz con los servicios que provee.
			- El comportamiento puede ser top-down o bottom-up.
		- Implementación:
			- Determinar el número de capas según el nivel de abstracción requerido.
			- Asignar responsabilidades a cada capa.
			- Especificar los servicios ofrecidos por cada capa.
			- Definir la estructura de cada capa.
			- Especificar la interfaz de cada capa.
			- Especificar el método de comunicación intercapas.
			- Definir el esquema para el manejo de errores.
	- **Analisis**
		- Ventajas:
			- Componentes estandarizados
			- Cambios afectan el nivel local
			- Reutilizacion de capas/componentes
		- Desventajas
			- Cambios afectan en cascada
			- Ineficiencia
			- Complejo de definir
	- **Ejercicio**
		- Un banco requiere un sistema para manejar las cuentas corrientes de sus clientes. Especificamente requiere las siguientes operaciones:
			- Consulta del saldo de una cuenta
			- Deposito en una cuenta
			- Giro desde una cuenta
			- Transferencia entre cuentas
		- Se pide definir este sistema utilizando la arquitectura de Capas
		- Solución:
			- Definir Capas:
				- UI
				- Transferencia
				- Giro | Deposito
				- Consulta.
				- Datos
- **Tubos y filtros**
	- Estructura aplicaciones en actividades para procesar flujos de datos en que cada actividad (o transformación) es un filtro que está unido por un tubo a los filtros contiguos. 
	- Contexto: Procesar flujos de datos.
- **Pizarrón**
- **Repositorio**

# 24-05-24
- Tubos y filtros
	- Estructura aplicaciones en actividades para procesar flujos de datos en que cada actividad (o transformación) es un filtro que está unido por un tubo a los filtros contiguos. 
	- Contexto: Procesar flujos de datos.
	- Requerimiento:
		- Descomponer el procesamientoen una serie de actividades(filtros) que transforman datos de entrada (recibidos desde un tubo) en datos de salida (entregados en un tubo).
		- Las transformaciones son independientes y no tienen estado
		- Cada actividad es un filtro
		- Los filtros se comunican entre sí mediante tubos
	- Solución:
		- Tubos(pipe)
			- Conecta origen de datos con un filtro
			- Conecta filtro con filtro
			- Conecta filtro con salida de datos
			- Esquema de procesamiento FIFO
		- Filtro(filter)
			- Aplica procesos de transformación de datos de entrada en datos de salida
			- Implementa un flujo que solicita datos (al filtro anterior)
			- Implementa un flujo que entrega datos (al filtro siguiente)
			- Filtros independientes
				- Estado no compartido
				- Desconocimiento de otros filtros
				- Filtros activos o pasivos
	- Implementación:
		- Dividir el sistema en una secuencia de procesos ordenados e independientes.
		- Definir el formato de los datos transmitidos por los tubos (rendimiento o flexibilidad)
		- Especificar el procesamiento de cada filtro
		- Construir los filtros
		- Definir el esquema para el manejo de errores
	- Ventajas:
		- Arquitectura flexible
		- No requiere de archivos intermedios
		- Filtros reutulizables
		- Procesamiento paralelo(eficiencia). (generar nuevas instancias de filtros manteniendo la misma cantidad de tubos)
		- Construcción independiente
	- Desventajas
		- Información no compartida
		- Conversión de datos (ineficiencia)
		- Errores pueden afectar el flujo de procesamiento
- MVC (Modelo Vista Controlador)
- PAC (Presentación Abstracción y Control)


# 28-05-24
- Pizarrón 
	- Patrón útil cuando:
		- No hay una solución completa y específica para un problema
		- Participan varios sistemas que aportan su conocimiento
		- Ejemplos: inteligencia artificial, reconocimiento de imagenes, toma de decisiones.
	- Contexto: dominio en el que no hay una solución completa
	- Problema:
		- Conocimiento parcial de la solución
		- Cada solución requiere diferentes paradigmas
		- El problema abarca muchas especialidades
		- No es factible una solución completa
		- Hay soluciones parciales que cubren parte del problema
		- Módulos aportal parcialmente a la solución
	- Solución:
		- Conjunto de sistemas independientes
		- Trabajo colaborativo
		- Datos compartidos
		- Cada sistema se especializa en parte del problema
		- Control centralizado que coordina la ejecución de los sistemas
		- Genera soluciones parciales que pueden ser desechadas
		- No hay comunicación directa entre los sistemas
		- Almacenamiento centralizado de información (repositorio)
		- Diccionario de datos del contenido del pizarrón
		- Sistemas especializados independientes leen y escriben en el pizarrón
		- Monitoreo centralizado del estado del sistema
		- Decisión centralizada de las acciones a seguir basada en el progreso alcanzado
		- Determinación si la solución es aceptable o insoluble

**PARA CONTROL 2 ENTRA PPT 3 Y 4 DE LAS QUE SE LLAMAN 01,02,03,04**:
- [ArquiSW_03.pdf](https://udp.instructure.com/courses/26976/modules/items/1379679 "ArquiSW_03.pdf")
- [ArquiSW_04.pdf](https://udp.instructure.com/courses/26976/modules/items/1382383 "ArquiSW_04.pdf")



# 07-06

## Patrones Adaptables

Patron es Herramienta no solución


Patrones para sistemas adaptables
### MicroKernel
- Sistemas que deben adaptarse a cambios en los requerimientos
- Requisitos Cambiants
- Separa funcionalidad en
	- Minima: Común a todos los clientes, no es minimo es lo comun lo para todo el mundo
	- Extendida: específica de un cliente
- Usa plugin para conectarse, e incorporar cosas funcionalidades etc![[Obsidian/Universidad/2024-1/Arquitectura de Software/Diagram.svg]]
- Este patrón adaptable sirve para:
	- Sistemas con interfaces de programación parecidas
	- Basados en el mismo núcleo funciona
	- Linux por ejemplo, su núcleo su parte central se diseño con esta arquitectura en la mente, entonces si yo quiero que haga algo, se le agrega.

### Reflection