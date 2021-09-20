# localanchorembedding.AnchorGraph

    AnchorGraph(Data, Anchor, t=3, cn=10, metric='euclidean')

Generates the graph matrix representing relationships between data samples and anchor points.


| Parameters  |    Format                       |Description
| :----------------- | :----------------------------------- |:-----------------------------------
| `Data`      |      {matrix} of shape (n_samples, D_features)| Note that we do not support the sparse matrix now.  |
| `Anchor`      | {matrix} of shape (m_anchors, D_features)| The input anchor points in the high-dimensional space. |
| `t` | int, default=3 | The number of neighboring anchor points of each data sample. |
| `cn` | int, default=10 | The number of iterations of the optimization process |
| `metric`   | str, default = 'euclidean' | The metric to use when calculating distance between data samples. It must be one of the options allowed by scipy.spatial.distance.pdist for its metric parameter |



| Returns  |    Format                       |Description
| :---------- | :----------------------------------- |:-----------------------------------
| `Z`      |    {matrix} of shape (n_samples, m_anchor)| The AnchorGraph matrix storing relations between data samples and anchor points. |