# Local Anchor Embedding

Anchor points are a small set of data points to roughly represent a  data distribution or a graph structure, e.g., by using a clustering algorithm and computing the cluster centers.  Each anchor point is denoted by  \(\mathbf{u}_i \in \mathbb{R}^D\), and stored in anchor point matrix  \(\mathbf{U} = \{\mathbf{u}_1,\dots,\mathbf{u}_m\}\subset \mathbb{R}^{m\times D}\).
 
[**Local Anchor Embedding**](https://icml.cc/Conferences/2010/papers/16.pdf) attempts to approximate each observed data point by  a convex combination of its \(t\)-nearest anchor points (\(t\)-NAP). 


Let   \(\mathbf{w}_i=[w_{i1}, w_{i2}, \ldots, w_{im}]^T\) denote the combination weights for reconstructing the \(i\)-th data point, and \(\mathbf{W} = \{\mathbf{w}_i\}\) is the reconstruction matrix. It is optimized by solving


$$
\mathbf{w}_{i}^{*}=\arg \min _{\mathbf{w}_{i} \in \mathbb{R}^{m}} \frac{1}{2}\left\|\mathbf{x}_{i}-\mathbf{U}^{T} \mathbf{w}_{i}\right\|_{2}^{2}
$$
subject to \(\mathbf{1}^{T} \mathbf{w}_{i}=1, w_{i j} \geq 0, w_{i j}=0\) if \(\mathbf{u}_{j} \notin t-\operatorname{NAP}\left(\mathbf{x}_{i}\right)\)


where \(\|\cdot\|_2\) denotes the \(l_2\) norm. The Nesterov’s method is used for optimization.  It alternates between gradient update and proper extrapolation for acceleration purpose.