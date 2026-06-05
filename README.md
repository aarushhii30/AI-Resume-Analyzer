# AI Resume Analyzer 🚀

An AI-powered resume analysis and job matching platform built with React, TypeScript, Express, Firebase, and Google Generative AI.

## Table of Contents
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Project Structure](#project-structure)
- [Models and Database](#models-and-database)
- [User Workflow](#user-workflow)
- [API Endpoints Overview](#api-endpoints-overview)
- [Getting Started](#getting-started)
- [Installation](#installation)
- [Running the Project](#running-the-project)
- [Building for Production](#building-for-production)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Features ✨
- **User Authentication:** Secure signup and login functionality using Firebase Authentication
- **Resume Upload & Parsing:** Users can upload resumes in PDF or DOCX format
- **AI Resume Analysis:** Provides feedback and scoring on uploaded resumes using Google Generative AI
- **AI Resume Builder:** Helps users generate professional resumes based on provided information
- **Job Matching:** Compares user resumes against job descriptions to assess suitability
- **Resume Tips:** Offers general advice and best practices for resume writing
- **User Dashboard:** A central place for authenticated users to manage their resumes, generate cover letters, and access features

## Technologies Used 🛠️

**Frontend:**
- **Framework/Library:** React
- **Build Tool:** Vite
- **Language:** TypeScript
- **UI Components:** shadcn/ui
- **Styling:** Tailwind CSS
- **Routing:** React Router DOM
- **State Management/Data Fetching:** TanStack Query (React Query)
- **API Client:** Axios
- **Authentication:** Firebase Client SDK

**Backend:**
- **Framework:** Express.js
- **Language:** TypeScript
- **Runtime:** Node.js
- **Authentication:** Firebase Admin SDK
- **AI:** Google Generative AI SDK (`@google/generative-ai`)
- **Database:** Firebase Firestore
- **File Handling:** Multer (uploads), Mammoth (docx parsing), pdf-parse (pdf parsing)

## Project Structure 🗂️
├── src/                          # Frontend source code
│   ├── components/               # Reusable UI components (shadcn/ui)
│   ├── pages/                    # Top-level page components
│   ├── lib/                      # Core utilities (api.ts, firebase.ts)
│   ├── context/                  # React context providers (AuthContext.tsx)
│   ├── App.tsx                   # Main application component with routes
│   └── main.tsx                  # Application entry point
├── backend/                      # Backend source code
│   └── src/
│       ├── controllers/          # Request handlers and business logic
│       ├── routes/               # API endpoint definitions
│       ├── middleware/           # Auth middleware (token verification)
│       ├── config/               # Multer, Firebase Admin setup
│       ├── models/               # Data models/schemas
│       └── server.ts             # Express app entry point
├── public/                       # Static assets
├── index.html                    # HTML entry point
├── package.json
├── tailwind.config.ts
└── vite.config.ts

## Models and Database 📈

- **Models:** The `backend/src/models/` directory defines the structure of data — User profiles, Resume details (metadata, parsed content, analysis results), and Job Match results
- **Database:** Firebase Firestore stores user account information, uploaded resume metadata, parsed resume content, analysis scores, generated resume data, and job matching results

## User Workflow 📊

1. **Authentication:** New users sign up / existing users log in
2. **Resume Management:**
   - **Upload & Analyze:** Upload PDF/DOCX → AI-driven analysis and ATS scoring
   - **Build:** Use Resume Builder to create resume from scratch
3. **Job Matching:** Provide a job description → select resume → get match insights
4. **Review & Refine:** Apply suggestions, refine resume, access tips
5. **Cover Letter:** Generate AI-powered cover letters

## API Endpoints Overview 📚

Key route groups under `/api`:

- `/auth`
  - `POST /signup` — User registration
  - `POST /login` — User login
- `/resumes` (Requires Authentication)
  - `GET /` — Get list of uploaded resumes
  - `POST /upload` — Upload resume file for parsing and storage
  - `POST /:resumeId/analyze` — Trigger AI analysis for a resume
- `/builder` (Requires Authentication)
  - `GET /generated` — Get list of AI-generated resumes
  - `POST /generate` — Generate new resume from user input
  - `GET /download/:generatedResumeId` — Download generated resume
- `/match` (Requires Authentication)
  - `POST /resume-job` — Compare resume against job description
- `/tips`
  - `GET /` — Fetch general resume writing tips

## Getting Started 🚀

### Prerequisites
- Node.js and npm
- Firebase Project (Authentication + Firestore enabled)
- Google Generative AI API Key

### Environment Variables

**Frontend (`.env` in root):**
VITE_FIREBASE_API_KEY="your_firebase_api_key" VITE_FIREBASE_AUTH_DOMAIN="your_firebase_auth_domain" VITE_FIREBASE_PROJECT_ID="your_firebase_project_id" VITE_FIREBASE_STORAGE_BUCKET="your_firebase_storage_bucket" VITE_FIREBASE_MESSAGING_SENDER_ID="your_firebase_messaging_sender_id" VITE_FIREBASE_APP_ID="your_firebase_app_id" VITE_BACKEND_API_URL="http://localhost:3000/api"


**Backend (`backend/.env`):**
PORT=3000 GOOGLE_API_KEY="your_google_generative_ai_api_key" CORS_ORIGIN="http://localhost:5173"
## Installation 🛠️

```bash
# Clone the repository
git clone https://github.com/aarushhii30/AI-Resume-Analyzer.git
cd AI-Resume-Analyzer

# Install frontend dependencies
npm install

# Install backend dependencies
cd backend
npm install
cd ..
```

## Running the Project 🚀

```bash
# Terminal 1 - Start Backend
cd backend
npm run dev

# Terminal 2 - Start Frontend
npm run dev
```

Open your browser at `http://localhost:5173`

## Building for Production 📦

**Frontend:**
```bash
npm run build
```

**Backend:**
```bash
cd backend
npm run build
```

## Contributing 🤝

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature-name`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature/your-feature-name`)
5. Open a Pull Request

## License 📄
This project is licensed under the MIT License.

## Contact 📧
**Aarushi Sharma**
- Email: aarushhisharma@gmail.com
- GitHub: [github.com/aarushhii30](https://github.com/aarushhii30)
- LinkedIn: [linkedin.com/in/aarushhiisharma](https://linkedin.com/in/aarushhiisharma)

---
Made with ❤️ by Aarushi Sharma