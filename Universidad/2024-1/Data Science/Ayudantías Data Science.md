# Ayudantía 1

## Clustering

Dataset importa, debe tener correlación entre sus características.

### K-Means
K-Means es un algoritmo de agrupamiento que divide un conjunto de datos en grupos basados en similitudes entre los puntos de datos. Funciona iterativamente para asignar puntos a grupos y calcular los centros de los grupos. Es popular por su simplicidad y eficiencia, pero puede tener dificultades con ciertos tipos de datos y requiere que especifiques el número de grupos por adelantado.

```
# Cargar el conjunto de datos
data = load_breast_cancer()


# Obtener las características (X) y las etiquetas (y)
X = data.data
y = data.target

# Inicializar y ajustar el modelo K-Means
kmeans = KMeans(n_clusters=3, random_state=42)
kmeans.fit(X)


# Obtener los centroides y las etiquetas de los clusters

centroids = kmeans.cluster_centers_

labels = kmeans.labels_

# Visualizar los resultados del clustering
plt.figure(figsize=(8, 6))

# Graficar las muestras coloreadas por los clusters
plt.scatter(X[:, 0], X[:, 1], c=labels, cmap='viridis', s=50, alpha=0.5)

# Graficar los centroides de los clusters
plt.scatter(centroids[:, 0], centroids[:, 1], marker='o', c='red', s=200, edgecolor='k')

plt.xlabel(data.feature_names[0])
plt.ylabel(data.feature_names[1])
plt.title('K-Means Clustering')

plt.show()
#nos ayuda a ver la relacion entre 2 parametros
```

