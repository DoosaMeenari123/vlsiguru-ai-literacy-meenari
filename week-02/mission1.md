# MISSION 1: Build the AI and ML Landscape
# Question: What is artificial intelligence and where exactly does machine learning fit?
# Answer:
Artificial Intelligence (AI) is a branch of computer science that focuses on making machines perform tasks that normally require human intelligence, such as understanding language, solving problems, recognizing images
and making decisions.
Machine Learning (ML) is a part of AI that allows computers to learn patterns from data and use those patterns to make predictions or decisions without needing a programmer to write every rule manually.
In simple words, AI is the bigger concept, and ML is one of the methods used to build AI systems.

# Labelled Concept Map:
```text
                    ARTIFICIAL INTELLIGENCE (AI)
                Making machines perform intelligent tasks
                              |
                +-------------+-------------+
                |                           |
          RULE-BASED AI               MACHINE LEARNING (ML)
          Human-written rules         Learns patterns from data
                |                           |
                v                           v
          Explicit logic              DEEP LEARNING
          and conditions              Multi-layer neural networks
                                            |
                                            v
                                      GENERATIVE AI
                                      Creates new content
                                            |
                                            v
                                  LARGE LANGUAGE MODELS
                                          (LLMs)
                                  Understands and generates
                                          language


  CONVENTIONAL PROGRAMMING                AUTOMATION
  Follows explicit instructions           Performs tasks automatically
              |                                      |
              v                                      v
  Example: Calculator                  Example: Scheduled email
  Uses predefined logic                Uses predefined instructions.
```
# Comparison: Artificial Intelligence vs Conventional Rule-Based Programming vs Machine Learning
| Basis | Artificial Intelligence (AI) | Conventional Rule-Based Programming | Machine Learning (ML) |
|---|---|---|---|
| **Meaning** | Makes machines perform tasks that require intelligence. | Follows instructions and rules written by humans. | Learns patterns from data to make predictions. |
| **Working** | Uses rules, search, reasoning or learning techniques. | Uses predefined rules and conditions. | Trains models using data. |
| **Data Usage** | Depends on the AI approach. | Processes data using fixed logic. | Learns patterns from training data. |
| **Adaptability** | Depends on the technique used. | Usually requires manual rule changes. | Can apply learned patterns to new data. |
| **Human Role** | Humans design the system and define its goals. | Humans write the rules and logic. | Humans design the model and training process. |
| **Example** | Chess-playing AI. | Calculator following programmed operations. | Spam detector trained on emails. |
| **Relationship** | The broad field of intelligent systems. | A programming approach that may be used in AI. | A subset of AI. |

# Why automation is not necessarily AI, and why AI does not always mean ML
Automation is not necessarily AI: Automation means using machines or software to perform tasks automatically without needing a person to do every step. For example, a washing machine following a fixed washing cycle is
automation, but it does not necessarily use AI because it follows predefined instructions.
AI does not always mean ML: AI is a broader concept that allows machines to perform tasks that require intelligence. Some AI systems use machine learning to learn patterns from data, while others use predefined rules
and logic. For example, a chess-playing program can use rules and search algorithms to choose moves without learning from data.
Automation is about performing tasks automatically, AI is about performing intelligent tasks, and ML is about learning patterns from data. Therefore, not all automation is AI, and not all AI uses ML.

# Identify What is explicitly programmed versus what can be learned from data
In conventional programming, the programmer writes the rules and instructions that tell the computer what to do. The computer follows these instructions to produce an output.
In machine learning, the programmer defines the model and training process, but the model learns patterns from the data provided. It uses these patterns to make predictions or decisions on new data.
Example: In a rule-based email filter, the programmer can write a rule to mark emails containing a specific word as spam. In a machine learning email filter, the model learns patterns from examples of spam and genuine
emails to identify spam.
In simple words,Explicitly programmed means humans write the rules, while learned from data means the computer learns patterns from examples during training.

# Five distinctions in my own words
# 1. Artificial Intelligence vs Machine Learning: 
AI is the overall field of making machines perform tasks that require intelligence, whereas ML is a part of AI that allows computers to learn patterns from data instead of relying only on manually written rules.
# 2. Conventional Programming vs Machine Learning: 
In conventional programming, humans tell the computer exactly which rules to follow. In ML, humans provide data and a learning process, and the computer learns patterns that help it make predictions or decisions.
# 3. Machine Learning vs Deep Learning:
ML is a method of learning from data, while deep learning is a specialized type of ML that uses multiple layers of neural networks to learn complex patterns, such as features in images or relationships in language.
# 4. Traditional Predictive AI vs Generative AI: 
Predictive AI is often used to classify information or forecast outcomes, such as detecting spam. Generative AI is designed to create new content, such as writing a paragraph, producing an image or generating computer
code.
# 5. Generative AI vs Large Language Models: 
Generative AI is the broader category of systems that create new content. LLMs are a specific type of model focused on language and can be used to answer questions, summarize information, write content and assist with
coding.

