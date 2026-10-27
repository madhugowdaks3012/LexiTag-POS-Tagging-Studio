# LexiTag Studio — Document POS Tagging Web App

**LexiTag Studio** is a visually polished Natural Language Processing (NLP) web application that extracts text from documents, performs Part-of-Speech (POS) tagging, and presents the results through interactive charts and token-level tables.

## Features

- Upload **PDF, DOCX, TXT, and Markdown** documents, or paste text directly.
- Extract text and analyse it using the spaCy English NLP pipeline.
- Display token, lemma, universal POS, fine-grained tag, tag meaning, dependency relation, and head word.
- Interactive POS distribution and fine-tag visualisations.
- Search tokens/lemmas and filter by POS category.
- Sentence segmentation and readable POS-tagged text preview.
- Download annotations as CSV, tagged text as TXT, or extracted text as TXT.
- Dark, dashboard-style interface suitable for a project demonstration.

## Tech stack

| Component | Technology |
|---|---|
| User interface | Streamlit |
| NLP / POS tagging | spaCy (`en_core_web_sm`) |
| Data tables | pandas |
| Visualisations | Plotly |
| Word documents | python-docx |
| PDF extraction | pypdf |

## Project structure

```text
pos_tagging_studio/
├── app.py
├── requirements.txt
├── README.md
├── .gitignore
├── LICENSE
├── .streamlit/
│   └── config.toml
└── sample_documents/
    └── sample_text.txt
```

## Run locally

### 1. Install Python
Use Python 3.10 or 3.11 for a smooth setup.

### 2. Create and activate a virtual environment

**Windows (PowerShell):**
```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

**macOS / Linux:**
```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies
```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Start the app
```bash
streamlit run app.py
```

Streamlit will print a local URL, usually `http://localhost:8501`.

## Deploy free with Streamlit Community Cloud

1. Push this project to a GitHub repository.
2. Sign in to Streamlit Community Cloud.
3. Create a new app and select your repository.
4. Set the main file path to `app.py`.
5. Deploy. The dependencies in `requirements.txt` install the NLP model.

Deployment dependency installation can take a few minutes because the English language model is included as a dependency.

## How it works

1. **Input:** The user uploads a document or pastes text.
2. **Extraction:** The app extracts text from PDF, DOCX, TXT, or Markdown.
3. **NLP processing:** spaCy tokenises the text and assigns POS tags, lemmas, and dependency labels.
4. **Analytics:** pandas aggregates counts and Plotly visualises the POS distribution.
5. **Exploration and export:** The user filters token records and downloads the results.

## Important terms

- **Token:** A word, number, or punctuation unit identified by the tokenizer.
- **Lemma:** The base/dictionary form of a word (e.g. `running` → `run`).
- **POS tag:** A grammatical category such as `NOUN`, `VERB`, `ADJ`, or `ADV`.
- **Fine-grained tag:** A more detailed tag such as `NN` (singular noun) or `VBD` (past-tense verb).
- **Dependency:** The grammatical relationship between a token and another token.
- **Stopword:** A common word such as “the” or “is” that may be filtered in some analyses.

## Limitations

- The included pipeline is designed for **English** text.
- Scanned PDFs are image-based and need OCR; OCR is not included.
- POS tags are model predictions and can be incorrect for ambiguous words or unusual text.
- This is an educational NLP tool, not a clinical, legal, or production linguistic system.
- Avoid uploading confidential or sensitive documents to a public cloud deployment.

## Suggested future improvements

- Add OCR support for scanned PDFs.
- Add multilingual models.
- Add named-entity recognition and noun-phrase extraction.
- Add sentence-level export and comparison between documents.
- Add a model evaluation page with a labelled test set and accuracy metrics.

## Author

**Madhu Gowda K S**  
B.Tech — Artificial Intelligence & Machine Learning  
Srinivas University

## Academic integrity note

This repository is intended as a learning and demonstration project. Understand the pipeline, test it with your own examples, and be ready to explain the implementation during evaluation.
