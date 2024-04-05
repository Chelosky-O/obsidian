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












# 21-#clase4
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





# 28-03
#Clase9

overfitting → 

underfitting → 

Control es sobre la parte de gestión de proyectos, toma de decisiones 
2DO sobre visualizaciones
el proyecto es para las técnicas

Estudio de misiles XD (aves)

Como sabemos si esta bueno → Matriz de confusión

Falso negativo peor que Falso Positivo


# 25-03
## Matriz de confusión

| **TRUE POSITIVE**  | **FALSE NEGATIVE** |
| -------------- | -------------- |
| **FALSE POSITIVE** | **TRUE NEGATIVE**  |
**Error tipo 1**: Falsos positivos
**Error tipo 2:** Falsos negativos

## Overfitting vs Underfitting
- El problema aparece cuando hablamos del grado polinomial del modelo.
- El grado del polinomio determina la flexibilidad.
- Un modelo subajustado (Underfitting) es menos flexible y no es capaz de captar el problema (en algunos casos).
- Un modelo sobreajustado (Overfitting) es muy flexible pero no sirve para generalizar los problemas por lo que no es muy útil.
- Underfit: Tendrá error alto tanto en entrenamiento como en las pruebas.
- Overfit: Tendrá error extremadamente bajo en el entrenamiento pero un error alto en las pruebas.
## Validación cruzada
Genera una seríe de experimentos donde voy cambiando los datos para entrenar al modelo, estos datos que se cambian son los grupos de validación

**Obs**: Si tengo un modelo no supervisado no puedo saber si hay o no overfitting o underfitting

# 28-03
## Reconocimiento de aves en la ciudad de Paecetopia
- Este ejemplo está adaptado de una aplicación real en producción, pero con detalles disfrazados para proteger la confidencialidad.
Eres un famoso investigador en la Ciudad de Peacetopia. La gente de Peacetopia tiene una característica común: tienen miedo a las aves. Para salvarlos, tienes que construir un algoritmo que detecte cualquier ave volando sobre Peacetopia y alerte a la población.
El Ayuntamiento te da un conjunto de datos de 10,000,000 imágenes del cielo sobre Peacetopia, tomadas de las cámaras de seguridad de la ciudad. Están etiquetadas:
- y = 0: There is no bird on the image
- y = 1: There is a bird on the image

Tu objetivo es construir un algoritmo capaz de clasificar nuevas imágenes tomadas por las cámaras de seguridad de Peacetopia.

Hay muchas decisiones que tomar:
**¿Cuál es la métrica de evaluación? ¿Cómo estructuras tus datos en conjuntos de entrenamiento/desarrollo/prueba?**
### Métrica de éxito
El Ayuntamiento te dice que quieren un algoritmo que:
- Tenga una alta precisión. 
- Funciona rápidamente y solo tarda un corto tiempo en clasificar una nueva imagen. 
- Pueda caber en una pequeña cantidad de memoria, para que pueda ejecutarse en un pequeño procesador al que la ciudad conectará a muchas cámaras de seguridad diferentes.

**Preguntas respecto al caso:**
1. Tener tres métricas de evaluación hace que sea más difícil para ti elegir rápidamente entre dos algoritmos diferentes y ralentizará la velocidad con la que tu equipo puede iterar. ¿Verdadero/Falso? **R:** Verdadero

Después de más discusiones, la ciudad reduce sus criterios a:
Necesitamos un algoritmo que pueda informarnos de que un ave está volando sobre Peacetopia con la mayor precisión posible”. “Queremos que el modelo entrenado no tarde más de 10 segundos en clasificar una nueva imagen”. “Queremos que el modelo quepa en 10MB de memoria”

2. Si tuvieras los tres siguientes modelos, ¿cuál elegirías?
	1. Precisión de  98%
	2. Tiempo de ejecución 9 segundos
	3. Tamaño de memoria 9MB
	**R:** El tamaño de la memoria, ya que si eso no se cumple el proyecto es inviable
