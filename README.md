

🧬 Variant Effect Prediction Web App
🧾 Overview
This project is a full-stack AI-powered web application that predicts how harmful (pathogenic) a specific genetic mutation (specifically single nucleotide variants or SNVs) might be. These predictions help assess whether small changes in DNA could potentially lead to diseases like cancer.

We use Evo2, a cutting-edge protein language model built by the Arc Institute, to perform variant effect prediction — i.e., determining whether a mutation in a gene is likely benign (safe) or pathogenic (harmful).

You don’t need any prior biology knowledge — the app guides users through selecting a human genome assembly (like hg38), browsing or searching for genes (like BRCA1), and exploring that gene’s DNA sequence. Users can input custom mutations or choose from known variants and see:

Evo2's prediction (Benign or Pathogenic)

ClinVar’s official classification (if available)

Confidence scores from the model

Why this matters
Imagine DNA as a very long text written using the letters A, T, G, and C. If even one letter changes at a critical place (mutation), it can cause major issues — or no problem at all. This tool helps figure out which mutations matter and which ones don’t.

⚠️ All heavy processing is handled on a GPU server (NVIDIA H100) using Modal to keep things fast and free.
📦 The backend is written in Python using FastAPI, and the frontend is built using Next.js + Tailwind CSS + Shadcn UI.

🌟 Features
🔬 Prediction
✅ Predict Pathogenicity: Upload or input single nucleotide variants (SNVs) and get Evo2’s prediction.

💡 Prediction Confidence Score: See how confident Evo2 is in its result.

⚖️ ClinVar Comparison: Compare Evo2’s result with known ClinVar labels to validate or challenge predictions.

🧬 Gene & Genome Tools
🌍 Genome Assembly Selector: Switch between genome versions (e.g., hg38).

🔍 Gene Search & Browse: Quickly search for or browse chromosomes to find genes (e.g., BRCA1, TP53).

📖 Reference Genome Viewer: See the actual DNA sequence for a selected gene (via UCSC Genome Browser API).

🧬 Explore Known Variants: Load existing SNVs from ClinVar and test them with Evo2.

💻 Architecture
🚀 FastAPI Python Backend: Handles variant effect prediction requests using Evo2.

⚡ GPU Inference via Modal: H100 GPUs power real-time variant scoring.

🧠 Evo2 Model: Uses transformer-based protein modeling for accurate variant predictions.

🔄 API Integrations:

UCSC Genome API – for reference sequences

NCBI ClinVar (via E-utilities) – for known mutation data

🖥️ UI/UX
🎨 Modern Responsive UI: Built with Next.js, Tailwind CSS, and Shadcn UI.

📱 Mobile-Friendly: Works smoothly on phones, tablets, and desktops.

🧩 Built on T3 Stack: Typesafe, scalable, and easy to extend.

📚 Learn More
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
