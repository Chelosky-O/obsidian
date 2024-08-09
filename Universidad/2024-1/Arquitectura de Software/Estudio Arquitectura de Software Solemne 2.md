## Requerimientos no funcionales
- Performance: Eficiencia con la que el sistema realiza sus tareas. Se mide en throughput y tiempo de respuesta.
- Escalabilidad: Que un sistema sea capaz de adecuarse de forma dinámica a la carga. Esto puede ser respecto a concurrencia de conexiones, volumen de datos, escalabilidad horizontal y vertical.
- Mantenibilidad: Qué tan fácil es modificar una pieza o función del sistema.
- Seguridad: Facultad del sistema de resistir ataques. Esto puede ser respecto a usuarios o los datos.
- Confiabilidad: Que pueda confiar que mi sistema está operable. Regla de 99999.
- Integrabilidad: Capacidad de mi sistema de agregar componentes externos. Interoperable.
- Portabilidad: Que el sistema pueda ejecutarse en más de un entorno.
- Verificabilidad: Capacidad del sistema de auto chequearse.
- Soportabilidad: Diagnóstico y corrección de incidencias.
## Patrones de Arquitectura

Patrón es Herramienta no solución
Objetivos de patrón:
- Dar indicaciones para la implementación de una cierta arquitectura.
- Solución de diseño a un problema.

Características:
- Posee esquema genérico
- Ha sido probado y testeado anteriormente
- Recurrente
### Descripción de un Patrón
Nombre de patrón

Contexto: 
El contexto define la situación que origina el problema. No todos los patrones son adecuados para todos los contextos. Se debe describir el ambiente de trabajo de forma genérica y detallada. Es complicado proporcionar todo el contexto, por lo que la solución varía según la especificidad del contexto.

Requerimiento o problema: Describe de forma general el problema a resolver. Esto incluye:
- Fuerzas presentes en el contexto
	- propiedades del problema
	- Los requisitos necesarios para la solución.
	- Las restricciones operativas que limitan la solución.
- Descripción genérica de la necesidad
- Define lo que se debe resolver

Solución: 
- Esquema de solución de la necesidad.
- Balance de fuerzas.
- Define la estructura de los componentes y sus relaciones.
- Define el comportamiento de los componentes y cómo se relacionan.
- Prioriza las fuerzas en juego para equilibrar las diversas opciones y determinar la mejor solución.

#### Clasificación de patrones
##### Patrones simples
- **Capas o Layers** 
- ![[Pasted image 20240627172302.png]]
	- Estructura aplicaciones descomponiéndolas en tareas con diferentes niveles de abstracción
	- **Contexto**: Sistemas estructurados con diversos niveles de acción (Sistemas que contienen una jerarquía de distintos niveles con acciones.)
	- **Requerimiento**: Organización inadecuada genera problemas de escalabilidad y mantenibilidad.
	- **Solución**: Estructuración en esquema multi-capa
		- Capa base con nivel de abstracción más bajo ( Descomponer el sistema en distintos niveles de funcionalidades, donde la capa más baja es el "core")
		- Avanzar capa a capa utilizando los servicios de la capa inmediatamente anterior. 
		- Componentes estructurados en módulos relacionados
		- **Características**:
			- La capa K se relaciona solamente con la capa K-1. (Cada capa se relaciona solamente con la capa inmediatamente anterior.)
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
###### Ejercicio
Un banco requiere un sistema para manejar las cuentas corrientes de sus clientes. Específicamente requiere las siguientes operaciones:
			- Consulta del saldo de una cuenta
			- Deposito en una cuenta
			- Giro desde una cuenta
			- Transferencia entre cuentas
**Se pide definir este sistema utilizando la arquitectura de Capas**
- Definir Capas:
	- UI
	- Transferencia
	- Giro | Deposito
	- Consulta Saldo
	- Datos


