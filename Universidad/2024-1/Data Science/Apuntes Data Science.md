# 07-03

Marzo -> Buscar proyecto
## Data Science:

Academia vs Industria
- La academia busca Reducir el error
- La industria busca Aumentar Ingresos o Disminuir Gastos

Interpretabilidad -> No inventar Razones, Motivos o Pesos (Que es lo mas relevante)

Random Forest: Entrega Pesos

## Distribución de Probabilidad

Todo tiene Bayes

## Evaluaciones

Control 1 20% 
Control 2 20%
Proyecto 60%
	Presentación intermedia 20%
	Feria (Demos) modelo como servicio 40%

# 11-03

Profesor O. Ceballos

## Ciencia de datos
### Frameworks Data Science

Son formas de trabajar

#### KDD (Knowledge discovery in DataBases)
Datos

#### OSEMN

---
En el contexto de Machine Learning
Clasificación da 1 dato como respuestas

$$
Y=M(X)
$$
Donde M = Modelo y X = Un conjunto de datos estocásticos

#### CRISP-DM


# 14-03
*Ppt clase 3*
## Train/Dev/Test y Distribuciones
Se dividen los datos normalmente es Train y Test pero ojala fueran los tres.

### Velocidad Progreso

Normalmente se desarrolla en local.

Se busca configurar conjuntos dev y test.

El dev es el conjunto de validación del modelo. Es un conjunto pequeño.
El test debe ser más grande.

Train → deb → test
60% → 20% → 20%

Cuando se hace DeepLearning es 90% 2% 8%

---
Problema de distribución

## Distribuciones distintas
Tradicionalmente se utiliza el 70/30 para entrenamiento y test
o un 60/20/20 para entrenamiento dev y test.

## Deep learning
98/1/1

---
Hay que revolver bien los datos a utilizar.

---
*Ppt Clase 2*

## Single Number Evaluation Metric
Para medir si va bien o va mal

Si va bien, que tiene buena precisión, que se equivoque poco.

---
## Precisión y recall
Búsqueda algo en palabras, cuantas de esas búsquedas retornaron lo que precisamente estaba buscando.

Son métricas utilizadas para evaluar rendimiento de un clasificador.

### Precisión
Proporción de casos positivos identificados sobre el total de casos positivos identificados.

Sabiendo cuantos eran, cuantos me clasifico correctamente?

Falso positivo: 

### Recall
Proporción de casos positivos correctamente identificados sobre el total de casos verdaderamente positivos.

El recall se dio cuenta de los 5.

es al revés que precisión, toma en cuenta los falsos positivos.

---
## Clasificador de gatos

Precisión es mejor el B para casos usos médicos
Recall para fraude, bloqueos de cuenta.

Clasificaciones → precition recall con f1 score.

# 18-03

## Datos

### Diferencia entre datos e información

Datos es al aspecto 



### Tipos de datos

En análisis de datos la forma de verlos cambia.

- Categorical (que no es numérico) 0 o 1 por ejemplo o otros
	- Ordinal:  Dato categórico, pero que tiene cierto nivel de jerarquia, ej segmento de empresa, alto, bajo o medio.
	- Nominal: Nombre de objeto, comuna
- Numerical (Datos numéricos)
	- Discreto
	- Continuo



## Cantidad de Información

Información de Shannon → Mide cantidad de información en una fuente de datos


#### Entropía
Mide el nivel de incertidumbre de una fuente de información.

Que tan poca información tenemos de algo.

La entropía tiene un máximo, ej: una columna con un rut, todos los alumnos tienen un rut distinto, la entropía es máxima.

Hay 2 escenarios donde una columna no entrega nada de información, rut por ej, todos casos distintos, nada información 0.

El otro escenario es que todas las columnas digan alumno udp , alumno udp, etc. 
La entropía es mínima. En ese caso lo que no hay es varianza.
#### Problemas en los datos
1. Datos faltantes → Todos tienen edad en udp menos 3 personas
	1. Missing at Random → El dato se perdió pero depende de si mismo ej: La gente mas vieja no entrega su edad, solución ah tengo el dato promedio les pongo eso. Pero en realidad eran de 70 o más.
	2. Missing Completly at Random → 
	3. Missing not at Random → El dato perdido depende del resto de los datos. Ej: Por ej esta perdido el sueldo, pero justo era una persona que salía con crédito hipotecario. Hay un dato que la persona no quiere facilitar por el resto de variables. Estrategia: Inputear el dato.

2. Datos Inútiles (o poco útiles)
	1. Features completamente concentradas → Datos con la columna entera son datos : basura
	2. Outliers
		1. Unidimensionales
		2. Multidimensionales
	3. Skewed numerical features
	4. Clases desbalanceadas
	5. Maldición de la dimensionalidad → demasiadas columnas para entrenar y esto perjudica












# 21-03
#clase4
¿Cuándo cambiar los conjuntos Dev/Test y las métricas?

DataWareHouse → conjunto de sv donde hay un conjunto de bd.
BD que no es la productiva o es como un respaldo.

Problema son para datos estructurados, se debe modelar.


DATA LAKE: tirar datos

Data lake house : estructurar datos un poco antes de guardarlos ahí ,ya sea como dataset o json.

---
Proyecto:
Tenemos un set de datos de proyecto o pruebas.

Cuando se comienza se ve el objetivo.

Se puede cambiar la función de error.


---
Error se trata
Modificando los datos de entrenamiento.
Modificando la formula del error.

Matemáticamente son iguales, pero una requiere mas trabajo que otra.
Claramente los datos de entrenamiento son muchos mas difíciles.

---
#Clase5

Ideas de proyectos

Hay que tener un objetivo, lo mas importante son los datos y limpiar los datos gg.

Feature ening


Se entrena
Trabajar error del modelo
Armar algo usable

---
Sistemas de recomendaciones
1. Recomendaciones en base a historial → 2 usuarios similares, lo que consuma uno se le recomienda a otro.
2. Recomendaciones via lo que consume uno, se recomienda algo similar.

En supermercados, aliexpress, siempre usa "otros usuarios tambien compraron esto..."

---
Proyectos analisis de datos

Análisis de taxis con el clima
Análisis de datos de tienda
Análisis de ofert

---
Analisis de sentimiento en texto

Los LLM se comieron esto, pero son más lentos que los algoritmos hechos para esto.

---
Sistemas de Detección de fraude

---
Clasificador de imagenes

---
Generador de Captions → De que se trata la imagen

---
Chatbot → Con un LLM valido con un proposito, vendedores en linea, callcenter, etc...

---
Detectores de imagenes medicas.

---
Camara que reconoce letreros y dice vel. limite etc..

En los camiones, hay un computador con 2 camaras, una hacia el conductor para ver si esta pendiente y otra viendo la velocidad .

Aplicación de cabezazos? 

---

Detector de Fake News


Detectar fuentes, si la url es veridica etc...

---
Predictor de cuando comienza un incendio

detector de humo pero con camaras

---

ecolocalización
Saber de donde lanzaron los fuegos artificiales

---

NeRF neural radiance fields

Camara y reconstruir en 3d

---

Stable difussion

----
LLM para hacer algo

---





# 25-03

Outlayer → Los datos en la grafica que se salen de la curva. 

:) the lost kl

Grid search el mejor :D ?

AMONGUS

randomizedsearchcv lo hace mas rapido







