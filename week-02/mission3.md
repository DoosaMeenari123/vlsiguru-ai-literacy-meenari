# MISSION 3: To understand main ML approaches
# Question: How does a system learn when it has labels ,no labels ,or feedback from actions?
# Answer:
Machine learning systems learn in different ways depending on the information they receive. The three main approaches are supervised learning, unsupervised
learning, and reinforcement learning. Self-supervised learning is another related approach that creates training targets from the data itself.
## Comparison of Machine Learning Approaches
| Requirement | Supervised Learning | Unsupervised Learning | Reinforcement Learning | Self-Supervised Learning |
|---|---|---|---|---|
| **Definition** | Learns from data with known answers. | Finds patterns in data without labels. | Learns through actions and feedback. | Creates training targets from the data itself. |
| **Training Signal** | Correct labels or target values. | Similarities and patterns in data. | Rewards or penalties. | Targets generated from the input data. |
| **What It Produces** | Predictions or classifications. | Groups or hidden patterns. | A strategy for choosing actions. | Useful patterns or data representations. |
| **Limitation** | Requires labelled data. | Patterns may be difficult to interpret. | May require many trials. | The training task may not match the final goal. |
| **Example** | Predict whether a chip passes or fails timing. | Group similar chip designs. | Optimize chip performance using rewards. | Predict a hidden value in chip measurements. |
| **When It Is Suitable** | When known answers are available. | When we want to discover patterns. | When actions receive feedback from an environment. | When unlabelled data can provide training targets. |
# Explaination of each learning process:
A. Supervised Learning:
The model learns from examples that already contain the correct answers. It uses these examples to predict results for new data.
Diagram:
Labelled Data
(Inputs + Correct Answers)
          |
          v
     Train Model
          |
          v
    Learn Patterns
          |
          v
 Predict New Results
Example: A model learns from previous chip measurements labelled Pass or Fail and predicts whether a new chip design will pass timing requirements.
B. Unsupervised Learning :
The model receives data without labels and tries to find similarities, groups, or hidden patterns.
   Unlabelled Data
          |
          v
    Analyse Data
          |
          v
   Find Similarities
          |
          v
  Groups and Patterns
Example: A model groups chip designs with similar area, power consumption, and clock frequency without knowing their timing results.
C. Reinforcement Learning:
The system learns by taking actions, observing the results, and receiving rewards or penalties. It uses this feedback to improve its future decisions.
     +-------------+
     |    Agent    |
     +-------------+
            |
            v
       Take Action
            |
            v
     +-------------+
     | Environment |
     +-------------+
            |
            v
    Reward or Penalty
            |
            v
      Improve Strategy
            |
            +----> Repeat
Example: An agent tries different chip-design settings and receives a reward when it improves timing while staying within power limits.
# Understanding Self-Supervised Learning
Self-supervised learning uses the data itself to create training targets. Instead of requiring people to label every example, the system creates a task from the available data and learns by solving it.
Example: A model receives a sentence with one word hidden and learns to predict the missing word from the surrounding text.
Simple Diagram:
    Unlabelled Data
           |
           v
 Create Training Targets
    from the Data
           |
           v
      Train Model
           |
           v
   Learn Useful Patterns
# Why Self-Supervised Learning Is Not Always the Same as Unsupervised Learning
Both approaches can use data without human-provided labels, but they use different learning methods.
Unsupervised learning generally focuses on discovering patterns, similarities, or groups in data without predefined target answers.
Self-supervised learning creates its own training targets from the data and trains the model to predict those targets.
For example, grouping similar chip designs is an unsupervised learning task, while hiding part of a data record and predicting the missing value can be a self
supervised task.
Self-supervised learning is closely related to unsupervised learning, but the two terms are not interchangeable in every context because their training objectives differ.
# When Is Each Approach Suitable?
| Approach | When It Is Useful |
|---|---|
| Supervised Learning | When labelled data is available and we need to predict a known outcome. |
| Unsupervised Learning | When data has no labels and we want to discover groups or patterns. |
| Reinforcement Learning | When a system must learn actions through rewards and feedback from its environment. |
| Self-Supervised Learning | When large amounts of unlabelled data are available and training targets can be created from the data itself. |
