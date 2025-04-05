## Generative Models
Models that can understand and replicate the underlying distribution of data. They mainly aim to model the distribution P(X) when focusing solely on the input data or the joint probability distribution P(X,Y) when considering both the input data and the target variable. This allows them to generate new data instances by sampling from these learned distribution.

Key applications:
1) Augmentation: Creating additional training instances to improve model robustness.
2) Imbalance Correction: Generating synthetic instances to balance class distributions.
3) Testing and validation: Creating diverse datasets for evaluating model performance.
4) Privacy preservation: Generating synthetic data for sharing without revealing sensitive information.

#### Types of generative algorithms
1) Classical
   - Classical algorithms are good at learning patterns from structured data. They struggle to learn from more complex or unstructured data. Some classical generative algorithms include <br />
a) Gaussian Naive Byes: <br />
      - It is a variation of Naive Bayes algorithm and is specifically tailored for datasets with continuous and numerical features. It assumes that the features follow a Gaussian (normal) distribution and is based on same fundamental principles of Bayes' theorem. 


b) Gaussian Mixture Models (GMMs): <br />
c) Hidden Markov Models (HMMs): <br />
d) Boltzmann Machines: <br />

3) Modern
- Modern generative algorithms learn from complex data distributionss and are wells suited for tasks such as generating realistic images and producing accurate textual outputs in response to queries. Common generative models are: <br />
a) Variational Autoencoders( VAEs): <br />
b) Generative adversial networks (GANs): <br />
c) Diffusion models: <br />
d) Auto Regressive models:  <br />


## References
[1] https://medium.com/@gridflowai/exploring-generative-ai-from-concepts-to-practical-examples-using-gaussian-naive-bayes-4fe53f31d406
[2] 
