# Chess-Inspired AI System for Crowd Threat Assessment and Escalation Prediction

## Overview

This project presents a novel AI-driven system for real-time crowd threat assessment and escalation prediction from single images. Inspired by chess engine architectures, the system combines deep learning, probabilistic reasoning, and simulation-based planning to analyze crowd behavior and forecast potential risk escalation.

Unlike traditional approaches that only evaluate the current state, this system predicts how a crowd situation may evolve, enabling proactive intervention and improved public safety. 

---

## Key Contributions

* Two-phase pipeline for **anomaly detection + escalation prediction**
* Integration of **Monte Carlo Tree Search (MCTS)** with **Bayesian Networks**
* Vision-based feature extraction using **YOLOv11, ResNet-18, and ViT-MAE**
* Confidence-weighted fusion of probabilistic and simulation-based predictions
* Real-time inference with optimized latency (~76 ms on GPU)
* Achieves **0.804 F1-score and 0.847 AUC**, outperforming multiple baselines 

---

## Problem Statement

Given a single crowd image, the system must:

1. Detect whether the crowd configuration is anomalous
2. Predict the probability of escalation to a high-threat state

The output is a **three-level alert system**:

* 🟢 GREEN — Safe
* 🟡 YELLOW — Monitor
* 🔴 RED — Immediate intervention

---

## System Architecture

The system follows a **two-phase pipeline**:

### Phase 1: Feature Extraction

* Person detection using YOLOv11
* Gaussian interaction graph construction
* Feature extraction via ResNet-18
* Anomaly scoring based on:

  * spatial irregularity
  * density variation
  * outlier detection

### Phase 2: Threat Prediction

* ViT-MAE anomaly trigger (filtering stage)
* ThreatNet (MLP) for per-person threat scoring
* MCTS-based simulation of future threat states
* Bayesian Network for causal reasoning
* Final prediction using confidence-weighted fusion

👉 As shown in the architecture diagram (page 3), the pipeline combines detection → graph modeling → AI inference → probabilistic fusion into a unified system. 

---

## Technology Stack

* Python
* PyTorch
* YOLOv11 (Object Detection)
* ResNet-18 (Feature Extraction)
* Vision Transformer (ViT-MAE)
* Monte Carlo Tree Search (MCTS)
* Bayesian Networks
* HDF5 (Feature storage)

---

## Dataset

* **ShanghaiTech Crowd Dataset**
* 1,198 images (dense + sparse crowd scenes)
* Used for anomaly detection and escalation prediction

---

## Methodology

### 1. Crowd Representation

* Individuals detected and represented as nodes
* Interaction modeled using Gaussian-weighted graphs

### 2. Feature Engineering

* Spatial density and irregularity metrics
* Local neighborhood analysis (k-NN)
* Combined anomaly scoring

### 3. Deep Learning Models

* **ResNet-18** → appearance features
* **ViT-MAE** → anomaly detection
* **ThreatNet (MLP)** → threat scoring

### 4. Escalation Prediction

* **MCTS** → simulates future threat trajectories
* **Bayesian Network** → causal inference
* **Fusion model** → combines both predictions

---

## Results

* Accuracy: **0.820**
* F1 Score: **0.804**
* AUC: **0.847**

Outperforms:

* Isolation Forest
* One-Class SVM
* Autoencoder
* CNN-based models
* MCTS-only approaches 

---

## Performance

* Real-time inference: **~76.5 ms per image (GPU)**
* Efficient pipeline using anomaly gating (reduces computation by ~68%) 

---

## Project Structure

crowd-threat-assessment/
│── data/                # Dataset and preprocessing
│── models/              # Deep learning models
│── mcts/                # Monte Carlo Tree Search
│── bayesian/            # Bayesian Network logic
│── pipeline/            # Full system pipeline
│── README.md

---

## Applications

* Smart surveillance systems
* Crowd safety in public events
* Disaster and emergency monitoring
* Smart city infrastructure
* AI-driven security systems

---

## Future Work

* Extension to video-based analysis
* Integration with reinforcement learning
* Graph Neural Networks for interaction modeling
* Multi-camera surveillance systems
* Real-time deployment on edge devices

---

## Disclaimer

This project is developed for academic and research purposes. It is intended to improve public safety systems and should not be misused.

---

## Authors

Thrishika and Team
B.Tech CSE (AI)
