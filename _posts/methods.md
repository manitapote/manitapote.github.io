
<details>
  <summary></summary>
  [Link]()
  
  ##### 
  
</details>

<details>
  <summary>Hypothesis Testing</summary>
  [Link](Think Stats)
  
  ##### Classical Hypothesis Testing
  - The first step is to quantify the size of the apparent effect by choosing a test statistis. For example: test statistics could be difference in mean between two group, Chi square test statistics
  - Define null hypothesis, which is a model of the system based on the assumption that the apparent effect is not real.
  - Third step is to compute a p-value which is the probability of seeing the apparent effect if the null hypothesis is true. (the probability of seeing a difference as big or bigger under the null hypothesis)
  - Interpret the result, if the p-value is low the effect is said to be statistically significant.
  
  ##### Error 
  An effect is considered statistically significant if the p-value is below some threshold, commonly 5%. This procedure raises two questions. 
  - If the effect is actually due to chance what is the probability that we will wrongly consider it significant? The probability is the **false positive rate**.
  - If the effect is real, what is the chance that the hypothesis test will fail? This probability is the **false negative rate**.
  
  If the threshold is 5%, the false positive rate is 5%.
  
  ##### Power
  The false negative rate is harder to compute because it depends on the actual effect size and normally we don't know that. One option is to compute a rate conditioned on a hypothetical effect size.
  The correct positive rate is called the power of the test, or
sometimes 'sensitivity'. It reflects the ability of the test to
detect an effect of a given size.
As a rule of thumb, a power of 80% is considered acceptable so
a test with 30% power is called underpowered.
In general a negative hypothesis test does not imply that there is
no difference between the groups; instead it suggests that if 
there is a difference, it is too small to detect with this sample
size.

Replication:
If we explore larger dataset, find a surprising effect,
and then test whether it is significant, we have good chances,
of generating a false positive.

Usually, the dataset used for exploration and testing are
different.
  
</details>

<details>
  <summary>Statistics</summary>
  [Link]()
  
  There are two school of thoughts in statistics:
  - **Frequentist**: The frequentist viewpoint holds that the parameters of probabilistic models are fixed, but we just don't know them. 
  - **Bayesian**: The Bayesian viewpoint holds that model parameters are  not only unkown, but also random. In this case, we'll encode our prior belief about them using a probability distribution.
  
</details>

### Cohen's Kappa
### Fleiss K
### Welch's t-test
### Chi-squared test


