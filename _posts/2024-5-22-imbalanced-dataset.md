#### How to handle extremely imbalanced dataset?

1) Undersampling
One way of handling imbalanced dataset is to reduce the number of observations from all classes but the minority class. The most well known algorithm in this group is random undersampling, where samples from the targeted classes are removed at random. There are more ways to do so, they can be grouped based on their undersampling strategy into:
- Prototype generation methods
- Prototype selection methods

#### Prototype Generation

Given original data set $S$, prototype generation algorithms will generate a new set $S'$ where $|S'| < |S|$ and $|S|$&#8836$S$. The prototype generation techniques will reduce the number of samples in the targeted classes but the remaining samples are generated - and not selected - from the original set.
Some of the methods are :
**ClusterCentroids** makes use of K-means to reduce the number of samples. Therefore, each class will be synthesized with the centroids of the K-means method instead of the original samples.

####  Prototype Selection
This algorithms select samples from the original set $S$ generating a dataset $S'$ where $|S'| < |S|$ and $S' \subset S$. $S'$ is subset of $S$. Prototype selection algorithms can be divided into two groups:
(i) controlled under-sampling techniques and (ii) cleaning under-sampling techniques. <br /><br />

Controlled under-sampling methods reduce the number of observations in the majority class or classes to an arbitrary number of samples specified by the user. Typically, they reduce the number of observations to the number of samples observed in the minority class. <br /><br />
In contrast, cleaning under-sampling techniques 'clean' the feature space by removing either 'noisy' or 'too easy to classify' observations, depending on the method. The final number of observations in each class varies with the cleaning method and can't be specified by the user.

##### Controlled under-sampling techniques
It involves random undersampling to match the data size of minority class.

##### Cleaning under-sampling techniques
Cleaning under-sampling methods 'clean' the feature space by removing either noisy observations or observations that are 'too easy to classify', depending on the method. The final number of observations in each targeted class varies with the cleaning method and cannot be specified by the user. Some of these algorithms are:

1) Tomek Links: Tomek Links are pairs of instances from different classes that are each other's nearest neighbors. Removing the majority class instance from these pairs can help in creating a clearer decision boundary between classes. <br />
Algorithm:
- Identify all pairs of nearest neighbors from different classes.
- If an instance from the majority class is part of a Tomek Links, remove it. <br /><br />

2) Condensed Nearest Neighbor (CNN)
CNN aims to retain a subset of instances from the majority class that are crucial for defining the decision boundary. <br />
Algorithm:
- Start with an empty set 'S'
- Add all minority class instances to 'S'
- For each majority class instance:
    - If the instance is misclassified by the current set 'S', add it to 'S'

3) One-sided selection (OSS)
- OSS combines Tomek Links and CNN to remove both noisy instances and redundant instances from the majority class. <br />
Algorithm: <br />
- Apply CNN to reduce the majority class
- Apply Tomek Links to the reduced set to remove noisy instances

4) Edited Nearest Neighbor (ENN)
- For each instance, find its k-nearest neighbors
- If the instance is misclassified by the majority of its neighbors, remove it.

5) Neighborhood Cleaning Rule (NCL)
NCL combines ENN and Tomek Links to clean the dataset by removing misclassified instances and borderline instances. <br />
Algorithms: <br />
- Apply ENN to remove misclassified instances
- Apply Tomek Links to remove borderline instances.




