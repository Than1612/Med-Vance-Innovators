# MEDIxtract Server  
*A Flask-based application for extracting structured data from images/PDFs using AI*

![Demo](https://img.shields.io/badge/Demo-Av://img.shields.io/badge/P](https://img.shields.io/badge/Flask-2.0%2B-lightgreyures

- **Multi-Format Support**  
  Process both image files (JPEG/PNG) and PDF documents.

- **AI-Powered Extraction**  
  Uses OpenAI GPT to intelligently extract and format key data (particulars, amounts, etc.).

- **Excel Integration**  
  Automatically stores extracted data in organized Excel spreadsheets.

- **Easy File Management**  
  Dedicated folders for uploads (`uploads/`) and generated files (`excel_files/`).

- **Simple API Endpoints**  
  RESTful routes for uploading files and downloading results.

---

## Tech Stack

- **Backend**: Python + Flask
- **AI Engine**: OpenAI GPT
- **PDF Processing**: PyPDF2
- **Excel Handling**: openpyxl
- **HTTP Requests**: requests

---

## Installation

1. **Clone the repository**  
   ```bash
   git clone https://github.com/Aakash0705/MEDIExtract-Server.git
   cd MEDIExtract-Server
   ```

2. **Set up virtual environment**  
   ```bash
   python -m venv venv
   source venv/bin/activate  # Windows: venv\Scripts\activate
   ```

3. **Install dependencies**  
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure API Key**  
   Add your OpenAI API key in `main.py`:  
   ```python
   openai.api_key = 'your-api-key-here'  # Replace with actual key
   ```

5. **Create directories**  
   ```bash
   mkdir uploads excel_files
   ```

---

## Usage

### Running the Server
```bash
python main.py 
```
Access via: `http://127.0.0.1:5000/`

### File Upload Instructions
1. **POST** to `/post_image` with your image/PDF file
2. **GET** `/download_excel` to retrieve processed data

---

## API Endpoints

| Method | Route             | Description                          |
|--------|-------------------|--------------------------------------|
| GET    | `/`               | Welcome message                      |
| POST   | `/post_image`     | Upload image/PDF for processing      |
| GET    | `/download_excel` | Download generated Excel file        |

---

## Error Handling  
Returns JSON-formatted errors for:
- Invalid file uploads
- API key failures
- Processing errors

---

## Future Roadmap
- Support additional file formats (e.g., DOCX)
- Enhanced data validation
- Customizable Excel templates
- Batch processing support
