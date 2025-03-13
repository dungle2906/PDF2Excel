# PDF to Excel Converter

## Overview

This project provides a solution for extracting tabular data from PDF files and converting them into Excel spreadsheets using Python. It supports both native PDFs and scanned documents by leveraging OCR (Optical Character Recognition) when needed.

## Features

- **Convert PDFs to Excel (.xlsx)**
- **Supports both text-based and image-based PDFs**
- **Uses `pdf2image` to process scanned PDFs**
- **Extracts structured tabular data**
- **Exports to Excel format for easy analysis**

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/dung2906/PDF2Excel.git
   cd PDF2Excel
   ```
2. Install dependencies:
   ```bash
   pip install pdf2image pandas openpyxl pytesseract poppler-utils
   ```
3. Verify installation:
   ```bash
   python -c "import pdf2image; print('PDF2Image installed successfully')"
   ```

## Usage

### Convert a PDF to Excel

Run the script to extract tables from a PDF and save them as an Excel file:
```python
from pdf2image import convert_from_path
import pandas as pd

# Convert PDF pages to images
images = convert_from_path("sample.pdf")

# Process extracted data and save as Excel
df = pd.DataFrame(data)  # Replace with extracted data processing logic
df.to_excel("output.xlsx", index=False)
```

### OCR for Scanned PDFs

If the PDF contains scanned images, enable OCR using Tesseract:
```python
import pytesseract
from PIL import Image

text = pytesseract.image_to_string(Image.open("page.jpg"))
print(text)  # Extracted text from the scanned page
```

## Future Improvements

- Improve table structure detection.
- Enhance OCR performance for low-quality scans.
- Automate multi-page PDF processing.