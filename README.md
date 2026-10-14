# ATS Resume Copilot

A Streamlit website that runs five resume-tailoring steps in one workflow:

1. Analyzes the job description.
2. Reviews the current resume.
3. Calculates a transparent, rubric-based resume-to-job match estimate.
4. Generates a tailored, ATS-friendly resume.
5. Lists gaps, rejection risks, an application checklist, and likely interview questions.

## Run locally (Windows)

1. Install Python 3.10+.
2. Extract this ZIP.
3. Open Command Prompt in the extracted folder.
4. Run:

```bash
py -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
streamlit run app.py
```

The app opens in your browser.

## AI setup option A: Ollama (local)

1. Install Ollama from https://ollama.com
2. Open a terminal and run:

```bash
ollama pull llama3.1
ollama serve
```

If Ollama is already running, you may not need the second command. In the website sidebar, choose **Ollama (local)** and use `http://localhost:11434` and model `llama3.1`.

Other locally installed Ollama models can be selected by entering their exact model name.

## AI setup option B: OpenAI-compatible API

Choose **OpenAI-compatible API** in the sidebar, enter the endpoint, model name, and API key. API usage may cost money. The app does not persist the key.

## Deploying

You can deploy this Streamlit app on a hosting provider that supports Python apps. For a hosted deployment:
- Configure an accessible AI endpoint; `localhost` on the hosting server is not your personal computer.
- Store API keys in the host's secret manager instead of hard-coding them.
- Check the provider's privacy terms before processing resumes.
- Add authentication before using it with multiple users or storing resumes.

## Privacy and limitations

- Uploaded resume text is sent to the AI provider selected in the sidebar.
- With local Ollama, AI processing can remain on your machine.
- This prototype does not store resume files in a database.
- The match score is an illustrative rubric-based estimate, not an actual ATS score or callback prediction.
- Always review dates, links, claims, and metrics before using a generated resume.
- A scanned PDF may not contain selectable text; use a text-based PDF or paste the resume text.

## Project structure

- `app.py` — Streamlit website and analysis workflow
- `requirements.txt` — dependencies
