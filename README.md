# CrowdVision AI

**Chess-Inspired AI for Crowd Threat Prediction and Risk Escalation Analysis**

CrowdVision AI is an intelligent computer vision system that predicts crowd risk and potential threat escalation from a single image. Inspired by the strategic decision-making process of chess engines, the system combines deep learning, probabilistic reasoning, and simulation-based planning to understand crowd dynamics and forecast how a situation may evolve.

Unlike conventional crowd monitoring systems that only analyze the current scene, CrowdVision AI estimates future risk levels to support proactive decision-making for surveillance, emergency response, and public safety applications.

---

## Overview

Monitoring large crowds is essential in public events, transportation hubs, stadiums, and smart cities. Most existing surveillance systems focus on detecting anomalies after they occur, providing limited support for anticipating future risks.

CrowdVision AI addresses this challenge through a two-stage AI pipeline that combines computer vision, graph-based crowd representation, probabilistic reasoning, and search-based planning. The system analyzes crowd behavior, estimates escalation probability, and generates interpretable alert levels that can assist security personnel in making informed decisions.

---

## Key Features

- Intelligent crowd risk prediction from a single image
- Two-stage anomaly detection and threat prediction pipeline
- Chess-inspired planning using Monte Carlo Tree Search (MCTS)
- Bayesian reasoning for probabilistic decision making
- Deep learning-based visual feature extraction
- Confidence-weighted prediction fusion
- Modular architecture for smart surveillance applications

---

## System Architecture

```text
                Crowd Image
                     │
                     ▼
          Person Detection (YOLOv11)
                     │
                     ▼
      Crowd Representation & Graph Modeling
                     │
                     ▼
       Visual Feature Extraction
      (ResNet-18 & ViT-MAE)
                     │
                     ▼
           Crowd Anomaly Detection
                     │
                     ▼
      Monte Carlo Tree Search (MCTS)
                     │
                     ▼
      Bayesian Network Reasoning
                     │
                     ▼
      Confidence-Based Prediction Fusion
                     │
                     ▼
          Crowd Risk Prediction
                     │
                     ▼
      🟢 Green   🟡 Yellow   🔴 Red
```

---

## Core Components

### Crowd Detection

The system detects individuals within the scene using YOLOv11 and represents each detected person as part of a structured crowd model.

---

### Crowd Representation

Detected individuals are connected through Gaussian-weighted interaction graphs to model spatial relationships, local neighborhoods, and crowd density patterns.

---

### Feature Extraction

The framework extracts visual and spatial information including:

- Crowd density
- Spatial irregularity
- Local interaction patterns
- Appearance features
- Anomaly descriptors

Deep learning models capture both local and global scene characteristics.

---

### AI Prediction Pipeline

The prediction pipeline combines multiple AI techniques.

**Computer Vision**

- YOLOv11
- ResNet-18
- Vision Transformer (ViT-MAE)

**Decision Intelligence**

- ThreatNet
- Monte Carlo Tree Search (MCTS)
- Bayesian Networks

Simulation predicts possible future crowd conditions, while probabilistic reasoning estimates escalation likelihood.

---

### Alert Generation

The final prediction is translated into a simple three-level warning system.

| Alert | Description |
|--------|-------------|
| 🟢 Green | Normal crowd conditions |
| 🟡 Yellow | Increased risk, continue monitoring |
| 🔴 Red | High-risk situation requiring immediate attention |

---

## Dataset

| Attribute | Details |
|-----------|---------|
| Dataset | ShanghaiTech Crowd Dataset |
| Images | 1,198 |
| Scene Types | Dense and Sparse Crowds |
| Purpose | Crowd anomaly detection and risk prediction |

---

## Technology Stack

| Category | Technology |
|-----------|------------|
| Programming Language | Python |
| Deep Learning | PyTorch |
| Object Detection | YOLOv11 |
| Feature Extraction | ResNet-18 |
| Vision Transformer | ViT-MAE |
| Search Algorithm | Monte Carlo Tree Search |
| Probabilistic AI | Bayesian Networks |
| Data Storage | HDF5 |
| Development Environment | Jupyter Notebook |

---

## Project Structure

```text
crowd-threat-assessment-ai/
│
├── crowdvision_ai.ipynb
├── README.md
├── LICENSE
└── .gitignore
```

---

## Installation

### Clone the repository

```bash
git clone https://github.com/thrishikav9-del/crowd-threat-assessment-ai.git

cd crowd-threat-assessment-ai
```

### Install dependencies

```bash
pip install torch torchvision opencv-python numpy scipy matplotlib networkx
```

### Launch the notebook

```bash
jupyter notebook crowdvision_ai.ipynb
```

---

## Workflow

1. Detect individuals in the crowd.
2. Build a graph-based crowd representation.
3. Extract visual and spatial features.
4. Identify anomalous crowd behavior.
5. Simulate future crowd states using MCTS.
6. Estimate escalation probability through Bayesian reasoning.
7. Fuse predictions using confidence scores.
8. Generate the final crowd risk level.

---

## Applications

- Smart Surveillance
- Public Event Monitoring
- Smart Cities
- Transportation Safety
- Stadium Security
- Emergency Response
- Disaster Management

---

## Future Enhancements

- Video-based crowd analysis
- Graph Neural Networks
- Reinforcement Learning for adaptive planning
- Multi-camera monitoring
- Edge AI deployment
- Real-time surveillance dashboard

---

## License

This project is licensed under the MIT License.

---

## Disclaimer

This project was developed for academic and research purposes to demonstrate computer vision, probabilistic AI, and intelligent planning techniques for crowd risk prediction. It is intended to support surveillance research and public safety applications.

---

## Author

**Thrishika**

B.Tech Computer Science and Engineering (Artificial Intelligence)

Amrita Vishwa Vidyapeetham
