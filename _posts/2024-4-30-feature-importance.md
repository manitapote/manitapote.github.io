#### Understanding Feature Importance in Machine Learning

[Source](https://towardsdatascience.com/the-mathematics-of-decision-trees-random-forest-and-feature-importance-in-scikit-learn-and-spark-f2861df67e3)
[Node Impurity](https://www.baeldung.com/cs/impurity-entropy-gini-index)


**Decision Trees:** Decision trees learn how to best split the dataset into smaller and smaller subsets to predict the target value. The condition, or test, is represented as the 'leaf' (node) and the possible outcomes as 'branches' (edges). This splitting process continues until no further gain can be made or a preset rule is met, eg. the maximum depth of the tree is reached. <br /><br />

**Decision Tree Algorithms:** <br />
A decision tree is a greedy algorithm we use for supervised machine learning tasks such as classification and regression. <br /> <br />
1) Splitting in Decision Trees <br />
- Firstly, the decision tree nodes are split based on all the variables. During the training phase, the data are passed from a root node to leaves for training. A decision tree uses different algorithms to decide whether to split a node into two or more sub-nodes. The algorithm chooses the partition maximizing the purity of the split (i.e. minimizing the impurity). Informationally, impurity is a measure of homogeneity of the labels at the node at hand. For classification task, Gini impurity index and entropy are used. <br /><br />
**Gini Impurity** <br />
Let's assume that a dataset $T$ contains examples from $n$ classes. Its Gini Index, $gini(T)$, is defined as: <br />
$gini(T) = 1 - \sum_{j=1}^{n} p_j^2$

<br /><br />
Example: For a sample of 4 balls of two colors, red and blue: <br />
4 red and 0 blue balls:
$gini = 1 - (P(ball=red)^2 + P(ball=blue)^2) = 1 - (1+0) = 0$ <br />
2 red and 2 blue balls:
$gini = 1 - (P(ball=red)^2 + P(ball=blue)^2) = 1 - ((\frac{1}_{2})^2 +(\frac{1}_{2})^2) = 0.5$ <br />
3 red and 1 blue balls: 
$gini = 1 - (P(ball=red)^2 + P(ball=blue)^2) = 1 - ((\frac{3}_{4})^2 +(\frac{1}_{4})^2) = 0.375$ <br /> <br />
The intuition behind the gini impurity is same as entropy. Higher the uncertainity higher is the impurity.
<br /><br />

**ID3**:
**CART**:
**Random Forests(RF):** RF construct many individual decision trees at training. Predictions from all trees are  pooled to make the final prediciton; the mode of the classes for classification or the mean prediciton for regression. As they use a collection of results to make a final decision, they are referred to an Ensemble techniques. <br /><br />

**Information Gain**: $Gain(T,X) = Entropy(T) - Entropy(T,X)$ <br />
It is calcualted as the decrease in entropy after the dataset is split on an attribute. <br />
T = Target Variable <br />
X = Feature to be split on <br />
Entropy(T,X) = The entropy calculated after the data is split on feature X <br />

**Feature Importance** <br />
Feature importance is calcuated as the decrease in node impurity weighted by the probability of reaching that node. The node probability can be calculated by the number of samples that reach the node, divide by the total number of samples. The higher the value the more important the feature. <br /><br />
**Feature importance** is a step ofmachine learning that involves calculating the score for each feature to establish importance of  each feature in prediciton. The higher the score for a feature, the larger effect it has on the model to predict a certain variables.<br /><br />

**Why is feature importance is needed?** <br />
- It helps to find irrelevant features of the model.
- Feature importance helps to reduce the dimensionality of the model. Higher scores are kept and lower scores are deleted as they are not important for the model.
- It helps to interpret and communicate the model to other stakeholders. By calculating scores for each feature, we can determine which feature attribute the most to the predicitve power of the model.
  <br /><br />

**Methods of Feature Importance:**
- **Gini Importance:** <br /><br />
Assuming only two child nodes (binary tree): $ni_j = w_jC_j - w_{left(j)}C_{left(j)} - w_{right(j)}C_{right(j)}$ <br /><br />
- $ni_j$ = importance of node j <br />
- $w_j$ = weighted number of samples reaching node j <br />
- $C_j$ = impurity value of node j <br />
- $left(j)$ = child node from left split on node j <br />
- $right(j)$ = child node from right split on node j <br /><br />
  The importance for each feature on a decision tree is then calculated as: <br />
  $fi_i = \frac{\sum{j:node} (j split on feature i ni_j)}_{\sum{k E all nodes}_{ni_k}}$

- fi sub(i) = the importance of feature i
- ni sub(j) = the importance of node j
 
<br />
Impurity-based importance are biased towards high-cardinality and numerical features: <br />
- High-Cardinality features: High-cardinality features are those with a large number of unique values. These features tend to have more levels or categories, leading to more opportunities for splitting the data and reducing impurity. As a result, decision trees may assign higher importance to high-cardinality features because they have the potential to provide more information gain. <br />
- Numerical Features: Numerical features with wide range of values tend to be assigned higher importance in impurity-based calculations. This is because numerical features can be split at multiple points along their range, leading to finer-grained partitions of the data and potentially greater reductions in impurity.
-  It simply reflects the way impurity-based feature importance calculations prioritize features that lead to greater reductions in impurity when making splits in the decision tree. In some cases, other types of features (such as categorical features with a small number of levels) may still be highly predictive, even if they are not assigned as high importance scores in impurity-based calculations. <br /><br />


- **Permutation importance:**
