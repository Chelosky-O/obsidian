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

