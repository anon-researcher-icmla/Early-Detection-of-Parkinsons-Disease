# 🧠 Early Detection of Parkinson's Disease using Dual-Modal Machine Learning

This repository accompanies the research paper **"Advancing Early Detection of Parkinson’s Disease Through Dual-Modal Machine Learning on Speech and Gait Data"**. It explores the potential of **non-invasive, interpretable AI models** for detecting early signs of Parkinson's Disease (PD) using **speech** and **gait** data.

## 🧩 Project Overview

Parkinson’s Disease is often diagnosed too late — after substantial neurological damage has occurred. This project presents a **dual-modal machine learning framework** that independently analyzes **vocal recordings** and **gait signals** to detect PD at an early stage. Our models leverage classical ML, deep learning (LSTM), and SHAP-based explainability to deliver **transparent**, **accurate**, and **clinically aligned** predictions.

## 📚 Datasets Used

### 1. **Speech Dataset**  
- Source: [UCI Parkinson’s Dataset](https://archive.ics.uci.edu/dataset/174/parkinsons)  
- 195 recordings from 31 individuals  
- 22 acoustic features: jitter, shimmer, MFCCs, HNR, etc.

### 2. **Gait Dataset**  
- Source: [WearGait-PD on Synapse](https://www.synapse.org/Synapse:syn52540892/wiki/)  
- 271 subjects with 196 gait features each  
- Features from accelerometer and gyroscope readings: stride length, postural sway, swing time, etc.

## ⚙️ Methodology

### 🧼 Data Preprocessing
- Removed irrelevant metadata
- Z-score normalization for scale-sensitive models
- Handled missing data via median imputation
- Addressed class imbalance with **SMOTE**

### 🔍 Feature Engineering
- LASSO + Recursive Feature Elimination (RFE)
- Pearson correlation heatmaps & VIF analysis to remove multicollinearity

### 🤖 Models Used
| Type              | Models                                        |
|-------------------|-----------------------------------------------|
| Classical ML       | Logistic Regression, SVM, Random Forest, XGBoost |
| Deep Learning      | Stacked LSTM (2 layers)                        |

- Hyperparameter tuning via grid search (5-fold CV)
- Evaluation metrics: Accuracy, Precision, Recall, F1-Score
- Model interpretability: **SHAP (SHapley Additive Explanations)**

## 📊 Key Results

| Modality | Model         | Accuracy |
|----------|---------------|----------|
| Gait     | LSTM          | **96%**  |
| Speech   | LSTM          | **97%**  |
| Gait     | Gradient Boosting | 93% |
| Speech   | Logistic Regression / SVM | 92% |

- **SHAP** analysis highlighted physiologically valid predictors such as:
  - Gait: Stride width, Step ratio, Swing time
  - Speech: Pitch Period Entropy (PPE), shimmer, jitter

## 🩺 Interpretability and Clinical Relevance

By integrating SHAP, our framework offers:
- **Global and local interpretability**
- **Visual explanations** for each prediction (e.g., force plots)
- Alignment with known PD indicators, building clinician trust

## ⚖️ Ethical Considerations

- Emphasized transparency in AI decision-making
- Models avoid black-box risks through feature attribution
- Future iterations will incorporate fairness audits and privacy compliance (e.g., HIPAA, GDPR)

## 🔭 Future Work

- Validate on larger and more diverse populations
- Extend to multimodal fusion (e.g., combining speech + gait)
- Deploy lightweight versions for real-time monitoring via mobile apps
- Explore transfer learning and longitudinal modeling for disease progression

## 📎 Supplementary Materials

All code, model training scripts, and SHAP visualizations are available in this repository.


👉 **[GitHub Repository Link](https://github.com/anon-researcher-icmla/Early-Detection-of-Parkinsons-Disease
)**  





