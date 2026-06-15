# ResumePath.Ai

**Created by Shubham**

ResumePath.Ai is a Flask-based web application for generating professional resumes in PDF format and extracting subjective questions from uploaded PDF documents. The project combines resume-building form inputs with a simple NLP-based question generator that analyzes PDF text and creates question prompts.

## Features

- Generate a resume PDF from user-provided profile, education, skills, internship, project, and achievement details.
- Upload a PDF and generate subjective question prompts based on the extracted text.
- Uses Flask for the web interface and `pdfkit` for PDF conversion.
- Leverages NLTK and NumPy for NLP-based question generation.

## Requirements

- Python 3.8+ recommended
- Flask
- nltk
- numpy
- pdfkit
- PyPDF2
- pdfminer.six
- wkhtmltopdf (required by `pdfkit`)

## Installation

1. Clone or download the repository.
2. Open a terminal in the project root:

```bash
cd c:\Users\Shubham\Downloads\Resumepath.Ai\Resumepath.Ai
```

3. Create and activate a virtual environment:

```bash
python -m venv .venv
.\.venv\Scripts\activate
```

4. Install required Python packages:

```bash
pip install flask nltk numpy pdfkit PyPDF2 pdfminer.six
```

5. Install `wkhtmltopdf` for PDF generation. On Windows, download the installer for `wkhtmltox-0.12.6-1.msvc2015-win64` and add it to your PATH.

6. Download NLTK data once before running the app:

```python
import nltk
nltk.download('punkt')
nltk.download('averaged_perceptron_tagger')
```

If you prefer, you can also download all NLTK data with:

```python
import nltk
nltk.download('all')
```

## Usage

1. Start the Flask application:

```bash
python app.py
```

2. Open your browser and navigate to:

```text
http://localhost:5000/
```

3. Use the home page to access the available features:

- `/` - Home page
- `/predict` - Upload a PDF and generate subjective questions
- `/generate` - Fill resume details and generate a PDF resume

## Application Structure

- `app.py` - Main Flask application and route definitions.
- `subjective.py` - NLP-based question generation utility.
- `templates/` - HTML templates for the web pages.
- `static/` - Static assets such as CSS.

## Notes

- `pdfkit` relies on `wkhtmltopdf`; without it, resume PDF generation will fail.
- The current question generator uses regular expression-based chunking and may work best with English text.
- The resume PDF is generated from a simple HTML template embedded in `app.py`.

## Troubleshooting

- If PDF generation fails, verify that `wkhtmltopdf` is installed and accessible from your PATH.
- If the app cannot parse uploaded PDFs, ensure the file is a valid PDF and contains extractable text.
- For any NLTK errors, confirm the required corpora and tokenizers are downloaded.

## License

This repository does not include a license file. Add a license if you plan to share or distribute the project publicly.
