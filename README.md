# Russian Grammar Error‑Correction Dataset (25 k Sentence Pairs)

<!--
  One‑stop, open‑source corpus for building and benchmarking **Russian grammatical error‑correction (GEC)** models.
  25 362 aligned sentence pairs (incorrect → correct) • CSV • ready for fine‑tuning transformers (mT5, T5, GPT‑style) or seq2seq architectures.  
  Keywords: Russian grammar dataset, grammatical error correction, GEC corpus, NLP dataset, Russian language learning, LoRA fine‑tuning, machine translation, open data.
-->

[![Dataset Size](https://img.shields.io/badge/sentences-25k-blue?style=flat-square)](./russian_gec_dataset.csv)
[![License](https://img.shields.io/badge/license-CC%20BY%204.0-green?style=flat-square)](#license)
[![Last Update](https://img.shields.io/badge/date-June_2025-lightgrey?style=flat-square)](#changelog)

---

## 🚀 Quick Look

| Metric                 | Value                                               |
| ---------------------- | --------------------------------------------------- |
| Sentence pairs         | **25 362**                                          |
| Avg. tokens / sentence | **≈ 12**                                            |
| File size              | \~5 MB (compressed)                                 |
| Format                 | **CSV** (UTF‑8)                                     |
| Columns                | `incorrect`, `correct`, `input_text`, `target_text` |

> Ideal for training, evaluation, and benchmarking of Russian **automatic grammar correction**, **translation post‑editing**, or **language‑learning assistants**.

---

## 📂 Repository Structure

```
.
├─ russian_gec_dataset.csv        # full corpus (25 k pairs)
├─ sample_preview.csv             # 100 random examples for a quick taste
├─ notebooks/
│   └─ EDA_and_Baselines.ipynb    # exploratory data analysis + starter models
└─ README.md                      # you are here ✓
```

---

## 💾 Loading the Dataset

```python
import pandas as pd

df = pd.read_csv("russian_gec_dataset.csv")
print(df[["incorrect", "correct"]].head())
```

Need train/val/test splits? Use:

```python
from sklearn.model_selection import train_test_split
train, test = train_test_split(df, test_size=0.1, random_state=42)
train.to_csv("train.csv", index=False)
```

---

## 🔍 Column Schema

| Column        | Type | Description                                                             |
| ------------- | ---- | ----------------------------------------------------------------------- |
| `incorrect`   | text | Original sentence containing one or more grammatical errors             |
| `correct`     | text | Human‑corrected version of the same sentence                            |
| `input_text`  | text | Prompt flavour used for seq2seq fine‑tuning (e.g. *"corregir ruso: …"*) |
| `target_text` | text | Target output identical to `correct`                                    |

`input_text` & `target_text` are optional; many users fine‑tune mT5/T5‑style models directly with these columns.

---

## 📊 Dataset Statistics

* **Total pairs:** 25 362
* **Unique tokens:** 78 k+
* **Error types covered:** noun‑adjective agreement, verb conjugation, prepositions, case selection, word order, punctuation.

---

## 🛠 Getting Started with mT5

```python
from transformers import MT5ForConditionalGeneration, MT5Tokenizer

tokenizer = MT5Tokenizer.from_pretrained("google/mt5-small")
model = MT5ForConditionalGeneration.from_pretrained("google/mt5-small")

# LoRA or full fine‑tune with your favourite trainer …
```

Check `notebooks/EDA_and_Baselines.ipynb` for a full walk‑through including LoRA setup with 🤗 PEFT.

---

## 🎯 Use‑Cases

* **Grammatical Error Correction (GEC)** systems for Russian
* Intelligent **writing assistants** (IDE/office plugins, chatbots)
* **Second‑language learning** tools and automated feedback
* **Translation post‑editing** models and research

---

## ⚠️ Limitations & Ethical Considerations

* Sentences are synthetic and semi‑crowdsourced; distribution may not perfectly mirror native corpora.
* Some topics are general‑purpose; offensive or sensitive content was filtered, but **manual review is advised** for production.
* Corrections follow contemporary standard Russian; regional variants may differ.

---

## 📜 License

This corpus is released under **Creative Commons Attribution 4.0 International (CC BY 4.0)**.
You may **share** and **adapt** the data for any purpose, even commercially, as long as you **credit the authors** and indicate changes.

```
@misc{russianGEC2025,
  author       = {Dreux X.},
  title        = {Russian Grammar Error‑Correction Dataset},
  year         = 2025,
  howpublished = {GitHub},
  url          = {https://github.com/dreuxx/russian‑gec‑dataset}
}
```

---

## 🤝 Contributing

Pull requests are welcome! If you spot an error or want to add new examples, please open an issue first.

1. Fork the repo
2. Create your feature branch (`git checkout -b feature/my‑improvement`)
3. Commit your changes (`git commit -am 'Add awesome feature'`)
4. Push to the branch (`git push origin feature/my‑improvement`)
5. Open a pull request

---

## 📅 Changelog

| Date (UTC) | Version | Notes                                 |
| ---------- | ------- | ------------------------------------- |
| 2025‑06‑04 | 1.0.0   | Initial public release (25 362 pairs) |

---

## 🙏 Acknowledgements

This project was inspired by the **JESC**, **Lang‑8**, and **FCE** corpora. Special thanks to the open‑source community for continuous support.

---

## 📫 Contact
profile
