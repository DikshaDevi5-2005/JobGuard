JobGuard – Fake Job Posting Detection System

**Check a job posting for scam signs before you reply.**

JobGuard is a project designed to help students and job seekers identify suspicious job postings. It checks job descriptions and recruiter messages for possible scam signs and provides a risk score, highlights suspicious phrases, and suggests what to do next.

## Project Structure

**frontend/** React + Vite application with login, signup, job checking, result and history pages.

**backend/** Express API for authentication, job analysis, history, rate limiting and security headers.

## Technologies Used

**Frontend:** React.js, Vite

**Backend:** Node.js, Express.js

**Detection:** JavaScript Rule Engine and Naive Bayes Text Model

**Security:** Scrypt password hashing and signed login tokens

**Storage:** In-memory storage (data resets when the server restarts)

## Features

**User Authentication:** Users can create an account and log in securely.

**Job Posting Analysis:** Checks job descriptions, recruiter emails and job links.

**Rule-Based Detection:** Looks for warning signs such as registration fees, bank or ID requests, unrealistic salaries, urgent hiring messages, personal email addresses and suspicious links.

**Text Model:** Uses a small Naive Bayes model trained on sample genuine and scam job postings.

**Risk Score:** Combines rule-based checks and text model predictions to generate a score between 0 and 100.

**Risk Level:** Displays the result as Low, Medium or High.

**Warning Highlights:** Highlights the exact words or phrases that trigger warnings.

**Safety Recommendations:** Provides suggestions based on the warning signs found.

**Analysis History:** Allows users to view their previous job checks.

**User-Specific History:** Each user can access their own analysis history.

**Demo Mode:** Allows users to explore the frontend without running the backend.

## API Endpoints

| Method | Endpoint | Authentication |
|---|---|---|
| POST | `/api/auth/signup` | Not Required |
| POST | `/api/auth/login` | Not Required |
| GET | `/api/auth/me` | Required |
| POST | `/api/analyze` | Required |
| GET | `/api/history` | Required |
| GET | `/api/analysis/:id` | Required |
| GET | `/api/health` | Not Required |

## Future Improvements

**MongoDB Integration:** Store user accounts and analysis history permanently.

**Machine Learning:** Improve the detection model for better results.

**Report a Scam:** Allow users to report suspicious job postings.

**Admin Panel:** Add admin functionality to review reported jobs.

**Model Retraining:** Use admin-approved reports to improve the detection model.

**Testing and Deployment:** Test the application and make it available online.

## How JobGuard Helps

JobGuard helps users become more aware of common recruitment scams. It highlights suspicious signs in job postings, explains why they may be risky, and provides suggestions to help users make safer decisions before responding to a job opportunity.
| PATCH | `/api/admin/reports/:id` | Update report status (admin) |

## Disclaimer

JobGuard gives a risk estimate, not a verdict. Always verify a company yourself before sharing personal details or money.
