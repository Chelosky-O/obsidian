# Funciones de la Arquitectura de un Sistema

La arquitectura de un sistema:

- **Define la estructura** del mismo, identificando sus componentes principales (por ejemplo, módulos, clases, o paquetes) y la forma en que estos componentes se organizan y se interconectan.
- **Especifica la comunicación entre componentes**, detallando cómo los diferentes elementos del sistema interactúan entre sí para cumplir con los objetivos del sistema. Esto puede incluir la definición de interfaces, protocolos de comunicación, y mecanismos de intercambio de datos.
- **Plantea los requerimientos no funcionales**, los cuales incluyen:
    - **Restricciones técnicas**: Limitaciones en el uso de ciertas tecnologías, estándares de codificación, o herramientas específicas.
    - **Restricciones de negocio**: Reglas derivadas de las necesidades del negocio, como el cumplimiento de regulaciones específicas o la necesidad de integrarse con sistemas existentes.
    - **Atributos de calidad**: Expectativas sobre el comportamiento del sistema en áreas como rendimiento, seguridad, fiabilidad, y usabilidad.
- **Es una abstracción del sistema**, proporcionando una vista simplificada y conceptual del mismo, que ayuda a comprender su estructura y funcionamiento sin necesidad de entrar en los detalles de implementación.
- **Tiene diversas vistas**, cada una enfocada en aspectos específicos del sistema:
    - **Vista Lógica**: Muestra los principales elementos funcionales del sistema y cómo interactúan.
    - **Vista de Proceso**: Se enfoca en los procesos del sistema, su interacción, y cómo se maneja la información.
    - **Vista Física**: Describe cómo se distribuye el sistema en el hardware o la infraestructura de red.
    - **Vista de Desarrollo**: Se centra en el aspecto del desarrollo del software, mostrando la organización del código, las bibliotecas, y las dependencias.

**Ejemplo**: Imaginemos un sistema de comercio electrónico. La vista lógica mostraría cómo interactúan los componentes como el carrito de compras, la gestión de inventario, y el procesamiento de pagos. La vista de proceso podría describir el flujo de un pedido desde que es colocado hasta que se entrega. La vista física detallaría cómo se despliega el sistema en servidores cloud y la vista de desarrollo podría organizar el código en módulos según la funcionalidad (frontend, backend, base de datos, etc.).

# Los tres pilares básicos de cualquier arquitectura de software son:

1. **Componentes**: Son las unidades fundamentales de software o módulos que realizan un conjunto específico de funciones dentro del sistema. Los componentes son partes discretas del sistema que pueden desarrollarse, probarse y mantenerse de manera independiente. Pueden ser simples, como una función o una clase en un lenguaje de programación, o pueden ser complejos, como un servicio web o un microservicio que realiza una serie de tareas. Los componentes son cruciales porque encapsulan la lógica del negocio, los procesos de datos, y las interfaces de usuario, entre otras cosas.
    
    **Ejemplo**: En un sistema de comercio electrónico, algunos componentes podrían ser el sistema de gestión de inventarios, el procesador de pagos, y la interfaz de usuario del carrito de compras.
    
2. **Relación entre los componentes**: Se refiere a cómo interactúan o se comunican estos componentes entre sí. Esto incluye la definición de interfaces, protocolos de comunicación, y cualquier otro mecanismo que facilite el intercambio de información o la coordinación de actividades entre componentes. La forma en que se definen estas relaciones afecta directamente la modularidad, la escalabilidad, y la mantenibilidad del sistema.
    
    **Ejemplo**: En el sistema de comercio electrónico mencionado, el componente del carrito de compras necesita comunicarse con el sistema de gestión de inventarios para verificar la disponibilidad de productos y con el procesador de pagos para completar transacciones.
    
3. **Ambiente**: También conocido como el entorno de operación, incluye la infraestructura sobre la cual se despliegan los componentes del sistema, así como otros factores externos que influyen en su diseño, como los sistemas operativos, el hardware, las redes, y las interacciones con otros sistemas software. El ambiente también abarca las condiciones operativas, como la carga de trabajo esperada, requisitos de disponibilidad, y estrategias de despliegue y mantenimiento.
    
    **Ejemplo**: El ambiente para el sistema de comercio electrónico podría incluir servidores en la nube para alojar la aplicación, bases de datos para almacenar información del producto y de los clientes, y la integración con servicios de terceros para pagos y logística.
    

