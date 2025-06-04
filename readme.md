## AI Interview System

This project is an AI-powered system that matches candidate resumes to the most suitable job descriptions and conducts a voice-based interview in the candidate's preferred language (English or Hindi). It leverages state-of-the-art NLP models, vector databases, and speech technologies to automate and enhance the recruitment process.

---

**Features**

- **Semantic Resume–Job Matching:** Uses embeddings to find the best job matches for a candidate's resume.
- **Voice-Based Interview:** Conducts an automated interview using Text-to-Speech (TTS) and Speech-to-Text (STT) in English or Hindi.
- **Dynamic Question Generation:** Generates interview questions relevant to the selected job using a large language model.
- **Multilingual Support:** Supports both English and Hindi for interviews and translations.
- **Persistent Storage:** Stores job descriptions and resumes (with interview answers) in a vector database (ChromaDB).
- **End-to-End Workflow:** From resume input, job matching, interview, to storing enhanced candidate profiles.

---

## How It Works

1. **Resume Input:**
The user enters their resume text and selects a preferred language (English or Hindi).
2. **Job Matching:**
The system encodes the resume and compares it to stored job descriptions using semantic similarity to find the top matches.
3. **Interview Process:**
    - The user selects a matched job.
    - The system generates job-specific questions.
    - Questions are asked via TTS; user answers via microphone (STT).
    - Answers are translated if needed and stored.
4. **Result Storage:**
    - The resume, interview questions, and answers are stored in ChromaDB for future retrieval and analysis.
5. **Resume Enhancement:**
    - The candidate's resume is enriched with their interview answers for the selected job(s).

---

## Example Usage

```
=== RESUME MATCHER WITH VOICE INTERVIEW ===

Enter your resume text: [Paste your resume here]
Preferred language (en/hi): hi

Finding best job matches...

TOP JOB MATCHES:
1. AC Technician (Score: 90.67 %)
2. Electrician (Score: 88.58 %)
3. HVAC Technician (Score: 87.64 %)
...

Select job to interview for (1-5): 1

Starting interview for: AC Technician

=== Interview for AC Technician ===

QUESTION: How often should the air filter be replaced in your unit?

[Listening... Speak now]
[Recognized Hindi]: पांच बार एयर फिल्टर बदल डाल
[Translated English]: Replace the air filter five times
STORED ANSWER: Replace the air filter five times

=== COMPLETE RESUME ===

Original Resume Text:
[Your resume text]

=== INTERVIEW ANSWERS ===

For Job: AC Technician

Q: How often should the air filter be replaced in your unit?
A: Replace the air filter five times
```


---

## Tech Stack

- **Python**
- **NLP Models:** SentenceTransformers, HuggingFace Transformers (Qwen-1.8B-Chat)
- **Speech:** OpenAI Whisper (STT), gTTS (TTS), Google Translate (translation)
- **Database:** ChromaDB (vector database for semantic search)
- **Audio:** sounddevice, soundfile, pydub, pygame
- **Other:** scikit-learn, difflib, tempfile, os

---

## Setup Instructions

1. **Clone the Repository**

```
git clone https://github.com/yourusername/resume-matcher-voice-interview.git
cd resume-matcher-voice-interview
```

2. **Install Dependencies**

```
pip install -r requirements.txt
```

3. **Run the Application**

```
python main.py
```


---

## Project Structure

- `main.py` — Main application logic
- `chroma_data/` — Persistent vector database storage
- `requirements.txt` — Python dependencies

---

## Customization

- **Add More Job Descriptions:**
Modify the `SAMPLE_JDs` list in the code to add or update job descriptions.
- **Change Language Support:**
Extend translation and TTS/STT modules for more languages as needed.

---

## Limitations \& Notes

- The system relies on the accuracy of speech recognition and translation APIs.
- Interview answers are stored verbatim; further post-processing may be needed for downstream applications.
- The project is a prototype and may require additional error handling for production use.

---

## Acknowledgements

- [SentenceTransformers](https://www.sbert.net/)
- [HuggingFace Transformers](https://huggingface.co/)
- [OpenAI Whisper](https://github.com/openai/whisper)
- [ChromaDB](https://www.trychroma.com/)
- [Google Translate](https://pypi.org/project/googletrans/)
- [gTTS](https://pypi.org/project/gTTS/)

---

## Contact

For questions or contributions, please open an issue or submit a pull request.

---

> This project demonstrates an end-to-end AI workflow for automated, multilingual resume screening and interviewing, leveraging modern NLP and speech technologies for real-world recruitment scenarios.

<div style="text-align: center">⁂</div>


