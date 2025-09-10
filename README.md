# PDF Chunker Tool

## 📖 Overview
**PDF Chunker** is an internal-only tool for converting large sets of PDF manuals, flyers, and technical documents into structured text "chunks" suitable for ingestion into downstream systems (e.g., Aprimo, Palantir Foundry, or other AI pipelines).  

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
- All third-party dependencies retain their original licenses, which are listed above.  
- If in the future this tool is distributed outside the organization, the legal/licensing strategy will need to be revisited.

---

## 🔒 Disclaimer
This software is provided *as is* for internal workflows.  
No warranty is expressed or implied regarding functionality, fitness for purpose, or compliance beyond internal usage.  

---

## 🚀 Usage (Quickstart)

```powershell
# Activate virtual environment
cd C:\Users\****\Projects\pdf_chunker
.\.venv\Scripts\Activate.ps1

# Run chunker against a folder of PDFs
python pdf_chunker.py "C:\path\to\pdfs" --out "C:\path\to\chunks" --version v2025.09.10

```
## License
This project is licensed under the MIT License — see the [LICENSE](./LICENSE) file for details.

### 🤓 LONG STORY SHORT
You can use, modify, and share this code pretty much however you like, as long as you keep my name and the license notice in there somewhere.

### 😂 PUT SIMPLY
- Yes, you can use it.  
- Yes, you can tweak it.  
- Yes, you can sell something with it.  
- No, you can’t sue me if ChunkyPDF accidentally prints 10,000 blank pages and eats your toner budget.
