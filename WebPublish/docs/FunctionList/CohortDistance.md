# FunctionFile.CohortDistance

    CohortDistance(Data, DataLabel, CohortMetric='average', metricC='euclidean')

Calculate the adjacency matrix of a given dataset.


| Parameters  |    Format                       |Description
| :---------- | :----------------------------------- |:-----------------------------------
| `Data`      |      {matrix} of shape (n_samples, D_features)| Note that we do not support the sparse matrix now.  |
| `DataLabel` |  {column} of shape (n_samples, 1)   |  The corresponding labels of each data sample |
| `CohortMetric`    | str, default = 'average' | Different approaches for calculating the cohort distance, the options are: 'single', 'complete', 'centroid', 'Hausdoff'. |
| `metric`   | str, default = 'euclidean' | The metric to use when calculating distance between data samples. It must be one of the options allowed by scipy.spatial.distance.pdist for its metric parameter |


| Returns  |    Format                       |Description
| :---------- | :----------------------------------- |:-----------------------------------
| `dCluster`      |      {matrix} of shape (c_cohort, c_cohort)| A cohort distance matrix dCluster such that each indice is the distance between two data cohorts  |
