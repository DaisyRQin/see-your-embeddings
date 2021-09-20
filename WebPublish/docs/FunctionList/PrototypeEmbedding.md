# COVA.PrototypeEmbedding

    PrototypeEmbedding(Dc, DataLabel, dim=2, Embedding='SOE', init=0)

Calculate embedded prototypes in the low-dimesional space.


| Parameters  |    Format                       |Description
| :----------------- | :----------------------------------- |:-----------------------------------
| `Dc`      |  {matrix} of shape (c_cohort, c_cohort)| A cohort distance matrix dCluster such that each indice is the distance between two data cohorts  |
| `DataLabel` |  {column} of shape (n_samples, 1)   |  The corresponding labels of each data sample |
| `dim` | int, {2 or 3} | The dimensionality of the embedded space. |
| `Embedding` | str, default='SOE' | Switch between different isometric embedding approaches. The options are 'SOE', 'MDS', and 'Isomap'.
| `init` | 0 or {matrix} of shape (n_samples, dim) | Whether to fix the initialization manually. The default init=0 gives the random prototypes initialization of the optimization process.|



| Returns  |    Format                       |Description
| :---------- | :----------------------------------- |:-----------------------------------
| `V`      |    {matrix} of shape (c_cohort, dim)| The embedded prototypes in the low-dimensional space. |