Estos tres elementos trabajan conjuntamente para definir la arquitectura de un sistema de software, y cada uno de ellos debe ser cuidadosamente considerado y diseñado para asegurar que el sistema final sea robusto, escalable, y capaz de satisfacer las necesidades de sus usuarios y las demandas del negocio.
# Arquitecto de Software

Su función principal es diseñar el sistema de manera que cumpla con los requisitos tanto funcionales como no funcionales, mientras que la del ingeniero de software es implementar este diseño, construyendo el sistema con base en las especificaciones proporcionadas por el arquitecto.

1. **Administración de riesgo**: Evalúa y propone estrategias para mitigar riesgos asociados al desarrollo del proyecto. Por ejemplo, si se identifica que el plazo de entrega es insuficiente, el arquitecto puede sugerir simplificar ciertas características o explorar soluciones tecnológicas que aceleren el desarrollo.
    
2. **Conocimiento de la tecnología**: Está al tanto de las últimas tecnologías y decide cuáles son las más adecuadas para el proyecto en función de los requisitos y restricciones. Por ejemplo, podría elegir entre utilizar microservicios o una arquitectura monolítica basándose en la escala y complejidad del sistema.
    
3. **Excelentes habilidades de diseño**: Capaz de crear soluciones técnicas innovadoras y efectivas, asegurando que el sistema sea escalable, mantenible, y seguro.
    
4. **Interfaz entre el cliente y el equipo técnico**: Actúa como mediador, traduciendo las necesidades del negocio en requerimientos técnicos y asegurando que el equipo de desarrollo comprenda las expectativas del cliente.
    
5. **Promoción de buenas prácticas de desarrollo**: Fomenta el uso de metodologías de desarrollo eficaces, estándares de codificación, y herramientas que mejoren la calidad del software y la eficiencia del equipo.
    
6. **Puente de comunicación entre los equipos de desarrollo**: Facilita la colaboración y comunicación entre diferentes equipos de desarrollo, especialmente en organizaciones grandes donde pueden existir múltiples equipos trabajando en diferentes aspectos del mismo proyecto.
    

**Ejemplo**: Un arquitecto de software en un proyecto de desarrollo de una aplicación móvil puede optar por usar Flutter para aprovechar su capacidad de compilar hacia múltiples plataformas móviles a partir de una única base de código, promoviendo así la eficiencia y reduciendo los tiempos de desarrollo. También podría trabajar estrechamente con el equipo de seguridad para asegurar que la arquitectura de la aplicación cumple con los estándares de seguridad más recientes, mitigando así los riesgos asociados con la protección de datos del usuario.
# Requerimientos no Funcionales (Atributos de Calidad del Software)

Los requerimientos no funcionales son esenciales para garantizar la calidad, eficiencia y satisfacción del usuario en el uso de un sistema. A diferencia de los requerimientos funcionales, que describen lo que el sistema debe hacer, los RNF definen cómo debe comportarse el sistema en términos de rendimiento, seguridad, mantenibilidad, etc.

1. **Rendimiento (Performance)**: Se refiere a la capacidad del sistema para realizar sus tareas dentro de parámetros específicos.

	- **Throughput**: Mide el número de operaciones o transacciones que el sistema puede procesar en un tiempo determinado. Ejemplo: Un servicio de streaming que puede entregar 100,000 vídeos por segundo a sus usuarios.
	- **Tiempo de respuesta**: El tiempo que tarda el sistema en responder a una entrada específica. Ejemplo: Un motor de búsqueda que devuelve resultados en menos de un segundo.
	- **Plazos (Deadlines)**: Tiempo máximo permitido para que se complete una operación específica. Ejemplo: Un sistema de procesamiento de pagos que garantiza la autorización de la transacción en menos de 3 segundos.

