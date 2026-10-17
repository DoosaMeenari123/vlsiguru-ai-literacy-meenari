# MISSION 6 | Understand Evaluation and Generalisation
# Research Question: How do we know whether a model has learned something useful?
A machine learning model has learned something useful when it can identify meaningful patterns in training data and use those patterns to make good predictions on new, unseen data. We cannot judge a model only by how well it performs on the examples it has already seen.
To evaluate a model properly, we use separate datasets, check suitable performance metrics, look at the mistakes it makes, and compare its performance with a simple baseline. These steps help us understand whether the model can solve the actual problem rather than simply
memorising examples.
# Different Roles of Training, Validation and Test Datasets
A dataset is usually divided into three parts so that the model can be trained, improved and evaluated fairly.
| Dataset | Main Purpose | Example |
|---|---|---|
| Training Dataset | Teaches the model to learn patterns from data. | Chip measurements labelled as defective or good. |
| Validation Dataset | Helps compare models and tune their settings during development. | Checking which model settings detect defects more effectively. |
| Test Dataset | Evaluates the final selected model on unseen data. | Testing the selected model on a separate set of chip measurements. |

The test dataset should be kept separate during training and model selection. If we repeatedly use test results to make decisions, the evaluation may become less reliable.
# Define  Generalisation, Overfitting and Underfitting
Generalisation: The ability of a model to make useful predictions on new data that it did not see during training.
Overfitting: Happens when a model learns the training data too closely, including noise or unimportant details. It performs very well on training data but poorly on unseen data.
Underfitting: Happens when a model fails to learn the important patterns in the data. It performs poorly on both training data and unseen data.
| Concept | Training Performance | Unseen Data Performance | Explanation |
|---|---|---|---|
| Good Generalisation | Good | Good | The model has learned useful patterns. |
| Overfitting | Very good | Poor | The model has learned training-specific details instead of general patterns. |
| Underfitting | Poor | Poor | The model has not learned enough to make reliable predictions. |

# Why Training Performance May Differ from Performance on Unseen Data
A model learns directly from its training data, so it may become very good at predicting those examples without learning patterns that work equally well on new data.
The main reasons include:
-Overfitting: The model learns noise or specific details in the training examples.
-Insufficient data: The training examples may not represent all possible situations.
-Different data: New examples may have different characteristics from the training data.
-Data quality problems: Incorrect labels, missing values or measurement errors can affect the model.
-Different difficulty levels: The unseen examples may be more difficult than the training examples.
For example, a semiconductor defect detection model might perform well on the chips used for training but miss defects in newly manufactured chips if the new defects look different from the training examples.
This is why evaluating a model on unseen data is important for checking whether it has learned patterns that are useful in practice.
# Important Evaluation Metrics
| Metric | Question It Answers | Meaning |
|---|---|---|
| Accuracy | How many predictions were correct overall? | The proportion of all predictions that were correct. |
| Precision | When the model predicts a positive case, how often is it correct? | Measures the reliability of positive predictions. |
| Recall | Of all actual positive cases, how many did the model identify? | Measures how many positive cases were successfully found. |
| False Positive (FP) | How many negative cases were incorrectly predicted as positive? | A good chip is incorrectly flagged as defective. |
| False Negative (FN) | How many positive cases were incorrectly predicted as negative? | A defective chip is incorrectly classified as good. |
| Absolute Error | How far is a numerical prediction from the actual value? | The absolute difference between the predicted and actual values. |

In semiconductor defect detection, the positive class can represent defective chips.
True Positive (TP): A defective chip is correctly identified.
True Negative (TN): A good chip is correctly identified.
False Positive (FP): A good chip is incorrectly flagged as defective.
False Negative (FN): A defective chip is incorrectly classified as good.
Accuracy measures overall correctness, while precision and recall help us understand performance on positive cases. Absolute error is used for numerical prediction tasks, such as estimating chip power consumption.

