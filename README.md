# ✍️ Pause & Pen

> *Slow down. Feel your day. Write one line.*

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Status](https://img.shields.io/badge/status-hackathon--ready-brightgreen)
![AI](https://img.shields.io/badge/AI-local--offline-ff69b4)
![Platform](https://img.shields.io/badge/platform-localhost-lightgrey)

**Pause & Pen** is a private, AI‑assisted journaling companion that helps you **live slowly** – not write faster.  
It runs **100% locally** on your computer. No cloud, no tracking, no AI that writes for you.  
Just a gentle pause in your day to feel, reflect, and capture what matters.

🎯 **Live slow. Write lightly. Know yourself better.**

---

## 📌 Table of Contents

- [The Problem](#the-problem)
- [Our Solution](#our-solution)
- [Key Features](#key-features)
- [Tech Stack](#tech-stack)
- [Architecture](#architecture)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)
- [Team & Acknowledgments](#team--acknowledgments)

---

## 😔 The Problem

Most people stop journaling because:

- **Too busy** – writing feels like another task.
- **Writer’s block** – “I don’t know what to write.”
- **Lack of motivation** – no gentle companion.
- **Privacy fears** – cloud diaries feel unsafe.

And many existing “AI journal” apps actually **write for you** – taking away the very act of reflection.

---

## 🌱 Our Solution

**Pause & Pen** is different.

We don’t believe AI should replace your voice.  
We believe AI should **disappear** until you need a little help with wording, formatting, or reflection.

- ✅ **You write** – AI only suggests (and only when you ask)
- ✅ **100% local** – your words never leave your laptop
- ✅ **Slow‑first** – reminders are gentle, not addictive
- ✅ **Privacy by default** – no accounts, no analytics, no cloud

> 💡 *AI is a humble editor, not a ghostwriter.*

---

## ✨ Key Features

| Feature | Description |
|---------|-------------|
| 📝 **Write freely** | Simple, clean editor – just you and your thoughts |
| 🖼️ **Attach photos** | Save moments with images (stored locally) |
| 😊 **Emoji mood** | Pick an emoji (optional) – AI never predicts your feelings |
| 🔔 **Gentle reminders** | Daily nudge: *“How was today?”* (customizable) |
| 🤖 **AI assist (on‑demand)** | – Improve wording <br> – Suggest synonyms <br> – Re‑format as bullet points or short poem <br> – Ask reflective questions |
| 🏞️ **Slow living focus** | No dashboards, no stress, no performance metrics |
| 🔒 **Offline & private** | Runs on localhost, no internet required after setup |
| 💾 **Local storage** | SQLite + image files – easily backup your diary |

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-------------|
| Frontend | React + TypeScript + Tailwind CSS |
| Backend | FastAPI (Python) |
| Database | SQLite |
| Local AI | Ollama + Llama 3.2 (or Gemma 2 / Mistral) |
| Image handling | Multer + Sharp |
| Notifications | Web Notifications API |

---

## 🧱 Architecture

```
┌─────────────────────────────────────────────────┐
│ Frontend (React) │
│ localhost:5173 │
└─────────────────────┬───────────────────────────┘
│ HTTP / REST
┌─────────────────────▼───────────────────────────┐
│ Backend (FastAPI) │
│ localhost:8000 │
└─────────┬───────────────────────────┬───────────┘
│ │
┌─────────▼─────────┐ ┌─────────▼─────────┐
│ SQLite │ │ Ollama │
│ (entries, │ │ (Llama 3.2) │
│ images metadata)│ │ local LLM │
└───────────────────┘ └───────────────────┘

```
 
All components run on your machine. No external calls.

---

## 📦 Installation

### Prerequisites

- Python 3.10+
- Node.js 18+
- [Ollama](https://ollama.com) installed
- Git

### Step‑by‑step

# 1. Clone the repository
```
git clone https://github.com/your-username/pause-and-pen.git
cd pause-and-pen
```
# 2. Install Ollama model (first time only)
```
ollama pull llama3.2
```
# 3. Backend setup
```
cd backend
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
python init_db.py          # Create SQLite database
```
# 4. Frontend setup
```
cd ../frontend
npm install
```
# 5. Run both servers
```
- Terminal 1 - Backend
cd backend
uvicorn main:app --reload --port 8000
- Terminal 2 - Frontend
cd frontend
npm run dev
```
- Open your browser at http://localhost:5173
- ✅ No internet required after initial download of the Ollama model.

---

# 🎮 Usage
- Write an entry – type what’s in your heart. No pressure.
- Add a photo (optional) – capture the moment.
- Pick an emoji (optional) – just for you.
- Need help? Click the ✨ Ask AI button:
- Polish my wording
- Suggest better vocabulary
- Re‑format as bullet points
- Ask me a reflective question
- Set a reminder – daily gentle nudge.
- Browse past entries – see your slow journey.
> 🧘 *No streaks, no graphs, no competition. Just you and your pages.*

 ---

## 📁 Project Structure
```
pause-and-pen/
├── backend/
│   ├── main.py
│   ├── database.py
│   ├── ai_helper.py
│   ├── routes/
│   │   ├── entries.py
│   │   ├── images.py
│   │   └── ai.py
│   ├── uploads/               # stored images (local)
│   └── requirements.txt
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   │   ├── Home.jsx
│   │   │   ├── Write.jsx
│   │   │   └── Archive.jsx
│   │   ├── App.jsx
│   │   └── main.jsx
│   └── package.json
├── README.md
└── LICENSE
```
---

## 🗺️ Roadmap
- Core writing + local storage
- On‑demand AI assistance (wording, format, questions)
- Photo attachments
- Gentle reminders
- Dark mode
- Search entries
- Export diary (JSON / Markdown)
- Voice input (transcribe locally)

---

## 🤝 Contributing
- We welcome contributions that respect the slow living spirit.
- Please open an issue or pull request.
- Fork the repo
- Create your branch (git checkout -b feature/amazing-idea)
- Commit changes (git commit -m 'Add something')
- Push (git push origin feature/amazing-idea)
- Open a Pull Request

---

## 📄 License
Distributed under the MIT License. See ``` LICENSE ``` for more information.

---

## 👥 Team & Acknowledgments
- Built with ❤️ for the IBM UNSA Hackathon – supporting SDG 3: Good Health and Well‑being.
- Inspired by the slow living movement and the belief that technology should serve reflection, not replace it.
- Special thanks to Ollama, FastAPI, React, and the open‑source community.

---

> “Pause. Pick up your pen. That’s enough.”

🌿 GitHub · 🐦 [@olympusxvn] · 📧 vo.q.cuong@gmail.com
