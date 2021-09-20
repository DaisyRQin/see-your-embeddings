# ANGEL.ANGEL_embedding

    SOE(Matrix, DataLabel, C=0, anchor=0, dim=2, init=0, metric='euclidean', flagMove=0, T=50, scale=1)

Calculate embedded anchor points in the low-dimesional space.


| Parameters  |    Format                       |Description
| :----------------- | :----------------------------------- |:-----------------------------------
| `Matrix`      | {matrix} of shape (n_samples, n_samples)| A distance matrix D such that \(D_{ij}\) is the indicator whether \(j\)-th sample is among the neighborhood of the \(i\)-th sample of the given matrix Data  |
| `DataLabel` |  {column} of shape (n_samples, 1)   |  The corresponding labels of each data sample |
| cinit | {matrix} of shape (c_cohorts, dim) | Note that it only has the effect when flagMove=1. The embedded cohort positions in the low-dimensional space.|.
| `anchor`      | {matrix} of shape (m_anchors, dim)| Note that it only has the effect when flagMove=1. The oringal anchor points before applying the position refinement process. |
| `dim` | int, {2 or 3} | The dimensionality of the embedded space. |
| `init` | 0 or {matrix} of shape (n_samples, dim) | Whether to fix the initialization manually. The default init=0 gives the random data points initialization of the optimization process.|
| `metric`   | str, default = 'euclidean' | The metric to use when calculating distance between data samples. It must be one of the options allowed by scipy.spatial.distance.pdist for its metric parameter |
| `flagMove`    |  int, {0 or 1} |  Whether to refine the position of the embedded anchor points. The default flagMove=0 keeps the original positions of embedded anchor points |
|  `T` | int, default=50 | The number of iterations of the optimization process |
| scale | float, default = 1.0 | Note that it only has the effect when flagMove=1. In that case, the scale parameter controls the rescaling of each data cohort. |


| Returns  |    Format                       |Description
| :---------- | :----------------------------------- |:-----------------------------------
| `result`      |    {matrix} of shape (n_sample, dim)| The embedded data points in the low-dimensional space. |
