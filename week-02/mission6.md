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