#  Why Metrics Must Match the Problem and Why a Baseline Is Useful
The choice of evaluation metric depends on the problem and the consequences of making mistakes.
For example, in semiconductor defect detection, missing a defective chip may be more costly than incorrectly flagging a good chip. In this case, recall is important because it measures how many defective chips the model
successfully detects. Precision is also important because it tells us how many chips flagged as defective are actually defective.
For predicting chip power consumption, absolute error may be more useful because it shows how far the predicted power value is from the actual value.
A baseline is a simple model or rule used as a starting point for comparison. For example, a classifier can predict the majority class for every input. A more advanced model should provide a meaningful improvement over this simple approach.
A baseline helps us determine whether the model has actually learned useful patterns. It also prevents us from assuming that a high accuracy score automatically means the model is good.
# Worked Example: How Accuracy Can Be Misleading with Imbalanced Classes
Imagine a semiconductor factory checks 1,000 chips:
980 chips are good.
20 chips are defective.
Since good chips are much more common than defective chips, the dataset is imbalanced.
Now imagine a model that predicts every chip as good. It correctly classifies all 980 good chips but fails to detect all 20 defective chips.
| Actual Class | Predicted Good | Predicted Defective | Total |
|---|---:|---:|---:|
| Good Chips | 980 | 0 | 980 |
| Defective Chips | 20 | 0 | 20 |
| **Total** | **1000** | **0** | **1000** |

#Accuracy Calculation:
The model makes 980 correct predictions out of 1,000 chips.
Accuracy = (Correct Predictions / Total Predictions) × 100
Accuracy = (980 / 1000) × 100 = 98%
The model appears to perform very well because its accuracy is 98%. However, it has failed to detect even one defective chip.
# What Do the Other Metrics Reveal?
| Metric | Why It Matters in Semiconductor Defect Detection |
|---|---|
| Accuracy | Shows the overall proportion of correct predictions. |
| Precision | Helps determine how many chips flagged as defective are actually defective. |
| Recall | Shows how many actual defective chips are detected. |
| False Positives | Help estimate unnecessary inspections of good chips. |
| False Negatives | Help identify defective chips that may incorrectly pass inspection. |
| Baseline Comparison | Shows whether a more advanced model provides meaningful improvement over a simple approach. |

# Which Additional Metric Is Useful and Why?
Recall is especially useful in this example. It tells us what proportion of actual defective chips the model successfully identifies. The model's recall is 0%, revealing that it is useless for finding defects despite having 98% accuracy.
Precision is also useful when a model predicts defective chips, because it measures how many of those predictions are correct. Both metrics help us understand performance beyond overall accuracy.
In a real factory, the choice of metric should also consider the cost of missed defects, unnecessary inspections and other consequences.
# Why Is a Baseline Comparison Useful Here?
The model that predicts every chip as good is a simple majority-class baseline. Its 98% accuracy shows that a high score can be achieved without detecting any defects.
A better defect detection model should be compared with this baseline using recall, precision and false-positive and false-negative counts, rather than accuracy alone. This helps us determine whether the more advanced model provides real value.

# References:
1. Google for Developers. *Datasets: Dividing the Original Dataset*.  
   https://developers.google.com/machine-learning/crash-course/overfitting/dividing-datasets
2. Google for Developers. *Overfitting*.  
   https://developers.google.com/machine-learning/crash-course/overfitting/overfitting
3. Scikit-learn. *Metrics and Scoring: Quantifying the Quality of Predictions*.  
   https://scikit-learn.org/stable/modules/model_evaluation.html
4. Scikit-learn. *Classification Report*.  
   https://scikit-learn.org/stable/modules/generated/sklearn.metrics.classification_report.html
5. Scikit-learn. *Mean Absolute Error*.  
   https://scikit-learn.org/stable/modules/generated/sklearn.metrics.mean_absolute_error.html




