# Evo2 Variant Effect Predictor 🧬

demo video coming soon .

An AI-powered web application to predict the pathogenicity of genetic variants using the state-of-the-art **Evo2** protein language model.

This full-stack project provides a user-friendly interface to assess whether single nucleotide variants (SNVs) in human DNA are likely benign (harmless) or pathogenic (disease-causing). These predictions are crucial for research in fields like oncology, where understanding the impact of mutations is key.

**[Live Demo Link (Coming Soon)]**

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
| **AI/ML Model**        | [Evo2 Protein Language Model](https://github.com/arcinstitute/evo)                                   |
| **Infrastructure**     | [Modal](https://modal.com/) (for serverless H100 GPU inference)                                      |
| **APIs**               | [UCSC Genome Browser API](https://genome.ucsc.edu/goldenPath/help/api.html), [NCBI E-utilities](https://www.ncbi.nlm.nih.gov/books/NBK25501/) (for ClinVar) |

### System Architecture
The application follows a decoupled architecture:
1.  **UI (Next.js)**: The user interacts with the responsive frontend to select a gene and input a variant.
2.  **API Backend (FastAPI)**: The Next.js app sends a request to the FastAPI backend.
3.  **GPU Inference (Modal)**: The FastAPI backend offloads the heavy prediction task to a serverless function on Modal, which runs the Evo2 model on an H100 GPU.
4.  **Data Fetching**: The backend also communicates with external APIs (UCSC, NCBI) to fetch reference sequences and ClinVar data.
5.  **Response**: The result is passed back through the chain and displayed to the user in real-time.

## 🚀 Getting Started

Follow these steps to set up and run the project on your local machine.

### Prerequisites
-   [Git](https://git-scm.com/)
-   [Python 3.10](https://www.python.org/downloads/)
-   [Node.js and npm](https://nodejs.org/en/download/)
-   A [Modal](https://modal.com/) account (for backend deployment).

### 1. Clone the Repository
Clone the repository and its submodules:
```bash
git clone --recurse-submodules https://github.com/Andreaswt/variant-analysis-evo2.git
cd variant-analysis-evo2