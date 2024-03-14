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





