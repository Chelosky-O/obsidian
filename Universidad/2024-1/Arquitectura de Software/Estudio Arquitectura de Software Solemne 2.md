## Patrones de Arquitectura

Patron es Herramienta no solución

- Solución de diseño a una necesidad
- Características:
	- Esquema genérico
	- Probado
	- Recurrente
- Especificación:
	- Componentes
	- Responsabilidades
	- Relaciones

### Descripción de un Patrón
Nombre de patrón

Contexto: 
- Situación que origina la necesidad
- Ámbito de la necesidad
- Descripción de las situaciones que la originan
	- Descripción general
	- Descripción detallada
- Difícil de precisar completamente
	
Requerimiento: 
- Fuerzas presentes en el contexto
	- propiedades
	- requisitos
	- restricciones
- Descripción genérica de la necesidad
- Define lo que se debe resolver

Solución: 
- Esquema de solución de la necesidad.
- Balance de fuerzas.
- Estructura.
	- Componentes.
	- Relaciones.
- Comportamiento.
	- Organización de componentes.
- Priorización de fuerzas.

#### Clasificación de patrones
##### Patrones simples
- **Capas o Layers** 
	- Estructura aplicaciones descomponiéndolas en tareas con diferentes niveles de abstracción
	- **Contexto**: Sistemas estructurados con diversos niveles de acción
	- **Requerimiento**: Organización inadecuada genera problemas de escalabilidad y mantenibilidad.
	- **Solución**: Estructuración en esquema multi-capa
		- Capa base con nivel de abstracción más bajo
		- Avanzar capa a capa utilizando los servicios de la capa inmediatamente anterior.
		- Componentes estructurados en módulos relacionados
		- **Características**:
			- La capa K se relaciona solamente con la capa K-1.
			- No hay otras dependencias entre capas.
			- Cada capa puede estar integrada por distintos componentes.
			- Los componentes pueden interactuar entre sí, pero quedan acoplados.
			- Cada capa expone una interfaz con los servicios que provee.
			- El comportamiento puede ser top-down o bottom-up.
		- **Implementación**:
			- Determinar el número de capas según el nivel de abstracción requerido.
			- Asignar responsabilidades a cada capa.
			- Especificar los servicios ofrecidos por cada capa.
			- Definir la estructura de cada capa.
			- Especificar la interfaz de cada capa.
			- Especificar el método de comunicación intercapas.
			- Definir el esquema para el manejo de errores.
	- **Análisis**
		- **Ventajas**:
			- Componentes estandarizados
			- Cambios afectan el nivel local
			- Reutilización de capas/componentes
		- **Desventajas**:
			- Cambios afectan en cascada
			- Ineficiencia
			- Complejo de definir
	- **Ejercicio**
		- Un banco requiere un sistema para manejar las cuentas corrientes de sus clientes. Específicamente requiere las siguientes operaciones:
			- Consulta del saldo de una cuenta
			- Deposito en una cuenta
			- Giro desde una cuenta
			- Transferencia entre cuentas
		- Se pide definir este sistema utilizando la arquitectura de Capas
		- **Solución**:
			- Definir Capas:
				- UI
				- Transferencia
				- Giro | Deposito
				- Consulta Saldo
				- Datos