2. **Escalabilidad**: Capacidad del sistema para manejar el aumento de carga de trabajo sin comprometer el rendimiento.

	- **Carga (TPS, transacciones por segundo)**: Máxima carga de transacciones que el sistema puede manejar eficientemente. Ejemplo: Un sitio web de comercio electrónico que soporta 50,000 transacciones por segundo durante el Black Friday.
	- **Conexiones simultáneas**: Número máximo de usuarios o dispositivos que pueden interactuar con el sistema al mismo tiempo. Ejemplo: Un juego en línea que puede soportar 1 millón de jugadores conectados simultáneamente.
	- **Volumen de datos**: Capacidad del sistema para manejar grandes volúmenes de datos. Ejemplo: Una base de datos de clientes que puede gestionar registros de 100 millones de clientes sin degradar el rendimiento.
	- **Despliegue**: Facilidad con la que se puede instalar o desplegar el sistema en nuevos entornos. Ejemplo: Software que ofrece contenedores Docker para facilitar su despliegue en cualquier infraestructura cloud.

3. **Mantenibilidad**: Facilidad con la que el sistema puede ser modificado para corregir defectos, mejorar rendimiento o adaptarse a cambios en el entorno.

	- **Modificable**: Capacidad de realizar cambios sin afectar negativamente el sistema. Ejemplo: Un sistema con una arquitectura modular que permite actualizar componentes individuales sin interrumpir el servicio.
	- **Adaptabilidad a nuevos requerimientos funcionales**: Facilidad para incorporar nuevas funciones. Ejemplo: Un CMS que permite añadir nuevos tipos de contenido mediante plugins o módulos.

4. **Seguridad**: Protección de la información y los procesos del sistema contra accesos no autorizados, uso indebido o malintencionado. Mientras más seguridad tenga un sistema más lento es generalmente.

	- **Autenticación y Autorización**: Verificar la identidad de los usuarios y restringir el acceso a recursos basado en permisos. Ejemplo: Un sistema bancario online que utiliza autenticación multifactor y roles de usuario para proteger las cuentas y transacciones.
	- **Encriptación**: Uso de algoritmos para proteger la información sensible. Ejemplo: Un servicio de mensajería que utiliza encriptación de extremo a extremo para proteger la privacidad de las comunicaciones.
	- **Integridad y No repudio**: Garantizar que la información no sea alterada y que las acciones no puedan ser negadas posteriormente. Ejemplo: Un sistema de votación electrónica que utiliza firmas digitales para asegurar la integridad del voto y el no repudio.

5. **Confiabilidad (Reliability)**: Capacidad del sistema para funcionar correctamente y sin fallos durante un período determinado bajo condiciones específicas.

	- **Disponibilidad**: Porcentaje de tiempo que el sistema está operativo y accesible. Ejemplo: Un servicio en la nube que ofrece un SLA (Acuerdo de Nivel de Servicio) con una disponibilidad del 99.999% (cinco nueves).
	- **Recuperable**: Capacidad del sistema para recuperarse rápidamente después de una falla. Ejemplo: Un sistema de base de datos que utiliza réplicas y backups automáticos para restaurar el servicio en minutos después de un fallo.

6. **Integrabilidad**: Capacidad del sistema para interactuar y operar con otros sistemas, internos o externos.

	- **Interoperabilidad y APIs**: Facilidad con la que el sistema puede comunicarse e intercambiar datos con otros sistemas. Ejemplo: Una aplicación de gestión empresarial que proporciona API REST para integrarse con sistemas de contabilidad y recursos humanos.

7. **Portabilidad**: Capacidad del sistema para operar en diferentes entornos de hardware o software.(Segun profe no hay sistema portable)

	- **Independencia de plataforma**: Diseño del sistema de manera que pueda funcionar en distintos sistemas operativos o dispositivos sin necesidad de modificaciones. Ejemplo: Un software de procesamiento de texto disponible para Windows, macOS y Linux.

8. **Verificabilidad**: Capacidad del sistema para incorporar elementos o mecanismos que no solo permitan su evaluación a través de pruebas, sino también faciliten la autocorrección y la prevención de errores antes de que estos afecten al usuario o al funcionamiento del sistema
	1. Testeable: Indica cuán fácilmente se puede comprobar un sistema para asegurar que cumple con los requisitos definidos. Un sistema testeable facilita la identificación y corrección de errores, permitiendo pruebas eficientes de sus componentes individuales y de su funcionamiento global. Ejemplo: Una aplicación web de comercio electrónico estructurada para permitir pruebas automatizadas de su función de búsqueda y proceso de pago, garantizando que los usuarios puedan buscar productos y completar compras sin errores tras cada actualización.
