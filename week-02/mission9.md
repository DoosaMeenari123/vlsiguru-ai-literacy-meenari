# MISSION 9: Connect the Full Map to Semiconductor Engineering
# Research Question: Where Does ML Fit into the Semiconductor Value Chain?
## Case Study: Machine Learning for PPA Estimation in Physical Design
# 1. Application Area and Engineering Problem:
-Application Area: VLSI Physical Design
In semiconductor engineering, PPA stands for Power, Performance and Area. Engineers must estimate these metrics to determine whether a chip design meets its requirements.
Traditional evaluation often requires running electronic design automation (EDA) tools, which can take considerable time. Engineers may need to repeat this process for many design alternatives.
Machine learning can help by predicting PPA metrics early in the design process. This allows engineers to compare alternatives faster and focus detailed tool runs on promising designs.
 
# 2.Data Required:
An ML model needs historical design data containing input features and corresponding results from EDA tools.
| Data Required | Purpose |
|---|---|
| RTL code or circuit representation | Describes the hardware design being evaluated. |
| Circuit features | Provides information about operators, gates, registers and connections. |
| Design constraints | Includes clock targets and other design requirements. |
| Technology and library information | Describes the target manufacturing technology and available cells. |
| Previous EDA results | Provides actual power, timing and area values for training. |

The data should cover different designs and operating conditions. Incorrect or limited data may cause inaccurate predictions.

# 3.Intended Model Output and Learning Approach:
The intended output is an estimate of the design's PPA metrics before completing the full implementation process.
A suitable approach is supervised learning, because the model learns from previous designs with known input features and measured results.
| Model Output | Meaning |
|---|---|
| Power estimate | Predicts the expected power consumption. |
| Performance estimate | Predicts timing-related results, such as delay or timing slack. |
| Area estimate | Predicts the expected hardware area. |

The problem can be treated as a regression task because the model predicts numerical values. The predicted results help engineers compare design alternatives, but they do not replace final EDA verification.

# 4. Evaluation and Limitations:
The model should be tested on designs that were not used during training. Its predictions should be compared with results from trusted EDA tools.
| Evaluation or Limitation | Explanation |
|---|---|
| Prediction error | Use metrics such as MAE or RMSE to measure the difference between predicted and actual values. |
| Generalisation | Check whether the model works on different designs, rather than only familiar examples. |
| Data quality | Incorrect measurements or inconsistent labels can reduce reliability. |
| Technology differences | A model trained for one process technology or tool flow may not work well with another. |
| Final verification | Engineers must still use appropriate EDA tools to verify timing, power, area and design constraints. |

ML predictions can save evaluation time, but inaccurate estimates may cause engineers to select a design that fails its final PPA requirements.

# 5. Reliable Sources and Evidence:
Research publications demonstrate that ML-based PPA estimation is a real research direction in VLSI engineering.
Research demonstration — IEEE (2025): Machine Learning Framework for Early Power, Performance, and Area Estimation of RTL. This paper presents a proposed ML framework for estimating PPA metrics from RTL designs and evaluates it on 147 designs.
Research demonstration — ACM (2024): An Open-Source ML-Based Full-Stack Optimization Framework for Machine Learning Accelerators. This research explores ML-based PPA prediction and design-space exploration for accelerator implementations.
These sources support the use of ML for early PPA estimation and design exploration. They describe research methods and evaluations; they do not establish that every commercial physical-design flow uses such a model in production.
