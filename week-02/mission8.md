# MISSION 8: Does This Problem Actually Need ML?
# Research Question: When should an engineer use ML instead of a fixed rule or conventional program?
# Answer:
Machine learning (ML) is useful when a problem involves complex patterns that are difficult to describe using fixed rules. However, not every problem needs ML. If a simple rule-based program can solve the problem accurately and consistently, it may be the better choice.
Before choosing a technique, an engineer should understand the problem, define the desired outcome, check data availability, decide how success will be measured and consider the consequences of incorrect results.
For example, in semiconductor manufacturing, a fixed rule can detect a chip when a measurement exceeds a known limit. ML may be more useful when detecting defects that depend on several measurements and complex patterns.

# Define the Problem and Desired Outcome before choosing a technique
The first step is to clearly identify the problem and what the system should achieve before selecting a solution.
For example, a semiconductor factory wants to identify defective chips before they reach customers. The desired outcome is to detect defects accurately, reduce waste and maintain product quality.
The engineer should decide whether the problem can be solved using known thresholds or whether it requires recognising more complicated patterns.

# To Check Whether a Simple Rule-Based Solution Is Enough
A rule-based system follows predefined instructions written by a programmer. It does not learn from examples.
For example, if a chip's temperature exceeds a specified safety limit, the program can flag it for inspection.
Machine learning is more suitable when the relationship between measurements and defects is complex and difficult to describe using a small set of rules.
| Feature | Rule-Based Solution | Machine Learning Solution |
|---|---|---|
| How it works | Follows predefined rules. | Learns patterns from training data. |
| Example | Flag a chip when temperature exceeds a fixed limit. | Predict defects using temperature, voltage and other measurements. |
| Best suited for | Clear and stable conditions. | Complex patterns that are difficult to define manually. |
| Changes | Rules must be updated manually. | The model may need retraining with new data. |
| Complexity | Usually simpler to build and understand. | May require more development and testing. |

If fixed rules already solve the problem reliably, ML may add unnecessary cost and complexity.

# To Check Data Availability and Decide What the Model Should Predict
Before using ML, an engineer must check whether enough reliable and relevant data is available.
For a chip defect detection model, useful data may include temperature, voltage, sensor readings, chip type and verified inspection results. These examples help the model learn the relationship between measurements and defects.
The engineer should also define the model's task clearly. For example, it may classify a chip as defective or good, or estimate the probability of a defect.
| Requirement | Rule-Based Solution | Machine Learning Solution |
|---|---|---|
| Data needed | Measurements and known thresholds or conditions. | Representative historical examples and reliable labels for supervised learning. |
| Knowledge required | Experts define the rules. | The model learns patterns from examples. |
| Data preparation | Usually limited. | Often requires cleaning, validation and feature preparation. |
| Main limitation | May miss complex patterns not covered by the rules. | May learn incorrect patterns if the data is poor or biased. |

If suitable data is unavailable, a rule-based solution may be more practical until enough reliable data can be collected.

# Decide How Success Will Be Measured
A solution should be evaluated using measures that match the problem's goals.
For semiconductor defect detection, accuracy alone may not be sufficient because missing a defective chip could be more serious than incorrectly flagging a good chip.
| Evaluation Measure | Meaning |
|---|---|
| Accuracy | Percentage of predictions that are correct. |
| Precision | Of the chips predicted as defective, how many are actually defective? |
| Recall | Of all defective chips, how many does the system correctly identify? |
| False positive rate | How often good chips are incorrectly flagged as defective. |
| Cost and speed | Whether the solution reduces inspection costs and operates quickly enough. |

A rule-based system and an ML model should be tested on suitable examples and compared using the same success criteria. The engineer should choose the solution that meets the requirements reliably, not simply the one that uses more advanced technology.

# Consequences of Incorrect Predictions:
Both rule-based systems and ML models can make mistakes, but their failure modes may differ.
For example, a rule-based system may miss a defect that does not exceed a predefined threshold. An ML model may miss a rare defect because it has not learned enough examples of that defect.
| Possible Failure | Rule-Based Solution | Machine Learning Solution |
|---|---|---|
| Defective chip passes inspection | The defect does not violate any defined rule. | The model fails to recognise the defect pattern. |
| Good chip is rejected | A threshold is too strict. | The model incorrectly classifies the chip as defective. |
| New conditions appear | Existing rules may not cover the new situation. | New data patterns may reduce model performance. |
| Troubleshooting | Engineers inspect and update the rules. | Engineers investigate data, predictions and model behaviour. |

Incorrect predictions can cause waste, production delays and unreliable products. Therefore, high-risk decisions may require additional testing, human review and ongoing monitoring.

# Comparison of a Rule-Based Solution and an ML Solution
Example: Detecting Defective Chips in a Semiconductor Factory
Problem: A factory needs to identify defective chips before they move to the next production stage.
Rule-Based Approach: The system checks predefined limits. If a chip's temperature or voltage falls outside the acceptable range, it is flagged for inspection.
Machine Learning Approach: The model learns from historical chip measurements and verified inspection results to identify patterns associated with defects.
| Comparison | Rule-Based Solution | Machine Learning Solution |
|---|---|---|
| Approach | Uses predefined thresholds. | Learns patterns from historical examples. |
| Data requirements | Known limits and current measurements. | Reliable, representative training data with defect labels. |
| Advantages | Simple, transparent, fast and easy to maintain when conditions are stable. | Can identify complex patterns and relationships among several measurements. |
| Trade-offs | May miss defects that do not violate predefined rules. | Requires data preparation, validation, monitoring and potentially more computing resources. |
| Failure modes | Incorrect thresholds or rules that do not cover new conditions. | Poor-quality data, rare defects, bias or changes in real-world data. |
| Best use case | Defects associated with clear, known limits. | Defects associated with complex patterns across multiple measurements. |

# Which Solution Should the Engineer Choose?
If defects can be detected reliably using known temperature and voltage limits, a rule-based solution is likely sufficient. It is easier to explain, test and maintain.
If defects depend on complicated combinations of measurements that fixed rules cannot capture adequately, an ML solution may be worth considering, provided that sufficient reliable data is available.
A combined approach may also work well: use fixed rules for clear safety limits and ML to identify more complex defect patterns. Important predictions can then be verified through additional inspection.

# REFERENCES:
1. Google – Rules of Machine Learning  
   https://developers.google.com/machine-learning/guides/rules-of-ml
2. Google – Problem Framing  
   https://developers.google.com/machine-learning/problem-framing
3. Google – Machine Learning Crash Course  
   https://developers.google.com/machine-learning/crash-course/
4. Google Cloud – ML Solutions Guidelines  
   https://docs.cloud.google.com/architecture/guidelines-for-developing-high-quality-ml-solutions