- **Tubos y filtros**
- ![[Pasted image 20240627172331.png]]
	- Estructura aplicaciones en actividades para procesar flujos de datos en que cada actividad (o transformación) es un filtro que está unido por un tubo a los filtros contiguos. 
	- Contexto: Procesamiento de información (flujos de datos).
	- **Requerimiento**:
		- Descomponer el procesamiento en una serie de actividades(filtros) que transforman datos de entrada (recibidos desde un tubo) en datos de salida (entregados en un tubo).
		- Las transformaciones son independientes y no tienen estado
		- Cada actividad es un filtro
		- Los filtros se comunican entre sí mediante tubos
	- **Solución**:
		- Los tubos conectan filtros, con el fin de comunicar.
		- Los filtros provocan cambios en el input/output con el fin de trabajar con información de forma más cómoda.
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
		- Filtros reutilizables
		- Procesamiento paralelo(eficiencia). (generar nuevas instancias de filtros manteniendo la misma cantidad de tubos)
		- Construcción independiente (Cada tubo o filtro puede funcionar de forma independiente.)
	- **Desventajas**:
		- Información no compartida
		- Conversión de datos (ineficiencia)
		- Errores pueden afectar el flujo de procesamiento

###### Ejercicio
El exclusivo club de golf ArquiGolf requiere un sistema para la captación e ingreso de socios. El proceso se inicia cuando un ejecutivo de Atención de Clientes contacta al futuro socio para evaluar si cumple con los requisitos para pertenecer al club. Si los cumple, el futuro socio procede a llenar el formulario de ingreso y lo envía al departamento de Validación de antecedentes. En caso de ser exitosa la validación de los antecedentes aportados por el futuro socio, el formulario es aprobado y enviado al departamento de Finanzas, en donde se calculan las cuotas de ingreso y mensual, las que son informadas al futuro socio. Este tiene un plazo de 2 días para pagar las cuotas iniciales (ingreso y primer mes) utilizando los medios de pago que tienen convenio con el club. Una vez efectuado el pago, el proceso continua en el departamento de Atención de Socios, el que emite las credenciales correspondientes, las envía al nuevo socio e informa a la Portería del club que hay un nuevo socio que está autorizado a ingresar. Con ello, el socio ya puede ingresar a las dependencias del club y disfrutar de sus beneficios.

- **Justifique el patrón arquitectónico que propondría para este sistema, junto a una posible arquitectura genérica.**
Lo que se describe es un flujo de trabajo (workflow), por lo tanto la arquitectura mas adecuada es Tubos y Filtros, en la que cada filtro implementa la funcionalidad de cada uno de los departamentos del club.

Eventualmente, se podría proponer SOA, ya que cada servicio implementaría los requerimientos de cada departamento.

- **Describa los componentes principales del sistema e indique que funcionalidad implementaría cada uno de ellos.**
El componente inicial es el de Atención de Clientes, que recibe el formulario que el futuro socio ha llenado. Luego de validarlo, lo almacena en la base de datos y cambia el estado del formulario a Iniciado.
El siguiente componente es el de Validación de Antecedentes, que se activa al detectarse que hay un formulario Iniciado en la base de datos. Si los datos aportados son aprobados, se cambia el estado del formulario a Validado. El componente de Finanzas se activa al existir en la base de datos un formulario Validado, recupera el formulario, calcula y graba las cuotas y marca al formulario En-financiamiento.

A continuación, se debe ir a un proceso externo de Medios de Pago, en el que el futuro socio procede a cancelar lo que corresponde. Una vez aprobado el pago, se marca al formulario con el estado Financiado.

Finalizado lo anterior, el componente de Atención de Socios emite las credenciales, las envía al socio e incorpora al nuevo socio y lo marca como Socio Activo. Con ello, el socio queda habilitado a ingresar al club, dado que en Portería se va validar que sea un socio activo para permitirle el ingreso a las dependencias del club.

###### Ejercicio
Comente el siguiente párrafo, justificando sus comentarios.

1. **El objetivo del patrón Tubos y Filtros es procesar una cadena de procesos, la que se inicia en el tubo de entrada y luego va pasando filtro tras filtro hasta llegar al tubo de salida.**
En general es correcto, pero cabe recalcar que el procesamiento no inicia en el tubo, ya que este sólo hace fluir la información, sino que en el filtro, que es quién procesa la información.

