---
title: "ML System Design"
date: 2026-10-07
description: "Agents"
tags: ["ML", "System", "Design"]
---

## ML Problems
For what kind of problems ML will be better:
- **Repetition**: If the task if repetitive with same kind of pattern.
- **Wrong predicition is cheap**: The cost of wrong predicitons is cheap.
- **Scale**: Cost of integrating ML solution often comes with non-trivial investment. So if the prediction can be made at scale it is a better investment.
- **Changing pattern, no fixed rule**: If the problem is constantly changing with time, the pattern that models the problem also changes. Hardcoded rules won't be sufficient and human knowledge about it might be limited. Let the machine learn over time.

Latency vs throughput
- **Latency**: How much time does it take to process one query. Metric for latency calculation is p50 or median ore 50% of the request. Higher percentile means outlier and is important to look at to understand the problem.
- **Throughput**: How many queries can be processed in a second.


Four requirements:
- **Reliability**: The system continues to perform the correct function at the desired level of performance even in the face of adversity.
- **Scalability**: Handing more request either by scaling resources or having models. Having models means monitoring and maintaining scales with it.
- **Maintainability**: Same set up, strucutre and proper documentation.
- **Adapatability**: Adapt to new data automatically.

**Multilabel**: When same data point has multiple labels it is called multilabel. The way to work with this is to choose the number of highest probabilites for the number of label the data point ground truth belongs to.

Framing a ML problem matters. If framed a prediction problem as classification. The model needs to be trained for new class. How about it is frame as regression class so that it gives probability and label is chosen based on highest probability.

 Cross-entropy for multiclass classification, RMSE or MAE for regression, logistic loss or log loss for binary classification.

#### When there are multiple objectives, it is good idea to decouple them first because it makes model development and maintenance easier.

## Data Engineering
#### Data Sources
- **User input data** (usually requires fast process)
- **System-generated data** (logs, system outputs, needed for debugging and potentially improving the application), this does not need to be stored long term if not needed
- **Third-party data**: data collected by third party companies on the public who aren't their direct customers.

#### Data Formats
- How to store multiple data types so that it is cheap to store and easy to access? text, image, networks etc.
- How to store complex models so that they can be loaded and run correctly on different hardware?

**Row major vs column-major format**:
- CSV: row major, faster, better for accessing samples, alot of writes
- Parquet: column major, better for accessing features, best for column based read.


#### Data Models
- SQL (declarative language)
- NoSQL (document or relational model)

**Document model**: Each document in the form of JSON, XML or binary format like BSON (Binary JSON) is row and collection of document is the table.
**Graph model**: Relation is more important. Better for filtering.

**Data warehouse**: repository for storing structured data
**Data lake**: repository for storing unstructured data

Databases are optimized for two types of workloads:
- **Transactional processing**: Basically CRUD operation, online transaction processing (OLTP). Requires low latency and high availability. ACID (Atomicity: if any transatcion fails, none happens, Consistency: All transactions coming through must follow predefined rules, Isolation: two transactions can happen at same time as if they were isolated, Durability: once transaction is committed, it will remain commited even in the case of system failure.)

- **Analytical processing**: Database optimized for aggregations across column across multiple rows. They are efficient with queries called online analytical processing (OLAP).

**ETL: Extract, Transform and Load**

**Modes of Dataflow**: Passing data from one process to another.
- Data passing through databases
- Data passing through services using requests such as the requests provided by REST and RPC APIs. RPCs are like calling functions in the program to make a request to remote network service.
- Data passing through a real-time transport like Apache Kafka, amazon kinesis. Two types of real-time tansport: pubsub (publish subscribe) and message queue. In pubsub, any service can publish to different topics in a real-time transport and it does not care who consumes it. Old data are removed. In case of message queue, there is a specific intended consumers example: RocketMQ, RabbitMQ etc.

**Batch processing vs stream processing**
- **Batch processing**: When the historical data is processed in batch jobs. They are processed once a day.
- **Stream processing**: Computation in streaming data periodically, within time shorter than priods of batch jobs.

Batch processing is usually used to compute features that change less often, batch features.

Stream processing is used to compute features that change quickly, information that change with time example: number of drivers nearby. These are dynamic features.

## Training Data

#### Sampling
**Nonprobability Sampling**:
- Convenience sampling: samples of data are selected based on their availability.
- Snowball sampling: future samples are selected based on existing samples
- Judgment sampleing: Experts decide what samples to include
- Quota sampling: Samples are selected based on quotas for certain slices of data without randomization. Example: in survey, 100 people in age 30-40, 20 people below 19 age etc.

