# 🧠 Chinese Learning App — Proof of Concept (POC)

An AI-powered Chinese learning app focused on personalized vocab-driven exercises, stories, and language immersion. This is a minimal but functional POC aimed at validating the core learning loop for self-learners.

---

## 🔧 Stack Overview

| Layer        | Tech         | Role                             |
|--------------|--------------|----------------------------------|
| Frontend     | Next.js      | UI for vocab, exercises, stories |
| Backend CMS  | Strapi 5     | Manages users, vocab, sets, data |
| AI Engine    | FastAPI      | Generates exercises & stories    |
| Database     | PostgreSQL   | Used by Strapi (via Prisma)      |
| Storage      | Supabase/S3  | (Optional) Audio/image caching   |

---

## 📦 Core Features in POC

-  Add + organize Chinese vocab (characters, pinyin, definition)
- AI-generated exercises (fill-in-the-blank, reordering, multiple choice)
- Mini-stories using your vocab
- Lazy audio generation for pronunciation
- Import vocab from Anki, clipboard (MVP-friendly)

---

## 📁 Project Structure

```
/frontend        → Next.js app
/backend/strapi  → Strapi 5 CMS (Node, PostgreSQL)
/backend/ai      → FastAPI app (Python AI logic)
```

---

## 🚀 Getting Started

### 1. Setup Strapi Backend

```bash
cd backend/strapi
npm install
npm run develop
```

> Ensure PostgreSQL is running and configured in `.env`.

### 2. Setup FastAPI Server

```bash
cd backend/ai
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
uvicorn main:app --reload
```

> Handles AI logic (TTS, story and exercise generation).

### 3. Setup Next.js Frontend

```bash
cd frontend
npm install
npm run dev
```

---

## 📘 Content Types (Strapi)

- `VocabEntry`: character, pinyin, definition, tags
- `VocabSet`: organizes vocab
- `Exercise`: generated quizzes with feedback
- `MiniStory`: stories that use vocab in context

---

## ⚙️ API Routes

### FastAPI
| Route | Description |
|-------|-------------|
| `/generate/exercise` | Generate smart exercise |
| `/generate/story`    | Generate a vocab-based story |
| `/generate/audio`    | TTS pronunciation |

### Strapi
| Route | Description |
|-------|-------------|
| `/api/vocab-entries` | CRUD for vocab |
| `/api/vocab-sets`    | CRUD for sets |
| `/api/exercises`     | Save & query exercises |
| `/api/mini-stories`  | Save & read stories |

---

## 📅 Roadmap (for later)

-  Audio pronunciation caching
-  Speech-to-text & tone evaluation
-  Gamification (XP, streaks)
-  Community/shared vocab sets
-  Teacher dashboard + lesson plans

---

## 💡 Built For

- Self-directed Chinese learners
- Personalized vocab-driven immersion
- AI-assisted active recall

---