2. **Ello es posible dado que cada filtro conoce quién le antecede, y a quién debe entregar el resultado de su proceso, información que se obtiene de lo que se ha especificado en la cadena a procesar.**
Falso, los filtros no necesariamente conocen su predecesor ni sucesor, ya que son independientes.

3. **Adicionalmente, los tubos son los encargados de recibir el resultado del procesamiento realizado en el filtro y pasarlo al filtro que sigue, para lo cuál debe hacer las transformaciones de datos que corresponda.**
Esta afirmación es incorrecta, ya que los tubos no son quienes realizan las transformaciones en los datos, sino que los filtros.

- **Pizarrón** 
- ![[Pasted image 20240627183903.png]]
- Se utiliza para resolver problemas complejos que pueden ser descompuestos en partes más pequeñas y manejables, donde estas partes pueden trabajar de manera independiente pero comparten y colaboran a través de un repositorio común, conocido como el "pizarrón"
	- **Patrón útil cuando:**
		- No hay una solución completa y específica para un problema
		- Participan varios sistemas que aportan su conocimiento
		- Ejemplos: inteligencia artificial, reconocimiento de imagenes, toma de decisiones.
	- **Contexto**: dominio en el que no hay una solución completa, Ejemplos: inteligencia artificial, reconocimiento de imágenes, toma de decisiones.
	- **Problema**:
		- Conocimiento parcial de la solución
		- Cada solución requiere diferentes paradigmas
		- El problema abarca muchas especialidades o múltiples disciplinas
		- No es factible una solución completa (No hay una única solución que lo cubra todo.)
		- Hay soluciones parciales que cubren parte del problema
		- Módulos aportan parcialmente a la solución
	- **Solución**:
		- Conjunto de sistemas independientes que contribuyen al problema en su área de especialización.
		- Trabajo colaborativo y coordinado.
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
	- **Análisis**:
		- **Ventajas**:
			- Flexibilidad para incorporar diversas perspectivas y paradigmas.
			- Facilita la contribución de múltiples expertos en diversos campos.
			- Divide un problema grande en problemas más pequeños y manejables.
			- Permite la integración de soluciones parciales para obtener una solución más completa.
		- **Desventajas**:
			- Coordinación compleja entre múltiples sistemas.
			- Riesgo de generar soluciones parciales que no se integran bien en el conjunto.
			- Podría requerir un gran ancho de banda y recursos de computación para gestionar la comunicación y los datos.
			- Dado que está más orientado a la investigación, puede carecer de aplicaciones comerciales directas.

###### Ejercicio
Comente el siguiente párrafo, justificando sus comentarios.

1. **El patrón Pizarrón facilita la resolución de problemas complejos al permitir que múltiples módulos, llamados expertos, colaboren escribiendo y leyendo en un espacio común de datos, denominado pizarra.**
La oración es correcta, no obstante los módulos son denominados agentes, no expertos.

2. **Cada experto tiene un acceso exclusivo a la pizarra, lo que garantiza que los datos no se sobre-escriban por error.**
Falso, cada agente tiene acceso compartido a la pizarra, lo que permite la colaboración.
La sobre-escritura se solventa implementando mecanismos de sincronización.

3. **La pizarra centraliza el control de flujo del sistema, decidiendo cuál experto debe ejecutar en cada momento, optimizando así el uso de recursos. Los expertos actualizan la pizarra con información parcial y resultados intermedios, lo que permite que otros expertos puedan construir sobre este trabajo.**
Falso, la pizarra centraliza los datos y las comunicaciones, pero no controla el flujo de ejecución, esto lo realiza el controlador.

4. **La interacción entre los expertos y la pizarra es gestionada por un coordinador que asegura que todas las contribuciones son validadas y coherentes antes de ser integradas en la solución final.**
La oración es correcta, en términos de agentes.
##### Patrones para Sistemas Interactivos