3. Antes de implementar tu algoritmo, necesitas dividir tus datos en conjuntos de entrenamiento/desarrollo/prueba. ¿Cuál de estos crees que es la mejor opción?
	- entrenamiento: 50% desarrollo 10%, test: 40%
	- entrenamiento: 90% desarrollo 5%, test: 5%
	- entrenamiento: 50% desarrollo 40%, test: 10%
	- entrenamiento: 50% desarrollo 25%, test: 25%
	**R:** Ya que hay muchisimos datos (10 millones), la mejor opción es entrenamiento 90%, desarrollo 5% y test 5% ya que de esta forma se entrena un sistema robusto.

Después de configurar tus conjuntos de entrenamiento/desarrollo/prueba, el Ayuntamiento encuentra otras 1.000.000 de imágenes, llamadas “datos de los ciudadanos”. Aparentemente, los ciudadanos de Peacetopia están tan asustados de los pájaros que se ofrecieron voluntariamente para tomar fotos del cielo y etiquetarlas, contribuyendo así con estas 1.000.000 de imágenes adicionales. Estas imágenes son diferentes a la distribución de imágenes que el Ayuntamiento te había dado originalmente, pero crees que podrían ayudar a tu algoritmo.
4. No deberías agregar los datos de los ciudadanos al conjunto de entrenamiento, porque esto hará que las distribuciones de los conjuntos de entrenamiento y desarrollo/prueba sean diferentes, lo que perjudicará el rendimiento de los conjuntos de desarrollo y prueba. ¿Verdadero/Falso? **R:** Verdadero,no se debe ensuciar el set de datos
5. Un miembro del Ayuntamiento sabe un poco sobre el aprendizaje automático y cree que deberías agregar las 1.000.000 de imágenes de datos de los ciudadanos al conjunto de prueba. Te opones porque: 
	1. Las 1.000.000 de imágenes de datos de los ciudadanos no tienen una asignación consistente de x–>y como el resto de los datos
	2. Un conjunto de prueba más grande reducirá la velocidad de iteración debido al costo computacional de evaluar modelos en el conjunto de prueba.
	3. Esto haría que las distribuciones de los conjuntos de desarrollo y prueba sean diferentes. Esto es una mala idea porque no estás apuntando a donde quieres llegar.
	4. El conjunto de prueba ya no refleja la distribución de datos (cámaras de seguridad) que más te importa.
	**R:** 4
6. Entrenas un sistema y sus errores son los siguientes (error = 100% - Precisión): Error del conjunto de entrenamiento 4.0% Error del conjunto de desarrollo 4.5%. Esto sugiere que una buena forma de mejorar el rendimiento es entrenar una red más grande para reducir el error de entrenamiento del 4.0%. ¿Estás de acuerdo?
	1. Sí, porque tener un error de entrenamiento del 4.0% muestra que tienes un sesgo alto.
	2. Sí, porque esto muestra que tu sesgo es mayor que tu varianza.
	3. No, porque esto muestra que tu varianza es mayor que tu sesgo.
	4. No, porque no hay suficiente información para decirlo.
	**R:** Si tengo mucha varianza aumenta la probabilidad de que los conjuntos de entrenamiento queden distintos. Por lo tanto 3.
Pides a algunas personas que etiqueten el conjunto de datos para averiguar cuál es el rendimiento a nivel humano. Encuentras los siguientes niveles de precisión: Experto en observación de aves #1 error del 0.3% Experto en observación de aves #2 error del 0.5% Persona normal #1 (no es un experto en observación de aves) error del 1.0% Persona normal #2 (no es un experto en observación de aves) error del 1.2%

