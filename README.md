# General Introduction to Machine Learning

## General Introduction to Machine Learning

Machine learning \(ML\) is the scientific study of algorithms and statistical models that computer systems use to effectively perform a specific task without using explicit instructions, relying on patterns and inference instead. Machine learning algorithms build a mathematical model of sample data, known as "training data", in order to make predictions or decisions without being explicitly programmed to perform the task. Machine learning algorithms are used in a wide variety of applications, such as email filtering, detection of network intruders, and computer vision, where it is infeasible to develop an algorithm of specific instructions for performing the task. Machine learning is closely related to computational statistics, which focuses on making predictions using computers. The study of mathematical optimization delivers methods, theory and application domains to the field of machine learning. Data mining is a field of study within machine learning, and focuses on exploratory analysis through unsupervised learning. In its application across business problems, machine learning is also referred to as predictive analytics.

::: video

 :::

## Types of ML tasks

### Unsupervised learning:

In unsupervised learning, the algorithm builds a mathematical model from a set of data which contains only inputs and no desired output labels. Unsupervised learning algorithms are used to find structure in the data, like grouping or clustering of data points. Unsupervised learning can discover patterns in the data, and can group the inputs into categories, as in feature learning. Dimensionality reduction is the process of reducing the number of "features", or inputs, in a set of data.

### Supervised learning

In supervised learning, the algorithm builds a mathematical model from a set of data that contains both the inputs \(predictors\) and the desired outputs \(target variables\). For example, if the task was determining whether an image contained a certain object, the training data for a supervised learning algorithm would include images with and without that object \(the input\), and each image would have a label \(the output\) designating whether it contained the object. In special cases, the input may be only partially available, or restricted to special feedback. We can split this category into two sub-categories:

### Classification:

Classification algorithms are used when the outputs are restricted to a limited set of values. For a classification algorithm that filters emails, the input would be an incoming email, and the output would be the name of the folder in which to file the email. For an algorithm that identifies spam emails, the output would be the prediction of either "spam" or "not spam", represented by the Boolean values true and false. Regression: Regression algorithms are named for their continuous outputs, meaning they may have any value within a range. Examples of a continuous value are the temperature, length, or price of an object.

### Reinforcement learning

An area of ML concerned with how software agents ought to take actions in an environment so as to maximize some notion of cumulative reward. It differs from supervised learning in that correct input/output pairs need not be presented, and sub-optimal actions need not be explicitly corrected. A typical example of these types of problems is teaching agent how to play games like chess or tetris, where it is difficult to say which action influenced the outcome of the game in what manner \(therefore the "correct" output labels are missing\). Other important types of problems Time series: Subset of regression problems where the ordering of data matters as each of the data samples is connected to the specific date and time. Most commonly, a time series is a sequence taken at successive equally spaced points in time. Thus it is a sequence of discrete-time data. Examples of time series are heights of ocean tides, closing price of electricity price or counts of sunspots. Time series usually require different algorithmic approach as it is necessary to exploit inner correlation of successive data points - which is not the case in other regression problems where we can reorder data arbitrarily without loosing information. Anomaly detection: Anomaly detection \(also outlier detection\) is the identification of rare items, events or observations which raise suspicions by differing significantly from the majority of the data. Typically the anomalous items will translate to some kind of problem such as bank fraud, a structural defect, medical problems or errors in a text. Anomalies are also referred to as outliers, novelties, noise, deviations and exceptions. Three broad categories of anomaly detection techniques exist: Unsupervised anomaly detection techniques detect anomalies in an unlabeled test data set under the assumption that the majority of the instances in the data set are normal by looking for instances that seem to fit least to the remainder of the data set. Supervised anomaly detection techniques require a data set that has been labeled as "normal" and "abnormal" and involves training a classifier \(the key difference to many other classification problems is the inherent unbalanced nature of outlier detection\). Semi-supervised anomaly detection techniques construct a model representing normal behavior from a given normal training data set, and then test the likelihood of a test instance to be generated by the learnt model.