- **MVC (Modelo Vista Controlador)**
Patrón arquitectónico utilizado en ingeniería de software para separar una aplicación en tres componentes principales: el Modelo, la Vista y el Controlador. Este patrón es especialmente útil para aplicaciones con interfaces de usuario complejas y flexibles.
![[Pasted image 20240627172927.png]]
-  **El sistema se divide en 3 partes:**
		- Modelo: datos y funcionalidad esencial
		- Vista: Comunicación con el usuario
		- Controlador: Controla cambios al modelo
		- Interfaz de usuario: Vista + Controlador
		- Lógica de negocio: Controlador + Modelo
		- Controlador Desacopla la vista el modelo
		- Flexibilidad, mantenibilidad, adaptabilidad
	- **Contexto**:
		- Sistemas interactivos con interfaz flexible, Ejemplo: juegos en línea, aplicaciones empresariales, aplicaciones web.
	- **Requerimiento**:
		- Interfaz con diferente representación:
			- Texto, gráficos, listas, iconos.
		- Paradigmas de ingreso diversos
			- Digitación: cajas de texto
			- Selección: listas desplegables, iconos
			- Ingreso mixto
		- Interfaz cambiante (en constante evolución):
			- Mejora, evolución
		- Facilidad de modificación de la interfaz (sin afectar la lógica del negocio.)
		- Funcionalidad nueva implica modificar interfaz
		- Presentación de la información en multi-formato
	- **Solución**:
		- Separar las responsabilidades en tres componentes principales:
			- Comunicación (vista):
				- Envía requerimientos de usuario
				- Recibe datos (del modelo) y los despliega al usuario
			- Administración (controlador):
				- define el comportamiento del sistema
				- recibe eventos (desde la interfaz del usuario) y solicita servicios al modelo (Coordina la Vista y el Modelo.)
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
			- Modelo soporta múltiples vistas: Una misma lógica de negocio puede tener diferentes interfaces de usuario.
			- Flexible, mantenible, adaptable: Facilita cambios y adaptaciones en la interfaz sin afectar la lógica del negocio / Permite la incorporación de nuevas funcionalidades sin grandes cambios estructurales.
			- Frameworks implementan MVC: Hay muchos frameworks que facilitan la implementación de este patrón.
		- **Desventajas**
			- Modelo acoplado con vistas y controladores: A pesar de la separación, el Modelo, la Vista y el Controlador están intrínsecamente relacionados; uno no funciona bien sin los otros.
			- Vista sin acceso a los datos(ineficiencia): Al no tener acceso directo a los datos, la Vista depende del Controlador para obtener la información que necesita.
			- Complejidad: La separación de responsabilidades puede aumentar la complejidad del sistema.

###### Ejercicio:
 La empresa BigSell necesita un sistema para la venta online de sus productos. Para ello, requiere un sistema de ventas que cumpla con los siguientes requerimientos:
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

**Solución**:
Vista (interfaz de usuario) 
* registro y autenticación de usuarios 
* ver productos, imágenes, descripción, precio 
* manejar el carro de ventas 
	- agregar/quitar productos 
	- modificar cantidades 		
	- desplegar total venta 
* interacción con medios de pago externo 
* finalización de la venta, detalle de productos, valor total, medio de pago utilizado
Modelo (lógica de negocio) 
* gestión de base de datos con información de 
	- clientes 
	- productos 
	- ventas 
* gestión del carro de ventas 
	- productos en el carro (agregar/quitar)
	- valorización del contenido
	- estado de la venta
Controlador (intermediario) 
* autenticación de usuarios 
* interacción usuario/carro de ventas 
* interacción usuario/medio de pago externo 
* direccionamiento de transacciones
Comunicaciones 
* Vista 
	- Controlador: evento HTTP/HTTPS 	
* Controlador 
	- Modelo: interfaz API

###### Ejercicio:
Analice el patrón MVC respecto a los siguientes requerimientos no funcionales:
Mantenibilidad.
Portabilidad.
Verificabilidad.

