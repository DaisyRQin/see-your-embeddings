# Introduction

Dimensionality reduction for cohort data visualization is to plot a high-dimensional dataset in \(2,3\text{-D}\) spaces to help analysts to identify data properties and gain insights visually. To maximize the information conveyed by plots, three aspects of local neighborhood preservation, cohort structure preservation, and cohort separation are required to be satisfied. COVA and ANGEL are novel data visualization algorithms providing a simple but effective way to comprehensively improve cohort data visualization performance. The core strategy of the algorithms are the following:


- Applying prototypes/anchor points to represent the global structure of the dataset.
- Generating data points around the prototypes/anchor points to maintain the local and global structural preservation.
- Hyperparameters can be adjusts to enhance the cohort separation.
   
&nbsp;

A set of new evaluation approaches are also proposed to assess preservation quality fairly. Experimental results show that the proposed algorithm can provide informative visualization results.

The details for the mathematics of the algorithms can be found in our papers: [COVA](https://ieeexplore.ieee.org/abstract/document/7949023).


The main layout of this documentation website is as the following:


- Tutorial: How COVA and ANGEL algorithms works
    - [COVA Tutorial](COVATutorial.md)
    - [ANGEL Tutorial](PageUnderConstruction.md)
    - [Evaluation](PageUnderConstruction.md)
- [Demo](Demo.md): Demos for helping to understand algorithms
- [Key Knowledge](KeyKnowledges.md): Explaining key terminologies and concepts
    - [adjacency matrix](./KeyKnowledge/adjacencymatrix.md)
    - [cohort distance](./KeyKnowledge/cohortdistance.md)
    - [cohort membership](./KeyKnowledge/cohortmembership.md)
    - [confidence matrix](./KeyKnowledge/confidencematrix.md)
    - [isometric embedding](./KeyKnowledge/isometricembedding.md)
    - [kmeans clustering](./KeyKnowledge/kmeansclustering.md)
    - [Local Anchor Embedding](./KeyKnowledge/localAnchorEmbedding.md)
    - [Soft Ordinal Embedding](./KeyKnowledge/softOrdinalEmbedding.md)
- [Function Lists](FunctionLists.md): API guide
    - ANGEL
        - [AnchorPointGeneration](PageUnderConstruction.md)
        - [AnchorEmbedding](PageUnderConstruction.md)
        - [ANGEL_embedding](PageUnderConstruction.md)

    - COVA
        - [PrototypeGeneration](./FunctionList/PrototypeGeneration.md)
        - [PrototypeEmbedding](./FunctionList/PrototypeEmbedding.md)
        - [CohortConfidence](./FunctionList/CohortConfidence.md)
        - [COVAembedding](./FunctionList/COVAembedding.md)
    - Evaluation
        - [Prev](PageUnderConstruction.md)
    - FunctionFile:
        - [loadData](./FunctionList/loadData.md)
        - [DataScaler](./FunctionList/DataScaler.md)
        - [CohortDistance](./FunctionList/CohortDistance.md)
        - [AdjacencyMatrix](./FunctionList/AdjacencyMatrix.md)
    - localanchorembedding
        - [AnchorGraph](./FunctionList/AnchorGraph.md)
    - SOEembedding
        - [SOE](./FunctionList/SOE.md)
- [Examples](PageUnderConstruction.md): Examples results of applying algorithms on real-world datasets
