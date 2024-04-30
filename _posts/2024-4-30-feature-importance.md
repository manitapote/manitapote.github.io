#### Understanding Feature Importance in Machine Learning

[Source](https://towardsdatascience.com/the-mathematics-of-decision-trees-random-forest-and-feature-importance-in-scikit-learn-and-spark-f2861df67e3)

Feature importance is a step ofmachine learning that involves calculating the score for each feature to establish importance of  each feature in prediciton. The higher the score for a feature, the larger effect it has on the model to predict a certain variables.<br /><br />

Why is feature importance is needed?<br />
- It helps to find irrelevant features of the model.
- Feature importance helps to reduce the dimensionality of the model. Higher scores are kept and lower scores are deleted as they are not important for the model.
- It helps to interpret and communicate the model to other stakeholders. By calculating scores for each feature, we can determine which feature attribute the most to the predicitve power of the model.

<br /><br />
**Decision Trees:** Decision trees learn how to best split the dataset into smaller and smaller subsets to predict the target value. The condition, or test, is represented as the 'leaf' (node) and the possible outcomes as 'branches' (edges). This splitting process continues until no further gain can be made or a preset rule is met, eg. the maximum depth of the tree is reached. <br /><br />
**Decision Tree Algorithms:** 
**ID3**:
**CART**:

**Information Gain**: $Gain(T,X) = Entropy(T) - Entropy(T,X)$ <br />
It is calcualted as the decrease in entropy after the dataset is split on an attribute.
T = Target Variable <br />
X = Feature to be split on <br />
Entropy(T,X) = The entropy calculated after the data is split on feature X <br />
Methods of Feature Importance:
- Gini Importance: 


- Permutation importance: 
