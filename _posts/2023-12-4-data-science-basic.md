
<script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

<details>
  <summary>Resoures</summary>
  

  [Data Science Interview Resources: rbhatia46](https://github.com/rbhatia46/Data-Science-Interview-Resources) <br />
  [Data Science Interview Resources : cdeweyx](https://github.com/cdeweyx/DS-Career-Resources/blob/master/Interview-Resources.md)  
  [Forms PhD](https://luddy.indiana.edu/academics/grad-programs/graduate-forms/index.html)
</details>


<details>
  <summary></summary>
</details>

<details>
  <summary>Handling Class Imbalance </summary>
  
  1) **Resampling method** <br />
  
  - We can **oversample** the minority classs until certain ratio is reached. The model might overfit in this case. <br />
  - Another method is **SMOTE (Synthetic Minority Oversampling Technique)**. In this method new examples are generated from minority class using 'k' nearest neighbors. SMOTE first selects a minority class instance 'a' at random, finds its 'k' nearest minority class neighbors and then create a new instance by convex combination of 'a' and anyone of the neighbor at random. This basically means new instance is created along the line segments connecting 'a' and the selected neighbor. The new instance is created without considering the majority class therefor the resulting example might be ambiguous if there is a strong overlap for the classes.<br /> <br />
  **What is convex combination?** <br />
  - In a given set of points in a convex set, a convex combination is a way to express a new point as a weighted average of those points where weights are non-negative and sum to 1.
  The combination of SMOTE and under-sampling performs better than plain under-sampling. <br /> <br />
  - **Undersampling the majority class** : If there are not enough instances in minority class, the model in this approach might not learn the pattern. <br /> <br />
  
- **Tomek links** : We find a pair of examples from opposite class that are close in proximity and remove the sample of majority class in each pair. This might lead to case where the model can not learn the subtle decision boundary.<br /><br />

2) **Model level method** :
  - This method makes model more robust to class imbalance. We can update loss function by weighting the loss inverse of the class ratio.
  - **Tree-based models** and **logistic regression** work well on tasks involving small and imbalanced datasets. <br />
  - We can combine multiple techniques, example: under sampling and ensemble, under-sampling and update loss function <br /><br />
  
  3) **Evaluation metric method** :
  - AUC of ROC curve, Precision-Recall curve <br />
  - Precision, Recall and F1 for positive class. <br /><br />
  
</details>