**Solución:**
- Mantenibilidad: Ya que el patrón MVC separa el sistema en tres componentes principales, Modelo, Vista y Controlador, permite trabajar en partes específicas del sistema sin afectar las otras. Logrando así cumplir mantenibilidad.
- Portabilidad: Dado que existe una separación entre el modelo y la vista, esto permite cambiar la forma de presentación sin modificar la lógica de negocio, y gracias a las múltiples vistas, se puede lograr adaptar múltiples plataformas, cumpliendo la soportabilidad.
- Verificabilidad: La separación de responsabilidades del modelo permite la integración de pruebas unitarias, automáticas y de integración de manera aislada, facilitando la identificación y corrección de errores, consiguiendo una mejor verificabilidad.

Por tanto, el patrón MVC mejora la mantenibilidad, soportabilidad y verificabilidad del
sistema.

###### Ejercicio:
Estamos a casi dos semanas del Plebiscito Constitucional y aún no se tiene un sistema informático que permita, entre otras funcionalidades, lo siguiente:
- Ingresar información de los locales de votación y mesas receptoras de votos.
- Identificar al presidente de la mesa, quien será el usuario autorizado a interactuar con el sistema durante el periodo de votación.
- Registrar las mesas electorales constituidas en cada local de votación.
- Ingresar los resultados de cada mesa electoral, una vez cerrada la mesa y contabilizados los votos emitidos.
- Obtener resultados acumulados por local, región y a nivel nacional.
En cada mesa electoral, habrá un computador que será usado para obtener la información de cada votante, de manera de verificar la cédula de identidad de la persona. Estos computadores estarán conectados a una red de cada local, en la que se ha dispuesto un servidor pequeño para atender a las necesidades de información de los computadores del local. A su vez, estos servidores se conectarán a un servidor regional, los cuáles centralizarán la información de la región para ser enviada al servidor central ubicado en las dependencias del Servel.
1. **.Justificar la arquitectura y el patrón que propondría para este sistema.**
Para este sistema, utilizaría la arquitectura SOA, ya que permitirá que diferentes servicios (como validación de votantes, registro de resultados, consolidación de datos, etc.) se desarrollen, desplieguen y gestionen de forma independiente. Esto ofrece flexibilidad y escalabilidad, esencial en un sistema electoral que puede requerir ajustes rápidos y soportar una gran cantidad de transacciones en poco tiempo.

Junto a esto, propondría utilizar un patrón MVC, ya que este patrón es adecuado para la interfaz de usuario en los computadores de las mesas electorales, donde se necesita una separación clara entre la lógica de negocio (Modelo), la interfaz de usuario (Vista), y el control de la interacción del usuario (Controlador). Facilita el mantenimiento y la escalabilidad del sistema.
2. **Describir los componentes principales del sistema e indicar que funcionalidad implementaría en cada uno de ellos.**
Primero se tiene el Cliente, que corresponde al computador de la mesa electoral. Este tiene los componentes:
- Vista: Interfaz gráfica para los usuarios (presidentes de mesa) que incluye formularios para ingresar datos de votantes, registrar resultados y consultar el estado de la mesa.
- Controlador: Gestiona las interacciones del usuario, valida entradas y coordina las acciones entre la vista y el modelo.
- Modelo: Representa la lógica de negocio y los datos relacionados con el votante, la mesa y los resultados. Se conecta con el servidor local para obtener y enviar información.

Luego, se tienen los servicios y componentes que consideraría por cada servidor:
- Servidor Local en el Centro de Votación: Servicios de Validación de Votantes, Registro de Mesas Constituidas y Almacenamiento Temporal de Datos.
- Servidor Regional: Agregación de Datos Locales, Gestión de Comunicación, Seguridad y Auditoría.
- Servidor Central (Servel): Consolidación Nacional de Datos, Base de Datos Central, Servicios de Reportes, Interfaz de Administración.

Finalmente, se tendría el BUS de datos que controlaría el flujo de datos entre el cliente y los distintos servicios.

