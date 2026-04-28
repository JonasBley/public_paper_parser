# 📚 STEM & Quantum Education Literature Archive

Welcome to the **STEM & Physics Education Literature Archive**. This repository is an automated, continuously updated collection of academic literature focusing on physics education, quantum curriculum innovation, and cognitive methodologies in STEM.

## ⚙️ How It Works

This repository serves as the public-facing data archive for an automated pipeline. Every week, a private self-hosted runner executes a Python ingestion script that:
1. **Scrapes** the latest preprints from arXiv (`physics.ed-ph`, `quant-ph`) and published articles from Crossref (covering top-tier journals like *American Journal of Physics*, *PRPER*, *Science Education*, etc.).
2. **Filters & Categorizes** the literature using a local Large Language Model (Gemma 4) to evaluate the abstract against strict pedagogical criteria.
3. **Ranks** the papers using dense vector embeddings (Cosine Similarity) against a predefined research profile focusing on educational frameworks, mental models, novel educational techniques and modern quantum physics.
4. **Pushes** the finalized database and readable digests to this public repository.

*(Note: The scraping code, LLM inference engine, and API logic remain in a separate, private repository to ensure infrastructure security).*

## 📂 Repository Contents

This repository is updated automatically every Monday. You will find two types of files here:

### 1. `literature_archive.db` (The Complete Database)
A permanent, continuously expanding SQLite database containing every paper ever processed by the pipeline. 
* **To view it:** Download the `.db` file and open it using a free tool like [DB Browser for SQLite](https://sqlitebrowser.org/).
* **Data points:** Includes Titles, Authors, Abstracts, URLs, Publication Dates, LLM-generated Tags, and semantic Relevance Scores.

### 2. `digest_*.md` (The Weekly Summaries)
Read-friendly Markdown files containing the latest literature from the past 7 days, sorted by relevance score.
* **`digest_education_YYYY-MM-DD.md`**: Papers strictly focused on education, teaching, curriculum, or pedagogical research.
* **`digest_technical_YYYY-MM-DD.md`**: Purely technical/scientific physics papers without an explicit educational focus.

## 🏷️ Thematic Criteria
The LLM evaluates and tags papers based on the following specific criteria:
* **Cognitive Frameworks:** Empirical STEM education focusing on cognitive models (e.g., Fidelity of Gestalt, Functional Fidelity).
* **Multimedia & Representations:** Theories of multimedia learning or multiple representations.
* **STEM Educational Research Methodology:** Eye-tracking, spatial reasoning, cognitive load measurements.
* **Quantum/Modern Curriculum:** Curriculum innovation in modern physics, quantum mechanics, optics, and computing.
* **Workforce:** Quantum workforce development and competences.
* **Emerging Tech:** Application of AI, GenAI, or AR/VR in physics education.

---
*This repository is maintained by an automated GitHub Actions workflow.*
