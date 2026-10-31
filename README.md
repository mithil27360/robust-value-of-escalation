# Robust Value-Based Escalation for Reliability Monitoring Under Distribution Shift


## Overview

This research investigates whether a learned value estimator can identify inputs that benefit from additional model monitoring under distribution shift.

We propose a selective escalation framework using a ResNet-18 base classifier, a Random Forest value estimator, and three additional neural network monitors.

## Methodology

- **Dataset:** CIFAR-10 and CIFAR-10-C
- **Base Model:** ResNet-18
- **Monitoring Models:** ResNet-34, ResNet-50, DenseNet-121
- **Value Estimator:** Random Forest Regressor
- **Features:** Confidence, predictive entropy and classification margin
- **Monitoring Rule:** At least 2 of 3 monitors must agree; otherwise, abstain.
- **Primary Escalation Budget:** 20%

## Key Results

| Policy | Utility Gain |
|---|---:|
| Oracle | 0.1609 |
| Low Confidence | 0.0548 |
| High Entropy | 0.0534 |
| Low Margin | 0.0536 |
| Value Gate | 0.0455 |
| Random | 0.0173 |

The learned value gate did not outperform simple confidence-based selection in the pilot evaluation.

Selective monitoring achieved approximately one-third of the latency of always-on monitoring.

## Repository Contents

- `Research_Report.pdf` — Complete research paper and experimental findings.
- Research notebook/code — Implementation, experiments and evaluation.

## Limitations

This pilot evaluation covers Gaussian noise at five severity levels, one data-split seed and a 20% escalation budget.

## Future Work

- Evaluate additional corruption types.
- Test multiple random seeds and escalation budgets.
- Investigate richer predictive features.
- Improve value estimation under distribution shift.
- Evaluate on additional datasets.

## References

Refer to `Research_Report.pdf` for the complete literature review and references.
