# Adjacency Matrix

Given a set of data sample \(\mathbf{X}=\{\mathbf{x}_1, \mathbf{x}_2,\dots, \mathbf{x}_n\}\), the **adjacency matrix** of this dataset is a square \(n\times n\) matrix \(\mathbf{W}\) where each element \(w_{ij}\) representing the connection information between the data sample \(\mathbf{x}_i\) with the data sample \(\mathbf{x}_j\). The \(w_{ij}\) is bigger than \(0\) when there is an edge between these two data samples while \(w_{ij}\) is \(0\) when there is no edge. The diagonal elements \(w_{ii}\) are set to be zeros since there is no edge from the data sample to itself. 

Our adjacency matrix is built on the graph connecting the \(k\)-nearest neighborhood samples with each data sample. That means, an edge \(w_{ij}\) exists if the data sample \(\mathbf{x}_j\) is among the \(k\)-nearest neighborhood points of the data sample \(\mathbf{x}_i\), otherwise there is no edge. 

If the graph is directed, the fact that the data sample \(\mathbf{x}_j\) is among the \(k\)-nearest neighborhood points of the data sample \(\mathbf{x}_i\) will not guarantee that data sample \(\mathbf{x}_i\) is also among the \(k\)-nearest neighborhood points of the data sample \(\mathbf{x}_j\), which will lead to \(w_{ij}\neq w_{ji}\). If the graph is undirected, then \(w_{ij} = w_{ji}\) as we will make sure that both samples are in the neighborhood of the other one. 

If the graph is weighted, the indice \(w_{ij}\) can take the real distance value as the weight of the edge. The actual weight \(w_{ij}\) can be computed using any predefined similarity measure, such as the Gaussian kernel, cosine similarity, etc. The unweighted graph only has \(w_{ij} = 1\) as the indicator of all edges. 

An example of the undirected weighted adjacency matrix based on 3-nearest neighborhood graph is as the following:


$$
\mathbf{W} = \begin{bmatrix}0& 1.2& 0& 1.4& 0.8& 0 \\1.2& 0& 0.6& 0.7& 0& 0 \\ 
0& 0.6& 0& 1.0& 0& 1.5\\ 0& 0.7& 1.0& 0& 1.2& 0& \\
0.8& 0& 0& 1.2& 0& 1.0\\ 1.6& 0& 1.5& 0& 1.0& 0 \end{bmatrix}
$$

As for a real-world dataset, the adjacency matrix of the daset can be viewed as a heatmap where the temperature denotes the numerical value of weights. Here are two heatmap examples of weighted adjacency matrix and the unweighted adjacency matrix.

