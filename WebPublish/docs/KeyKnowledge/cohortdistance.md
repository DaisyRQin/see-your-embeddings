# Cohort Distance

The **cohort distance** measures the proximity information betwee cohorts of a given dataset \(\mathbf{X}=\{\mathbf{x}_1, \mathbf{x}_2,\dots, \mathbf{x}_n\}\). Assume there are \(c\) different cohorts in the dataset \(\mathbf{X}\), we construct a \(c\times c\) cohort distance matrix \(\mathbf{D}_c\) where each indice \(d_{ij}\) represent the proximity information between cohort \(c_i\) and cohort \(c_j\). The most straightforward way to compute \(d_{ij}\) is to calculate the distance between cohort centers where

$$
d_{ij} = d\left(\frac{1}{n_{i}}\sum_{y_p = i}\mathbf{x}_p, \frac{1}{n_{j}}\sum_{y_q = j}\mathbf{x}_q\right).
$$

Here, \(d(\cdot,\cdot)\) denotes any distance measures between two data samples, which can be the Euclidean distance(which we applied to our algorithms), a Gaussian kernel, etc.

Another popular way of generating cohort distance is to find the average-linkage distance which is based on calculating the average sample pair relations,

$$
\mathbf{d}_{ij} = \frac{1}{n_i n_j} \sum_{{y}_{p}=i}\sum_{{y}_{q}=j} d(\mathbf{x}_{p},\mathbf{x}_{q}).
$$

Moreover, the adjacency matrix \(\mathbf{W}\) generated for the local neighbor preservation can be used to adjust the average distance between cohorts as

$$
d_{i j} \leftarrow \frac{1}{n_{i} n_{j}} \sum_{y_{p}=i, y_{q}=j} w_{p q},
$$

which reflects density of neighbor link between samples from two cohorts.

More generally, the users can define their own cohort similarity measures according to the applications of different datasets. One example is that, when visualizing images based on their pixel content (e.g., using a convolutional neural network (CNN) to construct \(\mathbf{X}\)), proximity between image cohorts can be computed externally by examining the image captions. For instance, by treating the collection of image captions from each cohort as a document and modelling the documents using a bag-of-word model, proximity between two cohorts can be computed as the cosine similarity between their two document vectors.
