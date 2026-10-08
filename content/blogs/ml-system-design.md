---
title: "ML System Design"
date: 2026-10-07
description: "Agents"
tags: ["ML", "System", "Design"]
---

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
- Data passing through a real-time transport like Apache Kafka, amazon kinesis


