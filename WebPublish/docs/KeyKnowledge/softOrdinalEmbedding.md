# Soft Ordinal Embedding

[**Soft Ordianl Embedding**](http://proceedings.mlr.press/v32/terada14.pdf) is a typical ordinal embedding method.  It constructs the embedded data by enforcing ordinal constraints derived from the original data. Given a triplet of data points \((\mathbf{x}_i, \mathbf{x}_j, \mathbf{x}_l)\), the ordinal constraint of the triplet is settled as

$$
    \text{If } D(\mathbf{x}_i,\mathbf{x}_j) < D(\mathbf{x}_i,\mathbf{x}_l), \text{ then } \hat{D} (\hat{\mathbf{x}}_i,\hat{\mathbf{x}}_j) < \hat{D} (\hat{\mathbf{x}}_i,\hat{\mathbf{x}}_l).
$$

Here \(D(\cdot,\cdot)\) denotes the distance between two data points in the original space, while \(\hat{D}(\cdot,\cdot)\) denotes the distance in the embedded space. In the non-metric embedding setting, the value of \(D(\mathbf{x}_i,\mathbf{x}_j)\) is unknown but the distance order reflected by the left inequality of the above equation is known. 

The triplet set, as  
$$
\Gamma^{\text{OE}}(\mathbf{X})=\left \{(i,j,l)| D(\mathbf{x}_i,\mathbf{x}_j) < D(\mathbf{x}_i,\mathbf{x}_l)\right\},
$$

stores the full distance order obtained in the original space. SOE finds the embedding coordinates by solving the following optimization problem:

$$
    \min_{\{\hat{\mathbf{x}}_i\}_{i=1}^n}    \sum_{(i,j,l)\in \Gamma^{\text{OE}}(\mathbf{X})}\text{max}^2\left(0, \hat{D}(\hat{\mathbf{x}}_i,\hat{\mathbf{x}}_j) +\delta - \hat{D}(\hat{\mathbf{x}}_i,\hat{\mathbf{x}}_l)\right),
$$

where \(\max(\cdot,\cdot)\) returns the larger one between the two  input numbers, and \(\delta>0\)  controls the embedding scale. A simple way to obtain the optimum \(\{\hat{\mathbf{x}}_i\}_{i=1}^n\) is  line search gradient descent. 

