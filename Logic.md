# My Approach & Logic:

This code implements a decision tree algorithm for classification. Let's go through it step by step:
1.	The entropy function calculates the entropy of a given column in the dataset. Entropy measures the impurity or disorder in the column's values.
2.	The information_gain function calculates the information gain when splitting the data based on a specific feature. It uses the entropy function to compute the entropy of the target variable before and after the split and returns the information gain.
3.	The divide_data function splits the dataset into two parts based on a given feature and threshold value. It uses boolean masking to create two subsets of the data: one where the feature values are greater than the threshold and the other where they are less than or equal to the threshold.
4.	The find_count function counts the occurrences of each class in the target variable of the given dataset and returns a list of counts.
5.	The DecisionTree class represents a node in the decision tree. It has attributes such as left and right for storing references to child nodes, key and val for storing the feature and threshold value used to split the data, count for storing the class counts, max_depth for specifying the maximum depth of the tree, depth for keeping track of the current depth, and target for storing the predicted class at a leaf node.
6.	The train method of the DecisionTree class builds the decision tree recursively. It takes the training dataset (X_train) and a list of class names (names) as input.
7.	In the train method, the information gains for each feature are computed using the information_gain function. The feature with the highest information gain is selected as the splitting criterion (key), and the mean value of that feature is used as the threshold (val).
8.	The method prints information about the current node, such as the level, class counts, current entropy, and splitting decision if applicable.
9.	The data is split into left and right subsets using the divide_data function.
10.	If there is only one class present in the current node, it becomes a leaf node, and the most frequent class is assigned as the target class.
11.	If the maximum depth is reached, the node becomes a leaf node, and the most frequent class is assigned as the target class.
12.	If neither of the above conditions is met, the train method is called recursively for the left and right subsets, creating child nodes.
13.	Finally, the target class is assigned based on the majority class in the current node.
14.	An instance of the DecisionTree class (dt) is created, and the train method is called on the training data (data_) with the class names (names).


In summary, this code recursively builds a decision tree by finding the best feature to split the data, creating child nodes, and assigning the target class at each node based on majority voting.


