# 🥇 WiDS Datathon 2025 - 4th place solution (Data Raptors)

Welcome to the **Data Raptors**' top 4 winning solution for the **WiDS Datathon 2025**. This repository contains the full code used to achieve a **Private Leaderboard Score** of **0.81413** and a **Public Leaderboard Score** of **0.77506**, securing 4th place globally.

---

## 📊 Challenge Overview

The task was to predict two separate targets:
- **ADHD_Outcome**: ADHD diagnosis (1 = ADHD, 0 = Other/None)
- **Sex_F**: Sex of participant (1 = Female, 0 = Male)

The dataset included:
- **Functional MRI Connectome Matrices (19900 Features)**
- **Socio-demographic, emotional, and parenting metadata (60 Features)**

---

## 🚀 Key Features of Our Approach

### **1. Dimensionality Reduction with PCA**
- Reduced 19900 connectome features to a manageable size while retaining 90-95% variance.
- Per-fold PCA to avoid data leakage.
- Dynamically selected components based on variance threshold.

### **2. Ensemble Model (Voting Classifier)**
- Combined multiple strong base learners:
  - **LightGBM** (GPU, NVIDIA RTX 3090)
  - **XGBoost** (GPU, NVIDIA RTX 3090)
  - **CatBoost** (GPU, NVIDIA RTX 3090)
  - **Logistic Regression** (Balanced)

### **3. Threshold Tuning for Optimal F1 Score**
- Tuned the classification threshold for each fold to maximize F1 score.
- Used a per-fold approach to avoid bias and improve generalization.

### **4. Cross-Validation for Robustness**
- 5-Fold **StratifiedKFold** to ensure balanced class distributions.
- Separate training for **ADHD_Outcome** and **Sex_F** to optimize each target independently.

---

## 🚀 Hardware and Precision Note

- The final models were trained on an **NVIDIA RTX 3090** GPU.
- Results may **vary slightly** on different hardware (e.g., **P100**, **T4**) due to differences in **floating-point precision**.

---

## 📂 Repository Structure
WiDS-Datathon-2025-Top4-Solution/
├── README.md # This file
├── requirements.txt # Required packages
└── notebooks/
└── WiDS_Datathon2025__4th_place_solution.ipynb # Main training notebook


---

## 📝 Key Results

| Metric            | Public LB | Private LB |
|--------------------|-----------|------------|
| **Overall F1 Score** | 0.77506   | 0.81413    |

---

## ⚙️ Environment Setup

Clone the repo and install the required packages:

```bash
git clone https://github.com/yourusername/WiDS-Datathon-2025-4th-place-solution.git
cd WiDS-Datathon-2025-4th-place-solution
pip install -r requirements.txt

📋 Key Scripts and Notebooks
WiDS_Datathon2025__4th_place_solution.ipynb - Full training notebook with PCA, threshold tuning, and ensemble training.

❌ What Did Not Work
Using per-model weights for ensembling.

Overly complex stacking approaches.

Aggressive data augmentation and feature engineering without proper CV testing.


📫 Contact
For any questions, feel free to reach out via GitHub issues or direct messages.

🔗 Links
Kaggle Forum Post: WiDS Datathon 2025 4th Place Solution

Competition Page: WiDS Datathon 2025

⭐ Acknowledgments
Special thanks to the WiDS community and fellow competitors for valuable insights and shared knowledge.
