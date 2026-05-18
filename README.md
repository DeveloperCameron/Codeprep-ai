# CodePrep AI 🧠

An AI-powered coding interview practice tool built with vanilla HTML/CSS/JS, powered by Groq (free AI API) and deployed on Vercel.

## Features
- Generate coding interview questions by topic and difficulty
- Topics: HTML/CSS, JavaScript, DOM, Async JS, Flexbox, REST APIs, Python, Algorithms, Data Structures, SQL, Git, and more
- AI grades your answers and gives detailed feedback
- Streak and score tracking saved in localStorage
- Fully free to run

## Tech Stack
- **Frontend:** Vanilla HTML, CSS, JavaScript (no frameworks)
- **AI:** Groq API (llama-3.3-70b-versatile) — free tier
- **Backend:** Vercel serverless function (keeps API key secure)
- **Hosting:** Vercel

## Setup

1. Clone this repo
2. Go to [vercel.com](https://vercel.com) and import the repo
3. Add environment variable: `GROQ_API_KEY` = your key from [console.groq.com](https://console.groq.com)
4. Deploy — done!

## Project Structure
```
codeprep-ai/
├── index.html       # Main app (frontend)
├── api/
│   └── chat.js      # Vercel serverless function (proxy to Groq)
├── vercel.json      # Vercel routing config
└── README.md
```

## Why I built this
I'm a freshman web development student at TSTC and built this to help myself and others practice for coding interviews using AI-generated questions and feedback.
