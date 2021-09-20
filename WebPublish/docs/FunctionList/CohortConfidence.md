# COVA.CohortConfidence

    CohortConfidence(Data, DataCohort, lamb=0)

Calculate the cohort confidence matrix representing the confidence of each data sample belonging to a certain cohort.


| Parameters  |    Format                       |Description
| :----------------- | :----------------------------------- |:-----------------------------------
| `Data`      |      {matrix} of shape (n_samples, D_features)| Note that we do not support the sparse matrix now.  |
| `DataCohort` |  {column} of shape (n_samples, 1)   |  The corresponding labels of each data sample |
| `lamb`  | float, default=0 | The parameter that controls the confidence level of each data sample, default is 0 |



| Returns  |    Format                       |Description
| :---------- | :----------------------------------- |:-----------------------------------
| `R`      |    {matrix} of shape (n_samples, c_cohorts)| The ouput Confidence matrix|