9. **Soportabilidad**: Capacidad para diagnosticar, reportar y corregir errores encontrados en el sistema.

	- **Diagnóstico y Corrección de incidencias**: Herramientas y procedimientos para identificar y solucionar problemas. Ejemplo: Un sistema operativo que proporciona herramientas de diagnóstico y parches regulares para corregir vulnerabilidades y errores.



# **Preguntas tipo control:**
Analice el siguiente parrafo indicando y corrigiendo los errors:
- El objetivo del requerimiento funcional de mantenibilidad es mantener operativo el sistema el mayor tiempo posible. **R://** La **mantenibilidad** se refiere a la facilidad con la que un sistema puede ser modificado para corregir fallos, mejorar su rendimiento o adaptarse a un cambio de entorno. Lo que se describe es más adecuado para la **confiabilidad**, que se enfoca en la capacidad del sistema para funcionar sin fallos bajo condiciones especificadas durante un periodo de tiempo determinado.

- El optimo a alcanzar es que opere al 99,999% del tiempo, regla conocida como la de los cinco nueves. **R://** Esta afirmación es verdadera. La regla de los cinco nueves es un estándar de la industria para sistemas de alta disponibilidad, indicando que el sistema debe estar operativo el 99,999% del tiempo, lo que equivale a aproximadamente 5.26 minutos de tiempo de inactividad no planificado por año.

- Para lograr los cinco nueves, un sistema debe diseñarse con componen redundantes que puedan tomar el control de la operación del sistema en el caso que uno de ellos falle. **R://** Esta afirmación es verdadera. La redundancia de componentes es una estrategia clave para lograr altos niveles de disponibilidad y confiabilidad, permitiendo que el sistema continúe funcionando incluso si parte de sus componentes fallan.

- Si esto ocurre, utilizando los procesos definidos al incluir el requerimiento de mantenibilidad se podra corregir el error y restaurar el sistema a su estado normal del procesamiento. **R://** falso, la soportabilidad se refiere a la capacidad de un sistema para ser soportado, incluyendo actividades de mantenimiento y corrección de errores para restaurar la funcionalidad.


---
PPT2
# Diseño de Software

**Fase 0: Analizar el Contexto** → Donde se va a instalar
**Fase 1: Estructuración** → Identificar componentes y sus relaciones
**Fase 2: Modelo de control** → Comportamiento de los componentes
**Fase 3: Descomposición modular** → Diseño detallado

## Contexto
**Requerimientos funcionales** → Lo que debe hacer el sistema
**Requerimientos no funcionales** → Atributos de calidad requeridos
**Ambiente Operacional** → Hardware y software involucrados
**Restricciones**

## Estructuración
- Descompone el sistema en un conjunto de subsistemas  
- Utiliza un diagrama de bloques que muestra la estructura del sistema  
- Indica el flujo de datos entre los componentes del sistema  
- Muestra las interfaces que provee el sistema

## Modelos de Estructuración
### Modelo de repositorio
Ocurre cuando hay grandes cantidades de datos que deben ser compartidos  
- Gestión centralizada de datos  
- Almacenamiento centralizado / distribuido  
Modelo pasivo  → Almacena esto, relaciona esto
Modelo proactivo → El modelo le avisa a sus usuarios cuando hay modificaciones en los datos.

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
### Cliente/Servidor
Estructurado en base a  
- Servidores que ofrecen servicios específicos  
- Clientes que requieren servicios  
- Redes de comunicación que conectan ambos  
Es un modelo parcialmente distribuido (el procesamiento está dividido tanto en el cliente como en el servidor)
- Ventajas
	- Procesamiento distribuido
	- Datos distribuidos
	- Escalable (definir más instancias de los servidor)
