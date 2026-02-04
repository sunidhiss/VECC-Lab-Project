# UniPlay 🎮📊  
AI-Powered Inter-Department Gaming & Aptitude Platform

## 📌 Overview
UniPlay is a web-based platform designed for university students to compete, learn, and grow through daily aptitude challenges and multiplayer games. Students are automatically grouped by department using their unique university ID, fostering healthy inter-department competition.

---

## 🔑 Authentication Logic
Students log in using a University ID of the format:

NNMXXYYRRR

Where:
- **XX** → Year of admission  
- **YY** → Department code  
- **RRR** → Roll number  

Example:
NNM24AD067  
- Year: 2024  
- Department: AI & Data Science  
- Roll No: 067  

The system automatically extracts and assigns students to their department.

---

## 🚀 Core Features

### 🧠 Daily Aptitude Tests
- AI-generated questions using **Gemini AI API**
- New set of questions every day
- One attempt per student per day
- Automatic evaluation and scoring
- Scores contribute to department rankings

### 🎲 Multiplayer Games
- Inter-department games (Chess, Ludo)
- Real-time or turn-based gameplay
- Match results stored securely
- Individual and department scoring

### 🏆 Leaderboards
- Game-wise leaderboards
- Aptitude test leaderboard
- Overall department leaderboard
- Real-time rank updates

---

## 🛠️ Tech Stack

### Frontend
- React.js
- Tailwind CSS / CSS Modules
- Socket.IO (for real-time games)

### Backend
- Node.js
- Express.js
- JWT Authentication
- REST APIs

### Database
- MongoDB
  - Users
  - Departments
  - Games
  - Scores
  - Aptitude Attempts

### AI Integration
- Gemini AI API
- Daily question generation (cron-based)

### Other Tools
- Redis (session & rate limiting)
- Cron Jobs (daily refresh)
- Docker (optional for deployment)

---

## ⚙️ Workflow

1. Student logs in using University ID
2. Backend parses ID and assigns department
3. Student dashboard loads:
   - Available games
   - Daily aptitude test
   - Current rankings
4. Aptitude test:
   - Generated daily via Gemini AI
   - One attempt allowed
   - Score stored and ranked
5. Games:
   - Students play against other departments
   - Match results update scores
6. Leaderboards update dynamically

---

## 🧩 System Design

### High-Level Architecture

Client (React)
   ↓
API Gateway (Express)
   ↓
Auth Service → User Service → Game Service → Leaderboard Service
   ↓
MongoDB + Redis
   ↓
Gemini AI API (Daily Aptitude Generation)

---

## 📅 Daily Aptitude Refresh Logic
- Cron job runs every 24 hours
- Calls Gemini AI API to generate:
  - Questions
  - Options
  - Correct answers
- Stores new test set
- Resets attempt flags for all users

---

## 🔐 Security & Fair Usage
- JWT-based authentication
- Server-side validation for attempts
- Rate limiting on APIs
- Match verification logic

---

## 📈 Future Enhancements
- Admin panel
- Mobile app
- Tournament mode
- AI-based difficulty scaling
- Badges & rewards system

---

## 👨‍🎓 Target Users
- University students
- Admins / Faculty coordinators

---

## 📄 License
MIT License
