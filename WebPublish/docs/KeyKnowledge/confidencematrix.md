# Confidence Matrix

The confidence matrix \(\mathbf{R}=\{r_{ij}\}\) is generated with each element quantifies the degree of confidence that the \(i\)-th sample belongs to the \(j\)-th cohort. The template confidence \(r_{ij}\) to be matched in the target space can be computed by examining the proximity between the \(i\)-th sample and the centroid of the \(j\)-th cohort in the original space, such that

$$
r_{i j}=r\left(\boldsymbol{x}_{i}, \frac{1}{n_{j}} \sum_{y_{s}=j} \boldsymbol{x}_{s}\right),
$$

where \(r(\cdot,\cdot)\) is set as a similarity measure. It can also be computed as the averaged adjacency weights in \(\mathbf{W}\) between the \(i\)-th sample and samples from the \(j\)th cohort, given as

$$
r_{i j}=\left\{\begin{array}{ll}
\frac{1}{n_{j}-1} \sum_{s \neq i, y_{s}=j} w_{i s}, & \text { if } y_{i}=j \\
\frac{1}{n_{j}} \sum_{y_{s}=j} w_{i s}, & \text { otherwise }
\end{array}\right.
$$

The above formulations of \(r_{ij}\) push data samples that are closer to a cohort center in the original space to stay closer to its corresponding cohort prototype in the target space. To enhance cohort separation, the links between a data sample and prototypes can be adjusted based on the following rescaling process

$$
\mathbf{R} \leftarrow\left\{\begin{array}{ll}
\mathfrak{L}\left(\mathbf{R} \circ \mathbf{Y},\left[1-\lambda_{p}, 1\right]\right)+\mathfrak{L}\left(\mathbf{R} \circ(1-\mathbf{Y}),\left[0, \lambda_{p}\right]\right), & \text { if } \lambda_{p} \neq 0 \\
\mathbf{R} \circ \mathbf{Y}, & \text { if } \lambda_{p}=0
\end{array}\right.
$$

where \(0 \leq \lambda_p \ll 1\) and \(\mathcal{L}(\cdot,[a,b])\) is a mapping function that linearly rescales elements in the input matrix to a given interval \([a, b]\). When \(\lambda_p\) = 0, cohort separation is maximally enforced by simply cutting the links between a data sample and its irrelevant prototypes by fixing \(r_{ij}\) to zero when \(y_i \neq j\).

An alternative for computing the confidence degree is to formulate \(r_{ij}\) as a probability, according to

$$
r_{i j}=\left\{\begin{array}{ll}
p\left(s_{i j}\right), & \text { if } y_{i}=j \\
\lambda_{p}, & \text { otherwise }
\end{array}\right.
$$

Between samples and their irrelevant cohorts, \(r_{ij}\) is set as a small value \(0 \leq \lambda_p \ll 1\) to equally push the samples to stay away. Between a sample and its own cohort, \(r_{ij}\) is obtained using a probability function \(p(\cdot)\) estimated from the similarity \(s_{i j}\) which is the original confidence value calculated from the first two equations. The normal distribution, Student’s t-distribution, and other complex alternatives can be applied. 