- Desventajas
	- Datos no compartidos (cada servidor tiene sus propios datos)
	- Administración de datos en cada servidor
	- Performance deteriorada (ya que existe un medio de comunicación entre cliente y servidor, el cuello de botella es la red)
	- No hay registro centralizado de servicios (No se que servicios están operativos y cuales no, tampoco se donde están. Todo es en base a prueba y error)
### Modelo de capas
Conjunto de capas de software que ofrecen servicios específicos  
Cada capa tiene una interfaz claramente definida  
Desarrollo independiente de las capas

Ventajas  
- Desarrollo incremental  
- Flexible  
- Mantenible  
Desventajas  
- Difícil estructuración  
- Dependencias cruzadas  
- Baja performance
### Objetos distribuidos
Cada componente (objeto) define los datos y metodos que pueden ser invocados  
Cada objeto puede proveer y recibir servicios  
Objetos se comunican a través del sistema ORB (Object Request Broker)  
Arquitectura compleja

Ventajas  
- Diseño flexible  
- Fácil agregar objetos  
- Configuración dinámica  
- Escalabilidad, mantenibilidad  
Desventajas  
- Compleja construcción  
- Bajo rendimiento  
Objetos distribuidos
### Arquitectura Orientada a Servicios (SOA)
Evolución del modelo cliente/servidor  
- Clientes  
- Bus (Enterprise Service Bus)  
- Servicios independientes  
Ambiente de integración basado en estándares:  
- XML, JSON, SOAP, REST  
Servicios administrados centralizadamente  
Conecta aplicaciones como servicios  
Flujo de datos controlado  
Provee escalabilidad y seguridad

Ventajas  
- Reutiliza sistemas existentes  
- Bajo nivel de acoplamiento  
- Escalabilidad, mantenibilidad, interoperabilidad,  
reusabilidad  
Desventajas  
- Dependencia de estándares incompatibles  
- Complejidad en entornos grandes

#### Pasos SOA
1. Identificar los Servicios
2. Definir las transacciones de cada servicio
3. Especificar las Interacciones entre los servicios
4. Definir modelo de Datos
5. Especificar el funcionamiento de cada servicio
6. Definir la interfaz de usuario
### Arquitectura Cloud
Externalización de servicios computacionales  
- Infraestructura - IaaS  
- Plataforma - PaaS  
- Aplicación – SaaS  
Recursos elasticos (pay what you use)

Ventajas  
- Servicios ubicuos  
- Reducción de costos (?)  
- Disponibilidad, Escalabilidad, Elasticidad  
- Flexibilidad, Movilidad  
Desventajas  
- Dependencia de ente externo  
- Seguridad  
- Confidencialidad  
- Conectividad

## Modelos de control
- Control del flujo entre componentes  
- Control Centralizado  
- Control Basado en Eventos
### Control centralizado
- Un componente controla la ejecución del sistema  
#### Modelo Call-Return  
- Simple  
- Predecible  
- Rígido  
- Testeable  
- Bloqueante  
- Complejo manejo de excepciones

#### Modelo Administrador  
- No bloqueante  
- Coordinación de procesos  
- Lógica centralizada  
- Posible cuello de botella

### Control basado en Eventos
- Control descentralizado  
- Control no bloqueante  
- Manejan eventos generados externamente  
	- Transmisión Múltiple (broadcast)  
	- Manejador de Interrupciones
#### Transmisión múltiple
- Usan modelo Publicador-Suscriptor
	- Componentes Distribuidos
		- Publican servicios
		- Gatillan eventos
		- Suscriben eventos
- Ventajas
	- Activación descentralizada de componentes
	- Distribución de componentes
	- Evolución simple
- Desventajas
	- Respuesta incierta
	- Varios manejadores del mismo evento
#### Manejo de interrupciones
- Sistemas en tiempo real
- Manejador para cada tipo de interrupción
- Respuesta inmediata
- No bloqueante
- Procesamiento paralelo

## Descomposición modular
- Componentes divididos en módulos
- Posibilita visualizar el modelo de control
- Modelo de objetos
- Modelo de flujo de datos

### Modelo de Objetos
- Conjunto de clases débilmente acopladas  
- Interfaces bien definidas  
- Identifica atributos y métodos  
- Objetos creados a partir de las clases  
- Coordinación de operaciones entre objetos

