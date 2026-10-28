# Open-Source VLSI Tool Investigation: OpenROAD

## 1. Introduction

For my Physical Design (PD) track, I selected **OpenROAD**, an open-source project that supports automated digital integrated-circuit implementation.

Physical Design converts a synthesized digital design into a physical layout while considering area, timing, routing, and other design requirements.



## 2. What Problem Does OpenROAD Help Solve?

Digital Physical Design involves multiple stages, from preparing the design for implementation to placing cells, building a clock network, routing connections, and checking the results.

OpenROAD provides tools that help automate important parts of this process. This automation helps engineers follow repeatable implementation workflows and evaluate design results.

## 3. Basic Physical Design Workflow

```text
RTL Design
    |
    v
Logic Synthesis
    |
    v
Floorplanning
    |
    v
Placement
    |
    v
Clock Tree Synthesis (CTS)
    |
    v
Routing
    |
    v
Timing and Design Checks
    |
    v
Reports and Implementation Results
```

This is a simplified digital-design workflow. The exact stages and order depend on the configured flow and design requirements.

## 4. Major Stages of Physical Design

| Stage | Purpose | Expected Result |
|---|---|---|
| Logic Synthesis | Converts RTL into a gate-level representation. | Synthesized netlist |
| Floorplanning | Defines the core area and initial physical arrangement. | Initial floorplan |
| Placement | Assigns physical locations to standard cells. | Placed design |
| Clock Tree Synthesis (CTS) | Builds the clock distribution network. | Clock-tree implementation |
| Routing | Creates physical connections between cells. | Routed design |
| Timing Analysis | Evaluates whether timing requirements are satisfied. | Timing reports |
| Design Checks | Checks applicable physical and implementation requirements. | Check reports and results |

The exact files and reports depend on the design and implementation configuration.

## 5. Main Inputs and Outputs

### Inputs

| Input | Purpose |
|---|---|
| Synthesized netlist | Describes the gates and their logical connections. |
| Technology information | Describes the manufacturing technology and physical rules. |
| Standard-cell libraries | Provide cell functions and relevant cell characteristics. |
| Timing constraints (SDC) | Specify clocks and timing requirements. |
| Floorplanning configuration | Defines physical implementation settings. |
| Design configuration | Specifies the options used to run the flow. |

### Outputs

| Output | Purpose |
|---|---|
| Floorplan data | Describes the initial physical design arrangement. |
| Placement results | Describe standard-cell locations. |
| Clock-tree results | Describe the implemented clock network. |
| Routed design data | Represents physical interconnections. |
| Timing reports | Help identify timing problems. |
| Area reports | Help assess cell area and other reported area metrics. |
| Design-check reports | Help identify implementation issues. |

The precise input and output formats depend on the selected flow.

## 6. How Can AI or ML Help Physical Design?

AI and ML may help engineers estimate outcomes, recognise patterns, and compare implementation choices.

| Application | Engineering Problem | Possible ML Task |
|---|---|---|
| Congestion Prediction | Some design regions may have high routing demand. | Classification or regression |
| PPA Estimation | Engineers need early estimates of power, performance, and area. | Regression |
| Timing Violation Prediction | Some paths may be likely to fail timing requirements. | Classification or regression |
| Design-Space Exploration | Many implementation settings must be compared. | Ranking or optimisation |
| Placement Guidance | Alternative placement choices may affect design quality. | Prediction or optimisation |

These are potential applications, not claims that OpenROAD automatically performs all these tasks using ML. Any proposed model must be evaluated using suitable data and engineering metrics.

## 7. Limitations and Engineering Considerations

- Results depend on the quality of input files and the correctness of design constraints.
- Incorrect library or configuration information can affect implementation results.
- Timing, area, and routing must be evaluated rather than assumed to be satisfactory.
- ML predictions may be inaccurate for designs that differ from the training data.
- AI-generated commands and scripts should be reviewed and tested.
- Confidential design information must be protected.

## 8. Exploration and Practical Work

**Investigation method:** Reviewed the official OpenROAD documentation and studied the general digital Physical Design workflow.

**Practical status:** A complete OpenROAD implementation run has not yet been verified for this investigation.

My next steps are to:

1. Follow an official example from the OpenROAD Flow Scripts documentation.
2. Identify the required input files and configuration.
3. Run the example if the required environment is available.
4. Inspect the generated reports and implementation outputs.
5. Record errors, observations, and results.

## 9. Conclusion

OpenROAD is relevant to Physical Design because it supports automated digital implementation workflows. Understanding its stages helps me connect theoretical VLSI concepts with practical tools.

AI and ML may support prediction and optimisation in Physical Design, but their outputs must be checked against actual implementation results and design requirements.

## References
- OpenROAD Documentation: https://openroad.readthedocs.io/en/latest/
- OpenROAD Flow Scripts Documentation: https://openroad-flow-scripts.readthedocs.io/en/latest/
