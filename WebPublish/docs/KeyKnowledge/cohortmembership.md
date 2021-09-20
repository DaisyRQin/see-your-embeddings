# Cohort Membership

The **cohort membership** refers to a column storing information about which cohort should each data sample belong to. The vector \(\mathbf{y}=[y_1, y_2, \dots, y_n]^T\) with \(y_i\in\{1,2,\dots,c\}\) indicating the cohort index of \(i\)-th sample, and \(c\) is the total number of the existing cohort. 

The most straightforward way is to retrieve the label information from the given dataset or obtained by a classification problem. However, if labels are not given, the cohort membership should be generated before applying the embedding algorithms.

Regarding data cohorts, one way of generating cohort membership is to apply clustering algorithms which should assign each data sample to a certain cluster. The [**kmeans clustering**](kmeansclustering.md) is commonly used. Other clustering methods like spectral clustering, agglomerative hierarchical clustering, can also be used.
