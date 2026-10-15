# UAV Digital Twin: Adaptive Synchronization and Retraining

## 1. Project Overview

This project explores machine learning for synchronizing the arrival times of multiple Unmanned Aerial Vehicles (UAVs). A Random Forest Regression model predicts required speeds using synthetic data, and a simplified simulation evaluates arrival-time alignment.

Contextual-bandit learning, complete Digital Twin updates and automatic adaptive retraining are planned future extensions.

## 2. Objectives

- Develop a three-UAV synchronization simulation.
- Generate 1,000 synthetic scenarios for required-speed prediction.
- Train and evaluate a Random Forest Regression model.
- Analyze public UAV flight telemetry using EDA and prediction experiments.
- Design a future contextual-bandit-based adaptive synchronization framework.

## 3. Technologies Used

- Python
- Google Colab / Jupyter Notebook
- NumPy
- Pandas
- Scikit-learn
- Matplotlib
- IPython display

## 4. Dataset

### Synthetic Dataset
- Total scenarios: 1,000
- Training samples: 800
- Testing samples: 200
- Purpose: Required-speed regression and synchronization simulation.

### Public UAV Telemetry Dataset
- Repository: https://github.com/yogesh031020/drone-flight-operations-data
- File: `2024-05-20_Autonomous_Waypoint_Mission.csv`
- Purpose: Exploratory data analysis and separate prediction experiments.

The public dataset does not provide labelled multi-UAV synchronization scenarios, required-speed targets or contextual-bandit rewards.

## 5. Methodology

1. Define UAV positions, initial speeds and target location.
2. Generate synthetic training scenarios.
3. Split the dataset into training and testing sets.
4. Train the Random Forest Regression model.
5. Evaluate predictions using MAE and R².
6. Simulate UAV movement using predicted speeds.
7. Calculate arrival times and synchronization spread.
8. Analyze public telemetry separately.

## 6. Reported Results

### Model Performance

| Metric | Result |
|---|---:|
| Synthetic scenarios | 1,000 |
| Training samples | 800 |
| Testing samples | 200 |
| MAE | 0.0294 |
| R² | 0.9891 |

### Synchronization Results

| UAV | Initial Speed | Predicted Speed | Arrival Time |
|---|---:|---:|---:|
| UAV 1 | 0.800 | 0.629 | 44.97 s |
| UAV 2 | 0.500 | 0.498 | 44.87 s |
| UAV 3 | 1.000 | 0.496 | 45.09 s |

Reported arrival-time spread: approximately **0.216 seconds**.

These results come from synthetic experiments and simplified simulation, not real UAV flights or the public telemetry dataset.

## 7. How to Run

### Using Google Colab
1. Open https://colab.research.google.com/
2. Upload `UAV_Digital_Twin_Code.ipynb`.
3. Run the notebook cells in order.
4. Review the generated metrics, tables and visualizations.

### Using Python Locally

Install the required packages:

```bash
pip install numpy pandas matplotlib scikit-learn ipython notebook
```

Start Jupyter Notebook:

```bash
jupyter notebook
```

Open `UAV_Digital_Twin_Code.ipynb` and execute the cells in order.

Internet access is required for notebook steps that download the public dataset.

## 8. Proposed Contextual Bandit

A contextual bandit can select an action using the current operating context and learn from the resulting reward.

**Proposed actions:**
- MOVE
- WAIT
- SYNCHRONIZE
- RETRAIN

A possible reward could favour lower arrival-time spread while penalizing unnecessary speed changes and unsafe actions.

The contextual-bandit policy, reward function, complete Digital Twin update loop and automatic adaptive retraining are not yet implemented and evaluated.

## 9. Limitations

- Required-speed regression uses synthetic training data.
- Public telemetry lacks the labels required for supervised multi-UAV synchronization.
- The simulation assumes simplified constant-speed, straight-line movement.
- Wind, obstacles, acceleration and communication delays are not fully modelled.
- No real-flight validation has been performed.
- Adaptive components remain planned future work.

## 10. Future Scope

- Implement and evaluate the contextual-bandit policy.
- Define a suitable reward function and safe action space.
- Integrate the policy with the UAV simulator.
- Develop Digital Twin updates using new observations.
- Add performance monitoring and drift detection.
- Implement validated adaptive retraining.
- Test with realistic simulations and suitable labelled datasets.
- Conduct controlled validation before any real-world deployment.

## 11. References

1. Drone Flight Operations Data: https://github.com/yogesh031020/drone-flight-operations-data
2. McManus et al., “Digital twin-enabled domain adaptation for zero-touch UAV networks: Survey and challenges,” *Computer Networks*, Volume 236 (2023). https://doi.org/10.1016/j.comnet.2023.110000

## 12. Project Information

**Authors:**  
N. Hasini — 2520040039  
Ch. Sai Lahari — 2520040023

**Guide:** Mr. N. Lava Prasad, Assistant Professor  
**Department:** Electronics and Communication Engineering  
**Course:** Machine Learning (25SC2107E)  
**Academic Year:** 2026–2027
