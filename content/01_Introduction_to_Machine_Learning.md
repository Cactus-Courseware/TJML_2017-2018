Sylesh Suresh September 2017

# Introduction

Machine Learning is a subfield of computer science focusing on programming computers to learn from data without being explicitly programmed. Machine learning algorithms learn and recognize patterns in seen data (training data) and use these patterns to predict characteristics of unseen data.

# Types of Machine Learning

Machine learning algorithms generally fall into one of the three categories: Supervised Learning, Unsupervised Learning, and Reinforcement Learning.

## Supervised Learning

Supervised learning algorithms analyze known training data with labels, the characteristics of the data that we want to predict, to predict the labels of unseen data. For example, an e-mail spam filtering algorithm would analyze previously seen e-mails that are already labeled as being spam or non-spam to predict whether new, unseen e-mails are spam or non-spam. A supervised learning problem where the class labels are discrete (i.e. are made up of sepa- rate categories), such as the spam filter example, is called a classification task. Regression is another type of supervised task where the predicted value is continuous (e.g. predicting a student’s SAT score based on their GPA).

## Unsupervised Learning

Unsupervised learning algorithms analyze unlabeled training data. One com- mon unsupervised learning task is clustering, which creates different groups for data and categorizes similar data into each group. An example might be categorizing similar visitors of your website into different groups.

## Reinforcement Learning

Reinforcement learning is a different subset of Machine Learning where the learning system (agent) can perform different actions and receives rewards or
penalties in return and must learn the correct policy, which dictates which action the agent should take in a given situation, to get the most rewards over time.

##

Vocabulary
Here we have listed a few important words that we will use throughout the year.

- Classification - Taking each instance and assigning it to a particular category. Ex: If you are looking at MRI scans of tumors, classification would be determining if each tumor is "benign" or "malignant."
- Regression - Instead of having discrete classes, like classification, the "class" to be predicted is made up of continuous numerical values.
- Clustering - For data without pre-labeled classes, clustering is the act of grouping similar data points together. A form of unsupervised learning.
- Training Data - The initial set of data used to discover potentially pre- dictive relationships. It’s what your machine learning algorithm "trains" on and learns patterns from
- Testing Data - Set of data used to assess the strength and utility of predictive relationship.
- Error - The difference between algorithm’s prediction and ground-truth values.
- Ground Truth - Data that is known to be correct. A data-set’s labels.
- Features - The attributes of the data that are used to make a prediction
  about the labels.
- Feature space - The n-dimensions in which the features live where n = the number of features.