- **Tubos y filtros**
	- Estructura aplicaciones en actividades para procesar flujos de datos en que cada actividad (o transformación) es un filtro que está unido por un tubo a los filtros contiguos. 
	- Contexto: Procesar flujos de datos.
	- **Requerimiento**:
		- Descomponer el procesamientoen una serie de actividades(filtros) que transforman datos de entrada (recibidos desde un tubo) en datos de salida (entregados en un tubo).
		- Las transformaciones son independientes y no tienen estado
		- Cada actividad es un filtro
		- Los filtros se comunican entre sí mediante tubos
	- **Solución**:
		- **Tubos(pipe)**
			- Conecta origen de datos con un filtro
			- Conecta filtro con filtro
			- Conecta filtro con salida de datos
			- Esquema de procesamiento FIFO
		- **Filtro(filter)**
			- Aplica procesos de transformación de datos de entrada en datos de salida
			- Implementa un flujo que solicita datos (al filtro anterior)
			- Implementa un flujo que entrega datos (al filtro siguiente)
			- Filtros independientes
				- Estado no compartido
				- Desconocimiento de otros filtros
				- Filtros activos o pasivos
	- **Implementación**:
		- Dividir el sistema en una secuencia de procesos ordenados e independientes.
		- Definir el formato de los datos transmitidos por los tubos (rendimiento o flexibilidad)
		- Especificar el procesamiento de cada filtro
		- Construir los filtros
		- Definir el esquema para el manejo de errores
	- **Ventajas**:
		- Arquitectura flexible
		- No requiere de archivos intermedios
		- Filtros reutulizables
		- Procesamiento paralelo(eficiencia). (generar nuevas instancias de filtros manteniendo la misma cantidad de tubos)
		- Construcción independiente
	- **Desventajas**:
		- Información no compartida
		- Conversión de datos (ineficiencia)
		- Errores pueden afectar el flujo de procesamiento
- **Pizarrón** 
	- **Patrón útil cuando:**
		- No hay una solución completa y específica para un problema
		- Participan varios sistemas que aportan su conocimiento
		- Ejemplos: inteligencia artificial, reconocimiento de imagenes, toma de decisiones.
	- **Contexto**: dominio en el que no hay una solución completa
	- **Problema**:
		- Conocimiento parcial de la solución
		- Cada solución requiere diferentes paradigmas
		- El problema abarca muchas especialidades
		- No es factible una solución completa
		- Hay soluciones parciales que cubren parte del problema
		- Módulos aportal parcialmente a la solución
	- **Solución**:
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

##### Patrones para Sistemas Interactivos

- **MVC (Modelo Vista Controlador)**
	- **El sistema se divide en 3 partes:**
		- Modelo: datos y funcionalidad esencial
		- Vista: Comunicación con el usuario
		- Controlador: Controla cambios al modelo
		- Interfaz de usuario: Vista + Controlador
		- Lógica de negocio: Controlador + Modelo
		- Controlador Desacopla la vista el modelo
		- Flexibilidad, mantenibilidad, adaptabilidad
	- **Contexto**:
		- Sistemas interactivos con interfaz flexible
	- **Requerimiento**:
		- Interfaz con diferente representación:
			- Texto, gráficos, listas, iconos.
		- Paradigmas de ingreso diversos
			- Digitación: cajas de texto
			- Selección: listas desplegables, iconos
			- Ingreso mixto
		- Interfaz cambiante:
			- Mejora, evolución
		- Facilidad de modificación de la interfaz
		- Funcionalidad nueva implica modificar interfaz
		- Presentación de la información en multi-formato
	- **Solución**:
		- Tres componentes:
			- Comunicación (vista):
				- Envía requerimientos de usuario
				- Recibe datos (del modelo) y los despliega al usuario
			- Administración (controlador):
				- define el comportamiento del sistema
				- recibe eventos (desde la interfaz del usuario) y solicita servicios al modelo
			- Procesamiento (modelo):
				- provee la funcionalidad requerida por las vistas
				- encapsula el manejo de los datos
	- **Implementación**:
		- Separar la funcionalidad de la interacción del usuario
		- Diseñar e implementar
			- el modelo
			- las vistas
			- los controladores
			- la relación entre vista y controladores
	- **Análisis**
		- **Ventajas**:
			- Modelo soporta múltiples vistas
			- Flexible, mantenible, adaptable
			- Frameworks implementan MVC
		- **Desventajas**
			- Modelo acoplado con vistas y controladores
			- Vista sin acceso a los datos(ineficiencia)
			- Complejidad
	- **Ejercicio**:La empresa BigSell necesita un sistema para la venta online de sus productos. Para ello, requiere un sistema de ventas que cumpla con los siguientes requerimientos:
		* Registro de clientes 
		* Autenticación de usuarios en dos niveles, clientes y personal interno.
		* Autorización de acceso a distintas funcionalidades según sea el nivel del usuario 
		* CRUD de productos 
		* Administración del inventario 
		* Administración del carro de ventas 
			- agregar/quitar productos 
			- valorización del contenido 
			- confirmación de la compra 
			- uso de medios de pago externos 
		* Estadísticas de gestión 
			- Producto mas vendido 
			- Monto promedio de una venta 
			- Consulta de ventas en un periodo dado 
			- Cantidad total vendida de cada producto 
		- Diseñar este sistema usando el patrón MVC, indicando
		* componentes principales del sistema 
		* diagrama de ubicación en la solución (M, V o C) 
		* mecanismo de comunicación entre los componentes
	- Vista (interfaz de usuario) 
		* registro y autenticación de usuarios 
		* ver productos, imágenes, descripción, precio 
		* manejar el carro de ventas 
			- agregar/quitar productos 
			- modificar cantidades 
			- desplegar total venta 
		* interacción con medios de pago externo 
		* finalización de la venta, detalle de productos, valor total, medio de pago utilizado
	- Modelo (lógica de negocio) 
		* gestión de base de datos con información de 
			- clientes 
			- productos 
			- ventas 
		* gestión del carro de ventas 
			- productos en el carro (agregar/quitar)
			- valorización del contenido 
			- estado de la venta
	- Controlador (intermediario) 
		* autenticación de usuarios 
		* interacción usuario/carro de ventas 
		* interacción usuario/medio de pago externo 
		* direccionamiento de transacciones
	- Comunicaciones 
		* Vista 
			- Controlador: evento HTTP/HTTPS 
		* Controlador 
			- Modelo: interfaz API
