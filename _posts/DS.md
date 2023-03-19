### Understanding Descriptive Statistics (other kind is Understanding Descriptive Statistics)


Descriptive Statistics seeks to describe the data especially samples. It is not developed on the basis of probability theory.
Types: <br />
- The measure of Central Tendency: Central Tendency refers to the idea that there is one number that best summarizes the entire  set of measurements.
  - Mean/Avrage: Number around which whole data is spread out.
  - Median: Value that divides the data into 2 equal parts. If we sort data in descending order, it won't affect the median but IQR will be negative. For the values with
    arithmetic progression (the difference between the consecutive terms is constant), the median is always equal to the mean.
  - Mode: The term appearing maximum time in dataset i.e. term that has the highest frequency. If two values appeared same time and more than the rest of the values then the data
    set is bimodal. If three values appreared same time and more than the rest of the values then the data set is trimodal and for n modes, the data set is multimodal.
- The measure of spread/dispersion
  - Standard Deviation(SD): The measurement of the average distance between each quantity and mean. That is, how data is spread out from the mean. A low standard deviation indicates that the data
    points tend to be close to the mean of the data set, while a high standard deviation indicates that the data points are spread out over a wider range of values.
    The formula for population SD is different than the one for sample:
    $$SD_{sample} = \sqrt{\frac{1}{n-1}\sum_{i=0}^{n}(x_i - \overline{x})^2}$$
    $$\sigma = \sqrt{\frac{1}{n}\sum_{i=0}^{n}(x_i - \mu)^2}$$
    The reason for this is in the [Link](https://math.stackexchange.com/questions/15098/sample-standard-deviation-vs-population-standard-deviation?utm_medium=organic&utm_source=google_rich_qa&utm_campaign=google_rich_qa).
    
  - Mean Deviation/Mean Absolute Deviation: It is an average of absolute differences between each value in a set of values and the average of all values of that set.
    $$MD = \frac{1}{n}\sum_{i=0}^{n}{|x_i - \overline{x}|}$$
  - Variance: square of average distance between each quantity and mean.
  - Range : The difference between the lowest and highest value.
  - Percentile: The way to represent position of values in dataseet. In general, if *k* is *nth* percentile, it implies that *n%* of the total terms are less than *k*.
  - Quartiles: Quartiles are values that divides your data into quarters provided data is sorted in an ascending order.
    IQR = Q3 - Q2
  - Skewness: The measure of the asymmetry of the probability distribution of a real-valued random variable about the mean. The value can be positive or negative or undefined.
    When a distribution is skewed to the left, the tail on the curve's left-hand side is longer than the tail on the right-hand side, and the mean is less than the mode. This situation is negative skewness.
    
