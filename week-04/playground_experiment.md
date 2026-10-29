# Mission 5 — Experiment and Observe

**VLSIGURU | AI Literacy Layer | Week 04**


**Tool:** [TensorFlow Neural Network Playground](https://playground.tensorflow.org/)

## 1. Objective

The objective of this experiment is to understand how changing the number of hidden layers and neurons affects a neural network's decision boundary and training behaviour.

Using TensorFlow Playground, I will compare a simple network with a more complex network while keeping the dataset and other settings unchanged wherever possible.

This experiment will help me understand that a more complex model can learn complicated patterns, but it does not always perform better on unseen data.

## 2. Experiment Setup

I will first run a baseline configuration and then modify the network architecture.

| Setting | Baseline configuration | Modified configuration |
|---|---|---|
| Dataset | Select a two-class classification dataset | Use the same dataset |
| Hidden layers | One hidden layer | Three hidden layers |
| Neurons | Start with a small number, such as 2 | Increase the number, such as 4 per layer |
| Learning rate | Record the displayed value | Keep unchanged |
| Activation function | Record the selected function | Keep unchanged |
| Input features | Record the selected features | Keep unchanged |
| Training and test settings | Record the displayed settings | Keep unchanged where possible |

**Important:** These are proposed settings for comparison. I will record the actual settings displayed in Playground and will not treat the suggested values as experimental results.

## 3. Experiment Procedure

1. Open [TensorFlow Neural Network Playground](https://playground.tensorflow.org/).
2. Select a two-class classification dataset, such as the circle dataset.
3. Record the dataset, input features, activation function, learning rate and other displayed settings.
4. Configure the baseline network with one hidden layer and a small number of neurons.
5. Run the training process and observe the decision boundary and training/test loss, if displayed.
6. Record the baseline observations.
7. Change the network to three hidden layers and increase the number of neurons.
8. Keep the dataset and other settings unchanged wherever possible.
9. Run the training process again and record the new observations.
10. Compare both configurations and determine whether the more complex network provides a meaningful improvement.

For a fair comparison, use the same dataset and comparable training conditions. If training is stochastic, repeat the comparison where practical.

## 4. Observation Log

Complete this table after running both experiments.

| Question | My observation |
|---|---|
| What did the baseline decision boundary look like? | Write what you observed in the Playground visualization. |
| What changed after adding hidden layers? | Describe any changes in the shape or complexity of the boundary. |
| What changed after increasing the number of neurons? | Record the visible difference, if any. |
| Did the training behaviour change? | Compare the displayed loss and training progress. |
| Which configuration fitted the training points better? | Record the result shown by your experiment. |
| Which configuration performed better on test data? | Compare the displayed test loss or other available evidence. |
| Was there evidence of overfitting? | Check whether training performance improved while test performance remained worse or deteriorated. |
| Did greater complexity clearly improve the result? | State your conclusion based on the evidence. |

**Note:** Do not assume that the modified network performs better. Record the actual results shown by Playground.

## 5. Questions to Investigate

### What changed when the network became more complex?

Increasing the number of hidden layers or neurons gives a network greater capacity to learn complicated relationships. This may produce a more detailed decision boundary.

However, the actual change depends on the dataset, selected features, activation function, training process and other settings.

### Did the more complex network always perform better?

No. A larger network may fit the training examples more closely, but this does not guarantee better performance on unseen examples.

The comparison should consider both training and test behaviour rather than judging the network only by how closely its decision boundary fits the training points.

### What is the relationship between complexity and learning?

A simple network may struggle to represent a complicated pattern. Increasing the number of layers or neurons can help it learn more complex patterns.

However, excessive complexity relative to the available data can increase the risk of overfitting. More complexity also does not guarantee that the network will train more quickly or reach a better solution.

### Why is training performance not enough?

Training performance shows how well the network fits the examples used for learning. Test performance provides evidence about how well it handles examples excluded from training.

A network that performs well on training data but poorly on test data may not generalise well.

### How is this experiment different from real semiconductor inspection?

TensorFlow Playground is a simplified environment that demonstrates neural network behaviour using small datasets.

Real semiconductor inspection may involve:

- High-resolution wafer or chip images.
- Multiple defect types and difficult-to-distinguish patterns.
- Incorrect labels, noisy images and class imbalance.
- Different cameras, lighting and manufacturing conditions.
- Requirements for fast predictions and reliable defect detection.

Therefore, results from Playground cannot by themselves establish that a neural network is suitable for semiconductor inspection.

### What evidence is needed before practical use?

| Evidence | Why it matters |
|---|---|
| Representative held-out images | Tests whether the model works on unseen inspection data. |
| Precision | Indicates how many predicted defects are actually defects. |
| Recall | Indicates how many actual defects the model detects. |
| False-negative analysis | Identifies defects incorrectly classified as defect-free. |
| Baseline comparison | Shows whether the complex model provides a meaningful improvement. |
| Evaluation across inspection conditions | Checks reliability under different production conditions. |
| Prediction time | Determines whether the model meets operational requirements. |
| Human-review process | Helps manage uncertain predictions and high-impact mistakes. |


## 6. Conclusion

This experiment helps me understand the relationship between neural network complexity and performance. Adding hidden layers or neurons can help a network learn more complicated decision boundaries, but it does not guarantee better results.

I need to compare the actual decision boundaries and training/test behaviour before deciding which configuration performs better. In real semiconductor applications, model selection should also consider generalisation, false negatives, prediction speed and the quality of the inspection data.

The most important lesson is that **the best network is not necessarily the largest network; it is the one that performs reliably on relevant, unseen data.**

## References

1. TensorFlow Playground — [Interactive Neural Network Experiment](https://playground.tensorflow.org/)
2. Google for Developers — [Neural Networks](https://developers.google.com/machine-learning/crash-course/neural-networks)
3. Scikit-learn — [Cross-Validation and Model Evaluation](https://scikit-learn.org/stable/modules/cross_validation.html)

