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



