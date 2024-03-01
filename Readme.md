CREDIT CARD FRAUD DETECTION SYSTEM
Context
It is important that credit card companies are able to recognize fraudulent credit card transactions so that customers are not charged for items that they did not purchase.

Content
The datasets contains transactions made by credit cards in September 2013 by european cardholders. This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

It contains only numerical input variables which are the result of a PCA transformation. Unfortunately, due to confidentiality issues, we cannot provide the original features and more background information about the data. Features V1, V2, ... V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount, this feature can be used for example-dependant cost-senstive learning. Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise.
Inspiration
Identify fraudulent credit card transactions.

Given the class imbalance ratio, we recommend measuring the accuracy using the Area Under the Precision-Recall Curve (AUPRC). Confusion matrix accuracy is not meaningful for unbalanced classification.

Acknowledgements
The dataset has been collected and analysed during a research collaboration of Worldline and the Machine Learning Group (http://mlg.ulb.ac.be) of ULB (Université Libre de Bruxelles) on big data mining and fraud detection. More details on current and past projects on related topics are available on https://www.researchgate.net/project/Fraud-detection-5 and the page of the DefeatFraud project
After reading the dataset information regarding dataset and its attributes were analysed and conclusions were made on the basis of the kind of attributes we got after that we vizualized our dataset for better  understanding
Bar chart was created to check fraud vs normal distribution in which we concluded that normal class and fraud classes are highly imbalanced so we need to balance theses classes which will do lateron 
two histograms were created  to check the transaction amount per transaction (fraud vs normal) in which we conculded the transactions for fraud compared to normal are very less we can use this finding to further enchance our model training and selection
Two scatter plots were created between Time of Transaction vs Amount by class in for both normal and fraaud class and our conclusions were same this time like the previous one were fraud class is still lagging way behind than normal case so this information became crucial for the dataset that the data is highly imbalanced so we need to select the best learning algorithm accordingly 
After that we checked and removed null values if any existed 
Then we imported seaborn library to create correlation heatmap so that we can identify important and unimportant features and then perform feature selection accordingly on our dataset
Now to perform feature selection based on correlation heatmap so that we can eliminate all the unimportant feature and select 30 best features who has high co-relation to our target column and eliminate the rest 
After performing the feature selection we can move towards model selection and model trainig the algorithm that we used for predictions which can also handle class imbalance with ease are 
Isolation Forest Algorithm :
One of the newest techniques to detect anomalies is called Isolation Forests. The algorithm is based on the fact that anomalies are data points that are few and different. As a result of these properties, anomalies are susceptible to a mechanism called isolation.

This method is highly useful and is fundamentally different from all existing methods. It introduces the use of isolation as a more effective and efficient means to detect anomalies than the commonly used basic distance and density measures. Moreover, this method is an algorithm with a low linear time complexity and a small memory requirement. It builds a good performing model with a small number of trees using small sub-samples of fixed size, regardless of the size of a data set.

Typical machine learning methods tend to work better when the patterns they try to learn are balanced, meaning the same amount of good and bad behaviors are present in the dataset.

How Isolation Forests Work The Isolation Forest algorithm isolates observations by randomly selecting a feature and then randomly selecting a split value between the maximum and minimum values of the selected feature. The logic argument goes: isolating anomaly observations is easier because only a few conditions are needed to separate those cases from the normal observations. On the other hand, isolating normal observations require more conditions. Therefore, an anomaly score can be calculated as the number of conditions required to separate a given observation.

The way that the algorithm constructs the separation is by first creating isolation trees, or random decision trees. Then, the score is calculated as the path length to isolate the observation.

Local Outlier Factor(LOF) Algorithm
The LOF algorithm is an unsupervised outlier detection method which computes the local density deviation of a given data point with respect to its neighbors. It considers as outlier samples that have a substantially lower density than their neighbors.

The number of neighbors considered, (parameter n_neighbors) is typically chosen 1) greater than the minimum number of objects a cluster has to contain, so that other objects can be local outliers relative to this cluster, and 2) smaller than the maximum number of close by objects that can potentially be local outliers. In practice, such informations are generally not available, and taking n_neighbors=20 appears to work well in general.
Hyperparameter tunning will also be performed on all these models to get the best of models which can generate the best of the result in the end during model evaluation
The model evaluation metrics that we have used is accuracy score and classification report which gives us a clear understanding of all the models and how they are performing on the data and also help us to compare these models for better understanding and how one is better than the other one
Now the evaluation metrics that we are going to use to compare all these models will be accuracy score and classification report 
Accuray score-It represents the proportion of correct predictions made by the model out of all the predictions made.

The accuracy score is calculated by dividing the number of correct predictions by the total number of predictions made and is often expressed as a percentage.

Mathematically, the accuracy score 
Accuracy
Accuracy can be defined as:

Accuracy
=
(Number of Correct Predictions/Total Number of Predictions)
×
100
%
Accuracy= 
(Total Number of Predictions/
Number of Correct Predictions)
​
 ×100%
 Classification report-The classification report is another valuable tool for evaluating the performance of a classification model. It provides a more detailed analysis than accuracy alone, offering insights into a model's precision, recall, F1 score, and support for each class. Here's how the classification report helps in comparing models:

Comprehensive Evaluation: Unlike accuracy, which provides a single overall measure of performance, the classification report breaks down the performance metrics for each class individually. This allows for a more comprehensive evaluation, especially in scenarios where classes are imbalanced or where the cost of misclassification varies across classes.

Precision and Recall Analysis: The classification report includes precision and recall scores for each class. Precision measures the proportion of true positive predictions out of all positive predictions, while recall measures the proportion of true positive predictions out of all actual positives. Comparing precision and recall scores across different models provides insights into their ability to correctly classify instances of each class and avoid false positives and false negatives.

F1 Score: The F1 score, which is the harmonic mean of precision and recall, is also included in the classification report. It provides a balanced measure of a model's performance, taking into account both precision and recall. By comparing F1 scores across models, one can determine which model strikes the best balance between precision and recall for each class.

Support: The classification report includes the support for each class, which represents the number of instances of that class in the dataset. Understanding the support for each class helps in interpreting the precision, recall, and F1 score metrics and assessing their reliability.

Visual Comparison: The classification report is often presented in a tabular format, making it easy to visually compare the performance metrics of different models side by side. This facilitates quick identification of strengths and weaknesses across models and aids in decision making regarding model selection and improvement.

Overall, the classification report complements accuracy by providing a more detailed and nuanced analysis of a classification model's performance. By comparing precision, recall, F1 score, and support for each class across different models, stakeholders can make informed decisions about which model best suits their specific needs and requirements.
So overall we conculded that its a fairly good model as it has good classification report as well as agreat accuracy score we can further check other metrics also to keep enchancing the model in future 
 
