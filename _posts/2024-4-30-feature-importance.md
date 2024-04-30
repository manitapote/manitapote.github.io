#### Understanding Feature Importance in Machine Learning

[Source](https://towardsdatascience.com/the-mathematics-of-decision-trees-random-forest-and-feature-importance-in-scikit-learn-and-spark-f2861df67e3)
[Node Impurity](https://www.baeldung.com/cs/impurity-entropy-gini-index)


**Decision Trees:** Decision trees learn how to best split the dataset into smaller and smaller subsets to predict the target value. The condition, or test, is represented as the 'leaf' (node) and the possible outcomes as 'branches' (edges). This splitting process continues until no further gain can be made or a preset rule is met, eg. the maximum depth of the tree is reached. <br /><br />

**Decision Tree Algorithms:** <br />
A decision tree is a greedy algorithm we use for supervised machine learning tasks such as classification and regression. <br /> <br />
1) Splitting in Decision Trees <br />
- 
<br /><br />

**ID3**:
**CART**:
**Random Forests(RF):** RF construct many individual decision trees at training. Predictions from all trees are  pooled to make the final prediciton; the mode of the classes for classification or the mean prediciton for regression. As they use a collection of results to make a final decision, they are referred to an Ensemble techniques. <br /><br />

**Information Gain**: $Gain(T,X) = Entropy(T) - Entropy(T,X)$ <br />
It is calcualted as the decrease in entropy after the dataset is split on an attribute. <br />
T = Target Variable <br />
X = Feature to be split on <br />
Entropy(T,X) = The entropy calculated after the data is split on feature X <br /> <br />

**Feature Importance** <br />
Feature importance is calcuated as the decrease in node impurity weighted by the probability of reaching that node. The node probability can be calculated by the number of samples that reach the node, divide by the total number of samples. The higher the value the more important the feature. <br /><br />
**Feature importance** is a step ofmachine learning that involves calculating the score for each feature to establish importance of  each feature in prediciton. The higher the score for a feature, the larger effect it has on the model to predict a certain variables.<br /><br />
<br /><br />

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
- $right(j)$ = child node from right split on node j <br />

- Permutation importance: 
