<div align="center">

# Bank Islami Demo Voice Bot

Azure-native banking voice bot with GPT-4o, Azure AI Search, speech services, WhatsApp, and ACS integration.

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white&style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Reference%20Implementation-6366F1?style=for-the-badge)

[Story](#-the-story) · [Features](#-features) · [Setup](#-getting-started) · [Configuration](#-configuration)

</div>

---

## 🎯 Overview

Azure-native banking voice bot with GPT-4o, Azure AI Search, speech services, WhatsApp, and ACS integration.

## 📖 The Story

Banking assistants often begin as simple FAQ chatbots. This project explores what happens when that idea grows into a multimodal service: customers can type or speak, answers can be grounded in approved banking information, and the same intelligence can be exposed through web and messaging channels.

The implementation evolved from a local FAISS-style retrieval experiment toward an Azure-native architecture. Azure AI Search supplies relevant context, GPT-4o produces the response, and speech services handle the audio path. FastAPI ties these pieces together behind health, text, audio, media, and webhook endpoints.

Today, the repository is best understood as a production-oriented reference architecture. Its next chapter is operational hardening: managed identity, durable media storage, automated evaluation, observability, and stronger channel security.

## ✨ Features

- Text conversation endpoint
- Speech-to-text and text-to-speech
- Conversational AI responses
- WhatsApp and ACS integration

## 🧰 Tech Stack

| Technology | Purpose |
| --- | --- |
| **Python** | Primary programming language |
| **FastAPI** | API and web server |
| **Azure OpenAI** | Chat, transcription, and speech services |
| **LangChain** | RAG orchestration and text processing |
| **FAISS** | Vector similarity search |

## 🚀 Getting Started

```bash
git clone https://github.com/haseebconventarian2-gif/Bank-Islami-demo-voice-bot.git
cd Bank-Islami-demo-voice-bot
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
```

## ⚙️ Configuration

Configure Azure OpenAI deployments and any messaging-channel credentials in `.env`.

> Store credentials in `.env` and never commit secrets.

## ▶️ Run

```bash
uvicorn main:app --host 0.0.0.0 --port 8000
```

## 📌 Project Status

This is a learning and reference implementation. Review security, validation, monitoring, and deployment settings before production use.

## 🧩 Detailed Code Reference

**Runtime flow:** `Text/audio -> STT -> retrieval -> LLM -> TTS/text -> channel reply`

### 📁 Repository Map

- `.github/` - supporting package or resources
- `__pycache__/` - supporting package or resources
- `api/` - supporting package or resources
- `fastapi_app.py` - project file
- `IMPLEMENTATION_SUMMARY.md` - project file
- `main.py` - project file
- `QUICKSTART.md` - project file
- `rag_pipeline.py` - project file
- `README.md` - project file
- `requirements.txt` - project file
- `START_HERE.md` - project file
- `VERIFICATION_CHECKLIST.md` - project file

## 🧪 Validation Checklist

1. Install dependencies in a clean virtual environment.
2. Configure only the environment variables needed by enabled integrations.
3. Start the documented entry point and test its health or root route.
4. Exercise successful and invalid requests.
5. Confirm secrets, private datasets, indexes, and model artifacts are ignored.

## 🔒 Production Checklist

- Use managed secret storage.
- Add authentication, authorization, rate limiting, and request-size limits.
- Add automated tests, structured logs, monitoring, and health checks.
- Pin and audit dependencies.
- Define retention and privacy controls for audio and customer data.

> This README reflects the current codebase. External AI, telephony, and messaging features require their respective accounts, assets, and approvals.




## 🛠 Troubleshooting

<details>
<summary><strong>The application does not start</strong></summary>

Confirm the virtual environment is active, install `requirements.txt`, and check that every required environment variable is defined.
</details>

<details>
<summary><strong>An AI or messaging service cannot be reached</strong></summary>

Verify the endpoint, credentials, deployment names, network access, and external service status. Restart the application after changing `.env`.
</details>

<details>
<summary><strong>A model, index, or artifact is missing</strong></summary>

Run the repository's documented build or training step and confirm that generated files are stored at the paths expected by the code.
</details>
