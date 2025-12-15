# OCR-Robust Information Retrieval using Character 3-Grams

## Project Overview
This project implements an **Information Retrieval (IR) system robust to OCR errors**.  
We evaluate how **character-level q-grams (q = 3)** combined with **TF-IDF and cosine similarity**
handle noisy text produced by OCR systems.

The project was implemented as part of an **Information Retrieval course assignment**.

---

## Dataset
- **30 textual documents**
- Single coherent topic: **Europe**
  - European capital cities
  - Central markets
  - Medieval old towns
- Documents are short, descriptive paragraphs similar to travel or encyclopedia text.

---

## OCR Error Simulation
To simulate OCR noise, character-level errors were injected into:
- ~45% of the documents
- All queries (with at least one forced error per query)

### Error types:
- **Substitution** (e.g. `a → @`, `o → 0`, `t → 7`)
- **Deletion** (random character removal)
- **Insertion** (character duplication)

Examples:
- `european capital city` → `eur0pen c@pi7al city`
- `medieval old town` → `med1eval old town`

---

## Queries
Three queries were used, each consisting of **exactly 3 words**:
1. `european capital city`
2. `central market square`
3. `medieval old town`

Each query was evaluated in:
- **Clean form**
- **OCR-noisy form**

---

## Indexing Method
- **Character 3-grams (q = 3)**
- Implemented using `TfidfVectorizer`
- Character n-grams were chosen to improve robustness to OCR noise.

---

## Similarity Measure
- **Cosine similarity**
- Each query vector is compared against all document vectors.
- Documents are ranked by similarity.
- **Top-k results (k = 6)** are retrieved and analyzed.

---

## Results
The notebook presents:
- Tables of top-6 retrieved documents per query
- Bar charts comparing similarity scores:
  - Clean vs OCR-noisy queries
- A summary plot showing the **mean cosine similarity** across queries

### Observations:
- OCR noise consistently reduces similarity scores
- Character 3-grams remain effective at retrieving relevant documents
- Rankings remain largely stable despite noise

---

## Technologies Used
- Python
- scikit-learn
- pandas
- matplotlib
- Google Colab

---

## How to Run
1. Open the provided Google Colab notebook
2. Run all cells from top to bottom
3. View tables and plots generated for each query

No external datasets are required.

---

## Conclusion
This project demonstrates that **character-based q-gram indexing** combined with **cosine similarity**
is an effective strategy for **OCR-robust Information Retrieval**, maintaining reasonable performance
even under significant textual noise.

---

## Author
Yousef Shihade
Information Retrieval Course  
University of haifa