- **PAC (Presentación Abstracción y Control)**
	- Estructura jerarquica de agentes cooperativos
	- Provee la funcionalidad de la aplicación
	- Agente es responsable de una parte de la funcionalidad
	- Compuesto por 3 componentes
		- Presentación: Interfaz
		- Abstracción: funcionalidad
		- Control: comunicación con agentes
	- Segmentación del sistema en subsistemas especializados
	- **Contexto**:
		- Sistemas interactivas desarrollados utilizando agentes
	- **Requerimiento**:
		- Estructurar un sistema interactivo mediante agentes funcionando en forma integrada
		- Generar interfaces flexibles de usuario
		- Separar la presentación de la funcionalidad
		- Bajo acoplamiento
		- Agentes con interfaces propias de comunicación
		- Agentes con estado y datos privados
		- Trabajo cooperativo de los agentes
	- **Solución**:
		- Definir estructura jerárquica de tres niveles de agentes:
			- Alto nivel: funcionalidad central del sistema, interfaz global de usuario
			- bajo nivel: manejo interfaz específica de usuarios
			- intermedio: relaciona agentes de bajo nivel
		- Cada agente es responsable de una parte de la funcionalidad del sistema 
		- Agente esta compuesto por:
			- Presentación: aspecto visible del agente
			- Abstracción: modelo de datos interno y operaciones sobre ellos
			- Control: conexión entre presentación y abstracción, comunicación con otros agentes
	- **Implementación**:
		- Definir la funcionalidad central del sistema
		- Estructurar la jerarquía de agentes
		- Definir e implementar cada agente
			- Funcionalidad
			- Interfaz
			- Modelo de datos
			- Mecanismo de control
	- **Análisis**
		- **Ventajas**
			- Asigna responsabilidades específicas
			- Funcionamiento independiente
			- Soporta multitarea
		- **Desventajas**
			- Sistema complejo
			- Baja eficiencia
			- Complejo mecanismo de control

##### Patrones Patrones para Sistemas Adaptables

### MicroKernel

