## Papers

<details>
  <summary>Clustering Alogrithms</summary>
  [Link]()
  
  It is a class of unsupervised algorithms for grouping unlabeled data. If the labels are present then the task is classification. 
  
  
  Clustering task gives a cluster id to to a group of datapoints which is in result consensing the entire featue set for an example into cluster id. Clustering data can simplify large datasets. Output of clustering can serve as feature for downstream ML systems. <br />
  **Where can clustering be used ?** <br />
  - Generalization
  - Data Compression
  - Privacy preservation
  
 **Generalization**: When some examples in cluster have missing feature data, we can infer the missing data from other examples in cluster. <br />
  **Data Compression**: Feature data for all examples in a cluster can be replaced by the relevant cluster ID. This replacement simplifies the feature data and saves storage. This is benefitial in large datasets. Cluster ID itself can be used as input to ML instead of entire feature set.
  **Privacy Preservation**: We can preserve the privacy of user by associating user data with cluster ID instead of specific users. 
  
  Criterias for choosing clustering algorithms:
  - How does the algorithm scales to dataset? Many clustering algorithms work by computing the similarity beween all pairs of examples. This means their runtime increases as the square of number of exmaples n, denoted as $O(n^2)$
  
 
  ##### 
  
  ##### Similarity Measures
  
</details>


<details>
  <summary>Clustering attributed graphs: models, measures and methods (2015)</summary>
  [Link](https://arxiv.org/abs/1501.01676)
  
  ##### 
  
</details>