### Modelo de Flujo de Datos
- Descomposición en procesos funcionales  
- Transformación de entradas en salidas  
- Dependencia entre procesos  
- Flujo predeterminado  
- Adecuado para procesos batch

## Arquitecturas de Dominio específico
- Modelos específicos para algún dominio  
### Arquitecturas genéricas  
- Generalización de sistemas reales  
- Análisis de sistemas existentes  
### Arquitecturas de referencia  
- Idealización de una arquitectura específica  
- Estudios del dominio de una aplicación  
- Estándar de facto en su dominio



# Ejercicios
1. El gerente general de la empresa en que usted trabaja ha escuchado el término "Arquitectura de Software" y como él no es técnico le ha pedido que le explique en que consiste, pero sin utilizar terminología técnica. ¿Qué haría usted para responder a este requerimiento?
**Respuesta**: La arquitectura de software se refiere a la forma en que un programa de computadora está diseñado y organizado. Es como el plano de una casa, donde se establecen los cimientos y la estructura para que todo funcione de manera eficiente y se puedan agregar características adicionales. Al igual que un arquitecto diseña una casa para que sea funcional y atractiva, un arquitecto de software diseña el programa para que sea fácil de entender, modificar y mantener.

2. Describa 4 competencias que debe tener el arquitecto de software.
**Respuesta**:
- Administración del riesgo.
- Excelentes habilidades de diseño.
- Interfaz entre el cliente y el equipo técnico.
- Puente de comunicación entre los equipos de desarrollo.

3. Explique cuales factores son utilizados para medir la escalabilidad de un sistema de software.
**Respuesta:**:
- Carga: Cantidad de transacciones por segundo que puede soportar el sistema.
- Conexiones simultáneas
- Volumen de datos

4. Describa las diferencias que tienen entre si los siguientes requerimientos no funcionales:
- Mantenibilidad
- Soportabilidad
- Verificabilidad
**Respuesta**: La mantenibilidad está enfocada en la facilidad de modificación del sistema, mientras que la soportabilidad se enfoca en poder diagnosticar y resolver problemas en el sistema en ejecución. finalmente, la verificabilidad corresponde a la capacidad del sistema de comprobar su propio funcionamiento.

5. Explique qué se debe considerar al especificar una arquitectura de un sistema.
**Respuesta**: Al especificar una arquitectura se deben considerar los siguientes factores:
- Requerimientos funcionales: Que es lo que debe hacer el sistema.
- Requerimientos no funcionales: Que atributos de calidad son requeridos.
- Ambiente operacional: Dónde se utilizará el sistema (Hardware y Software involucrados).
- Restricciones: Las restricciones pueden ser tecnológicas, temporales, de personal, etc.

6. Analice cinco requerimientos no funcionales que podrían ser considerados al especificar una arquitectura para un sistema que deba desarrollar.
**Respuesta**:
- Escalabilidad: Algunas arquitecturas facilitan la escalabilidad del sistema (e.g. Cliente / Servidor) mientras que otras arquitecturas son más difíciles de escalar.
- Mantenibilidad: La especificación de una arquitectura de software puede aumentar la mantenibilidad de un sistema. Debido a que si el sistema se diseña bien (y no es monolítico), se puede alterar o añadir componentes sin afectar el resto del sistema.
- Performance: Algunas arquitecturas requieren mayor comunicación entre componentes que otras (e.g. SOA), lo que genera un deterioro en la performance en comparación a un sistema monolítico.
- Seguridad: La arquitectura especificada puede facilitar que el sistema sea seguro (e.g. añadir una capa de seguridad en el modelo de capas) mientras que en otras (e.g. Cliente / Servidor) es más complicado.
- Integrabilidad: Algunas arquitecturas facilitan el uso de sistemas ya construidos anteriormente (e.g. SOA), por lo que debe considerarse si se requiere interoperar con otros sistemas.