# Three Examples Classified with reasons:
# Example 1: Digital calculator
Conventional programming
Classification: Rule-based programming and automation.
Reason: A calculator follows programmed mathematical operations to calculate answers. The programmer has already defined how the calculations work, so the calculator does not need to learn from examples. It is an
example of automation without necessarily using AI.
# Example 2: Email spam detector
Machine learning
Classification: ML and AI.
Reason: A typical ML spam detector is trained using examples of spam and genuine emails. It learns patterns in message content, links and other features to predict whether a new email is spam. Its predictions come from
learned patterns rather than only fixed rules.
# Example 3: AI chatbot powered by an LLM
Generative AI
Classification: AI → ML → deep learning → LLM-based generative AI.
Reason: An LLM is trained on large amounts of language data to learn patterns in text. It uses those learned patterns, along with the user's prompt and conversation context, to generate answers, summaries and other
written content. This makes it an example of generative AI based on machine learning.

# MISSION 2 : Understand data : what does an ML system learn from?
# Question: What does it mean to learn a pattern from data?
# Answer:
Machine learning (ML) is a process in which a computer learns patterns from examples in data. Instead of programming every rule manually, we give the system data so it can identify relationships and make predictions
about new examples.
For example, in chip design, an ML model can learn from past chip measurements to predict whether a new design will pass or fail timing requirements.
# Important terms in a dataset
- Dataset: A collection of related data used to train or test a model.
- Sample: One example in a dataset, such as one chip design.
- Observation: A recorded instance or row of data containing information about a sample.
- Feature: An input value used by the model to learn patterns, such as clock frequency or power consumption.
- Label: The known answer associated with an example, such as whether a chip passed timing.
- Target: The result the model is trained to predict. In this example, the target is the timing pass/fail outcome.
# Difference between  structured and unstructured data, and numerical and categorical features.
- Structured data: Data arranged in rows and columns, like a spreadsheet.
- Unstructured data: Data that does not follow a fixed table format, such as images, videos, and documents.
- Numerical features: Values expressed as numbers, such as chip area, power consumption, and clock frequency.
- Categorical features: Values representing categories, such as chip type or operating mode.
# Distinguish labelled and unlabelled examples.
Labelled examples: Data that includes the correct answer, such as chip measurements with a known Pass or Fail result.
Unlabelled examples: Data that contains measurements but does not include the correct result.
# Important terms:
Data collection: Gathering information from experiments, simulations, sensors, or historical records.
Data cleaning: Finding and correcting errors before using the data.
Missing values: Measurements or information that have not been recorded.
Noisy data: Data containing errors, random variations, or inaccurate measurements.
Inconsistent labels: When the same result is recorded in different ways, such as “Pass,” “PASS,” and “Passed.”
# Why data quantity alone does not guarantee data quality.
Having a large amount of data does not always mean that a model will perform well. If the dataset contains incorrect measurements, missing values, or wrong
labels, the model may learn incorrect patterns. A smaller dataset with accurate and relevant information can sometimes be more useful than a large dataset with
poor-quality data.
The following is a small synthetic dataset showing how machine learning could predict whether a chip design passes timing requirements.
| Sample | Clock Frequency (GHz) | Chip Area (mm²) | Power (W) | Timing Result |
|--------|----------------------:|----------------:|----------:|---------------|
| 1      | 1.0                   | 40              | 8         | Pass          |
| 2      | 1.5                   | 45              | 10        | Pass          |
| 3      | 2.0                   | 50              | 13        | Fail          |
| 4      | 1.2                   | 38              | 7         | Pass          |
| 5      | 2.2                   | 55              | 15        | Fail          |
| 6      | 1.8                   | 48              | 11        | Pass          |
Dataset details:
- Dataset: Synthetic chip timing data.
- Samples/observations: 6 rows.
- Features: Clock Frequency, Chip Area, Power.
- Target/label: Timing Result (Pass/Fail).
- Numerical features: Clock Frequency, Chip Area, Power.
- Categorical target: Timing Result.
- Data type: Structured and labelled data.
Two ways data quality could affect the model:
1. Missing or incorrect measurements: If clock frequency or power values are missing or recorded incorrectly, the model may learn the wrong relationships and make inaccurate predictions.
2. Incorrect labels: If a chip that failed timing is mistakenly labelled as Pass, the model may learn from the wrong result and produce unreliable predictions.

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