- **PAC (Presentación Abstracción y Control)**
- ![[Pasted image 20240627174217.png]]
- El patrón de diseño Presentación-Abstracción-Control (PAC) es otro patrón arquitectónico utilizado para separar una aplicación en diferentes componentes, similar al Modelo-Vista-Controlador (MVC). Aunque ambos patrones tienen el objetivo de separar la lógica de negocio de la presentación de la interfaz de usuario, PAC introduce una estructura jerárquica de "agentes" para lograr una mayor modularidad y desacoplamiento.
- El patrón PAC es especialmente útil para sistemas grandes y complejos, donde la modularidad y el desacoplamiento son cruciales. Sin embargo, esta flexibilidad y modularidad vienen con el costo de una mayor complejidad en la coordinación y comunicación entre los componentes.
	- Estructura jerárquica de agentes cooperativos
	- Provee la funcionalidad de la aplicación
	- Agente es responsable de una parte de la funcionalidad
	- Compuesto por 3 componentes
		- Presentación: Interfaz
		- Abstracción: funcionalidad
		- Control: comunicación con agentes
	- Segmentación del sistema en subsistemas especializados
	- **Contexto**:
		- Sistemas interactivas desarrollados utilizando agentes
		- Sistemas interactivos que requieren una separación clara de funcionalidades.
		- Útil en sistemas donde la colaboración entre agentes es crucial.
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
			- Presentación: aspecto visible del agente (Definir la interfaz que expone un agente a los otros agentes para la utilización de sus servicios. No es exclusivamente la interfaz de usuario.)
			- Abstracción: modelo de datos interno y operaciones sobre ellos
			- Control: conexión entre presentación y abstracción, comunicación con otros agentes (Coordina la comunicación entre la presentación y la abstracción, así como con otros agentes.)
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
			- Asigna responsabilidades específicas (Cada agente tiene una funcionalidad y responsabilidad específica, lo que simplifica la comprensión del sistema.)
			- Funcionamiento independiente (Cada agente funciona de manera autónoma, lo que facilita la mantenibilidad y la incorporación de nuevos agentes.)
			- Soporta multitarea
		- **Desventajas**
			- Sistema complejo (La estructura jerárquica y la coordinación entre agentes pueden complicar el sistema.)
			- Baja eficiencia (Puede ser menos eficiente que un sistema monolítico debido a la necesidad de coordinación y comunicación entre agentes.)
			- Complejo mecanismo de control

###### Ejercicio
Comente el siguiente párrafo, justificando sus comentarios.
1. El patrón PAC posibilita la satisfacción de cada una de las funcionalidades especificas mediante la ejecución de varios agentes, los cuales aportan colaborativamente con una parte de la respuesta.
Verdadero, en la satisfacción de un requerimiento pueden participar varios agentes, los cuáles aportan con lo que les corresponde de la solución.
2. Ello es posible dado que cada agente tiene una copia del proceso de control que administra la ejecución de los agentes, proceso caracterizado con la ‘C’ de la sigla PAC.
Falso, si bien cada agente tiene un proceso de control, se utiliza para sus fines propios. No existe una copia común en todos los agentes.
3. Del mismo modo, el componente de presentación (la ‘P de PAC) le despliega al usuario la parte de la respuesta que le corresponde.
Falso, el componente de presentación define la interfaz que expone un agente a los otros agentes que quieran utilizar sus servicios. No necesariamente es la interfaz de usuario.





##### Patrones Patrones para Sistemas Adaptables

### MicroKernel

Se utiliza para diseñar sistemas operativos y otros sistemas de software donde se busca un alto grado de modularidad, flexibilidad y robustez. Divide el sistema en un núcleo mínimo (microkernel) que proporciona los servicios más básicos y esenciales, y otros componentes o servidores que se ejecutan en el espacio de usuario y manejan las funcionalidades restantes del sistema.

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
			- Vscode como “sistema core” y plugins como módulos
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
		- Portabilidad, si es diseñado de forma independiente del hardware.
		- Flexibilidad para responder a distintas necesidades, mediante la inclusión de servidores específicos.
		- Escalabilidad horizontal, confiabilidad
	- **Desventajas**:
		- Sistema complejo
		- Baja eficiencia
		- Compleja implementación
		- Punto único de falla Microkernel, pero depende de como este definido puede que haya solo en una parte

