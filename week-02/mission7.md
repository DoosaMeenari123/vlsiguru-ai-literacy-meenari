# MISSION 7 | Understand Why ML Systems Fail
# Research Question: Even if a model works during testing, why might it fail in reality?
# Answer
A machine learning model may perform well during testing but fail in real-world situations because the test data may not fully represent actual conditions. The model may learn from poor-quality data, incorrect labels, biased examples or information that would not be available when making real predictions.
Real-world data can also change over time, causing the model's performance to decrease. In addition, incorrect predictions can have serious consequences if people depend on the model without checking its results.
# Investigation of Poor-Quality or Unrepresentative Data, Label Errors, Missing Values and Noisy Observations
The quality of the training data strongly affects how well a machine learning model performs. If the data is incomplete, incorrect or unrepresentative, the model may learn misleading patterns.
| Data Problem | Meaning | Example | Possible Solution |
|---|---|---|---|
| Poor-quality data | Data contains incorrect, inconsistent or unreliable values. | A sensor records an impossible temperature during chip manufacturing. | Check data quality and correct or remove invalid records. |
| Unrepresentative data | The training data does not reflect the situations the model will encounter in reality. | A defect detection model is trained using only one type of chip but is used on many types. | Collect diverse examples that represent real operating conditions. |
| Label errors | Training examples have incorrect target labels. | A defective chip is incorrectly labelled as good. | Review labels and verify them with reliable inspection results. |
| Missing values | Some required measurements or features are unavailable. | A chip's voltage measurement is missing from the dataset. | Investigate why values are missing and use suitable imputation or missing-data handling methods. |
| Noisy observations | Data contains random variations or measurement errors. | A sensor produces unstable power readings. | Check sensor calibration, filter noise where appropriate and investigate unusual measurements. |

# Data Bias and Differences in Performance Across Data Subsets:
Data bias occurs when the collected data systematically overrepresents some situations or groups and underrepresents others. As a result, a model may work well for some subsets of data but poorly for others.
For example, a semiconductor defect detection model might be trained mostly on chips produced by one manufacturing line. When it is used on chips from another line with different sensors or production conditions, it may miss more defects.
Model performance should therefore be evaluated across relevant subsets, such as different manufacturing lines, chip types, locations or operating conditions.
| Type of Bias or Difference | Example | Possible Impact |
|---|---|---|
| Sampling bias | Training data contains chips from only one factory. | The model may perform poorly at other factories. |
| Underrepresentation | Rare defect types appear very few times in training data. | The model may fail to recognise those defects. |
| Measurement bias | Different manufacturing lines use sensors with different calibration. | The model may interpret similar chips differently. |
| Subgroup performance differences | The model has high accuracy for one chip type but low accuracy for another. | Some types of chips may receive less reliable predictions. |

# Data Leakage and Why It Makes Evaluation Misleading
Data leakage occurs when information that should not be available to the model during training is accidentally used in training or evaluation. This can make the model appear more successful than it really is.
| Leakage Type | Example | Why It Is a Problem | Possible Prevention |
|---|---|---|---|
| Target leakage | A feature contains information recorded after the outcome occurs. | The model uses information that would not be available when making a real prediction. | Remove features that reveal the target or are unavailable at prediction time. |
| Train-test contamination | Information from the test dataset influences training or model selection. | The test results no longer provide an independent evaluation. | Keep the test dataset separate until final evaluation. |
| Preprocessing leakage | Missing-value imputation or feature scaling is fitted using the entire dataset before splitting. | Information from the test set influences the training process. | Split the data first and fit preprocessing steps using training data only. |
| Duplicate or related records | Measurements from the same chip appear in both training and test datasets. | The test set may not represent truly unseen examples. | Group related records together before splitting the data. |

Data leakage can lead to unrealistic evaluation results. To prevent it, use a suitable data-splitting strategy, fit preprocessing steps only on training data, and make sure every feature would be available at the time of prediction.

# How Changes in Real-World Data Can Reduce Model Performance
A model learns patterns from the data available during training. If real-world data changes after deployment, those learned patterns may become less useful. This is commonly called data drift or, depending on the change, concept drift.
Data drift: The distribution of input data changes. For example, a factory begins producing a new chip design with different measurement ranges.
Concept drift: The relationship between inputs and the correct outcome changes. For example, a new manufacturing process changes which sensor patterns are associated with defects.
| Change | Example | Possible Effect |
|---|---|---|
| New input patterns | A factory introduces a new chip design. | The model may encounter examples it has not learned to handle. |
| Sensor or equipment changes | A sensor is replaced or recalibrated. | Measurements may differ from the training data. |
| Process changes | A new manufacturing process changes defect patterns. | Previously useful relationships may no longer predict defects correctly. |
| Environmental changes | Temperature or operating conditions change. | The model may make more errors under the new conditions. |