Microkernel: núcleo que hace funcione básicas y plugin que hacen que el núcleo se adapte a distintos entornos.

Estructura mínima: núcleo
Extendida: plugins

Si quiero que el sistema pueda añadir cosas como escuchar musica etc, se hacen con plugins

- Sistemas que deben adaptarse a cambios en los requerimientos
- Requisitos Cambiantes
- Separa funcionalidad en:
	- Mínima: Común a todos los clientes, no es mínimo es lo común, lo que es para todo el mundo
	- Extendida: específica de un cliente
- Usa plugin para conectarse, e incorporar cosas funcionalidades etc...![[Obsidian/Universidad/2024-1/Arquitectura de Software/Diagram.svg]]
- **Contexto**:
	- Este patrón adaptable sirve para:
		- Sistemas con interfaces de programación parecidas
		- Basados en el mismo núcleo funciona
			- Linux por ejemplo, su núcleo su parte central se diseño con esta arquitectura en la mente, entonces si yo quiero que haga algo, se le agrega.
- **Problema**:
	- Sistemas que perduran con el tiempo (legacy → legado, sistemas que han perdurado en mucho tiempo, ej linux, tecnología antigua que aun sigue siendo utilizado en la tecnología actual → COBOL: lenguaje de los años 60, en donde se hicieron todos los grandes sistemas de los 60, toda la infraestructura de los bancos de esa época esta basada en esos sistemas, hoy en 2024 todavía esos sistemas bancarios siguen funcionando. A comienzos del 2000, se estimo que en el mundo habían sistemas programados en cobolt y que estos sistemas tenían 2000 millones de instrucciones (juntando todos los sistemas) esas no serian factibles eliminarlas o cambiarlas a otra cosa. )
	- Deben adaptarse a cambios en la infraestructura (hardware/software)
	- Debe ser:
		- Extensible a nuevas tecnologías
		- Portable → con el mínimo esfuerzo se pueda correr en a b o c, un ejemplo de esto seria wasap, un plugin para windows un plugin para linux uno para android etc. no depende del sistema operativo ni del hardware, eso lo puedo llevar de un lado para otro pero debo hacer un plugin hacia el contexto que debe ser portable.
		- Adaptable → que se vaya adaptando a los tiempos
- **Solución**:
	- Microkernel: componente central(núcleo) → todo lo independiente a la plataforma donde va a correr
		- Funcionalidad básica
		- Administración de recursos
		- Servicio de comunicación entre componentes
	- Servidores internos: servicios específicos de la plataforma 
		- conversan con la plataforma, los plugins
	- Servidores externos: Interfaz de acceso al núcleo
		- los que nos permiten acceder al núcleo
	- Adaptadores: Mecanismo de comunicación cliente con servidor externo
	- Clientes
		- tiene un adaptador que permite que los clientes, 
		- cliente es un proceso que va a recibir requerimiento de los usuarios.
- **Análisis**:
	- **Ventajas**:
		- Adaptabilidad
		- Portabilidad
		- Flexibilidad
		- Escalabilidad horizontal, confiabilidad
	- **Desventajas**:
		- Sistema complejo
		- Baja eficiencia
		- Compleja implementación
		- Punto único de falla Microkernel, pero depende de como este definido puede que haya solo en una parte

**EJERCICIO**:
Una pastelería de barrio quiere ampliar la cobertura de atención de clientes abriéndose al comercio electrónico. Para ello, requiere el desarrollo de un sistema que cubra los siguientes requerimientos funcionales:  
* Recepción de pedidos online  
* Disponibilidad de diversos medios de pago (webpay, mercadoPago, transferencias, etc.)  
* Organización de los envíos a domicilio  
* Gestión de los repartidores  
* Estadísticas de venta, diaria, semanal, mensual, anual  
Se pide lo siguiente:  
1. Justificar la elección del patrón de arquitectura a usar  
CUAL? POR QUE?
SOA SOBRE MVC POR QUE UNOS DE LOS PROBLEMAS DE MVC ES QUE YO PIERDO EL CONTROL Y NO SE QUE SERVICIOS ESTÁN OPERATIVOS, ENTONCES EL SERVICIO 

