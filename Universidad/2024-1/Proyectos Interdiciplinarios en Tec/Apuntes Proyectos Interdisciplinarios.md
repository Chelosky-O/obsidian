# 11-03

Profesor: Mauricio Hidalgo

3 Productos
- Levantamiento requerimientos de usuario
- Desarrollo de Proyecto

# 14-03

## Reforzamiento

### Alcance de un Proyecto de SW
Es la identificación de los objetivos del proyecto, sus metas, las fases que incluye y sus tareas, los recursos, el presupuesto y la programación temporal.

Nos ayuda a identificar:
- Limitaciones
- Condicionales
- Que aspectos o parámetros del proyecto están o no están incluidos.

Existen contratiempos, limites de presupuestos, que bajo que hago, todo impacta en algo.
Es imposible que un proyecto sea algo bueno rápido y barato a la vez.

Requerimiento != Requisito

Hay que preguntar si es realmente necesario lo que pide al cliente.
- Consistente → Que tiene Solvencia, por lo que es necesario, no puede haber algo que sea un requisito o requerimiento que no este entre lo necesario.
- Correcto → Que se acopla lo que se puede utilizar.
- Factible → Algo que se puede cumplir. Ej: Estimar un tiempo claramente falso.
- Modificable → No es lo mismo un software que tenga la vida de una persona a uno de un banco o una pagina.
	- Misión critica: Software por objetivo, software tipo militar, lanzamiento misiles
	- Negocios critica: Bancarios fines monetarios
	- Seguridad Critica: Vida personas etc.
- Claro → Que sea sepa para que se utiliza el software


## Etapas generales del proceso de desarrollo
En este curso se verán en las primeras 3 etapas.
- Análisis de requisitos: tomamos requerimientos y los transformamos en aspectos que un software debe cumplir, que haremos y como en que orden etc.
- Diseño y arquitectura: 
- Implementación:
- Pruebas:
- Implantación
- Mantenimiento: 

## Modelos de desarrollo:
- Cascada: No permite sistema con errores
- Iterativo o incremental: Permite sistema con errores, es el base de metodologías de desarrollo ágil. se centro en softwares de negocio critico.
- En espiral: este no se usa.
- Prototipos reutilizables.
## Metodologías de desarrollo ágil

### XP
Extreme Programming
Programación en pares, 1 programa y el otro está atento mirando.

Hay distintos esquemas, novato novato, novato experto, experto experto.


----
### Scrum
Gestión.

Se utiliza para gestionar de manera eficiente la fase de desarrollo, prueba y transición.

Influye mucho el modelo iterativo incremental.

Product Owner no es el cliente, es el que se comunica con el.

Scrum permite gestionar tiempos y ver si una persona se atrasa, se puede reasignar la responsabilidad.

---
### Rational Unified Process RUP
Toma todo el ciclo del desarrollo, lo divide en 4, y divide los esfuerzos que se deben hacer para cada una de las etapas.

Inception: Modelo y requerimientos.
Entender el negocio es necesario.

---
### Requisitos de SW

Descripción de todas las restricciones, Servicios y Funciones que debe poseer el software

Problemas posibles:
- Confusión de requerimientos
- Baja participación del cliente
- Ambigüedad: Que no todo sea creatividad del desarrollador
- Priorización: Que es mas importante, lo que el software hace o las características que debe tener, Lo no funcional, son muchos mas importantes :o. Interfaz fea
- Proceso de Cambio inapropiado: Como gestiono los cambios de requisitos.

Resultado del proceso : Documento de Especificación de Requisitos de SW (SRS)


---
Requisitos de SW
mal llamado Requerimiento

| Identificación del requerimiento | RF02                                                                                                                                                                         |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nombre del requerimiento:        | Registrar Usuarios.                                                                                                                                                          |
| Características:                 | Los usuarios deberán registrarse en el sistema para acceder a cualquier parte del sistema.                                                                                   |
| Descripción del requerimiento:   | El sistema permitira al usuario (estudiante, docente y administrador) registrarse. El usuario debe suministrar datos como: CI, Nombre, Apellido, E-mail, Usuario y Password. |
| Requerimiento NO funcional:      | - RNF01<br>- RNF02<br>- RNF05<br>- RNF08                                                                                                                                     |
| Prioridad del requerimiento:     | Alta                                                                                                                                                                         |

---
Requisito funcional: El que describe funciones del sistema (lo que debe hacer) y declarar salidas ante input y comportamiento en situaciones particulares.

Requisito no funcionales

---
## Técnicas para levantar requerimientos:

- Análisis de documentación
- Etnografía : observación de comportamiento, elimina el cambio, es mejor el cambio.
- Entrevistas y grupos focales: Hacer entrevistas con usuarios, con el cliente se hacen reuniones.
- Encuestas:
- Workshops (JAD) y Brainstorming.

## Actividad propuesta
Refuerce su conocimiento previo a través del estudio de la Fase de “Levantamiento de  
Requerimientos” y “Especificación de requisitos”.

Libro Ingeniería de Software de sommerville
# 18-03
#Clase2

Dominio de aplicación != Dominio del sistema
Dominio de aplicación es entorno que regula el desarrollo


### Dominio de Sistema

Pueden gobernar a oros programas

ej: windows, nvidia drivers
### Software de aplicación
Sin relación directa con el funcionamiento del computador
Sirven para funciones determinadas como herramientas de trabajo
Incluidos o posteriormente instalados despues del software

