# Evo2 Variant Effect Predictor 🧬

🎥 **[Watch Demo Video](https://youtu.be/skZDbXulNdg)**  



An AI-powered web application to predict the pathogenicity of genetic variants using the state-of-the-art **Evo2** protein language model.

This full-stack project provides a user-friendly interface to assess whether single nucleotide variants (SNVs) in human DNA are likely benign (harmless) or pathogenic (disease-causing). These predictions are crucial for research in fields like oncology, where understanding the impact of mutations is key.

### 🧬 Variant Effect Prediction using Evo2 (Research Paper Implementation)
- Implemented the **Evo2 LLM research paper** (Arc Institute) to predict the pathogenicity of single nucleotide variants (SNVs) in DNA sequences.
- Built a full-stack application with a **FastAPI Python backend on H100 GPUs (via Modal)** and a **modern T3-stack frontend** using Next.js, TypeScript, Tailwind CSS, and Shadcn UI.
- Integrated **UCSC Genome Browser API** and **ClinVar dataset** to browse genes like BRCA1, fetch sequences, input mutations, and compare Evo2 predictions with clinical classifications.
- Enabled real-time mutation testing and AI-based classification (pathogenic/benign) with prediction confidence, all accessible via a beautiful and responsive UI.

---




## 🧾 Overview

Imagine DNA as a very long instruction manual written with the letters A, T, G, and C. A single typo (a mutation) in a critical sentence can lead to serious problems, while a typo in a less important section might have no effect at all. This tool helps scientists and researchers quickly distinguish between the typos that matter and those that don't.

We use **Evo2**, a cutting-edge protein language model from the Arc Institute, to perform variant effect prediction. The application is designed to be accessible even without prior biology knowledge, guiding users through gene selection, mutation input, and result interpretation.

All computationally intensive tasks are offloaded to a powerful **NVIDIA H100 GPU server via Modal**, ensuring that predictions are fast and the application remains free to use.

## 🌟 Features

### 🔬 Prediction Core
-   **✅ Predict Pathogenicity**: Input custom single nucleotide variants (SNVs) and receive an instant prediction from Evo2.
-   **💡 Confidence Score**: See how confident the Evo2 model is in its benign/pathogenic classification.
-   **⚖️ ClinVar Comparison**: Validate or challenge predictions by comparing Evo2's results with the official classifications from the NCBI ClinVar database.

### 🧬 Genomics Toolkit
-   **🌍 Genome Assembly Selector**: Easily switch between human genome reference versions (e.g., `hg38`).
-   **🔍 Gene Search & Browse**: Find genes of interest (like `BRCA1`, `TP53`) with a powerful search or by browsing chromosomes.
-   **📖 Reference Sequence Viewer**: View the DNA sequence of a selected gene, fetched directly from the UCSC Genome Browser API.
-   **🧪 Explore Known Variants**: Load existing SNVs from ClinVar to test and analyze them with Evo2.

## 💻 Tech Stack & Architecture

This project is built with a modern, scalable, and type-safe stack.

| Component              | Technology                                                                                           |
| ---------------------- | ---------------------------------------------------------------------------------------------------- |
| **Frontend**           | [Next.js](https://nextjs.org/), [React](https://reactjs.org/), [TypeScript](https://www.typescriptlang.org/), [Tailwind CSS](https://tailwindcss.com/), [Shadcn UI](https://ui.shadcn.com/) |
| **Backend**            | [Python](https://www.python.org/), [FastAPI](https://fastapi.tiangolo.com/)                           |
                                  |
| **Infrastructure**     | [Modal](https://modal.com/) (for serverless H100 GPU inference)                                      |
| **APIs**               | [UCSC Genome Browser API](https://genome.ucsc.edu/goldenPath/help/api.html), [NCBI E-utilities](https://www.ncbi.nlm.nih.gov/books/NBK25501/) (for ClinVar) |

### System Architecture
The application follows a decoupled architecture:
1.  **UI (Next.js)**: The user interacts with the responsive frontend to select a gene and input a variant.
2.  **API Backend (FastAPI)**: The Next.js app sends a request to the FastAPI backend.
3.  **GPU Inference (Modal)**: The FastAPI backend offloads the heavy prediction task to a serverless function on Modal, which runs the Evo2 model on an H100 GPU.
4.  **Data Fetching**: The backend also communicates with external APIs (UCSC, NCBI) to fetch reference sequences and ClinVar data.
5.  **Response**: The result is passed back through the chain and displayed to the user in real-time.

🔗 Evo2 Model GitHub

📄 Research Paper (bioRxiv)

🧬 NCBI ClinVar

🧪 UCSC Genome Browser



- [Paper](https://www.biorxiv.org/content/10.1101/2025.02.18.638918v1)
- [GitHub Repository](https://github.com/ArcInstitute/evo2)

## Setup

Follow these steps to install and set up the project.

### Clone the Repository

```bash
git clone --recurse-submodules https://github.com/Andreaswt/variant-analysis-evo2.git
```

### Install Python

Download and install Python if not already installed. Use the link below for guidance on installation:
[Python Download](https://www.python.org/downloads/)

Create a virtual environment for each folder, except elevenlabs-clone-frontend, with **Python 3.10**.

### Backend

Navigate to backend folder:

```bash
cd evo2-backend
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Modal setup:

```bash
modal setup
```

Run on Modal:

```bash
modal run main.py
```

Deploy backend:

```bash
modal deploy main.py
```

### Frontend

Install dependencies:

```bash
cd evo2-frontend
npm i
```

Run:

```bash
npm run dev
```
