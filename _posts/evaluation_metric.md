### Understanding evaluation metric for a classifier in imbalanced dataset
This is the summary/note from this [Source](https://machinelearningmastery.com/tour-of-evaluation-metrics-for-imbalanced-classification/)

#### Taxonomy of Classifier Evaluation Metrics
1) Threshold metrics <br />
2) Ranking Metrics <br />
3) Probability Metrics <br />


1) **Threshold Metrics**: These metric quantify the class perdiction error and are used to summarize the fraction, ratio or rate of when predicted class does not match the expected class in test dataset. <br />
  **Accuracy** = $\frac{\text{correct predictions}}{\text{total predictions}}$  <br />
  **Error** = $\frac{\text{Incorrect predicitons}}{\text{total predictions}}$ <br />
  
  Both error and accuracy are inappropriate for imbalanced classification as even no skill model can have good performance by just prediciting majority class.
  
  **Sensitivity** = $\frac{\text{True Positive}}{\text{True Positive + True Negative}}$  <br />
  **Specificity** = $\frac{\text{True Negative}}{\text{False Positive + True Negative}}$ <br />
  **G-Mean** = $\sqrt{Sensitivity*Specificity}$ <br />
  
  **Precision** = $\frac{\text{True Positive}}{\text{True Positive + False Positive}}$  <br />
  In other words, it shows of all the positive predictions, how many of them are truly positive. <br />
  **Recall** = $\frac{\text{True Positive}}{\text{True Positive + False Negative}}$  <br />
  **F1 score** = $\frac{\text{2 * Precision * Recall}}{\text{Precision + Recall}}$  <br />
  
  **micro-averaged Precision**: In multi-class data, the micro-averaged precision is the ratio of true positives to total number of true positive and false positive in whole data set regardless of class. <br />
  **micro-averaged Recall**: In multi-class classification, the micro-averaged recall is the ratio of number of true positives to total number of true positives and false negatives in whole data set regardless of class. <br />
  
  **micro-averaged F1 score**: Micro averaged F1 score is the harmonic mean of micro-averaged precision and micro-averaged recall. It is useful to evaluate the overall performance of the model without considering the individual class performance however it may be influenced by the majority class in imbalanced data sets. <br />
  
  **macro-averaged F1 score:** Macro-averaged F1 score is the average of F1 score of each class. This evaluation metric **might not** be suitable for imbalanced data sets as it treats each class equally and does not consider the class distribution.  <br />
  **Weighted average F1 score:** Weighted average F1 score is variant of the F1 score that calculates average of F1 score for each class weighted by the number of observations in each class. This metric takes into account both the individual class performance and the class distribution. It gives more weight to class with larger number of samples. The formula for the weighted average F1 score is given below: <br />
  $$\text{Weighted Average F1 score =} \sum_{i=1}^{N}{(F1_i)*S_i}$$
  
  where $F1_i$ is F1 score of class i. $S_i$ is the support proportion. Support proportion is the ratio of number of observation in a class to total observation.
  
  **Which metric to use in-case of imbalanced data set?** <br />
  If the data set is imbalanced and all classes are equally important, micro average F1 is a good metric to use. <br />
  If we want to assign greater contribution to classes with majority class then the weighted average is a good metric to use. <br />
  If we want a metric regardless of the class, micro averaged F1 score or accuracy. <br />

2) **Ranking Metrics for Imbalanced Classification** <br />
Ranking metrics evalucates how good the classifier is at separating classes. <br />

**ROC-Curve:** ROC-Curve is the a diagnostic plot of summarizing the behavior of a classifier model by plotting 'True Positive Rate' against the 'False Postive Rate' at different thresholds. A classifier that predicts majority class under all thresholds is represented by diagonal line in ROC curve. The area under the ROC curve (ROC AUC) can be calculated and this gives a single metric that can be used to compare model. In case of severe class imbalance, the ROC AUC can be optimistic.

**Precision-Recall Curve:** The curve in which precision is plotted against recall at different threshold is Precision-Recall Curve. The classifier that does better than random model has a curve above a horizontal line that is proportional to the number of positive observations in dataset. For balanced dataset, this would be 0.5. Area under the curve can be calculated for precision-recall curve which gives a single metric called 'Precision-Recall AUC' for comparison across the models. In case of imbalanced dataset where the minority class is more important, 'Precision-Recall AUC' is more useful.

3) **Probabilistics Metric for Imbalanced Classification**
   Probabilistic metics are used for quantifying the uncertainty in classifier's predictions.
