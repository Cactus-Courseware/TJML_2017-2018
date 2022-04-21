# Introduction

Decision trees are powerful and interpretable classifiers that mirror human decisions unlike many other classifiers in supervised machine learning and are the building blocks of random forests.

# Definition

In essence, decision trees asks a series of true/false questions to narrow down what class a particular sample is. Here is an example of a decision tree one might use in real life to decide upon an activity on a given day:

Although this figure asks categorical variable-based questions, we can ask numerical-based questions like "$x_1 < 5$?" when the features are continuous. To build our tree, we start at the root node and ask a question that splits the data based on the feature such that the information gain is maximized. We continuously do this for each node until the decision tree can classify all the training data. Note that in practice this leads to overfitting, so the tree is usually pruned, i.e. a limit on the depth of the tree is set.
