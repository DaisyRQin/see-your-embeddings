# COVA.COVAembedding

    COVAembedding(Data, R, W, V, init=0, dim=2, alpha=0.4, T=50, COVAType='cova1', opttype='GD_Euclidean')

Calculate embedded anchor points in the low-dimesional space.


| Parameters  |    Format                       |Description
| :----------------- | :----------------------------------- |:-----------------------------------
| `Data`      |      {matrix} of shape (n_samples, D_features)| Note that we do not support the sparse matrix now.  |
| `R`      |    {matrix} of shape (n_samples, c_cohorts)| The ouput Confidence matrix|
| `W`      |      {matrix} of shape (n_samples, n_samples)| A distance matrix D such that \(D_{ij}\) is the distance between the \(i\)-th and \(j\)-th vectors of the given matrix Data  |
| `V` |  {matrix} of shape (c_cohort, dim)| The embedded prototype points in the low-dimensional space. |
| `init` | 0 or {matrix} of shape (n_samples, dim) | Whether to fix the initialization manually. The default init=0 gives the random data points initialization of the optimization process.|
| `dim` | int, {2 or 3} | The dimensionality of the embedded space. |
| `alpha` | float, default=0.4 | It controls the balance between global and local visualizations. 0 < alpha < 1, 0: the most local choice, 1: the most global choice.
|  `T` | int, default=50 | The number of iterations of the optimization process |
| `COVAType` | str, default='cova1' | Switch between different COVA types according to the paper. The choices are 'AnalyticalCOVA1', 'cova1', 'cova2', 'cova3', 'cova4'. 
|  `optType` | str, default='GD_Euclidean' | Switch between two different optimization process. The default 'constrained' refers to the optimization based on Euclidean space, the other choice 'GD_Riemannian' is based on the manifold optimization process. Note that 'GD_Riemannian' only works for 'cova1' currently. |



| Returns  |    Format                       |Description
| :---------- | :----------------------------------- |:-----------------------------------
| `result`      |    {matrix} of shape (n_sample, dim)| The embedded data points in the low-dimensional space. |
