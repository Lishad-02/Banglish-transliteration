# Byte-Level Transliteration of Noisy Banglish to Bengali  
### Using ByT5 with Downstream Sentiment Validation

<p align="center">
  <b>A lightweight, robust NLP pipeline for low-resource Banglish text processing</b>
</p>

---

## 📌 Overview

Banglish (Bengali written in the Roman alphabet) is widely used in social media and informal communication in Bangladesh. However, Banglish has no fixed spelling rules, which makes it very difficult for traditional Natural Language Processing (NLP) systems to handle.

This project presents a **byte-level transliteration framework** using the **ByT5 transformer model** to convert noisy Banglish text into standard Bengali. To validate the quality of transliteration, a **cross-lingual sentiment analysis pipeline** is introduced.

The system is designed specifically for **low-resource and noisy text environments**.

---

## ✨ Key Features

- ✅ Byte-level transliteration (no vocabulary limitation)
- ✅ Handles highly inconsistent Banglish spellings
- ✅ High transliteration accuracy with low error rate
- ✅ Cross-lingual sentiment validation pipeline
- ✅ Suitable for low-resource languages
- ✅ Works well on real-world noisy text

---

## System Architecture

Banglish Text --> ByT5 Transliteration --> Standard Bengali --> English Translation --> Emotion / Sentiment Classification



---

## Dataset

- **Bengali–Banglish 80K Dataset**
- Approximately 80,000 sentence pairs
- Cleaned and preprocessed
- Data split:
  - 90% Training
  - 10% Testing

---

## Model Details

### 🔹 Primary Model: ByT5 (Byte-Level Transformer)

- Operates directly on UTF-8 bytes
- Eliminates the Unknown Token (UNK) problem
- Ideal for noisy and code-mixed Banglish text
- Fine-tuned using:
  - Learning rate: `2e-4`
  - Batch size: `8`
  - Epochs: `4`
  - Mixed precision (FP16)

---

## 📊 Evaluation Metrics

| Metric | Description |
|------|------------|
| BLEU Score | Measures transliteration fluency |
| CER (Character Error Rate) | Measures spelling accuracy |
| Sentiment Confidence | Validates semantic preservation |

---

## Results

### 🔹 Transliteration Performance

| Metric | Value |
|------|------|
| BLEU Score | **83.32** |
| Character Error Rate (CER) | **3.5%** |
| Validation Loss | 0.022 |

✔ High-quality Bengali output  
✔ Very low spelling error  
✔ Stable training behavior  

---

### 🔹 Sentiment Pipeline Validation

| Banglish Input | Final Emotion | Confidence |
|---------------|--------------|------------|
| amar khub kharap lagche | Sadness | 0.92 |
| tumi keno amake voy paccho? | Fear | 0.90 |
| tui eto boka keno? | Anger | 0.82 |

The pipeline produces more stable and confident sentiment predictions compared to direct Banglish sentiment analysis.

---

## Limitations

- Some semantic ambiguity remains for slang or context-dependent words
- Errors may propagate across pipeline stages
- Dataset is limited to supervised sentence pairs

---

## Future Work

- Context-aware semantic disambiguation
- End-to-end multilingual emotion classification
- Expansion using real-world social media data
- Extension to other low-resource code-mixed languages

