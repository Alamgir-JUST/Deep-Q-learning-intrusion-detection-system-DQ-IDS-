# 🚀 DQ-IDS: Deep Q-Learning Intrusion Detection System

This repository contains a clean, reproducible **PyTorch** implementation of the **DQ-IDS** method — an Intrusion Detection System that uses **Deep Q-Learning (DQN)** to classify IoT network traffic as **Benign** or **Attack**.

It is based on the paper:

> **DQ-IDS: Deep Q-Learning Intrusion Detection System for IoT Networks**  
> *(See `DQ-IDS.pdf` in this repository)*

---

## 🧠 Method Overview

Traditional Intrusion Detection Systems (IDS) use static machine learning classifiers (e.g., Random Forest, XGBoost).  
**DQ-IDS** reframes intrusion detection as a **reinforcement learning** problem:

- Each network flow/sample is treated as a **one-step episode**.
- The **agent (DQN)** chooses an **action**: `{Benign, Attack}`.
- It receives **+1 reward if correct, −1 if wrong**.
- Training uses:
  - **Experience Replay** (to stabilize learning)
  - **Target Network** updates
  - **Epsilon-Greedy exploration** with decay

This allows the IDS to **adapt dynamically**, avoid overfitting to fixed data distributions, and maintain strong performance on new traffic.

---

## 📊 Reported Results (from paper)

| Metric      | CICIoT2023 Dataset |
|-------------|--------------------|
| Accuracy    | ~97.2%             |
| Precision   | ~98%               |
| Recall      | ~98%               |
| F1-score    | ~98.5%             |
| ROC-AUC     | ~98%+              |

> *Your results may vary slightly depending on preprocessing and random seeds.*

---

🧑‍💻 Citation

If you use this code, please cite the original DQ-IDS paper and this repository:

@article{Hossain2025DQIDS,
  author    = {Md. Alamgir Hossain},
  title     = {Deep Q-learning intrusion detection system (DQ-IDS): A novel reinforcement learning approach for adaptive and self-learning cybersecurity},
  journal   = {ICT Express},
  year      = {2025},
  issn      = {2405-9595},
  doi       = {10.1016/j.icte.2025.05.007},
  url       = {https://www.sciencedirect.com/science/article/pii/S2405959525000694}
}

