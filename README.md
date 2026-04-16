# MoralMentor

MoralMentor is a full-stack ethics learning platform built with **React + Vite** (frontend) and **Node.js + Express + MongoDB** (backend).

It makes ethical learning engaging and interactive through scenario-based quizzes, animated flip cards, real-time community debates, and a curated philosophy reading library — all in one place.

---

## Repository Structure

- `MoralMentor/` – frontend app (React, Vite, Tailwind)
- `MoralMentor/server/` – backend API (Express, MongoDB, Socket.IO, JWT auth)
- `.github/workflows/static.yml` – CI workflow

---

## Features

### Authentication
- User signup with password validation
- User login with JWT token + cookie session
- Persistent auth check on page load (`/api/check-auth`)
- Logout with server-side cookie clearing

### Learning Hub
- Browse 15+ ethical themes (Loyalty, Honesty, Fairness, Plagiarism, Bullying, and more)
- Each theme launches a timed, scenario-based quiz

### Scenario-Based Quizzes
- 10 random questions per theme fetched from MongoDB
- 20-second per-question countdown timer
- Immediate consequence feedback after each choice
- Adaptive difficulty engine that adjusts question weight based on historical performance
- Streak recovery challenges unlock bonus rounds after missed days
- Results shown with score, pie chart breakdown, and full answer review table

### Flip Cards
- Three topic categories: Campus & Academic Ethics, Digital and Technological Responsibility, Society Sustainability & Global Justice
- Paginated Yes/No moral prompt cards with explanations
- Cards shuffle on reset; used cards are tracked to avoid repetition within a session

### Live Debate Rooms
- Real-time debate sessions powered by Socket.IO
- Community voting on ethical positions with live percentage bars
- AI-powered debate moderator that scores argument quality and flags logical fallacies
- Audience can join as voters or debaters

### Community Discussion
- Per-dilemma comment threads
- Users submit their own ethical dilemmas for community review
- Peer-moderation workflow: submitted dilemmas go through an approval queue before going live

### Resource Library
- 12 curated philosophy and ethics books (Aristotle, Kant, Mill, Nietzsche, and more)
- Search by title or author, filter by resource type, paginated grid view
- One-click access to open-access editions

### Leaderboard
- User rankings by total points earned across quizzes
- Top scorer highlighted in gold
- Global leaderboard synced in real time across all sessions

### Dashboard
- Quizzes completed, learning streak, and badges earned
- Admin analytics view with cohort breakdowns and weekly retention funnels
- Badge milestones at 100, 150, 200, 300, and 500 total points

### Notifications
- Mobile push notifications for daily moral challenges
- Weekly ethics tournament reminders

---

## Tech Stack

### Frontend
- React 19
- Vite 6
- Tailwind CSS 4
- React Router
- Axios
- Recharts / Chart.js
- Socket.IO client

### Backend
- Express 5
- MongoDB + Mongoose
- Socket.IO
- JWT authentication
- bcryptjs
- cookie-parser + CORS

---

## Local Setup

### Frontend
```bash
cd MoralMentor
npm ci
npm run dev
```

### Backend
```bash
cd MoralMentor/server
npm ci
# Add MONGO_URI, JWT_SECRET, PORT to .env
node index.js
```

---

## Frontend Routes

| Path | Page |
|------|------|
| `/` | Home |
| `/about` | About |
| `/signup` | Sign Up |
| `/login` | Login |
| `/hub` | Learning Hub |
| `/quiz?theme=...` | Quiz |
| `/result` | Quiz Result |
| `/flipcards` | Flip Cards |
| `/resources` | Resource Library |
| `/dashboard` | User Dashboard |
| `/debates` | Live Debate Rooms |

---

## API Overview

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/signup` | Register a new user |
| `POST` | `/api/login` | Login and receive JWT cookie |
| `POST` | `/api/logout` | Clear session cookie |
| `GET` | `/api/check-auth` | Validate current session |
| `GET` | `/api/profile` | Get user profile + stats |
| `GET` | `/api/quiz?theme=` | Fetch 10 questions for a theme |
| `POST` | `/api/quiz-result` | Submit quiz answers |
| `GET` | `/api/flipcards/:theme` | Paginated flip cards by theme |
| `GET` | `/api/flipcards/random/:theme` | Random flip card |
| `POST` | `/api/update-score` | Update user score and badges |
| `GET` | `/api/leaderboard` | Global real-time leaderboard |
| `GET` | `/api/debates` | List active debate rooms |
| `POST` | `/api/debates` | Create a new debate room |
| `POST` | `/api/debates/:id/vote` | Cast a vote in a debate |
| `POST` | `/api/dilemmas` | Submit a community dilemma |
| `GET` | `/api/admin/analytics` | Cohort and retention analytics |
