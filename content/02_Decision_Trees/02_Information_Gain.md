Sylesh Suresh

-

We split each node on the feature that yields the most information gain. The formula for information gain in a binary decision tree is as follows:

$IG(D_p,f)=I(D_p)− \frac{N_{left}}{I(D_{left})}− \frac{N_{right}}{I(D_{right})}$

$D_p$ is the dataset of the parent node (the node which we are splitting), $f$ is the feature of the dataset which we are splitting on, $N_p$ is the total number of samples in the parent node, $N_{left}$ and $N_{right}$ are the number of samples in the datasets of the left child node and right child node respectively, and $I$ is the impurity measure. A node is pure if all samples in its dataset belong to the same class and is most impure when an equal number of samples belong to each class. Essentially, information gain calculates the difference between the impurity of the parent node and the impurity of the child nodes.
One commonly used measure of impurity is Gini impurity:

$IG(i) = 1 − \sum_[p(k|i)^2]$

$p(k|i)$ is the proportion of samples of class $k$ to the total number of samples in the dataset of the $i$th node. The impurity is maximized when the classes of the node are perfectly mixed (for this example, consider a situation in which there are 2 classes, meaning $c = 2$):

$1 − \sum_{k=1}^{c}[0.5^2] = 0.5$

An alternative impurity measure is entropy, which is defined as:

$-\sum_{k=1}^{c}[p(k|i)log_2(p(k|i))]$

Note that this function has a maximum of $1.0$, not $0.5$. In practice, Gini impurity and entropy yield similar results, so it is more useful to test different pruning cut-offs rather than to evaluate trees with different impurity criteria.
To decide on a split for a specific node, we will search for the feature and the threshold (e.g. "petal length < 2.45 cm" for a flower classifier) that maximizes the information gain. We can choose the best threshold for a feature from the feature values in the training data or from the averages of every pair of feature values in the training set. Another method is to select the best threshold from the quartiles (20%, 40%, 60%, and 80% values) of the feature set.

Here is the pseudocode for determining the best split:

Algorithm 1. Best Split.

```
IG <- 0
for each feature do
	for each threshold do
		pot left, pot right <- split(parent, feature, threshold)
		pot ig <- information gain(parent, pot left, pot right)
		if pot ig > IG then
			left <- pot left
			right <- pot right
			IG <- pot ig
		end if
	end for
end for
return left, right
```

Algorithm 2. Split.

```
function split(feature, threshold)
	Initialize left and right lists
	for each data point do
		if feature of data point < threshold then
			append data point to left
		else
			append data point to right
		end if
	end for
	return left, right
end function
```

Algorithm 3. Gini Impurity.

```
function information gain(dataset)
	sum <- 0
	for each class label c do
		ratio <- (number of class labels c)/size of dataset
		sum <- sum + ratio * ratio
	end for
	return 1 - sum
end function
```
