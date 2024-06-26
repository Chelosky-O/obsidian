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
		- Ventajas:
			- Componentes estandarizados
			- Cambios afectan el nivel local
			- Reutilización de capas/componentes
		- Desventajas
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
		- Solución:
			- Definir Capas:
				- UI
				- Transferencia
				- Giro | Deposito
				- Consulta Saldo
				- Datos
- **Tubos y filtros**
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
- **Pizarrón** 
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
- **MVC (Modelo Vista Controlador)**
	- El sistema se divide en 3 partes:
		- Modelo: datos y funcionalidad esencial
		- Vista: Comunicación con el usuario
		- Controlador: Controla cambios al modelo
		- Interfaz de usuario: Vista + Controlador
		- Lógica de negocio: Controlador + Modelo
		- Controlador Desacopla la vista el modelo
		- Flexibilidad, mantenibilidad, adaptabilidad
	- Contexto:
		- Sistemas interactivos con interfaz flexible
	- Requerimiento
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
	- Solución:
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
	- Implementación:
		- Separar la funcionalidad de la interacción del usuario
		- Diseñar e implementar
			- el modelo
			- las vistas
			- los controladores
			- la relación entre vista y controladores
	- Análisis
		- Ventajas:
			- Modelo soporta múltiples vistas
			- Flexible, mantenible, adaptable
			- Frameworks implementan MVC
		- Desventajas
			- Modelo acoplado con vistas y controladores
			- Vista sin acceso a los datos(ineficiencia)
			- Complejidad
	- Ejercicio:La empresa BigSell necesita un sistema para la venta online de sus productos. Para ello, requiere un sistema de ventas que cumpla con los siguientes requerimientos:
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
	- Contexto:
		- Sistemas interactivas desarrollados utilizando agentes
	- Requerimiento:
		- Estructurar un sistema interactivo mediante agentes funcionando en forma integrada
		- Generar interfaces flexibles de usuario
		- Separar la presentación de la funcionalidad
		- Bajo acoplamiento
		- Agentes con interfaces propias de comunicación
		- Agentes con estado y datos privados
		- Trabajo cooperativo de los agentes
	- Solución:
		- Definir estructura jerárquica de tres niveles de agentes:
			- Alto nivel: funcionalidad central del sistema, interfaz global de usuario
			- bajo nivel: manejo interfaz específica de usuarios
			- intermedio: relaciona agentes de bajo nivel
		- Cada agente es responsable de una parte de la funcionalidad del sistema 
		- Agente esta compuesto por:
			- Presentación: aspecto visible del agente
			- Abstracción: modelo de datos interno y operaciones sobre ellos
			- Control: conexión entre presentación y abstracción, comunicación con otros agentes
	- Implementación:
		- Definir la funcionalidad central del sistema
		- Estructurar la jerarquía de agentes
		- Definir e implementar cada agente
			- Funcionalidad
			- Interfaz
			- Modelo de datos
			- Mecanismo de control
	- Análisis
		- Ventajas
			- Asigna responsabilidades específicas
			- Funcionamiento independiente
			- Soporta multitarea
		- Desventajas
			- Sistema complejo
			- Baja eficiencia
			- Complejo mecanismo de control

