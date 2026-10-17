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

# Sources:
1. [Google for Developers – Datasets: Data Characteristics](https://developers.google.com/machine-learning/crash-course/overfitting/data-characteristics)
   - Covers datasets, data types, missing values, noisy data, label errors, and data quality.
2. [Google for Developers – Machine Learning Glossary](https://developers.google.com/machine-learning/glossary)
   - Explains important terms such as features, labels, labelled examples, and unlabelled examples.
3. [IBM – Structured vs. Unstructured Data](https://www.ibm.com/think/topics/structured-vs-unstructured-data)
   - Explains the differences between structured and unstructured data with examples.
