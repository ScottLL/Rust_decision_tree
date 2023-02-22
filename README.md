# Rust linfa decision tree
A good starting point for a new Rust project

## References

* [Struct linfa_trees::DecisionTree](https://docs.rs/linfa-trees/latest/linfa_trees/struct.DecisionTree.html)

**Structure**
A decision tree structure is a binary tree where:

Each internal node specifies a decision, represented by a choice of a feature and a “split value” such that all observations for which feature <= split_value is true fall in the left subtree, while the others fall in the right subtree.

leaf nodes make predictions, and their prediction is the most popular label in the node

**Algorithm**
Starting with a single root node, decision trees are trained recursively by applying the following rule to every node considered:

Find the best split value for each feature of the observations belonging in the node;
Select the feature (and its best split value) that maximizes the quality of the split;
If the score of the split is sufficiently larger than the score of the unsplit node, then two child nodes are generated, the left one containing all observations with feature <= split value and the right one containing the rest.
If no suitable split is found, the node is marked as leaf and its prediction is set to be the most common label in the node;
The quality score used can be specified in the parameters.

**Predictions**
To predict the label of a sample, the tree is traversed from the root to a leaf, choosing between left and right children according to the values of the features of the sample. The final prediction for the sample is the prediction of the reached leaf.

**Data**
For this trial, we are using NumPy's ndarray to create an array that contains data related to happiness. The array has five columns, which include information about whether the participant watched TV that day (1 for yes, 0 for no), whether they have a pet cat (1 for yes, 0 for no), how many lines of Rust code they wrote that day (a quantitative variable), whether they ate pizza that day (1 for yes, 0 for no), and their happiness level, which is rated on a scale of 1-10, with higher values indicating greater happiness.

* Features:
The first three features - "watch TV", "Pet Cat", and "Ate Pizza" - are binary variables with values of 1 indicating that the participant engaged in that activity on that day, and 0 indicating that they did not. The "Rust LOC" feature is a quantitative variable that indicates how many lines of Rust code the participant wrote that day. 
* label:
The "happiness level" label is also a quantitative variable that ranges from 1-10, with higher values indicating greater happiness.

**Get Started**

* import packages

> cargo add linfa
> cargo add linfa_trees 
> cargo add ndarray 

* output
> dt.tex file

tex file require tex reader. we can use mactex to read it 
> brew install mactex

mactex is only for mac version. 
other solutions could be using online tex-pdf convert generator: https://cloudconvert.com/tex-to-pdf

result show below 

![decision_tree](/workspaces/Rust_decision_tree/linfa_test/dt.pdf)