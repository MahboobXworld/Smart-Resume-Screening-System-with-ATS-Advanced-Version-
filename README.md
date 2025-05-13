Smart Resume Screening System with ATS (Advanced Version)

📌 Project Overview:

      This is an advanced-level Smart Resume Screening System powered by ATS (Applicant Tracking System) techniques. It helps HR and recruiters to automatically screen, score, and shortlist resumes based on a given Job Description (JD). It also includes a Flask web interface, stores data in a SQLite database, and uses NLP and ML techniques like Named Entity Recognition (NER), TF-IDF, Cosine Similarity, and Job Role Classification using spaCy and other ML models.

---------------------------------------------------------------------------------------------------------

📁 Project Structure:

```
resume_screening_system/
├── app/
│   ├── main.py               # Main workflow script
│   ├── parser.py             # Extracts resume text
│   ├── ats_scorer.py         # Scores resumes based on job description
│   ├── mailer.py             # Sends emails to shortlisted candidates
│   ├── file_manager.py       # Handles file movements and storage
│   ├── ner_extractor.py      # Extracts name, email, skills using spaCy NER
│   ├── role_classifier.py    # Predicts job role category using ML model
│   ├── database.py           # SQLite database operations (insert, query, create)
│   └── flask_app.py          # Flask UI for uploading and viewing results
├── resumes/                  # Raw resumes input folder
├── shortlisted/              # Shortlisted resumes output folder
├── data/
│   ├── job_description.txt   # Job Description for screening
│   ├── ranked_candidates.csv # Output: ATS score and details
├── utils/
│   ├── text_cleaner.py       # Text preprocessing
│   ├── similarity.py         # TF-IDF and cosine similarity
├── logs/
│   └── ats_log.log           # Logs for system events
├── config/
│   └── email_config.json     # SMTP configuration for email
├── templates/
│   └── index.html            # HTML template for Flask app
├── static/                   # CSS/JS if needed for Flask UI
├── test/                     # Unit test files
├── requirements.txt          # List of required packages
└── README.md                 # Project documentation
```

---------------------------------------------------------------------------------------------------------

⚙️ Workflow (Advanced Pipeline):

1. User uploads resumes using the Flask UI.
2. `parser.py` reads and extracts raw text from resumes.
3. `text_cleaner.py` preprocesses the text.
4. `job_description.txt` is also cleaned similarly.
5. `ner_extractor.py` extracts entities like name, email, skills using spaCy NER.
6. `role_classifier.py` predicts the job role category for each resume.
7. `ats_scorer.py` calculates ATS score using TF-IDF + Cosine Similarity.
8. `ranked_candidates.csv` stores all info: name, score, predicted role, etc.
9. `database.py` stores this data in a SQLite database.
10. `file_manager.py` moves top-scoring resumes to `/shortlisted`.
11. `mailer.py` sends emails to shortlisted candidates.
12. Logs are written to `ats_log.log`.

---------------------------------------------------------------------------------------------------------

🌐 Flask UI:

* Upload resumes (PDF/DOCX)
* See real-time ATS score, extracted info, predicted role
* Search/filter resumes by score or role

---------------------------------------------------------------------------------------------------------

🧠 ML & NLP Features

NER Extraction using `spaCy` for:

  * Names
  * Emails
  * Phone Numbers
  * Skills

ATS Scoring using:

  * `TfidfVectorizer`
  * `cosine_similarity`

Role Classification:

  * Trained classifier (e.g., Logistic Regression or RandomForest)
  * Input: Resume text → Output: Predicted job role

---------------------------------------------------------------------------------------------------------

🧰 Tools & Libraries

| Feature             | Libraries/Tools Used                      |
| ------------------- | ----------------------------------------- |
| Resume Parsing      | `pdfminer.six`, `python-docx`, `textract` |
| Text Cleaning       | `re`, `nltk`, `spacy`, `string`           |
| NER                 | `spaCy`                                   |
| Similarity Matching | `scikit-learn`, `TfidfVectorizer`         |
| Classification      | `sklearn` models, `joblib`                |
| Database            | `sqlite3`, `pandas`                       |
| Web App             | `Flask`, `HTML`, `CSS`, `Jinja2`          |
| Emailing            | `smtplib`, `email.message`, `ssl`         |
| Logging             | Python `logging` module                   |
| Testing             | `unittest`, `pytest`                      |

---------------------------------------------------------------------------------------------------------

🔋 Setup Instructions

1. Clone the repository

```bash
git clone https://github.com/yourusername/resume_screening_system.git
cd resume_screening_system
```

2. Install requirements

```bash
pip install -r requirements.txt
```

3. Download NLTK and spaCy models

```python
import nltk
nltk.download('punkt')
nltk.download('stopwords')

python -m spacy download en_core_web_sm
```

4. Run Flask Web App

```bash
python app/flask_app.py
```

---------------------------------------------------------------------------------------------------------

🧪 Testing:

* Place test files in `/test/`
* Run with:

```bash
pytest test/
```

---------------------------------------------------------------------------------------------------------

✅ Future Improvements:

* Use MongoDB for large-scale resume data
* Integrate OpenAI embeddings for semantic similarity
* Add user authentication for HR dashboard
* Resume feedback system for candidates

---------------------------------------------------------------------------------------------------------

📬 Contact:

Developer: Mahboob Alam
Email: [ma.mahboob2002@gmail.com](mailto:ma.mahboob2002@gmail.com)
LinkedIn: [https://www.linkedin.com/in/mahboob-alam-242342152](https://www.linkedin.com/in/mahboob-alam-242342152)

---------------------------------------------------------------------------------------------------------

⭐ Acknowledgments:

Thanks to the open-source libraries and online resources that helped shape this project!