# Importance of Human Oversight and Consequences of Incorrect Predictions
Human oversight is important because machine learning predictions are not always correct. A model may be uncertain, encounter unfamiliar data or make errors that have serious consequences.
Human review is especially important in situations involving safety, quality control, financial decisions or other high-impact outcomes.
| Risk | Possible Consequence | Human Oversight or Mitigation |
|---|---|---|
| Defective chip predicted as good | A defective product may reach the next production stage. | Use appropriate inspection checks and review high-risk cases. |
| Good chip predicted as defective | Good products may be rejected unnecessarily. | Verify flagged chips using reliable testing procedures. |
| Model encounters unfamiliar data | Predictions may become unreliable. | Detect unfamiliar inputs and send them for additional review. |
| Model performance decreases over time | More incorrect predictions may occur. | Monitor performance and investigate changes in data or process conditions. |

Human oversight does not mean a person must manually check every prediction. Instead, the level of review should match the potential risk, the model's reliability and the consequences of an error.

# Deliverable: Analysis of Three Hypothetical ML Failures
#Failure 1: Defective Chips Are Classified as Good
Scenario: A factory uses an ML model to detect defective chips. Although the model performs well during testing, some defective chips pass inspection after deployment.
| Aspect | Analysis |
|---|---|
| Likely Cause | The training dataset contained too few examples of rare defect types, or some defective chips were incorrectly labelled as good. |
| Evidence to Confirm the Cause | Review missed defects, inspect their original labels, compare defect types in training and production data, and measure recall for each defect category. |
| Possible Mitigation | Collect more verified examples of rare defects, correct label errors, improve coverage of defect types and evaluate recall on representative test data. |
| Possible Consequence | Defective chips may reach later production stages or customers, increasing costs and reliability risks. |

#Failure 2: The Model Works Well in One Factory but Poorly in Another
Scenario: A defect detection model performs well at one factory but makes many incorrect predictions when introduced at a second factory.
| Aspect | Analysis |
|---|---|
| Likely Cause | The training data mainly represented the first factory. Different sensors, equipment, chip types or operating conditions at the second factory created a data-distribution mismatch. |
| Evidence to Confirm the Cause | Compare input measurements, sensor calibration, chip types and verified model performance across both factories. Examine false positives and false negatives separately for each location. |
| Possible Mitigation | Collect representative data from the second factory, check sensor calibration, validate the model separately at each location and retrain if needed. |
| Possible Consequence | The second factory may experience more missed defects, unnecessary rejections and production delays. |

#Failure 3: The Model Performs Well During Testing but Fails After Deployment
Scenario: A model achieves excellent test results but produces unreliable predictions for newly manufactured chips.
| Aspect | Analysis |
|---|---|
| Likely Cause | Data leakage occurred during development. For example, information recorded after inspection was included as a feature, or measurements from the same chip appeared in both training and test datasets. |
| Evidence to Confirm the Cause | Review feature timestamps, inspect the data-splitting process, search for duplicate or related records and check whether all features would be available at prediction time. Re-evaluate the model using a clean, independent test set. |
| Possible Mitigation | Remove leaked features, split related records appropriately, fit preprocessing only on training data and evaluate the final model on genuinely unseen examples. |
| Possible Consequence | The model's reported performance is misleading, and real-world decisions may be based on unreliable predictions. |

# REFERENCES:
1. **Google for Developers – Data Quality**
   - Covers data quality issues, missing values and sampling bias.
   - https://developers.google.com/machine-learning/guides/data-traps/quality
2. **Google for Developers – Monitoring ML Pipelines**
   - Explains monitoring ML systems and identifying problems after deployment.
   - https://developers.google.com/machine-learning/crash-course/production-ml-systems/monitoring
3. **Google – Rules of Machine Learning**
   - Explains training-serving differences and challenges with real-world data.
   - https://developers.google.com/machine-learning/guides/rules-of-ml
4. **Google Cloud – Guidelines for Developing High-Quality ML Solutions**
   - Covers model performance, data drift and production monitoring.
   - https://docs.cloud.google.com/architecture/guidelines-for-developing-high-quality-ml-solutions
5. **NIST – AI Risk Management Framework**
   - Covers AI risks, human oversight and trustworthy AI systems.
   - https://www.nist.gov/itl/ai-risk-management-framework/ai-risk-management-framework-resources

