# ChunkyPDF

## 📖 Overview
**ChunkyPDF** is an internal-only tool for converting large sets of PDF manuals, flyers, and technical documents into structured text "chunks" suitable for ingestion into downstream systems (e.g., Aprimo, Palantir Foundry, or other AI pipelines).  

The tool:
- Accepts a folder of PDF files (both digital-born and scanned).  
- Runs **OCR** on scanned documents to make them searchable.  
- Cleans and normalizes text (deskew, rotation, noise reduction).  
- Splits documents into **section-aware, token-limited chunks** with overlap for AI/LLM use.  
- Outputs structured JSONL or Parquet files with metadata (source file, section headers, checksums).  

This project is **strictly internal** and is not distributed or sold outside the company.

---

## ⚙️ Dependencies

### System Requirements
- **Tesseract OCR** – Apache License 2.0  
  <https://github.com/tesseract-ocr/tesseract>  
- **Ghostscript (64-bit)** – GNU AGPL License (internal use only)  
  <https://ghostscript.com/>  
- **qpdf** – Apache License 2.0  
  <https://qpdf.sourceforge.io/>

All three must be installed and available on the system `PATH`.

### Python Libraries
Installed in the project virtual environment (`.venv`):

- **ocrmypdf** – GPLv3  
- **unstructured[all-docs]** – Apache License 2.0  
- **PyMuPDF (fitz)** – AGPL (internal use only)  
- **pdfplumber** – MIT License  
- **tiktoken** – MIT License  
- **pandas** – BSD 3-Clause  
- **pyarrow** – Apache License 2.0  
- **tqdm** – MIT License  

---

## 📜 License and Legal Notes

- This project is **internal-use only**. It is not distributed, sublicensed, or sold to third parties.  
- Because of this, copyleft obligations under **AGPL/GPL** components (Ghostscript, PyMuPDF, OCRmyPDF) do **not** apply, as no external distribution occurs.  
- All third-party dependencies retain their original licenses, which are listed in [NOTICE.md](NOTICE.md).  
- If in the future this tool is distributed outside the organization, the legal/licensing strategy will need to be revisited.

---

## 🔒 Disclaimer
This software is provided *as is* for internal workflows.  
No warranty is expressed or implied regarding functionality, fitness for purpose, or compliance beyond internal usage.  

---

## 🚀 Usage (Quickstart)

```powershell
# Activate virtual environment
cd C:\Users\Phil\Projects\ChunkyPDF
.\.venv\Scripts\Activate.ps1

# Run ChunkyPDF against a folder of PDFs
python chunkypdf.py "C:\path\to\pdfs" --out "C:\path\to\chunks" --version v2025.09.10

```

---

## 📘 Notice

This project, **ChunkyPDF**, includes or depends on third-party software components.  
Each component remains licensed under its original license.  

This tool is **internal use only** and is not distributed externally.  
If this project is ever distributed outside the organization, licensing obligations may change.

---

## Third-Party Components

### OCR and PDF Tools
- **Tesseract OCR**  
  License: Apache License 2.0  
  Source: <https://github.com/tesseract-ocr/tesseract>

- **Ghostscript**  
  License: GNU Affero General Public License (AGPL) v3.0  
  Source: <https://ghostscript.com/>  
  *Note: AGPL obligations apply only if the software is distributed or made publicly available. Internal use only does not trigger copyleft requirements.*

- **qpdf**  
  License: Apache License 2.0  
  Source: <https://qpdf.sourceforge.io/>

---

### Python Libraries
- **ocrmypdf** – GPLv3  
  <https://github.com/ocrmypdf/OCRmyPDF>

- **unstructured** – Apache License 2.0  
  <https://github.com/Unstructured-IO/unstructured>

- **PyMuPDF (fitz)** – GNU Affero General Public License (AGPL) v3.0  
  <https://pymupdf.readthedocs.io/>

- **pdfplumber** – MIT License  
  <https://github.com/jsvine/pdfplumber>

- **tiktoken** – MIT License  
  <https://github.com/openai/tiktoken>

- **pandas** – BSD 3-Clause  
  <https://pandas.pydata.org/>

- **pyarrow** – Apache License 2.0  
  <https://arrow.apache.org/>

- **tqdm** – MIT License  
  <https://github.com/tqdm/tqdm>

---

## Internal Use Disclaimer

This project is **not** distributed or sublicensed outside the company.  
All dependencies are used in accordance with their licenses for internal processing only.  
Redistribution or commercial distribution would require a license review and possibly alternative arrangements for AGPL/GPL components.

## REQUIRED INSTALLS

ocrmypdf
unstructured [all-docs]
pymupdf
pdfplumber
tiktoken
pandas
pyarrow
tqdm


