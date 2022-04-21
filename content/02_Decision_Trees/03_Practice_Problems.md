Consider the following dataset:

| x1  | x2  | x3  | y   |
| --- | --- | --- | --- |
| 0   | 1   | 0   | -1  |
| 1   | 0   | 0   | +1  |
| 0   | 1   | 1   | +1  |
| 0   | 0   | 1   | -1  |

???
Question:
What feature will we split on at the root of our decision tree?
(x) x1
( ) x2
( ) x3
Explanation:
We decide the feature to split on by using Gini impurity.
As a reminder, Gini impurity is $1 - \sum_{all i}[p_i^2]$.

When splitting along x1, the left split is $y=(-1, +1, -1)$ and the right split is $y=(+1)$.
Let's find the impurity of the left side:

1. Each distinct y value has proportions $1/3$ and $2/3$.
2. The impurity is $1 − (1/3)^2 − (2/3)^2 = 4/9$.

Let's find the impurity of the right side:

1. There is only one distint y value: $+1$.
2. Therefore, the impurity is $0$. You can see this because $p = 1$, and $1 - p^2 = 0$.

Splitting along any other features and repeating the steps above gives a higher Gini impurity.

???

???
Question:
What will our information gain be from splitting on that feature using the Gini impurity measure?
( ) 4/9
( ) 1/3
(x) 1/6
( ) 0

Explanation:
Information gain is measured as the expected decrease in entropy. The entropy is measured as Gini impurity. So, what we do to calculate the entropy of the split is take the weighted sum of the Gini impurities of the two folds. This gives an expected entropy after the split. We find the decrease in entropy by subtracting the expected entropy after the split from the initial entropy.

The Gini impurity of the left features ($x_1 < 0.5$) is $1 - \sum_{all i}[p_i^2] = 4/9$.

The Gini impurity of the right features ($x_1 > 0.5$) is $0$.

The probability of having a feature on the left side is $3/4$, and the probability of having a feature on the right side is $1/4$. Therefore, the expected entropy is $3/4 * 4/9 + 1/4 * 0 = 3/4 * 4/9 = 1/3$.

The initial entropy is $1 - (1/2)^2 - (1/2)^2 = 1/2$, so the expected decrease in entropy is $1/2 - 1/3 = 1/6$.

???

???
Question:
Build a decision tree using the dataset. What is the depth of the tree?
( ) 1
( ) 2
(x) 3
( ) 4
Explanation:
First, the best feature to split on is $x_1$. The left split is $y=(-1, +1, -1)$ and the right split is $y=(+1)$.
We continue splitting the left side. We can split by either $x_2$ or $x_3$; it's symmetric. Let's say we split by $x_2$. We will have the left side be y=(-1), and the right side be (+1, -1). We will need one more split on the right side, leading to a total depth of 3. Let's say instead we split by $x_3$. We will have the left side be y=(-1), and the right side be (+1, -1). We will need one more split on the right side, leading to a total depth of 3.
???

???
Question:
What will the decision tree classify a data point with the features x1 = 0, x2 = 0, and x3 = 0 as (y = -1 or y = +1)?
(x) -1
( ) +1
Explanation:
No matter how we create the decision tree, as long as it is optimal, we will have a classification of -1. We can split in the order $x_1$, $x_2$, $x_3$, or we can split in the order $x_1$, $x_3$, $x_2$. For both $x_2$ and $x_3$, splitting will yield a -1 if either is 0.
???

<!-- | x1  | x2  | y   |
| --- | --- | --- |
| 0   | 0   | +1  |
| 0   | 1   | +1  |
| 1   | 0   | +1  |
| 1   | 1   | -1  |

?//??
Question:
What will the information gain be after the first split in the above data set with the Gini impurity measure?

Explanation:
?//??

?//??
Question:
With entropy as the impurity measure?

Explanation:
?//??

?//??
Question:
What is the depth of the final decision tree?
( ) 0
( ) 1
(x) 2
( ) 3
Explanation:

?//??
-->
