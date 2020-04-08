# :books: K Mean Clustering


`K Mean Clustering` is an Unsupervised Machine Learning algorithm that tries to divide the dataset into K distinct non-overlapping groups (clusters) where each data point belongs to only one group.

`Clustering` can be defined as the task of identifying groups in the data such that data points in the same group or cluster are similar while data points in different clusters are different.

To avoid the `Random Initialization Trap` k-mean++ is used.

## :books: Quickstart

:one: Choose the number of cluster (for optimal number of clusters use Elbow Method)

:two: Select a random K points, the centroid

:three: Assign each data point to the closest centroid -> that forms K clusters

:four: Compute and place the centroid of each cluster

:five: Reassign each data point to the closest centorid. If any reassignment take place then go back to STEP 4, otherwise go to FINISH.


## :arrow_right: Choosing the right number of clusters

`WCSS` is the sum of squares of the distances of each data point in all clusters to their respective centroids. The idea is to minimise the sum.

```
WCSS = [in cluster 1]Σ(distance(Pi, Ci)^2) + [in cluster 2]Σ(distance(Pi, Ci)^2 + [in cluster 3]Σ(distance(Pi, Ci)^2 + ))
```

## :arrow_right: Elbow method to find the optimal number of clusters

```
from sklearn.cluster import KMeans
wcss = []
for i in range(1,  11):
    kmeans = KMeans(n_clusters = i, init = 'k-means++', max_iter = 300, n_init = 10, random_state = 0)
    kmeans.fit(X)
    wcss.append(kmeans.inertia_)
plt.plot(range(1, 11), wcss)
plt.title('The Elbow Method')
plt.xlabel('Number of Clusters')
plt.ylabel('WCSS')
plt.show()
```

## :arrow_right: Applying k-mean to the dataset
```
kmeans = KMeans(n_clusters = 5, init = 'k-means++', max_iter = 300, n_init = 10, random_state = 0)
y_kmeans = kmeans.fit_predict(X)
```

## :arrow_right: Visualizing the results
```
plt.scatter(X[y_kmeans == 0, 0], X[y_kmeans == 0, 1], s = 100, c = 'red', label = 'Careful')
plt.scatter(X[y_kmeans == 1, 0], X[y_kmeans == 1, 1], s = 100, c = 'orange', label = 'Standard')
plt.scatter(X[y_kmeans == 2, 0], X[y_kmeans == 2, 1], s = 100, c = 'blue', label = 'Target')
plt.scatter(X[y_kmeans == 3, 0], X[y_kmeans == 3, 1], s = 100, c = 'green', label = 'Careless')
plt.scatter(X[y_kmeans == 4, 0], X[y_kmeans == 4, 1], s = 100, c = 'magenta', label = 'Sensible')
plt.scatter(kmeans.cluster_centers_[:, 0], kmeans.cluster_centers_[:, 1], s = 100, c = 'yellow', label = 'Centroid')
plt.title('Cluster of clients')
plt.xlabel('Annual Income (k$)')
plt.ylabel('Spending Score (1-100)')
plt.legend()
plt.show()
```
