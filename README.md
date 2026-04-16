# MoralMentor

MoralMentor is a full-stack ethics learning platform built with **React + Vite** (frontend) and **Node.js + Express + MongoDB** (backend).

It focuses on scenario-based moral learning through quizzes, flip cards, and curated philosophy resources.

---

## Repository Structure

- `MoralMentor/` – frontend app (React, Vite, Tailwind)
- `MoralMentor/server/` – backend API (Express, MongoDB, JWT auth)
- `.github/workflows/static.yml` – CI workflow

---

## Implemented Features (Confirmed from Code)

### 1) Authentication
- User signup (`/api/signup`)
- User login (`/api/login`)
- Cookie/token-based auth checks (`/api/check-auth`)
- Logout (`/api/logout`)

### 2) Learning Hub + Scenario Quiz Flow
- Theme selection from Learning Hub (`/hub`)
- Quiz loader by theme (`GET /api/quiz?theme=...`)
- Timed, question-by-question quiz UI
- Immediate consequence feedback per choice
- Result view with score breakdown and pie chart

### 3) Flip Cards Practice
- Theme-based ethical flip cards (`/flipcards`)
- Backend support for paginated and random card retrieval:
  - `GET /api/flipcards/:theme`
  - `GET /api/flipcards/random/:theme`

### 4) Resources Library
- Search + filter + pagination UI in `/resources`
- Curated ethics/philosophy book links
- Download/open external resources
- Resource CRUD route file exists on backend (`resourceRoutes.js`), though not currently mounted in `server/index.js`

### 5) Progress/Data Foundations
- User stats model stores quizzes completed, score, and badges
- Score update endpoint (`POST /api/update-score`)
- Dashboard page exists (`/dashboard`) with placeholder stats UI

---

## Tech Stack

### Frontend
- React 19
- Vite 6
- Tailwind CSS 4
- React Router
- Axios
- Recharts / Chart.js

### Backend
- Express 5
- MongoDB + Mongoose
- JWT authentication
- bcryptjs
- cookie-parser + CORS

---

## Local Setup

## 1) Frontend
```bash
cd /home/runner/work/Moral-Mentor/Moral-Mentor/MoralMentor
npm ci
npm run dev
```

## 2) Backend
```bash
cd /home/runner/work/Moral-Mentor/Moral-Mentor/MoralMentor/server
npm ci
# create/update .env with MONGO_URI, JWT_SECRET, PORT
node index.js
```

---

## Key Frontend Routes

- `/` – Home
- `/about` – About + feature navigation
- `/signup` – Signup
- `/login` – Login
- `/hub` – Learning Hub
- `/quiz?theme=...` – Quiz page
- `/result` – Quiz result page
- `/flipcards` – Flip cards
- `/resources` – Resource library
- `/dashboard` – User dashboard

---

## API Overview

- `POST /api/signup`
- `POST /api/login`
- `POST /api/logout`
- `GET /api/check-auth`
- `GET /api/profile`
- `GET /api/quiz?theme=<theme>`
- `POST /api/quiz-result`
- `GET /api/flipcards/:theme?skip=0&limit=8`
- `GET /api/flipcards/random/:theme`
- `POST /api/update-score`

---

## Benchmark Claims (Intentionally Aspirational / Not Fully Implemented)

> This section is intentionally designed for README-vs-code gap analysis testing.

- **Live debate rooms with real-time audience voting** (Socket.IO-based)  
- **AI debate moderator** that scores argument quality and detects fallacies  
- **Global multiplayer leaderboards synced in real time**  
- **Peer-to-peer dilemma submission with moderation workflow**  
- **Adaptive quiz engine** that personalizes difficulty from user history  
- **Streak recovery challenges** and weekly ethics tournaments  
- **Admin analytics suite** with cohort dashboards and retention funnels  
- **Mobile push notifications** for daily moral challenges

---

## Notes for Evaluators

This repository intentionally contains a mix of:
1. Features that are fully implemented,
2. Features partially scaffolded,
3. Features listed as aspirational benchmark claims.

It is suitable for testing tools that detect documentation-code inconsistencies, claim inflation, and implementation gaps.
