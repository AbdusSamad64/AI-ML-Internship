# 📰 News Topic Classifier Using BERT

## 📌 Overview
This project fine-tunes a **BERT (bert-base-uncased)** model on the **AG News dataset** to classify news headlines into one of four categories:
- 🌍 World  
- 🏅 Sports  
- 💼 Business  
- 🔬 Sci/Tech  

The model is trained using the **Hugging Face Transformers** and **Datasets** libraries. After training, it is deployed via **Gradio** for live interaction, where users can input a news headline and instantly receive the predicted topic.

---

## 📊 Dataset
- **Name:** [AG News Dataset](https://huggingface.co/datasets/ag_news)  
- **Size:**  
  - Train: 120,000 samples  
  - Test: 7,600 samples  
- **Labels:**  
  - 0 → World  
  - 1 → Sports  
  - 2 → Business  
  - 3 → Sci/Tech  

Each sample contains:  
```json
{
  "text": "Wall St. Bears Claw Back Into the Black (Reuters) Reuters - Short-sellers...",
  "label": 2
}

## ⚙️ Methodology

- **Load Dataset** using `datasets.load_dataset("ag_news")`  
- **Tokenization** with `bert-base-uncased` tokenizer (truncation enabled)  
- **Model Architecture:**  
  - Pretrained `bert-base-uncased`  
  - Classification head with 4 output neurons (softmax)  
- **Fine-Tuning Parameters:**  
  - Learning Rate: `2e-5`  
  - Batch Size: `16`  
  - Epochs: `2`  
  - Optimizer: `AdamW`  
- **Evaluation Metrics:**  
  - Accuracy  
  - F1-score (weighted)  

---

## 📈 Results

Final evaluation after **2 epochs** on the AG News test set:

- **Loss:** `0.1848`  
- **Accuracy:** `94.97%`  
- **F1-score (weighted):** `94.98%`  
- **Runtime:** `39.37s`  
- **Samples/sec:** `193.0`  
- **Steps/sec:** `12.06`  

> These results show that BERT achieves **high performance (~95% accuracy & F1)** on news topic classification.

---

## 🚀 Deployment

The model is deployed with **Gradio** for live demo.  
Users can enter a news headline, and the app will return probabilities for each category.