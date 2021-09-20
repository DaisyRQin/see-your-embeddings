# FunctionFile.AdjacencyMatrix

    AdjacencyMatrix(Data, neighbor=10, weight=1, metric='euclidean')

Calculate the adjacency matrix of a given dataset.


| Parameters  |    Format                       |Description
| :---------- | :----------------------------------- |:-----------------------------------
| `Data`      |      {matrix} of shape (n_samples, D_features)| Note that we do not support the sparse matrix now.  |
| `neighbor`   | int, default = 10    |  The number of neighborhood points we would like to link within each data samples |
| `weight`    |  int, {0 or 1} |  Whether to present the weighted matrix, when weight = 0; or a unweighted matrix, when weight = 1. |
| `metric`   | str, default = 'euclidean' | The metric to use when calculating distance between data samples. It must be one of the options allowed by scipy.spatial.distance.pdist for its metric parameter |


| Returns  |    Format                       |Description
| :---------- | :----------------------------------- |:-----------------------------------
| `W`      |      {matrix} of shape (n_samples, n_samples)| A distance matrix D such that \(D_{ij}\) is the distance between the \(i\)-th and \(j\)-th vectors of the given matrix Data  |