7. Si tu objetivo es que el “rendimiento a nivel humano” sea un proxy (o estimación) del error de Bayes, ¿cómo definirías el “rendimiento a nivel humano”?
	1. 0.0% (porque es imposible hacerlo mejor que esto)
	2. 0.3% (precisión del experto #1)
	3. 0.4% (promedio de 0.3 y 0.5)
	4. 0.75% (promedio de los cuatro números anteriores)
	**R:** 0.3% 
8. ¿Con cuál de las siguientes afirmaciones estás de acuerdo?
	1. El rendimiento del algoritmo de aprendizaje puede ser mejor que el rendimiento a nivel humano pero nunca puede ser mejor que el error de Bayes.
	2. El rendimiento del algoritmo de aprendizaje nunca puede ser mejor que el rendimiento a nivel humano pero puede ser mejor que el error de Bayes.
	3. El rendimiento del algoritmo de aprendizaje nunca puede ser mejor que el rendimiento a nivel humano ni mejor que el error de Bayes.
	4. El rendimiento del algoritmo de aprendizaje puede ser mejor que el rendimiento a nivel humano y mejor que el error de Bayes.
	**R:** 1
Imaginemos que has creado un algoritmo para reconocer aves en fotografías. Después de muchas pruebas y ajustes, descubres que un equipo de ornitólogos puede identificar las aves en las imágenes con un rendimiento del 0,1% mejor que tu algoritmo. A partir de ese momento, decides que ese nivel de rendimiento debe ser considerado como "rendimiento a nivel humano".

Sin embargo, no te rindes y sigues trabajando en mejorar tu algoritmo. Finalmente, consigues reducir el error en el conjunto de entrenamiento al 2,0% y el error en el conjunto de validación al 2,1%. Es decir, tu algoritmo ya supera el rendimiento humano en esta tarea en particular.

9. Basado en la evidencia que tienes, ¿cuáles de las siguientes cuatro opciones parecen las más prometedoras para probar? (Selecciona dos opciones).
	1. Entrenar un modelo más grande para intentar mejorar en el conjunto de entrenamiento.
	2. Conseguir un conjunto de entrenamiento más grande para reducir la varianza.
	3. Intentar aumentar la regularización
	4. Intentar disminuir la regularización
	**R:** 1,2 y 3
10. También evalúas tu modelo en el conjunto de prueba y encuentras lo siguiente: rendimiento a nivel humano 0,1%, error en el conjunto de entrenamiento 2,0%, error en el conjunto de desarrollo 2,1%, error en el conjunto de prueba 7,0%. ¿Qué significa esto? (Verifique las dos mejores opciones).
	1. Deberías intentar obtener un conjunto de desarrollo más grande.
	2. Te has ajustado demasiado al conjunto de desarrollo.
	3. Deberías obtener un conjunto de prueba más grande.
	4. Te has ajustado insuficientemente al conjunto de desarrollo.
	**R:** 2
11. Después de trabajar en este proyecto durante un año, finalmente logras: Rendimiento a nivel humano 0,10% Error en el conjunto de entrenamiento 0,05% Error en el conjunto de desarrollo 0,05%. ¿Qué conclusiones se pueden sacar? (Marque todas las opciones que correspondan)
	1. Es ahora más difícil medir el sesgo evitable, por lo que el progreso será más lento en el futuro.
	2. Si el conjunto de pruebas es lo suficientemente grande como para que la estimación de error del 0,05% sea precisa, esto implica que el error de Bayes es ≤0,05
	3. Se trata de una anomalía estadística (o debe ser el resultado de ruido estadístico) ya que no debería ser posible superar el rendimiento humano.
	4. Con solo un 0,09% de progreso adicional por hacer, deberías ser capaz de cerrar rápidamente la brecha restante hasta el 0%.
	**R:** 1, 2
12. ¡Has vencido fácilmente a tu competidor y tu sistema ahora está desplegado en Peacetopia y está protegiendo a los ciudadanos de los pájaros! Pero en los últimos meses, una nueva especie de pájaro ha estado migrando lentamente hacia la zona, por lo que el rendimiento de tu sistema se degrada lentamente porque tus datos están siendo probados en un nuevo tipo de datos. Solo tienes 1.000 imágenes de la nueva especie de pájaro. La ciudad espera un mejor sistema de ti en los próximos 3 meses. ¿Qué deberías hacer primero?
	1. Usa los datos que tienes para definir una nueva métrica de evaluación (usando un nuevo conjunto de desarrollo/pruebas) teniendo en cuenta la nueva especie y úsala para impulsar un mayor progreso para tu equipo.
	2. Agrega las 1.000 imágenes al conjunto de entrenamiento para intentar mejorar en estas aves.
	3. Intenta la ampliación de datos/síntesis de datos para obtener más imágenes del nuevo tipo de pájaro.
	4. Agrega las 1.000 imágenes a tu conjunto de datos y reorganiza en una nueva división de entrenamiento/desarrollo/pruebas.
	**R:** 3


---


# 01-04

## Regularización
- Es un concepto importante en el aprendizaje automático que se utiliza para prevenir el sobreajuste.
- Se aplica principalmente cuando tienes un modelo con demasiados parámetros o características, lo que podría hacer que e modelo se ajuste demasiado a los datos de entrenamiento y no generalice bien a nuevos datos.
- Dos métodos comunes de regularización:
	- Regularización L1(Lasso): Agrega la suma de los valores absolutos de los coeficientes como término de penalización.
	- Regularización L2 (Ridge): Agrega la suma de los cuadrados de los coeficientes como término de penalización. Esto penaliza los valores extremos , pero no los fuerza a ser exactamente cero.

El **Análisis de Componentes Principales** (PCA) es una técnica que se utiliza para reducir la dimensionalidad de un conjunto de datos, especialmente cuando tienes muchos atributos o características (dimensiones) y deseas simplificarlos sin perder demasiada información.

---

La idea principal detrás de PCA es encontrar las direcciones en las que los datos tienen la mayor variabilidad. Estas direcciones se llaman "componentes principales". PCA calcula estos componentes principales y los ordena según la cantidad de variabilidad que representan, de modo que el primer componente principal captura la mayor cantidad de variabilidad en los datos, el segundo componente principal captura la segunda mayor cantidad de variabilidad, y así sucesivamente.

---

1. Calcula la matriz de covarianza de los datos. Esto ayuda a comprender cómo las diferentes características están relacionadas entre sí.
    
2. Encuentra los vectores propios (eigenvectores) y los valores propios (eigenvalores) de la matriz de covarianza. Los eigenvectores representan las direcciones de máxima variabilidad, y los eigenvalores indican cuánta variabilidad se encuentra en esas direcciones.
    
3. Ordena los eigenvectores en función de los eigenvalores de mayor a menor. Esto determina el orden de importancia de los componentes principales.
    
4. Elige cuántos componentes principales deseas retener (por ejemplo, los dos o tres primeros). Esto dependerá de tus objetivos y de cuánta información quieras conservar.
    
5. Proyecta los datos originales en el espacio definido por los componentes principales seleccionados. Esto reduce la dimensionalidad de los datos.
    
6. Los datos proyectados en el nuevo espacio de componentes principales son los resultados del PCA. Puedes utilizarlos para el análisis, la visualización o el modelado posterior.
    

PCA simplifica los datos encontrando las direcciones de máxima variabilidad y proyectando los datos en un espacio de dimensiones reducidas, donde las dimensiones principales capturan la mayor parte de la información. Esto facilita la interpretación y el análisis de los datos, así como la reducción del ruido y la redundancia en los conjuntos de datos de alta dimensionalidad.

Las transformaciones de **Box y Cox** son una familia de transformaciones potenciales usadas en estadística para corregir sesgos en la distribución de errores, para corregir varianzas desiguales (para diferentes valores de la variable predictora) y principalmente para corregir la no linealidad en la relación (mejorar correlación entre las variables).