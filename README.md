# Clustering Ensemble
![Cat](https://github.com/Yanis2016/Clustering-Ensemble/blob/master/Images/Capture%20d%E2%80%99%C3%A9cran%20de%202020-04-05%2008-06-31.png)
![Cat](https://github.com/Yanis2016/Clustering-Ensemble/blob/master/Images/Capture%20d%E2%80%99%C3%A9cran%20de%202020-04-05%2008-08-36.png)
![Cat](https://github.com/Yanis2016/Clustering-Ensemble/blob/master/Images/Capture%20d%E2%80%99%C3%A9cran%20de%202020-04-05%2008-06-45.png)
![Cat](https://github.com/Yanis2016/Clustering-Ensemble/blob/master/Images/Capture%20d%E2%80%99%C3%A9cran%20de%202020-04-05%2008-06-54.png)
![Cat](https://github.com/Yanis2016/Clustering-Ensemble/blob/master/Images/Capture%20d%E2%80%99%C3%A9cran%20de%202020-04-05%2008-07-08.png)
![Cat](https://github.com/Yanis2016/Clustering-Ensemble/blob/master/Images/Capture%20d%E2%80%99%C3%A9cran%20de%202020-04-05%2008-07-43.png)
![Cat](https://github.com/Yanis2016/Clustering-Ensemble/blob/master/Images/Capture%20d%E2%80%99%C3%A9cran%20de%202020-04-05%2008-07-58.png)


## Highlights
* Some evidences in co-association matrix are removed to improve the performance of clustering ensemble
* An internal validity index that only uses co-association matrix information is proposed for clustering ensemble.
* The proposed method outperforms some state-of-the-art ensemble methods.

## Abstract
Clustering consists of partitioning a set of objects (instances) represented by a set of variables into homogeneous groups (classes). With the advent of Big Data, clustering has become an even more important task. A wide variety of clustering algorithms have been proposed: k-Means, EM, classification based on spectral graph theory, hierarchical clustering algorithms, etc. Each of its methods is tailored to detect a specific underlying structure. However, when we are working with data of more than 3 dimensions, it is difficult for us to visualize it and know how the data is organized in space, so it is almost impossible to be sure that we have used the best method. . . In this article, we have proposed a new method of grouping sets based on information extracted from the co-association matrix, and allowing to detect almost any underlying structure existing in the data. First of all, the basic data are transformed into a co-association matrix, then several candidate partitions are generated by gradually eliminating in the co-association matrix the noise that will have been introduced in the transformation phase, finally, the indices internal validity are used to select the best partition. We will show that this method surpasses all individual clustering approaches and gives competitive results with advanced ensemble clustering methods.

## Use
#### Model initialization parameters:
    CluterEnsemble(n_clusters=4, n_partitions=1000, max_iter=4, k_type='Fixed', cons_validation='ac', m=3, alpha=0.5)
    
    Parameters
    ----------
    n_cluters : int, default=4
        The number of clusters.

    n_partitions : int, default=1000
        Number of base partitions.

    max_iter : int, default=100
        Maximum number of iterations of the k-means algorithm for a single run.

    k_type : {'Fixed', 'Random'}, default='Fixed'
        The type to generate base partitions, 
    'Fixed' : k = sqrt(n_sample),
    'Random': k = random between 2 and sqrt (sample n).

    cons_validation: {'ac', 'anc', 'andc'}, default='ac'
        Type of method to use to select the final partition.
    'ac' : average Confidence of assignment of the objects to its clusters. 
    'anc': average Neighborhood Confidence of assigning the objects to its clusters.
    'andc': average dynamic neighborhood confidence of assigning the objects to its clusters.

    m : int, default=3
        Number of neighbors, used when cons_validation = 'anc'.

    alpha : float > 0, default=0.5
        Use when cons_validation = 'etc' to dynamically calculate the number of neighbors.
#### Attributes
 
    co_association_matrix : ndarray of shape (n_clusters, n_samples)
         Co-association matrix.

     labels_ : ndarray of shape (n_samples, )
         Labels of each point, corresponds to the best partition selected by
         one of the methods {'ac', 'anc', 'adnc'}

     partitions : ndarray of shape(n_samples, 50)
         Partitions generated by the ncut algorithm by removing negative evidence
         from the co-association matrix.

     quality_of_partitions : ndarray of shape (50).
         Quality measured on each partition 
         by one of the evaluation methods {'ac', 'anc', 'adnc'}
 
#### Methods:
##### fit(X):
      Compute clusters.

      Parameters
      ----------
      X : ndarray or DataFrame, shape=(n_samples, n_features)

      Returns 
      -------
      self
          Fitted estimator.
          
##### fit_predict(X):
      Compute clusters  and predict clustered index for each sample.

      Parameters
      ----------
      X : array, shape=(n_samples, n_features)

      Returns
      -------
      labels : array, shape [n_samples,]
          Index of the cluster each sample belongs to.
          
##### draw_vat(figsize=(10, 10))

     Calculate and display the matrix for visual assessment of the cluster trend.

     Parameters
     ----------
     figsize : tuple, default = (10, 10)
         The dimensions of the figure.


## Questions?
Don't hesitate to contact me if you have any questions regarding this work.  
Email: yanis.aithammou@outlook.com 
