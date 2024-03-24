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
	- API'S → Poder usar otros sistemas a través de las funcionalidadegits
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

- Ventajas:
	- Modo eficiente de compartir datos
	- Administración centralizada de los datos
	- Seguridad, Escalabilidad, Mantenibilidad
- Desventajas:
	- Fuerza un modelo de datos → La mas terrible
	- Difícil cambio del modelo de datos
	- Política centralizada de administración
	- Punto único de falla → El mas critico







