
<details>
  <summary></summary>
  [Link]()
  
  ##### 
  
</details>

<details>
  <summary>Burstiness measure</summary>
  [Link]()
  
  ### Inter-spike intervals (ISIs): 
  Inter-spike interval (ISI) analysis, which is a common technique in neuroscience, can also be used in computational social science to study the dynamics and patterns of social media activity. Specifically, ISI analysis can be used to analyze the temporal patterns of individual users' behavior on social media platforms. ISI analysis can also be used to investigate the regularity of behavior, such as identifying users who have highly regular posting patterns or who exhibit irregular activity. 
  
  
  Interpreting ISI:
  
  Mean and standard deviation: The mean and standard deviation of the ISIs can provide information about the regularity of the event timing. If the mean ISI is small and the standard deviation is also small, it suggests that the events are occurring at a regular interval. On the other hand, if the mean ISI is large and the standard deviation is also large, it suggests that the events are occurring at an irregular interval.

Coefficient of variation (CV): The CV is a measure of the relative variability of the ISIs. A low CV indicates that the ISIs are relatively consistent, while a high CV suggests that the ISIs are more variable. The CV is a useful measure when comparing different time series, as it allows you to assess the relative regularity of the event timing.

Fano factor: The Fano factor is a measure of the variability in the number of events that occur within a given time interval. If the Fano factor is close to 1, it suggests that the events are occurring at a relatively constant rate. If the Fano factor is greater than 1, it suggests that the event rate is more variable than would be expected by chance, while a Fano factor less than 1 suggests that the event rate is less variable than expected by chance.
  
  ##### 
  
</details>

<details>
  <summary>How weighted degree works?</summary>
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
  
  ### T-test: Inferetial statistics
  - Assumption: Normal distribution
    - Similar vairance
    - Datapoints: same number in two groups (20-30)
  
  - Compare two groups
  - Issue with considering mean: variation in distribution can produce statistically significant result
  - ratio of signal/noise = (difference group mean)/(variablity of groups itself) = $\frac{|\overline{x}_1 - \overline{x}_2|}{\sqrt{\frac{S^1_1}{n_1} + \frac{S^2_2}{n_2}}}$ where $\frac{S}{n}$ is variance
  - Higher values of the t-score indicate that a large difference exists between the two sample sets. The smaller the t-value, the more similarity exists between the two sample sets.
  
  Problem with T-test:
  When to use:
  
  ### Paired T-test or correlated t-test (dependent samples t-test, the paired difference t-test, the matched pairs t-test and the repeated-samples t-test)
  This T-test is performed when the samples consist of similar units or when there are repeated measures. For example: before and after measurements for a group of people. 
  Assumption: 
  - The distribution of differencess between the paired measurements should b normally distributed.
  - Subjects in the study should be independent.
  - Each of the paired measurements must be obtained from same subject.
  
 Formula:
  $\overline{x_d} =$ average of differences <br />
  Standard Error = $\frac{s_d}{\sqrt{n}}$ <br />
  Degree of freedom (df) = n -1
  
  $t = \frac{\text{Average difference}}{\text{Standard Error}}$ <br />
  
  The conclusion: If value lower than the t-table statistics, it means it might have occured by chance. If the difference is greater that means it is not by chance. <br />
  
  [What if it is not normally distributed?](https://www.jmp.com/en_us/statistics-knowledge-portal/t-test/paired-t-test.html) <br />
  "What if you know the underlying measurements are not normally distributed? Or what if your sample size is large and the test for normality is rejected? In this situation, you can use nonparametric analyses. These types of analyses do not depend on an assumption that the data values are from a specific distribution. For the paired t­-test, a nonparametric test is the Wilcoxon signed-rank test. "
  
  <details>
  <summary>Chi-squared test</summary>
  [Link]() <br />
   Chi-square test is used to check if observed frequencies in one or more categories match expected frequencies. If we have single measurement variable, we use a chi-square goodness of fit test. If we have two measurement variables, we use a chi-square test of independence.
    The basic idea behind the test is to compare the observed values in your data to the expected values that we would see if the null hypothesis is true.
    
  </details>
  
  <details>
  <summary>Non-parameteric methods</summary>
  [Link]() <br />
   ### Wilcoxon signed-rank test
  </details>
  
  ### Z-test
  ### F-test
  ### Welch's t-test
</details>

### Cohen's Kappa
### Fleiss K




