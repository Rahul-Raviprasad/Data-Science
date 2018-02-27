# Data-Science
Repo for collecting and storing Data science related articles and information

## Data science introduction

#### What is data science?
* process and resource optimization
* computational methods
* extracting information from massive amounts of data
* extends and complementing to various data analysis fields like statistics, predictive analysis and data mining.
* extract useful insights used for different needs in business, research etc.

#### What is Big Data?
* Large Volume: Massive Datasets
* Fast Velocity: data moves too fast
* doesn't fit or difficult for traditional RDBMS system to handle

#### Asking the right Questions
In big data analysis, it is very important to ask the right questions
* Is our solution solving a problem? which party does it help?
* what are the benefits?
* how is it being solved?
* where do the data inputs originate from?
* where are the outputs and where do they reside?
* how does it affect the bottom line?

#### Kinds of Data
* Structured data
  1. data stored
  2. data processed
  3. data handled traditionally like RDBMS
* Unstructured data
  1. Doesn't fit structured DB
* Semi Structured data
  1. Doesn't fit structured DB
  2. Structured with tags, useful for creating a form of order and hierarchy in semi structured data.

#### Data Science industry
* Statistician
 Individuals who models and summarizes datasets
* Domain experts
 Subject matter experts
* Computer scientists
Design using algorithms and data structures to use and visualize the data


## Stages
#### Stage 1 Planning/ Preparation
* Obtain data
  - Acquire this data necessary to analyze
  - Various sources can be used
    * Data Streamed on demand
    * Data files from repositories or libraries
    * Data can be generated automatically by physical devices
    * Data generated by the software
* Format and Clean data
  - Can be done by creating scripts
  - Manually by editing data

#### Stage 2 Analysis
* Create and manage scripts for analysis
#### Stage 3 Reflection



## Notes from how to become a Data Scientist in 2017

About the Host :
Jesse Steinweg-Woods is soon-to-be a Senior Data Scientist at tronc, working on recommender systems for articles and understanding customer behavior. Previously, he worked at Argo Group Insurance on new pricing models that took advantage of machine learning techniques. He received his PhD in Atmospheric Science from Texas A&M University, and his research focused on numerical weather and climate prediction.

why ?
best jobs in 2016 & 2017

do you need a PH.D.?

Burtch works 2016 Study, Data Scientist education levels
44% have masters, 48% have Ph.D.s and only 8% Bachelor's

#### Most used tools
Learn python and R

#### Python data stack
NumPy, SciPy, matplotlib, IP[y] I python interactive computing, scikit learn, pandas
Learn these libraries well!

#### Learn SQL
SQL Zoo: http://sqlzoo.net/

#### Machine Learning
1. Andrew Ng's Coursera course
2. Elements of Statistical Learning
3. Scikit-Learn documentation
#### Bayesian statistics
1. Bayesian methods for hackers:
https://github.com/CamDavidsonPilon/Probabilistic-Programming-and-Bayesian-Methods-for-Hackers
2. Statistics for Hackers
https://speakerdeck.com/jakevdp/statistics-for-hackers

#### Probability distributions
know your common distributions and understand them
http://blog.cloudera.com/blog/2015/12/common-probability-distributions-the-data-scientists-crib-sheet/

### Pet Projects
The best way to get better at data science is to DO data science.

"DO a project you care about. Make it good and share it." - Monica Rogati, Data Science advisor.

https://www.quora.com/How-can-I-become-a-data-scientist-1

link to host's website: jessesw.com

### About kaggle
Great for practicing machine learning, not all of Data science
Kaggle misses :
 - Asking the right questions
 - Desicions regarding data sources
 - Which metrics to optimize
 - Data Munging/ Wrangling work

Pet projects can cover all of these.

### Job Skills

Basic tools
Software Engineering
Statistics
Machine Learning
Multivariable Calculus and Linear Algebra
Data Munging
Data visualization and communication
Thinking Like a data scientist

### Interview tips
- Take home machine learning task
- "Whiteboard" coding (focus on Data structure and algorithms)
- "Whiteboard" SQL
- Bayes' Theorem probability questions
- Machine Learning evaluation metrics

tips for take home machine learning
Practice with tree based methods (random forests/gradient boosted trees)