7. Indique las características de las siguientes arquitecturas genéricas y analice sus ventajas y desventajas:
- Modelo de Repositorio.
- Cliente / Servidor.
- Arquitectura Orientada a Servicios (SOA).
**Respuesta**:
- Modelo de Repositorio Estructurado en base a una gran cantidad de datos que debe ser compartida. El almacenamiento de los datos puede ser centralizado o distribuido.
	Ventajas: – Eficiente en la compartición de datos. – Administración centralizada de los datos. – Escalable y fácil de mantener.
	Desventajas: – Fuerza un modelo de datos. – La base de datos es un punto único de falla. – Dificulta la modificación del modelo de datos.

- Cliente / Servidor Servidores que ofrecen servicios específicos y Clientes quienes requieren servicios, conectados por una red de comunicación. El modelo es parcialmente distribuido.
	Ventajas: – Procesamiento distribuido. – Almacenamiento distribuido. – Fácil de escalar.
	Desventajas: – Datos no compartidos. – Baja performance. – No hay registro centralizado de servicios.

- Arquitectura Orientada a Servicios (SOA) Ambiente de intergración basado en estándares, con servicios administrados centralizadamente. Evolución del modelo Cliente/Servidor.
	Ventajas: – Reutiliza sistemas existentes. – Bajo nivel de acoplamiento. – Escalable, mantenible e integrable.
	Desventajas: – Alta dependencia a estándares. – Baja performance.

8. Explique en qué contexto y para que tipo de sistemas es recomendable utilizar el modelo de repositorio.
**Respuesta**: El modelo de repositorio es recomendable cuando todos los componentes de un sistema tienen el mismo modelo de datos y se requiere administración centralizada de estos.

Por ejemplo, un tipo de sistema para el que sería recomendable este modelo es un e-commerce. El sistema necesita acceder a grandes volúmenes de datos tanto por el lado del cliente, como por el lado de la administración del negocio.

## Caso 1
A usted le han solicitado el desarrollo urgente de un sistema, cuya primera versión, con el 30% de los requerimientos funcionales implementados, debe estar operativa en dos semanas. Luego, tiene 4 semanas para finalizar la implementación de los restantes.  
En este contexto, analice tres requerimientos no funcionales que le pueden ayudar a cumplir con el plazo establecido y tres que lo retrasarían.

Solución Requerimientos no funcionales que ayudan a cumplir con el plazo establecido:

- Mantenibilidad: Si el sistema es mantenible, es más fácil implementar el resto de los requerimientos funcionales.
- Integrabilidad: Dependiendo del contexto, permitir que el sistema funcione en conjunto con sistemas ya existentes puede disminuir la cantidad de trabajo que debe hacerse.
- Escalabilidad: Si el sistema es escalable, se pueden añadir nuevos requerimientos sin problemas y el sistema podrá crecer a medida que se implenta el resto de los requerimientos.

Requerimientos no funcionales que retrasarían el desarrollo:

- Confiabilidad: Para lograr confiabilidad se deben tener en cuenta muchos factores que pueden afectar el funcionamiento del sistema.
- Verificabilidad: La verificabilidad implica que el sistema pueda probarse a sí mismo, por lo que se requeriría de trabajo adicional para cada componente del sistema.
- Seguridad: Si se requiere un alto nivel de seguridad, puede ser necesario dedicar una cantidad significativa de tiempo para lograrlo. Esto puede retrasar el desarrollo del sistema.


## Caso 2
Las empresas pertenecientes a un holding de empresas (del tipo de Cencosud, Falabella o Walmart) han desarrollado, independientemente unas de otras, sus propios sistemas de atención a clientes, mediante sitios web y sistemas internos. El directorio del holding ha planteado la necesidad de integrar en un solo portal los diversos sistemas

El directorio del holding ha planteado la necesidad de integrar en un solo portal los diversos sistemas de atención, de manera que los clientes tengan una experiencia única e integrada, independientemente de la empresa con la que estén interactuando.

Asimismo, requiere que los sistemas internos conversen entre si, de manera de aprovechar la información que cada uno administra. Así, por ejemplo, en lugar de tener varios sistemas que manejen la cartera de clientes, se plantea tener uno solo, de manera tal que pueda ser accedido por los sistemas que lo requieran. Cada empresa ha gastado una gran cantidad de dinero en el desarrollo independiente de sus sistemas y se requiere no perder esa inversión hecha. En definitiva, no se está planteando hacer nuevos sistemas, sino que adaptar los actuales sistemas para que funcionen mancomunadamente.

