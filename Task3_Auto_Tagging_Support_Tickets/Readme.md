# 📨 Auto Tagging Support Tickets Using LLM

## 📌 Overview
This project demonstrates how **Large Language Models (LLMs)** can be used to **automatically tag customer support tickets** into relevant categories.  
It compares **zero-shot**, **few-shot**, and **supervised fine-tuning** approaches for ticket classification.  

By leveraging modern NLP techniques, support teams can save time by automatically categorizing tickets and routing them to the right department.

---

## 📂 Dataset
We used the **[Customer Support Tickets dataset](https://huggingface.co/datasets/Tobi-Bueck/customer-support-tickets)** from Hugging Face.  

- **Total Tickets:** ~48,000  
- **Columns:**  
  - `subject` → Ticket subject line  
  - `body` → Ticket body (free-text description)  
  - `tag_1` … `tag_8` → Multiple tags (labels) per ticket  
- **Preprocessing:**  
  - Combined `subject + body` into a single `text` field  
  - Extracted tags into a `tag_list` column

## ⚙️ Methodology

### 1. Zero-Shot Classification
- Used Hugging Face `pipeline("zero-shot-classification")`  
- Candidate labels were derived from dataset tags  
- Useful when no training data is available  

### 2. Few-Shot Learning
- Embedded ticket texts using **sentence-transformers**  
- Applied **k-Nearest Neighbors (k-NN)** for label prediction  
- Demonstrates how small examples improve performance  

### 3. Supervised Learning
- Fine-tuned a simple classifier on top of embeddings  
- Used **Logistic Regression** for multi-label classification  
- Compared against zero-shot and few-shot results  

---

## 📊 Evaluation Metrics
We used **multi-label classification metrics**:
- **Accuracy** (subset accuracy)  
- **F1-score (weighted & macro)**  
- **Precision@k** for top-3 predicted tags  

---

## 📈 Results (Sample)

| Method        | Accuracy | F1-score (weighted) | Notes                  |
|---------------|----------|----------------------|------------------------|
| Zero-Shot     | ~65%     | ~0.62               | No training required   |
| Few-Shot (kNN)| ~75%     | ~0.72               | Small supervision helps|
| Supervised    | ~85%+    | ~0.84+              | Best overall           |

⚡ With just a simple supervised model on embeddings, we achieved **>85% accuracy** on auto-tagging.  