# Resume Ranking and Shortlisting Application

## Purpose
A web-based application designed to streamline the resume screening process for employers by ranking and shortlisting resumes based on their relevance to the job description.

---

## Features

- **Multi-Format Input**:
  Employers can upload resumes in **DOCX**, or **TXT** formats.

- **Job Description Input**:
  Employers can upload or input the job description directly for seamless integration.

- **Resume Analysis**:
  - Utilizes **Natural Language Processing (NLP)** techniques to compare resumes against the job description.
  - Combines **semantic similarity** and **keyword-based scoring** for a comprehensive analysis.

- **Semantic Similarity**:
  Powered by **spaCy**, the application calculates how closely each resume matches the job description.

- **Keyword-Based Scoring**:
  Scores candidates based on their skills and experience relevant to the job.

- **Similarity Score**:
  Each resume is assigned a similarity score (out of 100) indicating its relevance to the job description.

- **Ranked Results**:
  Displays resumes ranked by their similarity scores, helping employers focus on the best-fit candidates.

- **Data Security**:
  Automatically deletes uploaded resumes after analysis to ensure sensitive information is not stored.

- **File Management**:
  Uploaded files are processed and cleaned up automatically after analysis.

---

## Technology Stack

- **Backend**: Python with the **Flask** framework.
- **NLP Engine**: **spaCy** for semantic similarity analysis.

---

## Key Benefits

- Automates the tedious process of resume screening.
- Provides ranked results, making it easier to identify top candidates.
- Saves time and effort by streamlining the shortlisting process.

---

## Server Setup Guide

1. **Clone the Repository**
   ```bash
   git clone https://github.com/DeepansInt112/CV-RANK.git
   cd CV-RANK
   ```

2. **Set Up the Virtual Environment (Recommended)**
   ```bash
   # Create a virtual environment
   python -m venv venv

   # Activate the virtual environment
   # Windows:
   .\venv\Scripts\activate
   # Mac/Linux:
   source venv/bin/activate
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Download spaCy Language Models**
   ```bash
   python -m spacy download en_core_web_md
   ```

5. **Run the Application**
   ```bash
   # Set environment variables
   export FLASK_APP=main.py  # Linux/macOS
   set FLASK_APP=main.py  # Windows
   export FLASK_ENV=development  # For development mode

   # Start the server
   flask run
   ```

6. **Access the Application**
   Visit the application at: [http://localhost:5000](http://localhost:5000) or [https://127.0.0.1:5000](https://127.0.0.1:5000).

---

## File Structure

```
CV-RANK/
├── main.py                # Main application entry point
├── requirements.txt      # Dependency specifications
├── templates/            # HTML templates
│   ├── matchresume.html  # Matching results templates # Resume display template
├── uploads/              # Temporary storage for uploaded files
├── job_desc/             # Sample job descriptions
├── venv/                 # Virtual environment directory (auto-generated)
└── README.md             # Project documentation
```

> Note: The application will automatically create necessary directories (e.g., `uploads/`) on first run. Ensure you have write permissions in the project directory.

---

## Sample Testing

To test the application, use the sample resumes and job description files provided in the `job_desc/` and `uploads/` directories. These can serve as reference data for initial tests.

## Example Workflow

1. Upload multiple resumes in supported formats (PDF, DOCX, TXT).
2. Input or upload the job description.
3. Click "Analyze" to process the resumes.
4. View ranked results with similarity scores out of 100.
5. Download or save the top-ranked resumes for further review.

---

## Troubleshooting

- **Error: Missing Dependencies**:
  Ensure all dependencies in `requirements.txt` are installed and the `en_core_web_md` language model is downloaded.

- **File Upload Issues**:
  Verify that uploaded files are in supported formats and within size limits.

- **Server Not Starting**:
  Check that Flask is installed and environment variables are set correctly.

---

## Deployment in Production (Optional)

For deploying this application in a production environment, consider the following setup:

- Use **Gunicorn** as the WSGI server.
- Use **Nginx** as a reverse proxy to serve the application.
- Set up HTTPS for secure communication.