Al respecto, se le pide lo siguiente:

- Explicar la arquitectura que escogería para responder a lo pedido
- Analizar las ventajas y desventajas de la arquitectura elegida
- Justificar tres requerimientos no funcionales que debieran estar contemplados en la solución propuesta

Solución: La arquitectura que escogería para responder a los requerimiento es SOA (Arquitectura Orientada a Servicios). La razón para elegir SOA por sobre otras arquitecturas es que se desea integrar distintos sistemas ya existentes, lo que se puede realizar a través de un bus de servicios.

Ventajas:

- Reutilización de los sistemas existentes.
- Bajo acoplamiento.
- Alta escalabilidad.

Desventajas:

- Dependencia a estándares.
- Baja performance.
- Alta complejidad, debido a la gran cantidad de servicios involucrados.

Requerimientos funcionales a contemplar en la solución:

- Seguridad: Debido a que el sistema manejará administrará una cartera de clientes, es necesario que este sea seguro ya que una vulnerabilidad en el sistema podría afectar gravemente a las empresas del holding.
- Integrabilidad: Es necesario que el sistema presente interoperabilidad entre los distintos subsistemas que lo compondrán para que estos se presenten como un sistema único para el usuario.
- Escalabilidad: Debido a que el sistema a implementar será usado por un holding de empresas este estará sometido a una gran carga, la cual puede variar bajo ciertas circunstancias (e.g. Falabella en un cyber day). Por lo tanto el sistema debe ser escalable para poder manejar estos aumentos de carga.

## Caso 3
Se requiere desarrollar un sistema que permita ingresar y reportar la votación obtenida por cada candidato en cada una de las mesas receptoras de sufragios en todo el país. Las mesas receptoras están agrupadas en locales de votación a cargo de un jefe de local.

Entre otras funciones, el jefe de local es el encargado de recolectar las actas de votación de cada mesa receptora e ingresar los resultados al sistema. Para ello, dispone de un notebook con conexión a internet.

Se requiere, además, que el sistema genere un informe con los resultados disponibles hasta ese momento y consolidados por cada candidato, con una periodicidad preestablecida en el sistema. Este reporte debe considerar varios niveles de agrupación de los resultados, tales como, a nivel de la mesa receptora, del local de votación, de la comuna, del distrito (para los diputados), de la región senatorial (para los senadores) y, finalmente, a nivel país (para el presidente).

Considerando que las elecciones son en 23 días más, se pide lo siguiente:

- Analizar y justificar tres requerimientos no funcionales que el sistema debe satisfacer
- Analizar y justificar cuál de las arquitecturas de software genéricas va a usar para desarrollar el sistema
- Describir brevemente la funcionalidad de tres de los componentes que, a su juicio, son los más importantes del sistema a desarrollar.

Solución: Requerimientos no funcionales a satisfacer:

- Seguridad: Debido a que el sistema manejará datos electorales y los enviará por internet este debe ser seguro. Una vulnerabilidad en el sistema podría causar desde reportes incorrectos hasta fraude electoral.
- Verificabilidad: El sistema debe ser capaz de comprobar su propio funcionamiento debido a que será ejecutado en distinto hardware a lo largo de todo el país, y se debe asegurar que cada instancia funcione correctamente.
- Soportabilidad: En caso de alguna incidencia que perjudique el funcionamiento del sistema, deben existir herramientas de diagnóstico con el fin de poder solucionar dichos inconvenientes.

Arquitectura a utilizar: Debido a que existirán múltiples instancias de un subsistema que enviarán datos y que se debe realizar un análisis de los datos como conjunto se usará el modelo de repositorio. Esta arquitectura es eficiente para compartir datos, y se tiene una administración centralizada de estos.

Componentes principales:

- Componente de seguridad (e.g. un login) que permita autenticar que la persona que intenta ingresar datos es el jefe del local de votación.
- Componente que reciba los datos del local de votación y los envíe hacia la base de datos. Debe utilizar un protocolo de comunicación seguro (e.g. TLSv1.2).
- Componente de análisis de datos que genere el informe con los resultados cada cierto tiempo.