for Whiteboard coding
1. cracking the coding interview
2. interview cake interviewcake.com
3. hackerrank
4. projecteuler.net

for Whiteboard SQL
SQLZoo

Bayes Theorem
memorize the formula and understand each term
P(A|B) = (P(B|A)P(A))/P(B)

Sample problems at glassdoor:
https://www.glassdoor.co.in/Interview/data-scientist-interview-questions-SRCH_KO0,14.htm

### ML Evaluation metric
Understand how to evaluate a model's performance
- ROC curves
- cross validation
- metrics for classification

### Stuff you don't need yet (Learn later once basics are done)
- Deep Learning (with exception of images/ sound)
- Spark/Hadoop (most companies don't have the necessary scale)
- Recommender systems (most companies don't need them)
- Advanced Natural Language Processing (know the basics)


### Spark ML library
* Basic Statistics
  * summary statistics
  * hypothesis testing
  * random number generation
* Classification and regression
  * linear models(SVMs, log, & linear regression)
  * decision trees
  * ensembles of trees(Random Forests and GBTs)
* Collaborative filtering
  * alternating least squares(ALS)
* Clustering
  * k-means clustering
  * latent Dirichlet allocation(LDA)
* Dimensionality reduction
  * singularity value decomposition(SVD)
  * principal component analysis(PCA)
* Feature Extractors & Transformers
  * word2vec

### K-Means
#### Why?
* simple and fast algorithm to find clusters
* Common technique for anomaly detection
* Drawbacks
  * doesn't work well with non-circular cluster shape
  * Number of cluster and initial seed value need to be specified beforehand
  * Strong sensitivity to outliers and noise
  * Low capability to pass the local optimum

### Decision trees and random forests(Supervised Learning)
Why?
* Simple to understand and interpret(and explain to executives)
* requires little data Preparation.(other techniques often require data normalization, dummy variables need to be created and blank values to be removed.)
* Performs well with large datasets

### Random Forest(Ensemble Model)
* Main idea: build an ensemble of simple decision trees
* Each tree is simple and less likely o overfit
* Classify/predict by voting between all trees

### ML in Spark
Spark Ecosystem

| Spark SQL      | Spark Streaming| MLLib | GraphX |
| :------------- | :------------- |
| Spark Core     |

### MLlib & ML
* MLLib
  * Original "lower" API
  * Built on top of RDDs
  * Maintenance mode starting with spark 2.0
* ML
  * Newer "higher level" API for constructing workflows
  * Built on top of DataFrames

Both of these take advantage of parallelism

### Spark ML Pipeline
* Pipeline includes both fit() and transform() methods
  * fit() is for training
  * transform() is for prediction

```
model = pipe.fit(trainData) # Train model
results = model.transform(testData) # Test model
```
### example for random forest in MLlib
```

indexer = StringIndexer(inputCol="district", outputCol="dis-inx")
parser = Tokenizer(inputCol="text-field", outputCol="words")
hashingTF = HashingTF(numfeatures=50, inputCol="words", outputCol="hash-inx")
vecAssembler = VectorAssembler(inputCols=["dis-inx", "hash-inx"],  outputCol="features")

rf = RandomForestClassifier(numTrees=100, labelCol= "label", seed=42)
pipe = Pipeline(stages=[indexer, parser, hashingTF, vecAssembler, rf])

model = pipe.fit(trainData) # Train model
results = model.transform(testData) # Test model
```

### Apache Zeppelin - A modern web based data science studio
* Data exploratory and discovery
* Visualization
* Deeply integrated with Spark and Hadoop
* Pluggable interpreters
* Multiple languages in one notebook: R, Python, Scala

### Exporting ML Models - PMML
* Predictive Model Markup Language
* Supported models
  * k-means
  * Linear regression
  * ridge regression
  * Lasso
  * SVM
  * Binary

### MLLeap
another way to export models

## Resources
1. Burtch works 2016 Study, Data Scientist: http://www.burtchworks.com/files/2016/04/Burtch-Works-Study_DS-2016-final.pdf
2. A visual introduction to machine learning
http://www.r2d3.us/visual-intro-to-machine-learning-part-1/
3. https://www.datasciencecentral.com/profiles/blogs/understanding-the-changing-position-roles-in-data-science