ej: Google Chrome

### Software ingeniería y ciencias
Algoritmos devoradores de números
Campos científicos
SW de mercado
ej: stellarium, matlab

### Software Incrustado

Funciones limitadas y particulares
Capacidad de funcionamiento y control

EJ: sensores, funcionamiento de estufas.
### Software línea de productos

Control de inventario

Dirigido a mercados limitados, masivos, funciones especificas.

Ej: Neflix, pstore.

### Aplicaciones Web
BDD corporativas, se ejecutan en navegador web

ej: mercado libre, sap

### Software de Inteligencia artificial
Uso de algoritmos no numéricos.

Fuente abierta, diversas áreas, requieren gran capacidad de hardware.

Ej: Tensor flow , Keras, Kaluel

Prueba alfa: Prueba con usuario pero función muy acotado.
Beta: Pruebas en producción.


### Requisitos de Usuario

Tienen problemas asociados.

###### Problemas:
*Arreglar es mas caro que hacer*
Falta de claridad
Confusión de Requisitos 

Conjunción de Requisitos: diversos requisitos diferentes pueden expresar la misma funcionalidad.

---
Reducir ambigüedad

Software que sea intuitivo


Pensar + Sentir + Usar


Requerimiento lo que la gente pide
Requisito lo que haremos en el software

---
- No deben tratar de como se debe diseñar o implementar.
- Se debe describir el comportamiento externo del sistema y sus restricciones operativas.
- Son una expresión de requisitos funcionales pues reflejan las operaciones que el sistema llevará a cabo.

---

SqlServer y C# → Para crear cosas de office, tiene buen Portabilidad en cuanto a utilizar office.

---

Los requisitos de usuario se refinan, pero se hacen bien.

### Requisitos de Dominio


Ej: tener conexión a internet.

Future options (Te lo doy pero me pagas más después):
- Formas de pago
- Garantías
- Valor actual y futuro
- Multa

Regla de Negocio → Se sigue si o si.
Define como se hace.

---


# 21-03

Requerimientos funcionales : Requisitos que definen una función del software o de sus componentes.
Son aquellos que establecen servicios o funciones que proveen el sistema.

Requisitos no funcionales:
Criterios que se pueden utilizar para evaluar la operación de un sistema en lugar de sus comportamientos específicos.

Son una declaración de propiedades emergentes del sistema. Por ejemplo: Disponibilidad → Que el sistema se encuentre en operación en el momento que sea necesario, Fiabilidad, Tiempos de respuesta, entre otras.

También conocidos como "Atributos de calidad" en el ámbito de la Arquitectura de Software.

---

Requerimiento de seguridad safety  → Vida
Requerimiento de seguridad Security → Seguridad de información
Requerimiento de confiabilidad → que su resultado es confiable

Constitución → Ley → Regulación

## SQuaRE (System and Software Quality Requirements and Evaluation)
Descripción

- Adecuación Funcional
Capacidad del producto para proporcionar funciones que satisfacen las necesidades declaradas e implícitas, cuando el producto se usa en las condiciones especificadas.

- Eficiencia de desempeño
Como funciona a la realidad vs como lo probé

Formas de acceso a servidor fisico, etc

Entregar el producto perfecto a contra la perfección  


- Compatibilidad
Red de red o transantiago

Pago integrado con la tarjeta bip

- Usabilidad
Preguntar si les va a servir o no 
Cuanto se demora en aprender su aplicación
Protección errores de usuario
Estetica
Accebilididad → Software para persona ciega

- Fiabilidad
Capacidad para satisfacer fiabilidad en condiciones normales

Que sea maduro
Disponibilidad → Que este operativo y accesible cuando lo necesito
Tolerancia a fallos → que opere bien según lo previsto.
recuperación → recuperar datos en caso de interrupción o fallo


- Seguridad
Confidencialidad → Protección contra el acceso de datos
Integridad → prevenir acceso o modificaciones no autorizadas.
Se diferencia en que uno solo ve y el otro altera.

 No repudio → Que no se pueda negar que acción se hizo y quien la hizo
 Responsabilidad → paso algo y puedo saber quien la hizo
 Autenticidad → capacidad de demostrar la identidad de un sujeto 


Giadach maneja la bd de Corp Banca



- Mantenibilidad

Modularidad → Capacidad q un cambio tenga un impacto mínimo en los demás.

Reusabilidad → Capacidad que sea utilizado en mas de un sistema de software.

Analizabilidad → Tecnica para 

Capacidad para ser modificado → 
Esclerosis de codigo → Punto que un codigo llego a un nivel donde modificas algo y caga todo lo demas. Si eso pasa no lo toques

Capacidad para ser probado → todo se puede probar si no está mal planteado

- Portabilidad

Adaptabilidad
Portal canvas funciona en cualquier navegador
Sap no

Capacidad para ser instalado
que sea facil de instalar
Algunos son faciles de instalar pero de desinstalar??

Capacidad para ser reemplazado
Word con google docs

---
LUNES NO FALTAR













# 25-03

- Próximas 3 clases no se viene
- 3 Evaluaciones hay, todas en azules

Torniquetes.
Elicitación de requerimientos

---

Personas relevantes no contratadas por U:

- Personal de Aseo
- Casino

---





# 11-04

