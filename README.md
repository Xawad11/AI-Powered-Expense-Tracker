# 💸 AI-Powered Expense Tracker

A full-stack personal finance management application with smart transaction tracking, monthly budget monitoring, and AI-powered financial insights using the Google Gemini API.

---

## 🚀 Features

- **User Authentication** — Secure signup/login with JWT and bcrypt password hashing
- **Transaction Management** — Full CRUD for income and expense transactions with category tagging
- **Dashboard Analytics** — Monthly income vs expense trends, category breakdowns, savings rate, and KPI cards
- **Budget Tracking** — Set monthly spending limits per category with live progress bars
- **AI Insights** — Google Gemini-powered spending analysis, budget verdicts, financial summaries, and savings tips
- **12-Month Demo Seed** — Realistic mock data generator with ~790 transactions across 12 months

---

## 🛠️ Tech Stack

### Backend
- **Runtime:** Node.js
- **Framework:** Express.js
- **Database:** PostgreSQL (via `pg`)
- **Auth:** JSON Web Tokens + bcrypt.js
- **AI:** Google Gemini API (`@google/genai`)

### Frontend
- **Framework:** React 19 + Vite
- **Styling:** Tailwind CSS
- **Routing:** React Router
- **Charts:** Recharts
- **HTTP Client:** Axios

---

## 📂 Project Structure

```
AI-Powered-Expense-Tracker/
├── backend/
│   ├── controllers/       # Route handlers (auth, dashboard, transactions, budgets, insights)
│   ├── middleware/        # JWT auth guard
│   ├── routes/            # API route definitions
│   ├── scripts/           # migrate.js and seed.js
│   ├── sql/               # schema.sql
│   ├── utils/             # Default categories, Gemini wrapper
│   ├── db.js              # PostgreSQL pool
│   └── server.js          # Express app entry point
└── frontend/
    └── AIExpenseTracker/
        └── src/
            ├── components/    # UI components, charts, layout
            ├── context/       # Auth context
            ├── lib/           # Axios instance
            ├── pages/         # Dashboard, Transactions, Budgets, Categories, Insights, Auth
            └── utils/         # API paths, formatters, icon resolvers
```

---

## 📦 Getting Started

### Prerequisites
- Node.js v18+
- PostgreSQL database
- Google Gemini API key

### 1. Backend Setup

```bash
cd backend
npm install
```

Create a `.env` file in the `backend/` directory:

```env
PORT=8000
DATABASE_URL=your_postgresql_connection_string
JWT_SECRET=your_jwt_secret
GEMINI_API_KEY=your_gemini_api_key
```

Run migrations:

```bash
npm run migrate
```

(Optional) Seed demo data:

```bash
npm run seed
# Demo login: alex@timetoprogram.com / Test@1234
```

Start the server:

```bash
npm run dev
```

Backend runs on `http://localhost:8000`

### 2. Frontend Setup

```bash
cd frontend/AIExpenseTracker
npm install
```

Create a `.env` file:

```env
VITE_API_URL=http://localhost:8000/api
```

Start the dev server:

```bash
npm run dev
```

Frontend runs on `http://localhost:5173`

---

## 📊 Database Schema

| Table | Description |
|-------|-------------|
| `users` | User profiles with hashed passwords and currency preference |
| `categories` | User-specific income/expense categories with icons and colors |
| `transactions` | Financial records linked to users and categories |
| `budgets` | Monthly spending limits per category |
| `ai_insights` | Persisted Gemini AI analysis history as JSONB |

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
