# 😊🙁😐 Analysing Emotions in Cancer Narratives: A Corpus-Driven Approach

This repository supports the exploratory research project **"Analysing Emotions in Cancer Narratives: A Corpus-Driven Approach"**, which investigates how patients and carers express emotions in the context of cancer, especially across treatment stages. This work uses Reddit posts to build a real-world corpus of long-form cancer narratives and applies modern NLP techniques to extract emotional cues and sentiment classifications.

---

## 🎯 Motivation

Cancer affects not just physical health, but emotional and psychological wellbeing—for both patients and carers. While sentiment analysis has been extensively applied to short texts in social media and healthcare, **long, personal narratives** remain under-explored due to their complexity and ambiguity.

In this study, we:

- Analyze emotional expression in real patient/carer stories.
- Identify challenges in automatic sentiment classification.
- Compare results of **five state-of-the-art models** against human judgment.

---

## 📄 Key Highlights

- Focus on **long-form cancer narratives** from Reddit.
- Emotions are highly contextual, often ambiguous or conflicting.
- Linguistic difficulties are classified into:
  1. Clearly expressed emotions
  2. Conflicting/ambiguous emotional states
  3. Sentiment requiring context
  4. Implied sentiment/emotion without explicit markers

---

## 🧪 Sample Input

A Reddit post from a 15-year-old with lung cancer:

```text
i’m a 15 year old boy who was diagnosed with lung cancer 2 weeks ago and almost immediately started chemotherapy...
also i went for my chemo today and the cancer has reduced in size by 20% which is amazing...
````

---

## 🛠️ Emotion Analysis Pipeline

### 🔍 File: `transformer.py`

This Python script performs sentiment analysis using Hugging Face Transformers. It includes:

* Text preprocessing and emoji removal
* Sentence tokenization
* Sentiment classification using `distilbert/distilbert-base-uncased-finetuned-sst-2-english` via the `transformers` pipeline

### 🧾 Output Format

The script returns a dataframe with:

| Post Text                                           | Emotion Tag                            |
| --------------------------------------------------- | -------------------------------------- |
| "I was diagnosed with lung cancer two weeks ago..." | `{'label': 'NEGATIVE', 'score': 0.99}` |
| "The cancer has reduced in size by 20%..."          | `{'label': 'POSITIVE', 'score': 0.98}` |

---

## 📦 Installation

```bash
pip install transformers
pip install clean-text
pip install demoji emoji
```

Download NLTK data:

```python
import nltk
nltk.download('stopwords')
nltk.download('punkt_tab')
```

---

## 🚀 Running the Script

```bash
python transformer.py
```

Ensure your input narrative is embedded in the script or passed via function.

---

## 📚 Citation

If you use this work, please cite:

```bibtex
@inproceedings{lal2024analysing,
  title={Analysing emotions in cancer narratives: a corpus-driven approach},
  author={Lal, Daisy Monika and Rayson, Paul and Payne, Sheila A and Liu, Yufeng},
  booktitle={Proceedings of the First Workshop on Patient-Oriented Language Processing (CL4Health)@ LREC-COLING 2024},
  pages={73--83},
  year={2024}
}
```

---

## 🤝 Contributions

We welcome suggestions and contributions to improve model performance, emotion tagging schemes, or to expand the corpus with more patient/caregiver narratives.

---

## 📬 Contact

For questions or collaborations, reach out to \[Dr. Daisy Monika Lal] at \[[your.email@example.com](mailto:your.email@example.com)]

---

- A version that runs on Colab  
- Integration with other models (T5, RoBERTa, NRCLex)  
- Guidance on evaluating model-human agreement using your labeled data.