Se elige SOA dado que el sistema tiene diversos requerimientos que se pueden implementar en servicios independientes.  
Estos estarán enfocados en satisfacer los requerimientos de los distintos tipos de usuarios (clientes, repartidores, administración, gestión).  
Entonces, cada tipo de usuario tendrá un conjunto de servicios que los van a atender.

2. Diagrama global de la solución indicando como se va a satisfacer la funcionalidad requerida  
Tal como ya se mencionó, cada funcionalidad va a ser satisfecha por un conjunto de servicios independientes.  
Por lo tanto, los clientes generarán transacciones que serán procesadas por ese conjunto.  
Entonces, en el nivel cliente estarán los procesos captadores de los requerimientos de los usuarios.  
Estos procesos clientes generarán transacciones y las enviarán al bus.  
Este, redirigirá la transacción al servicio correspondiente, en donde se hará el procesamiento y retornará la información solicitada hacia el bus, y de ahí al cliente.

3. Adicionalmente a Confiabilidad y Rendimiento, que deben estar considerados de todas maneras, describa dos requerimientos no funcionales a implementar en el sistema.  
Seguridad: sobre todo en el proceso de pago se debe asegurar el correcto procesamiento de este, implementando comunicación encriptada con los diversos procesadores. Además, grabar la traza de las transacciones para responder a posibles cuestionamientos.  
Mantenibilidad: dado que el negocio esta creciendo, este RNF ayuda a implementar nuevas funcionalidades que vayan siendo requeridas.  
Rendimiento, no vas a esperar 30 min pa un café xd
### Reflection
 La adaptación lo hace en tiempo real, mientras se esta ejecutando, es una adaptación activa. a diferencia de microkernel

Se usa cuando quiero que el sistema se adapte, cambie, etc en tiempo real.

En las primeras versiones de UNIX, se podían instalar nuevas versiones con el sistema corriendo sin reiniciar etc... 
Ahora es impensado xd profe hater con esto

- Sistemas que deben adaptarse a cambios en su comportamiento en tiempo de ejecución
- Cambio dinámico de la estructura de un sistema
- Es útil cuando se requiere que la aplicación se adapte a los cambios del ambiente de ejecución.
- Ejemplos de aplicaciones:
	- frameworks
	- IDE'S
	- Middleware's

**Solución**:
- Nivel Base:
	- El sistema, que hacen los programas, en que están etc...
	- Contiene la lógica de la aplicación
	- Ejecuta los componentes que satisfacen los RF'S de la aplicación
- Nivel Meta:
	- Contiene meta-información del nivel base
	- Provee mecanismos de análisis y modificación a nivel base en tiempo de ejecución
	- El que sabe las características (no es el dato, es el tipo por ej INT).
	- Es como un programador automático, que esta verificando lo que esta pasando en el nivel base y nos permite modificar en tiempo real .
	- Este es el intruso, el que ve que hace el sistema XD
 **Análisis**:
- Ventajas:
	- Adaptable a los cambios del entorno de ejecución
	- Flexible: modifica el comportamiento del sistema en tiempo real(se puede hacer y deshacer cosas en tiempo de ejecución, por que los componentes del nivel meta son capaces de inspeccionar lo que esta pasando.)
	- Extensible: permite adición de nuevas funcionalidades, sin afectar a las que están corriendo (quiero soportar audio en mi sistema, digitalización de caracteres, etc...)
		- tiene que ver con mantenibilidad, pero es más que eso.
- Desventajas:
	- Complejidad en el diseño
	- Complejidad en implementación
		-  mucho mas complejo pero en tiempo de ejecución se ve la paga, es en tiempo real y dinámico, pago mas tiempo en diseño e implementación.
	- Seguridad en peligro
		- Por que como los cambios se hacen dinámicamente, alguien malicioso podría hacer un cambio y tomar el control. Si no se maneja bien la seguridad, fácilmente se puede exponer a alguien que pueda interferir en el meta puede interferir en el sistema. 