**Probability based sampling**:
- **Simple Random Sampling**: Each sample points get equal probability. Easy to implement but may not include rare class samples.
- **Stratified Sampling**: The sample is divided into groups and each groups is separately sampled. This makes sure that rare groups or class are included.
- **Weighted Sampling**: Each sample is given a weight, which determines the probability of it being selected.
- **Reservior Sampling**: This is useful to deal with streaming data in production. We can't fit all data for training so we need to sample in the stream.
- Step 1: select a reservior size to consider or data to consider, example: k = 4
- Step 2: For each incoming nth element, generate a random number, i between 1 <= i  <= n.
- Step 3: If 1 <= i <= k: replace the ith element in the reservior with the nth element else do nothing. Each incoming nth element has probability of k/n.

- **Importance Sampling**: This allows sampling from one distribution when we have only access to another distribution. We need to sample x from P(x) but P(x) is slow, expensive or infeasible to sample from. If we have Q(x) that is easier to sample from. Q(x) if proposal distribution or the importance distribution. 

```
E_p(x) [x] = E_q(x) [x \frac{P(x)}{Q(x)}]
```

#### Labeling
- **Hand Labels**: Data privacy issue, Expensive if require expert labeler, Slow process
- **Label Multiplicity**: Data from different sources can have different labels for same row. **Data lineage** means keeping track of sources, labels and versions of the data so that we can track the source of error later.
- **Natural Labels**
- **Feedback loop length**: Time it takes from when a prediction is served until when the feedback on it is provided. Recommender system have short feedback loops. Shorter time means we can evaluate our models faster and find the issue with it. Long feedback is observed in fraud detection. The model performance can be reported in the quaterly report.
- **Handling the Lack of Labels**: 
    - **Weak supervision**: In this we label the data based on heuristic function that is created by expert. This might not cover all the labels but a model can be trained on weakly supervised model and made to predict on new data.
    - **Semi-supervision**: It starts with few hand labeled data, model is trained to predit these labels. The trained model makes prediction on new data points. These new data points are used as input to make prediciton on new, so it is self supervision.
    - **Transfer learning**: This process uses a general model trained on large amount of generic data to label the data points.
    - **Active learning**: The model is trained on the examples that we are sure of its label or less uncertainty.  

#### Class imbalance
Class imbalance is especially affect the deep learning models for following reasongs.
- Lack of examples means insufficient signal for the model, the label might not exist for model.
- Class imbalance makes it easier for the model to get stuck in a nonoptimal solution by exploiting simple heuristic instead of learning anything useful about the underlying pattern of the data.
- Asymmetric costs of error, the cost of wrong prediction on a sample of the rare class might be much higher than a wrong prediciton on a sample of the majority class.

Handling class imbalance:
- **Choosing right metric**: F1, precision, recall, AUC-ROC, AUC-ROC
- **Data-level methods**: Undersampling, oversampling, dynamic sampling (oversample the low-performing classes and undersample the high performing classes during the training process)
- **Algorithm-level methods**: Cost sensitive loss where each wrong example is weighted, Weighted class-balanced loss (W_i = N/(number of samples of class i)), **Focal Loss** 
$$
FL(p_t) = -(1-p_t)^\gamma log(p_t)
$$

#### Data Augmentation

**Simple Label-Preserving Transformations**: This means the original data is changed but label is preserved. In case of images, the images are rotated, flipped, cropped, iverted etc. In case of text, words are changed with synomys assuming the replacement wouldn't change the meaning or the sentiment of the sentence. Embedding of words can be used to.

**Perturbation**: Adding noisy samples to training data so that model recognize the weak spots in their learned decision boundary and imporve their performance. This is also called 'adversarial augmentation'.

**Data Synthesis**: In NLP, the templates are used to generate training data.

## Feature Engineering

**Learned features vs engineered features**: Deep learning is learned features. Engineered features is where domain knowledge is important.
**Common features engineering operations**:
- Missing data
    - Missing not at random (MNAR): Missing values is missing due to a reason.
    - Missing at random (MAR): Missing value if due to another observed variable
    - Missing completely at random (MCAR): There is no pattern in when the value is missing.

- Deletion: remove the column itself, row deletion, 
- Imputation: Default value, mean, median or mode, bias or noise or data leakage may be injected when imputation
- Scaling: 
$$
x\cap(a) = \frac{x-min(x)}{max(x) - min(x)}
$$ this makes in range of [0, 1].

$$
x' = a + \frac{(x-min(x))(b-a)}{max(x) - min(x)}
$$ this makes in range of [a, b].

$$
x' = \frac{x-mean(x)}{\delta}
$$ this is standardization.


