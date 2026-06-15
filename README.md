# ResumePath.AI

A sophisticated Flask-based web application designed to streamline resume generation and intelligent question extraction from PDF documents. This project leverages modern NLP techniques to enhance the resume-building experience and facilitate interview preparation.

## Overview

ResumePath.AI provides two core functionalities:
- **Resume Generation**: Create professionally formatted PDF resumes from structured user input
- **Question Extraction**: Generate targeted interview questions by analyzing uploaded PDF documents

## Features

✨ **Core Capabilities**
- Generate professional PDF resumes from user-provided details (profile, education, skills, internships, projects, achievements)
- Extract and analyze PDF content to generate contextually relevant subjective interview questions
- Intuitive web-based interface for seamless user experience
- Responsive design for accessibility across devices

🛠️ **Technical Stack**
- Flask for robust web application framework
- `pdfkit` for reliable PDF conversion and generation
- NLTK and NumPy for advanced NLP-based question generation
- PyPDF2 and pdfminer.six for comprehensive PDF processing

## Prerequisites

- **Python**: 3.8 or higher
- **Operating System**: Windows, macOS, or Linux
- **wkhtmltopdf**: Required system dependency for PDF generation

## Installation

### Step 1: Clone the Repository
```bash
git clone https://github.com/ShubDeshmukh2006/Resumepath.Ai.git
cd Resumepath.Ai
```

### Step 2: Set Up Virtual Environment
```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
```

### Step 3: Install Python Dependencies
```bash
pip install flask nltk numpy pdfkit PyPDF2 pdfminer.six
```

### Step 4: Install wkhtmltopdf
**Windows:**
- Download the installer: [wkhtmltox-0.12.6-1.msvc2015-win64](https://wkhtmltopdf.org/downloads.html)
- Run the installer and follow the setup wizard
- Verify installation by adding to PATH (usually done automatically)

**macOS:**
```bash
brew install --cask wkhtmltopdf
```

**Linux (Ubuntu/Debian):**
```bash
sudo apt-get install wkhtmltopdf
```

### Step 5: Download NLTK Data
Run the following Python commands once before first use:
```python
import nltk
nltk.download('punkt')
nltk.download('averaged_perceptron_tagger')
```

Alternatively, download all NLTK data:
```python
import nltk
nltk.download('all')
```

## Quick Start

### Running the Application
```bash
python app.py
```

The application will be available at: `http://localhost:5000/`

### Available Routes
- `/` — Home page with feature overview
- `/generate` — Resume generation interface
- `/predict` — PDF upload and question extraction tool

## Project Structure

```
Resumepath.Ai/
├── app.py                 # Main Flask application and route handlers
├── subjective.py          # NLP utilities for question generation
├── templates/             # HTML templates for web interface
│   ├── index.html
│   ├── generate.html
│   └── predict.html
├── static/                # Static assets (CSS, JavaScript, images)
├── README.md
└── requirements.txt       # Python dependencies
```

## Usage Guide

### Generating a Resume
1. Navigate to `/generate`
2. Fill in your professional details (profile, education, skills, etc.)
3. Review the generated preview
4. Download your PDF resume

### Extracting Interview Questions
1. Navigate to `/predict`
2. Upload a PDF document (resume, project report, etc.)
3. The system will analyze the content and generate relevant interview questions
4. Review and prepare responses

## Configuration

### Optional: Create requirements.txt
```bash
flask
nltk
numpy
pdfkit
PyPDF2
pdfminer.six
```

Install from requirements file:
```bash
pip install -r requirements.txt
```

## Troubleshooting

| Issue | Solution |
|-------|----------|
| **PDF generation fails** | Verify `wkhtmltopdf` is installed and accessible in PATH. Test with `wkhtmltopdf --version` |
| **PDF parsing errors** | Ensure uploaded PDF contains extractable text (not image-only or corrupted) |
| **NLTK errors** | Run `nltk.download()` in Python to download required corpora and models |
| **Port already in use** | Modify `app.py` to use a different port (e.g., `app.run(port=5001)`) |
| **Missing dependencies** | Reinstall packages: `pip install -r requirements.txt` |

## Known Limitations

- Question generation uses regex-based text chunking and performs best with English language input
- Resume template is basic HTML; customize by modifying `app.py` for enhanced styling
- PDF extraction effectiveness depends on PDF structure and encoding

## Future Enhancements

- [ ] Support for multiple resume templates
- [ ] Multi-language question generation
- [ ] Resume format customization options
- [ ] Interview question difficulty levels
- [ ] User authentication and cloud storage
- [ ] API endpoints for programmatic access

## Contributing

Contributions are welcome! Please follow these steps:
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/enhancement`)
3. Commit changes (`git commit -m 'Add enhancement'`)
4. Push to branch (`git push origin feature/enhancement`)
5. Open a Pull Request

## License

This project does not currently include a license. Before distributing or using in production, please add an appropriate open-source license (e.g., MIT, Apache 2.0, GPL 3.0).

## Author

**Shubham Deshmukh**

## Support

For issues, questions, or suggestions, please open a GitHub issue or contact the project maintainer.

---

**Last Updated**: June 2026 | **Status**: Active Development
