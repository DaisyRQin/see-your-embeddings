# COVA.PrototypeGeneration

    ProtoGeneration(Data, DataLabel, C=1, metric='euclidean')

Generate relations between prototypes in the high-dimensional space.


| Parameters  |    Format                       |Description
| :----------------- | :----------------------------------- |:-----------------------------------
| `Data`      |      {matrix} of shape (n_samples, D_features)| Note that we do not support the sparse matrix now.  |
| `DataLabel` |  {column} of shape (n_samples, 1)   |  The corresponding labels of each data sample |
| `C` | int, {0 or 1} | Whether to use the original data cohort to generate prototypes. When default C=1, we further clustering the dataset into \(c_cohort = \lfloor0.1n\rfloor\) cohorts. When C=0, we keep the original data cohorts. |
| `metric`   | str, default = 'euclidean' | The metric to use when calculating distance between data samples. It must be one of the options allowed by scipy.spatial.distance.pdist for its metric parameter |



| Returns  |    Format                       |Description
| :---------- | :----------------------------------- |:-----------------------------------
| `Dc`      |  {matrix} of shape (c_cohort, c_cohort)| A cohort distance matrix dCluster such that each indice is the distance between two data cohorts  |