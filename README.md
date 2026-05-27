# A Hybrid Transformer-Based Approach for Misinformation Detection in Low-Resource Language Contexts

**Master Thesis · Computer Sciences · Transport and Telecommunication Institute, Riga · 2026**  
**Author:** Vita Maurīte · 

This repository contains the source code for a two-stage misinformation detection framework for Latvian language. The framework combines article-level and sentence-level classification using four model architectures: SVM, LSTM, LVBERT, and the proposed Hybrid Semantic Signal Classifier (HSSC).

---

## Repository Structure

```
master-thesis-misinformation-lv/
│
├── README.md                         
│
├── 1-data-collection/
│   ├── 1.1-fact-checking/
│   │   ├── 01_collect_delfi_atmaskots.ipynb
│   │   ├── 01_collect_tvnet_faktomats.ipynb
│   │   └── 01_collect_recheck_rebaltica.ipynb
│   └── 1.2-reliable-news/
│       └── 01_collect_all_reliable.ipynb
│
├── 2-data-cleaning/
│   └── 02_cleaning_mastermerge.ipynb
│
├── 3-data-split-analysis/
│   └── 03_explanatory_analysis_for_signal.ipynb
│
├── 4-model-training-article-level/
│   ├── 4.1-SVM/
│   │   └── 04_SVM_CV.ipynb
│   ├── 4.2-LSTM/
│   │   └── 04_LSTM_CV.ipynb
│   ├── 4.3-LVBERT/
│   │   └── 04_LVBERT_CV.ipynb
│   └── 4.4-HSSC/
│       ├── 04_HSSC.ipynb
│       ├── 04_01_SS_for_HSSC.ipynb
│       └── 04_02_S_for_HSSC.ipynb
│
└── 5-model-training-sentence-level/
    ├── 05_Sentence_level+_claim.ipynb
    └── 06_HSSC_truevsfalse_claim_example_.ipynb
```

---

## Tools and Environment

| Tool | Purpose |
|------|---------|
| Google Colab | Model training and experiments |
| scikit-learn | SVM implementation |
| TensorFlow / Keras | LSTM implementation |
| HuggingFace Transformers | LVBERT fine-tuning |
| pandas, numpy | Data processing |

---

## Key Results

### Article-Level Classification

| Model | Accuracy | Precision | Recall | F1 | ROC-AUC |
|-------|----------|-----------|--------|----|---------|
| SVM | 0.9686 | 0.9796 | 0.9536 | **0.9664** | 0.9902 |
| LSTM | 0.8339 | 0.8731 | 0.7748 | 0.8211 | 0.9130 |
| LVBERT | 0.9544 | 0.9536 | 0.9536 | 0.9536 | **0.9913** |
| HSSC | 0.9511 | **0.9658** | 0.9338 | 0.9495 | 0.9790 |

<img width="575" height="201" alt="image" src="https://github.com/user-attachments/assets/c2dd90da-d61e-4c87-b1a2-cc6797d819bf" />

### Sentence-Level Classification (CLAIM F1)

| Model | Accuracy | Macro F1 | Weighted F1 | CLAIM F1 |
|-------|----------|----------|-------------|---------|
| SVM | 0.9196 | 0.7806 | 0.9148 | 0.7632 |
| LSTM | 0.7373 | 0.5777 | 0.7272 | 0.7376 |
| LVBERT | 0.8921 | **0.8006** | 0.8898 | **0.8136** |
| HSSC | 0.9175 | 0.6867 | **0.9226** | 0.7933 |

<img width="579" height="196" alt="image" src="https://github.com/user-attachments/assets/07b6093d-eba6-49af-be23-679e5dcd6628" />

### True vs False Claim Classification

| Model | Accuracy | F1 |
|-------|----------|----|
| SVM | 0.9286 | 0.9394 |
| LSTM | 0.5893 | 0.7160 |
| LVBERT | **0.9643** | **0.9706** |
| HSSC | **0.9643** | **0.9706** |

<img width="577" height="201" alt="image" src="https://github.com/user-attachments/assets/017c691f-7775-42ed-a6d7-398b9daf331b" />

---

## Note on Data

Raw and processed datasets are not included in this repository due to copyright restrictions under Latvian Copyright Law (*Autortiesību likums*, Section 21) and EU Directive 2019/790 on Text and Data Mining for scientific research. Data was collected from publicly accessible Latvian news and fact-checking sources (DELFI, LSM, LTV, TVNET, Delfi Atmaskots, TVNET Faktomats, Re:Check) and used solely for non-commercial research purposes.

---

## Publication and Dissemination

Presented at: The 49th Research and Academic Conference *"Research and Technology – Step into the Future"* (RaTSiF-2026), TSI, Riga. A Hybrid Transformer-Based Approach for Misinformation Detection in Low-Resource Language Contexts. *Research and Technology – Step into the Future Scientific & Research Journal of TTI*, Vol. 21, No. 1. ISSN 1691-2853 / ISSN 1691-2861. Transport and Telecommunication Institute, Riga, Latvia