**Caso de uso**
Sistema Operativo para Dispositivos Médicos

- Microkernel: Gestión de tareas, comunicación entre procesos, gestión de memoria y manejo de interrupciones.
- Servidores:
	- Internos: Permiten acceso a las funcionalidades básicas del microkernel.
	- Externos: Monitoreo de signos vitales, almacenamiento de datos médicos, control de actualizaciones.
- Adaptadores:
	- Adaptador de sensor de datos biométricos y servidor de monitoreo de signos vitales.
	- Adaptador de datos del hardware médico con el servidor de almacenamiento de datos.
- Clientes:
	- Aplicación de supervisión médica.
	- Aplicación de administración de dispositivos.
	- Aplicación de notificaciones de emergencia.



###### Ejercicio
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

###### Ejercicio
Analice cuando se recomienda utilizar el patrón MicroKernel y explique como están estructurados los componentes que forman parte de la arquitectura.

Se recomienda cuando se va a desarrollar un sistema que debe permanecer en el tiempo,
adaptándose a los cambios de la tecnología y de los respectivos requerimientos. Tiene 5
componentes que se estructuran de la siguiente forma (desde el interior del sistema hasta
el exterior):

- Servidores internos: Implementa la funcionalidad interna.
- Microkernel (núcleo): Administra los recursos e implementa la funcionalidad básica y la comunicación entre los componentes.
- Servidores externos: Proveen el acceso a las funcionalidad del núcleo.
- Adaptadores: Comunican a los clientes con los servidores externos.
- Clientes: Reciben los requerimientos de los usuarios a través de la interfaz definida.

###### Ejercicio
Analice el patrón MicroKernel desde los siguientes requerimientos no funcionales:

- Mantenibilidad
- Soportabilidad
- Verificabilidad.

- Dado que Microkernel consiste de un diseño modular, en dónde se pueden agregar nuevas funcionalidades al sistema mediante servidores sin afectar al núcleo y la operabilidad como tal, se puede decir que Microkernel favorece y permite la mantenibilidad del sistema.
- Debido a la modularidad del sistema, un fallo en un servidor específico no afecta a otros, facilitando la identificación y localización del problema. Además, es más fácil implementar trazas de ejecución para cada servidor individualmente, permitiendo así la Soportabilidad.
- El diseño minimalista y robusto del microkernel permite la verificabilidad, ya que en éste se implementan métodos de auto-chequeo. No obstante, puede ser complicado lograr que todo el sistema sea capaz de realizar esto, dada la independencia de los servidores.

###### Ejercicio
Una universidad internacional con múltiples campus en diferentes países (similar a la Universidad de Nueva York, Universidad de California o Universidad de Manchester) ha desarrollado, de manera independiente, sus propios sistemas de gestión académica, administrativa y de recursos humanos. Cada campus tiene su propio sistema de gestión de estudiantes, inscripciones, administración de personal y gestión financiera, todos adaptados a las normativas locales.
El consejo directivo de la universidad ha decidido implementar un portal unificado que permita a estudiantes, profesores y personal administrativo acceder a los servicios y recursos de cualquier campus, sin importar su ubicación geográfica. Además, se requiere que estos sistemas se comuniquen entre sí para compartir información relevante, como registros de estudiantes, historial académico y datos de recursos humanos, permitiendo una administración más eficiente y centralizada.
La universidad ha invertido una considerable cantidad de dinero y tiempo en el desarrollo de estos sistemas individuales, por lo que no es viable desecharlos y construir uno nuevo desde cero. La solución debe integrar los sistemas actuales, preservando las funcionalidades existentes y permitiendo la interoperabilidad entre ellos.
1. **Justifique el patrón arquitectónico que implementaría en este sistema.**
Para este sistema, implementaría un arquitectura de software utilizando el patrón PAC, ya que se debe integrar sistemas independientes (desacoplados) manteniendo su funcionalidad y permitiendo la comunicación entre ellos.
1. **Realice un desglose de los componentes del sistema considerando el patrón a implementar.**
Jerárquicamente, tendríamos:
- Agentes de alto nivel: Estos incluyen la funcionalidad central e interfaz de usuario global, por tanto acá tendríamos un Agente Portal Unificado, que tiene como responsabilidad presentar información de múltiples sistemas.
- Agentes de nivel medio: Estos coordinan la comunicación entre agentes de bajo y alto nivel, por tanto tendríamos un Agente de Comunicación entre Sistemas, permitiendo así la comunicación de un sistema específico con el agente de portal unificado.
- Agente de nivel bajo: Acá se presentan las interfaces específicas de usuario,. interactuando directamente con los datos, por tanto tendríamos agentes para:
	- Gestión académica.
	- Gestión administrativa.
	- Gestión de recursos humanos.