- Discretization: process of turning a continuous features into discrete feature, binning.
- Encoding: Categories can be numerous. So the way to work with it is to use hash function. For example: if hash space is 18 bits which corresponds to $2^18=262,144$ possible hashed values all the categories even unseen will be encoded. There will be collisions.
- Feature crossing: combining two or more features to generate new features to model non-linear relations. 
- Discrete and continuous positional embedding: Fourier series can take any discrete and continuous value.

**Data Leakage**: Some form of labels are leaked to training data. Causes of data leakage:
- Splitting time-correlated data randomly instead of time: 
- Scaling before splitting: The scaling should happen after the split and mean and std should come from train split.
- Filling in missing data with statistics from the test split: The missing values should come from summary statistics from the train split.
- Poor handling of data duplication before splitting: The data duplication should happen after splitting the data into test and train.
- Group leakage: A group of examples have strongly correlated labels but are divided into splits. Like example: a patient with lung cancer has many samples of test results. If divided into test and train, some samples with common features will end up in both train and test.
- Leakage from data generation process: If there are different data from different sources, the good performance could be due to the generation process difference itself.


To detect data leakage, check the predicition of each features as well as combination so that we can find if there is high correlation between feature and labels.

**Engineering good features**:
- Too many features, the more opportunities for data leakage.
- Too many features, chances of overfitting
- Increase in memory requirement.
- Increase inference latency
- Useless features becomes technical debts. As there is change in data pipeline, all affected features needs to be adjusted.

**Feature importance**:
- Built-in feature importance functions implemented by XGBoost.
- SHAP (SHapley Additive exPlanations) is model agnostic  methods.
- InterpretML

**Feature generalization**:
- More coverage the feature has more generalization. Coverage means the percentage of samples that have the features.


## Model development and offline evaluation
**Modeling development and training**:
- Avoid the state-of-the-art-trap
- Start with simplest models
- Avoid human biases in selecting models
- Evaluate good performance now vs good performance later: Look into the learning curve and get a sense if the adding data helps.
- Evaluate trade-offs: false positive vs false negative, GPU vs CPU needed.
- Understand model's assumptions: Prediction assumption, IID, smoothness, Tractability, Boundaries, Conditional independence, Normally distributed

**Ensembles**: Use ensemble of different models to make final predicitons.

**Bagging** (Bootstrap Aggregating): Random Forest

**Boosting**: Iterative ensemble algorithms that convert weak learners to strong ones.

**Stacking**: Results from base models are used to train meta learners to give final predicition.

**Experiment tracking**:
- Loss curve corresponding to the train split and each of the eval splits
- The model performance metrics that you care about on allnontest splits, such as accuracy, F1, perplexity.
- Log of corresponding sample, prediction, ground truth label.
- Speed of the model, evaluated by the number of steps per second
- System performance metrics such as memory usage, CPU/GPU utilization
- The values over time of any parameter and hyperparameter whose changes can affect the model's performance.

**Versioning**:
Data versioning system

Debugging:
- Start simple and gradually add more components
- Overfit a single batch
- Set a random seed


**Distributed Training**:
- Data parallelism: Difficulty is how to update the gradient collected from different machines. The accumulations will have to wait for all the gradient to be available.
- Model parallelism: It is actually not parallel if the different layers are in different machines. If the same weight matrix is split into parts, then it can be parallel.
- Pipeline parallelism: 

**AutoML**
- soft AutoML: parameter, hyperparameter search
- hard AutoML: architecture search and learned optimizer
    - Search space
    - Performance estimation strategy
    - Search strategy

**Model offline evaluation**:
- Random baseline
- Simple heuristic like chronological order
- Zero rule baseline (predicts most common class)
- Human baseline: if the goal beat prediction done by human
- Existing solutions: We are replacing existing method, it is useful.

**Evaluation methods**
- Perturbation tests: To test how model performs in case of noisy data, we can test by making small changes to the test split to see how these changes affect the model's performance
- Invariance tests: Test if removing some features leads to difference in the result. This will help to find biases in the data.
- Directional expectation tests: If we know if any of the feature change leads to similar direction change in output, we can test if this works or not.
- Model calibration: 
- Confidence measurement: Usefulness threshold for each individual prediction.
- Slice-based evaluation: Use metrics in different slices of the data. Simpson's paradox: a phenomenon in which a trend appears in several groups of data but disappears or reverse when the groups combined.
    - Heuristic-based: Domain knowledge (mobile vs web traffic)
    - Error analysis: Manually go through misclassified examples and find patterns among them
    - Slice finder: Generating slice candidates with algorithms such as beam search, clustering, or decision.

## Model deployment and prediciton service
## Data distribution shifts and monitoring
## Continual learning and test in production
## Infrastructure and tooling for MLOps
## The human side of machine learning