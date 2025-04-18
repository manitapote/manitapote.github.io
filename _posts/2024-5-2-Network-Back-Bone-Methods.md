#### Different Network BackBone Extraction Methods
Source : [Altlas of Network Science](https://arxiv.org/abs/2101.00863)<br />
All the images and content are taken from Source.
##### Bi-partite Graph Projection
Projection of bi-partite graph with hyperbolic weight. <br />
Assumption:
- The hubs contribute less to the connection weight than non-hubs. For a connection given below:
  ![Bi-partite graph](hyperbolic.PNG)

  $$ w_(u,v) = \sum_{z \epsilon N_u \bigcap N_v } \frac{1}_{k_z -1} $$
  $$K_z is the degree of Z$$
  This method exaggerates the differences in weights so that thresholding becomes easier. The minus sign in the denominator never checks its similarity with itself.
  $$A*A^T$$ counts the degree. <br /><br />

  Resource Allocation: <br />
  ![Resource Allocation](resource.PNG)

 $$w_{u,v} = \sum_{|z \cap N_u \cap N_v|}{\frac{1}_{|N_u| \cdot |N_v|}$$

#### Graph Sparsification
Graph sparsification, sometimes called 'prunning' in combinatorics and neural networks is an alternative name for backboning. It is the process of simplify the network to be computationally tractable as well as filter out the noise so the connections we are observing are real connections. We need statistical test to determine that.
This process is different than graph summarization. In graph summarization, we take large complex network and reduce the size so that we can describe it better. Graph summarization may involve merging nodes into 'meta nodes'.

#### Methods of Graph Sparsification
1) Naive: For naive method, we choose a threshold of edge weight and filter out all the edges less than the threshold. Problem with naive method:
   - Broad weight distribution: Most of the real networks are fat tail skewed network. If we take a hard threshold, we will remove network without allowing any nuances. Also highly skewed distribution lacks a well defined average value and has undefined variance. We can not motivate our threshold choice by saying that it is 'x standard deviations from the average' or anything resembling this formula.
   - Local Edge Weight Correlations:  The edge weights are usually correlated. Nodes that connect strongly tend to connect strongly with everybody. Lets assume a user **u** shares only one url. If **u** connects to any **v**, there can be only one possible edge weight in the simple projection: one. All the edges around **u** will have weight equal to one. If **u** had shared thousands of URLs, it will likely connect to another user with similar sharing patterns, because statistically speaking they have high odds of sharing at least few of the same URLs, even if it happens by chance. Thus many edges around **u** will have high weights. The weight of an edge is correlated with the weights of the edges of the nodes it connects. Another method we can apply is to simply pick the top **n** strongest connections for each node. However, by applying it we are effectively determining the minimum degree of the network to be **n**. This will not work for power law degree distribution.
  
2) Doubly stochastic: <br />
   Row Stochastic matrix: All the elements in row adds up to 1.<br />
   Column Stochastic matrix: All the elements in column adds up to 1.<br />
   Regular matrix: A stochastic matrix is also a regular matrix if $P^n$ (n>1) has only non-zero positive entries.<br />
   Doubly stochastic matrix: If all the elements in row adds to 1 as well as all the elements in column also adds to 1 then it is doubly stochastic matrix.<br /><br />
   After we convert the matrix into doubly stochastic, we break the local correlations. We can now threshold the edges. We should pick the threshold that allows for the graph to be single connected component. The problem with this method is not all matrix can be converted into doubly stochastic. Only positive non zero matrix can converted. A real network has alot of zeros. Adding a small noise could be a trick but as $\epsilon -> 0, A+ \epsilon -> A$ but the normalization of $A + \epsilon$ does not converge. Also doubly stochastic matrix must be square.

3) High-salience Skeletion (HSS):<br />
For some network, the structure faciliting the exchange of information or goods are more important, connections that keep  the network together in a single component as well as the have the high throughput is important. To build a HSS network, we loop over the nodes and we build their shortest path tree: a tree originating from a node, touching all other nodes in the minimum number of hops possible and maximum amount of edge weight possible. In practice we start exploring the graph with a BFS and note down the total edge weight of each path. When we reach an node that we already visited we consider the edge weights of the two paths and the one with the highest one wins. Reminder a tree can not have a triangle. We perform this operation for all nodes in the network and we obtain a set of shortest path trees. We sum them so that each edge now has a new weight: the number of shortest path trees in which it appears. The network can now be thresholded with these new weights. We could have used betweenness centrality but it is  global measure. Forbidding the creation of cycles in shortest path trees causes the main difference with the edge betweenness measure. One could think that the edge are simply sorted according to their contributions to all shortest paths in the network, but that is not the case. By forcing the substructures to be trees, we are counting the edges that are salient from each node's local perspective, rather than the network's global perspective. 
<br /><br />
   
5) Convex Network Reduction: <br />
A subgraph of a network $G$ is convex if it contains all shortest paths existing in the main network $G$ between its $V' \subseteq V$ nodes.

7) Disparity Filter:
   This method
9) Noise-Corrected


Bi-partite;
- Fixed Sequence Degree Method
- Fixed Fill Method
- Fixed Row Method
- Fixed Column Method
- The stochastic degree sequence model
- 