#### Ejercicio:
El organigrama de la empresa ArquiSoft muestra que está organizada en varias  
Gerencias que dependen de la Gerencia General. Algunas de estas gerencias  
son las siguientes: Operaciones, Producción, Finanzas, Marketing, Ventas,  
Recursos Humanos. Debido a razones históricas de la formación de la empresa,  
cada gerencia funciona independientemente con sus propios sistemas y sus  
correspondientes datos asociados. Ello trae una serie de complicaciones  
debido a que hay datos repetidos e inconsistentes entre las gerencias y no  
se tiene una visión consolidada de la empresa.  
En vista de esto, el Gerente General ha ordenado el desarrollo de un Sistema de  
Gestión Centralizada que depure los datos existentes en la empresa y que  
consolide la información de cada gerencia, permitiéndoles compartir los datos  
generales, tales como información de Clientes, Ventas y Facturación. Sin  
embargo, las gerencias van a seguir utilizando sus sistemas propios, pero  
con las modificaciones necesarias para acceder a los datos generales.  
Con estos antecedentes, se le pide:  
a) justificar la arquitectura que propondría para los sistemas de la empresa,  
considerando, tanto los actuales sistemas, como el nuevo Sistema de Gestión  
Centralizada a desarrollar.  

Dado que la empresa ya tiene sistemas en la arquitectura Cliente/Servidor, lo lógico seria migrar los sistemas actuales a SOA y desarrollar el nuevo sistema en esta arquitectura. La migración seria simple, pues solo habría que agregar el bus de servicios e implementar el protocolo de comunicaciones que requiere SOA.

b) explicar las modificaciones que habría que hacer a los actuales sistemas de  
las gerencias, los que fueron desarrollados en la arquitectura Cliente/Servidor,  
para que puedan integrarse a la arquitectura propuesta.

1. Los sistemas actuales deben modificar la conexión entre el cliente y el servidor, para conectarse ahora al bus de servicios. Asimismo, los servidores deben conectarse al bus y esperar por las transacciones que les corresponde procesar.  
2. Implementar un servicio de bases de datos que centralice toda la información de la empresa. Esto implica que los servidores dejan de manejar sus base de datos y, ahora, van a tener que solicitar los datos que requieran a través de este nuevo servicio.  
3. Depurar los datos administrados por cada gerencia, de forma de tener un modelo de datos común a toda la empresa.  


##### Patrones Patrones para Sistemas Distribuidos

### Microservicios

- Sistemas con variados requerimientos funcionales que deben ser distribuidos en múltiples ambientes  
- Cada microservicio implementa un requerimiento funcional específico  
- Los microservicios  
	- son autónomos  
	- pueden ser instalados de manera independiente en diversas plataformas  
	- manejan sus datos  
	- ofrecen una interfaz tipo API  
	- se comunican usando protocolos HTTP/REST o similares

**Implementación**:
- descomponer el sistema en módulos y submódulos  
- elegir la tecnología a utilizar en cada microservicio  
- definir los datos requeridos en cada microservicio  
- definir la interfaz ofrecida al resto del sistema  
- definir la interaccion entre los microservicios  
- elegir el protocolo de comunicaciones a utilizar  
- definir el mecanismo de “tracing” de las transacciones  
- definir el esquema de manejo de errores
**Análisis**:
- Ventajas  
	- Desarrollo independiente  
	- Flexible en la(s) tecnologia(s) a usar  
	- Permite adición de nuevas funcionalidades  
	- Escalabilidad individual  
- Desventajas  
	- Compleja integracion de los microservicios  
	- Sistema complejo de gestionar  
	- Alta utilizacion de la red  
	- Dificil manejo de la consistencia de datos