<details>
  <summary> Probability and Statistics explained in the context of deep learning </summary>
  
  [Source](https://towardsdatascience.com/probability-and-statistics-explained-in-the-context-of-deep-learning-ed1509b2eb3f)
  
  **Discrete and Continuous probability**: The matrices in intermediate layers of Neural Network are randomly initialized from certain probability distributions. Some of the distributions that are used are as follows: <br />
  - **Binomial Distribution** <br />
  - **Continuous distributions**: In continuous distribution, we describe the distribution using probability density functions(pdf) denoted by p(x).<br />
  $$\int_{}^{} p(x)dx=1$$
  - **Uniform distribution**: Continuous distribution with every element equally likely. <br />
  pdf $$f(x) = \frac{1}{b-a}$$ x belongs to [a,b] <br />
  mean $$E(X) = \frac{(a+b)}{2}$$ <br />
  variance $$var(x) = \frac{(b-a)^2}{12}$$
  - **Normal Distribution**: “Order from Chaos” <br /> 
  In the absence of prior knowledge about what form a distribution over the real numbers should take, the normal distribution is a good choice because, it has high entropy and central limit theorem suggests that sum of several independent random variables is normally distributed.
  - **Exponential distribution**
  - **Poisson distribution**
  - **Softmax distribution**
  
##### Model accuracy measurement tools:
  
  
  Variance = $$Var(X) = E[(x - E(x))^2]$$
 
  Covariance: It shows how two variables are linearly related to each other. 
  $$Cov(X,Y)=E(X-\overline{X}).E(Y-\overline{Y})$$ where $\overline{X}$ and $\overline{Y}$ are mean values of X and Y.
  
</details>


<details>
  <summary> Understanding Descriptive Statistics (other kind is Understanding Descriptive Statistics)</summary>

[Source](https://towardsdatascience.com/understanding-descriptive-statistics-c9c2b0641291)
  
Descriptive Statistics seeks to describe the data especially samples. It is not developed on the basis of probability theory.
Types: <br />
- The measure of Central Tendency: Central Tendency refers to the idea that there is one number that best summarizes the entire  set of measurements.
  - **Mean/Avrage**: Number around which whole data is spread out.
  - **Median**: Value that divides the data into 2 equal parts. If we sort data in descending order, it won't affect the median but IQR will be negative. For the values with
    arithmetic progression (the difference between the consecutive terms is constant), the median is always equal to the mean.
  - **Mode**: The term appearing maximum time in dataset i.e. term that has the highest frequency. If two values appeared same time and more than the rest of the values then the data
    set is bimodal. If three values appreared same time and more than the rest of the values then the data set is trimodal and for n modes, the data set is multimodal.
- The measure of spread/dispersion
  - **Standard Deviation(SD)**: The measurement of the average distance between each quantity and mean. That is, how data is spread out from the mean. A low standard deviation indicates that the data
    points tend to be close to the mean of the data set, while a high standard deviation indicates that the data points are spread out over a wider range of values.
    The formula for population SD is different than the one for sample:
    $$SD_{sample} = \sqrt{\frac{1}{n-1}\sum_{i=0}^{n}(x_i - \overline{x})^2}$$
    $$\sigma = \sqrt{\frac{1}{n}\sum_{i=0}^{n}(x_i - \mu)^2}$$
    The reason for this is in the [Link](https://math.stackexchange.com/questions/15098/sample-standard-deviation-vs-population-standard-deviation?utm_medium=organic&utm_source=google_rich_qa&utm_campaign=google_rich_qa).
    
  - **Mean Deviation/Mean Absolute Deviation**: It is an average of absolute differences between each value in a set of values and the average of all values of that set.
    $$MD = \frac{1}{n}\sum_{i=0}^{n}{|x_i - \overline{x}|}$$
  - **Variance**: square of average distance between each quantity and mean.
  - **Range**: The difference between the lowest and highest value.
  - **Percentile**: The way to represent position of values in dataseet. In general, if *k* is *nth* percentile, it implies that *n%* of the total terms are less than *k*.
  - **Quartiles**: Quartiles are values that divides your data into quarters provided data is sorted in an ascending order.
    IQR = Q3 - Q2
  - **Skewness**: The measure of the asymmetry of the probability distribution of a real-valued random variable about the mean. The value can be positive or negative or undefined.
    When a distribution is skewed to the left, the tail on the curve's left-hand side is longer than the tail on the right-hand side, and the mean is less than the mode. This situation is negative skewness.
    Formulas to calulate skewness:
    1) Pearson First Coefficient of Skewness (Mode skewness)
      $$\frac{mean - mode}{Standard Deviation}$$
    2) Pearson second coefficient of skewness (Median skewness)
      $$\frac{3(mean - median)}{Standard Deviation}$$
  
  Interpretations: 
    - The direction of skewness is given by the sign. A zero means no skewness at all.
    - A negative value means the distribution is negatively skewed. A positive value means the distribution is positively skewed.
    - The coefficient compares the sample distribution with a normal distribution. The larger the value, the larger the distribution differs from a normal distribution.
  
  - **Kurtosis**: Its about the existence of outliers. Kurtosis is a measure of whether the data are heavy-tailed (profusion of outliers) or light-tailed (lack of outliers) relative to a normal distribution.
    There are three types of kurtosis:
    - Mesokurtic: The disribution that has similar kurtosis as normal distribution kurtosis, which is zero.
    - Leptokurtic: The distribution that has kurtosis greater than a Mesokurtic distribution. Tails of such distributions are thick and heavy. If the curve of distribtuion is more peaked than the Mesokurtic curve, it is referred to as a Leptokurtic curve.
    - Platykurtic: The distribution that has kurtosis lesser than a Mesokurtic distribution. Tails of such distributions are thinner. If a curve of a distribution is less peaked than Mesokurtic curve, it is referred to as a Platykurtic curve.
  
  The main difference between skewness and kurtosis is that the skewness refers to the degree of symmetry whereas the kurtosis refers to the degree of presence of outliers in the distribution.
  
 - **Correlation**: Statistical technique that can show whether and how strongly pairs of variables are related. The result range from -1 to 1. The closer *r* (correlation coefficient) is to +1 or -1, the more closely the two variables are related.
 </details>
    
