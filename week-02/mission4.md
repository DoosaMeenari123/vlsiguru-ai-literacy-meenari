# MISSION 4 | Understand ML Task Types
# Research Question: What kinds of problems can machine learning solve?
# Answer:
Machine learning can solve different types of problems by learning patterns from data. Depending on the problem, it can predict a category, estimate a numerical value, group similar data, detect unusual behaviour, reduce the number of features, or recommend and rank items.
In real-world applications, machine learning is used in many fields, including healthcare, education, banking, and semiconductor manufacturing. For example, it can identify defective chips, predict power consumption, group similar wafers, and detect unusual conditions in manufacturing equipment.
# Distinguish the Different Machine Learning Task Types
Machine learning can solve different problems depending on the output we expect. The main task types are classification, regression, clustering, anomaly detection, dimensionality reduction, and recommendation/ranking.
| Task type | Meaning | Input data | Expected output |
|---|---|---|---|
| Classification | Predicts a category or class | Features such as images, sensor readings, or measurements | A class label, such as defective or non-defective |
| Regression | Predicts a numerical value | Features related to the value being predicted | A numerical value, such as power consumption |
| Clustering | Groups similar data points without predefined labels | Unlabelled data containing different features | Groups or clusters of similar data |
| Anomaly Detection | Identifies unusual patterns or observations | Sensor readings, test measurements, or normal operating data | An anomaly score or normal/anomalous label |
| Dimensionality Reduction | Reduces the number of features while preserving useful information | Data containing many features or variables | A smaller set of features or components |
| Recommendation/Ranking | Suggests relevant items or arranges them by relevance | User preferences, item details, and historical interactions | Recommended items or a ranked list |

# Identify the Input and Expected Output for Each Task
The following examples show how these machine learning tasks are used in real-world situations, including semiconductor-related applications.
| No. | Real-world problem | Task type | Input data | Expected output |
|---|---|---|---|---|
| 1 | Detecting defective semiconductor chips | Classification | Chip inspection images and electrical test measurements | Defective or non-defective label |
| 2 | Predicting semiconductor chip power consumption | Regression | Operating voltage, frequency, and workload | Predicted power consumption in watts |
| 3 | Grouping similar semiconductor wafers | Clustering | Wafer test measurements and manufacturing features | Groups of wafers with similar characteristics |
| 4 | Detecting unusual conditions in semiconductor equipment | Anomaly Detection | Temperature, pressure, vibration, and sensor readings | Anomaly score or normal/anomalous label |
| 5 | Analysing semiconductor test data with many features | Dimensionality Reduction | Electrical test measurements and manufacturing process features | A smaller set of features or components |
| 6 | Recommending courses to students | Recommendation | Student interests, course details, and learning history | A list of recommended courses |
| 7 | Predicting house prices | Regression | House size, location, number of rooms, and age | Estimated house price |
| 8 | Filtering spam emails | Classification | Email text, sender information, and message features | Spam or not-spam label |

These examples show that each task has a different purpose and expected output. For example, classification predicts a category, while regression predicts a numerical value.
# Why Task Type Is Different from Learning Paradigm
A task type tells us what the model needs to do, while a learning paradigm tells us how the model learns from data or feedback.
| Task type | Learning paradigm |
|---|---|
| Describes the problem the model needs to solve | Describes how the model learns |
| Focuses on the expected output | Focuses on the learning process and available feedback |
| Examples include classification, regression, clustering, and anomaly detection | Examples include supervised, unsupervised, reinforcement, and self-supervised learning |
| Predicting whether a chip is defective is a classification task | Learning from labelled chip examples is supervised learning |
| Grouping similar wafers is a clustering task | Discovering groups without predefined labels is unsupervised learning |

For example, predicting whether a semiconductor chip is defective is a classification task. If the model learns from labelled examples of defective and non-defective chips, it uses supervised learning.
Similarly, grouping semiconductor wafers according to their measurements is a clustering task. If the model discovers groups without predefined labels, it uses unsupervised learning.
Therefore, the task type does not tell us how the model was trained. The same task may be approached using different learning paradigms, depending on the available data and training method
# Recognise That Multiple Algorithms Can Solve a Similar Task
Different algorithms can be used to solve the same machine learning task. The choice depends on the dataset, accuracy requirements, computational cost, and nature of the problem.
| Task type | Possible algorithms |
|---|---|
| Classification | Logistic Regression, Decision Tree, Random Forest, Support Vector Machine |
| Regression | Linear Regression, Decision Tree Regressor, Random Forest Regressor |
| Clustering | K-Means, DBSCAN, Hierarchical Clustering |
| Anomaly Detection | Isolation Forest, One-Class SVM, Local Outlier Factor |
| Dimensionality Reduction | PCA, t-SNE, Autoencoders |
| Recommendation/Ranking | Collaborative Filtering, Matrix Factorization, Learning-to-Rank models |

For example, semiconductor defect detection can be performed using a Decision Tree, Random Forest, or neural network. All can be used for classification, but they learn patterns in different ways.
Similarly, Linear Regression and Random Forest Regressor can both predict semiconductor chip power consumption. The most suitable algorithm depends on the data and the requirements of the application.

# Sources 
1. **Google – Machine Learning Crash Course**  
   https://developers.google.com/machine-learning/crash-course/
2. **Scikit-learn – Getting Started: Fitting and Predicting**  
   https://scikit-learn.org/stable/getting_started.html
3. **Google – Machine Learning Resources**  
   https://developers.google.com/machine-learning
