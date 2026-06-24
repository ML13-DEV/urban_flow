# 🚦 Urban Flow — Traffic Fine Intelligence Pipeline

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=flat&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=flat&logo=jupyter&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-Image%20Processing-5C3EE8?style=flat&logo=opencv&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-ORM-D71F00?style=flat)
![DVC](https://img.shields.io/badge/DVC-Data%20Versioning-13ADC7?style=flat&logo=dvc&logoColor=white)
![ChromaDB](https://img.shields.io/badge/ChromaDB-Vector%20Search-6A1B9A?style=flat)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Wrangling-150458?style=flat&logo=pandas&logoColor=white)

## 📌 Overview

Urban Flow turns messy, legacy speeding-fine records from urban radars in Vaalserberg, Belgium into a queryable, evidence-linked system. It cleans the raw data, uses computer vision to match each fine with its license-plate photo, and migrates the result into a relational + vector database architecture that supports both structured queries and image-similarity search.

## 🔑 Key Features

The project was built incrementally across three sprints, each one layering new capability on top of the last:

### Sprint 1 — Data Cleaning & EDA
- Normalized inconsistent date/time formats from the legacy system
- Cleaned malformed location strings and removed invalid/empty records
- Outlier detection and removal
- Engineered the `exceso_velocidad` (speed-over-limit) feature
- Custom `FineAnalyzer` class for reusable analysis methods
- Exploratory visualizations (plates, hours, months, midnight-anomaly checks)

### Sprint 2 — Computer Vision Matching
- Classified raw images by type (plate crops vs. full-scene photos)
- Preprocessing pipeline: grayscale conversion → Gaussian blur → Canny edge detection
- License-plate extraction and automated linking between images and fine records
- Match-quality scoring (`ratio` column) to flag fines with valid vs. missing visual evidence

### Sprint 3 — Relational + Vector Architecture
- Designed a domain model: `Vehiculo`, `Radar`, `Evidencia`, `Multa`, with proper entity relationships
- Implemented the model as a **SQLAlchemy ORM** layer over a **SQLite** database (`transito.db`)
- Migrated the Sprint 1–2 processed dataset into the relational schema
- Analytical queries: top offending plates, fines without evidence, most active radars, repeat offenders, evidence-coverage rate
- Built a **vector database with ChromaDB**, embedding plate images with **OpenCLIP (ViT-B/32)**, enabling semantic image-similarity search for a given plate photo
- Versioned all binary artifacts (raw images, processed datasets, the SQLite DB, and the vector store) with **DVC**

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| Language / Analysis | Python, Jupyter Notebook, Pandas, NumPy |
| Computer Vision | OpenCV (grayscale, blur, Canny edge detection, plate extraction) |
| Relational Layer | SQLAlchemy ORM, SQLite |
| Vector Search | ChromaDB, OpenCLIP (ViT-B/32) embeddings |
| Data Versioning | DVC |

## ⚙️ How to Run / Installation

> 📍 The full pipeline (Sprints 1–3) lives on the `Sprint_3` branch.

```bash
# 1. Clone and check out the branch with the complete pipeline
git clone https://github.com/ML13-DEV/urban_flow.git
cd urban_flow
git checkout Sprint_3

# 2. Set up the environment
python -m venv venv
source venv/bin/activate      # On Windows: venv\Scripts\activate
pip install pandas numpy opencv-python sqlalchemy dvc chromadb open-clip-torch jupyter

# 3. Pull the DVC-tracked data (raw/processed images, transito.db, chroma_db)
dvc pull

# 4. Run the notebook
jupyter notebook Urban_Flow_Sprint3.ipynb
```

## 📂 Repository Structure

```
urban_flow/
├── data/
│   ├── raw/             # Original CSV + raw plate images
│   ├── interim/          # Cleaned data, classified/preprocessed images
│   └── processed/        # Final dataset with image-fine links
├── .dvc/                 # DVC config
├── chroma_db.dvc         # DVC pointer for the vector store
├── transito.db.dvc       # DVC pointer for the SQLite database
├── Urban_Flow_Sprint3.ipynb
├── CHANGELOG.md
└── README.md
```

## 👥 Team

Group project for a Data Science coursework assignment:
- Castillo Nelson
- Cuello Agustín
- Lombardi Manuel
- Rojas Agustín

## 📈 Notes

Each sprint was developed on its own branch (`Sprint_1`, `Sprint_2`, `Sprint_3`), with `Sprint_3` integrating all prior work. The progression mirrors a realistic data-engineering maturity path: from ad-hoc cleaning, to CV-based data enrichment, to a versioned, queryable relational + vector architecture.
