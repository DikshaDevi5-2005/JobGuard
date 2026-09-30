# JobGuard

JobGuard helps job seekers check whether a job posting or recruiter message is a scam. Paste a posting and get a risk score, the exact phrases that raised red flags, and advice on what to do next.

## Features

- Login and sign up
- Scam analysis with a 0-100 risk score (Low, Medium, High)
- Red-flag phrases highlighted in the original text
- History of past checks
- Scam reporting, plus an admin page to review reports

## How It Works

The final score combines two parts:

- **Rule checks (60%)**: fees, bank or ID requests, unrealistic pay, urgency, chat-app-only contact, personal email addresses, missing company details
- **ML text model (40%)**: a trained classifier that scores the posting text

## Tech Stack

| Part | Tech |
|---|---|
| Frontend | React, Vite, React Router |
| Backend | Node.js, Express |
| ML model | Python (text classifier) |
| Database | MongoDB (change if different) |

## Project Structure

```
jobguard/
├── jobguard-frontend/   # React app
├── backend/             # Express API
└── ml/                  # Model training and prediction
```

## Getting Started

### 1. Frontend

```bash
cd jobguard-frontend
npm install
npm run dev
```

Runs at http://localhost:5173. Without a backend it runs in demo mode (data saved in your browser).

To use the real API, create `jobguard-frontend/.env`:

```
VITE_API_URL=http://localhost:5000
```

### 2. Backend

```bash
cd backend
npm install
npm start
```

Runs at http://localhost:5000. Create a `.env` file with your database URL, JWT secret and admin key.

### 3. ML model

```bash
cd ml
pip install -r requirements.txt
python train.py
```

## API Endpoints

| Method | Path | Purpose |
|---|---|---|
| POST | `/api/auth/signup` | Create an account |
| POST | `/api/auth/login` | Log in |
| GET | `/api/auth/me` | Get the current user |
| POST | `/api/analyze` | Analyze a posting |
| GET | `/api/history` | List past checks |
| GET | `/api/analysis/:id` | Get one result |
| POST | `/api/report` | Report a scam |
| GET | `/api/admin/reports` | List reports (admin) |
| PATCH | `/api/admin/reports/:id` | Update report status (admin) |

## Disclaimer

JobGuard gives a risk estimate, not a verdict. Always verify a company yourself before sharing personal details or money.