###### Ejercicio:
La empresa TechVision se compone de varias divisiones especializadas, incluyendo Investigación y Desarrollo, Servicios al Cliente, Tecnología de la Información, Ventas, y Marketing. Cada división ha desarrollado y mantenido su propio sistema de software específico para sus necesidades operativas, lo que ha llevado a problemas de interoperabilidad y duplicación de datos entre sistemas. Debido a la expansión reciente y la necesidad de mejorar la eficiencia operativa, la Dirección Ejecutiva ha decidido implementar un sistema central que permita la integración de funciones comunes, como gestión de usuarios, autenticación, y servicios de notificación, mientras permite que cada división siga utilizando sus sistemas especializados para sus operaciones específicas. Este sistema central debe ser altamente modular, permitiendo que se añadan o modifiquen componentes sin afectar al núcleo del sistema, garantizando así la continuidad y adaptabilidad de las operaciones de la empresa. 

**Justificar el patrón arquitectónico que propondría para los sistemas de la empresa, considerando tanto los actuales sistemas como el nuevo sistema central a desarrollar.**
El sistema propuesto por TechVision nos habla de un sistema central, con funciones comunes, altamente modular y mantenible. Para esto, propondría desarrollar el sistema utilizando el patrón de Microkernel, que cumple con los requerimientos provistos, teniendo un núcleo con funciones básicas y que permite que se añadan o modifiquen componentes sin compremeter la continuidad de la aplicación.

### Reflection
Adecuado para sistemas que necesitan adaptarse dinámicamente a cambios en tiempo de ejecución. Separa la aplicación en un nivel base, que maneja la funcionalidad principal, y el nivel meta, que gestiona la información sobre el nivel base y proporciona las herramientas para su modificación.
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

**Contexto**:
- Sistemas que necesitan adaptarse dinámicamente a cambios en tiempo de ejecución. Ejemplos: Frameworks, entornos de desarrollo integrados (IDE), y middleware.
**Problema**:
- Sistemas que deben modificar su estructura y comportamiento durante su ejecución para adaptarse a cambios en el entorno o en los requisitos de los usuarios.
- El sistema debe ser lo suficientemente flexible para permitir estas modificaciones sin una reingeniería completa.

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

###### Ejercicio:
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

###### Ejercicio:
Comente el siguiente párrafo, justificando sus comentarios.

1. El patrón Reflection permite la modificación dinámica de la estructura y
comportamiento de un sistema durante su ejecución.
Verdadero. Es una característica principal de Reflection.

2. Esto se logra mediante la separación de la funcionalidad en un nivel base y un
nivel meta, donde el nivel base contiene información sobre el nivel meta.
La afirmación es incorrecta. Es el nivel meta el cuál contiene información sobre el nivel base.

3. El nivel base incluye la lógica de la aplicación, mientras que el nivel meta provee
mecanismos para analizar y modificar el nivel base en tiempo de ejecución.
Verdadero. La separación de funcionalidades en los niveles es así.

4. La reflexión se basa en la premisa de que el sistema puede modificar su
comportamiento únicamente durante el desarrollo.
La afirmación es incorrecta, pues los cambios de comportamiento ocurren durante la ejecución, no durante el “desarrollo”.



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