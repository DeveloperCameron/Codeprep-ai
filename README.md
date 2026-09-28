# CodePrep AI 🧠

An AI-powered coding interview practice tool built with vanilla HTML/CSS/JS, powered by Groq (free AI API) and deployed on Vercel.

**Live app:** [codeprep-ai-dusky.vercel.app](https://codeprep-ai-dusky.vercel.app)

## Features
- Generate coding interview questions by topic and difficulty
- Topics: HTML/CSS, JavaScript, DOM, Async JS, Flexbox, REST APIs, Python, Algorithms, Data Structures, SQL, Git, and more
- AI grades your answers and gives detailed feedback
- Streak and score tracking saved in localStorage
- Fully free to run

## Tech Stack
- **Frontend:** Vanilla HTML, CSS, JavaScript (no frameworks)
- **AI:** Groq API (`openai/gpt-oss-20b`) — free tier
- **Backend:** Node.js serverless function on Vercel, which proxies requests to Groq so the API key stays server-side and never reaches the browser
- **Hosting:** Vercel

## How it works
The frontend never calls Groq directly. It sends the topic, difficulty, and answer to `/api/chat`, a serverless function that attaches the API key, forwards the request to Groq, and returns the result. This keeps the key private and out of the client-side code.

## Setup

1. Clone this repo
2. Go to [vercel.com](https://vercel.com) and import the repo
3. Add environment variable: `GROQ_API_KEY` = your key from [console.groq.com/keys](https://console.groq.com/keys)
4. Deploy — done!

## Project Structure
codeprep-ai/
├── index.html # Main app (frontend)
├── api/
│ └── chat.js # Vercel serverless function (proxy to Groq)
├── package.json # Declares the project as an ES module
├── vercel.json # Vercel routing config
└── README.md
## Notes
Groq periodically retires older models. If question generation stops working, check [console.groq.com/docs/models](https://console.groq.com/docs/models) for the current list and update the `model` field in `api/chat.js`.

## Why I built this
I'm a Computer Science student at Central Texas College, building and deploying this to practice for coding interviews and to learn how to build a full app with a real backend, not just a static frontend.
