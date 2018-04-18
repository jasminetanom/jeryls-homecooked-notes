# K means clustering (UNSUPERVISED)

K = number of cluster centres

Every step, calculate geometric mean to predefined cluster centres.

Update cluster centres. Each cluster centre starts at random point.

# Analysis of clusters

Do decision tree on each cluster to identify feature importance, or characteristics that are representative


# Good clustering characteristics
1. within cluster, point to point distance very short
2. distance between cluster as high as possible

# Cluster algos
K means (Centroids, mediods)
Hierachichal
DBSCAN
Affinity propogation
Mean shift
Spectral clustering - > Time series
Agglomerative clustering

# K means workflow
Partition data such that total sum of squared distance from each point to mean point is minimised

1. Pick value for k
2. Initialise k centroids (starting points)
3. Create clusters, assign each point to nearest centroid
4. Make clusters better, move each centroid to the centre of each cluster
5. Repeat steps 3 and 4 until centroid converges

Inertia (intra distance)
silhouette (inter distance)


# DBSCAN

minpoints = number of points to fit in each circle
epsilon = radius of circle