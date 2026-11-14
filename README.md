# DevOps Pipeline Analytics Platform 🚀

> **Tagline:** *"Monitor Every Build. Improve Every Deployment."*

A modern, production-grade DevOps Pipeline Analytics Platform built for real-time CI/CD workflow monitoring, deployment tracking, failure detection, and automated reporting connected with GitHub Actions via the GitHub REST API.

---

## 📁 Project Architecture & Folder Structure

```
Devops_pipeline/
├── backend/
│   ├── api/                 # External API integrations
│   ├── config/              # Environment & DB Configs
│   ├── controllers/         # Request handlers & logic
│   ├── database/            # MySQL Connection Pool & Query Executor
│   ├── middleware/         # Auth, Error & Validation Middlewares
│   ├── models/              # Data Models & Schemas
│   ├── routes/              # Express API Route Handlers
│   ├── services/            # GitHub REST API & Business Logic
│   ├── utils/               # Helper utilities & Formatters
│   ├── .env                 # Environment Variables Configuration
│   ├── .env.example         # Example Environment Blueprint
│   ├── package.json         # Backend Dependencies
│   └── server.js            # Express REST Application Entry point
│
├── frontend/
│   ├── src/
│   │   ├── assets/          # Images & Static Media
│   │   ├── components/      # Reusable UI Components
│   │   │   ├── Cards/
│   │   │   ├── Charts/
│   │   │   ├── Loader/
│   │   │   ├── Modal/
│   │   │   ├── Navbar/
│   │   │   ├── Sidebar/
│   │   │   └── Tables/
│   │   ├── context/         # React Context Providers (AuthContext)
│   │   ├── hooks/           # Custom React Hooks
│   │   ├── pages/           # Platform Pages
│   │   │   ├── Dashboard/
│   │   │   ├── Deployments/
│   │   │   ├── Login/
│   │   │   ├── Pipelines/
│   │   │   ├── Register/
│   │   │   ├── Reports/
│   │   │   └── Settings/
│   │   ├── services/        # Axios API Client Setup
│   │   ├── utils/           # Frontend Utilities & Formatters
│   │   ├── App.jsx          # Router & Layout Container
│   │   ├── index.css        # Tailwind CSS & Design System
│   │   └── main.jsx         # React 18 Entry Point
│   ├── index.html           # HTML5 Shell
│   ├── package.json         # Frontend Dependencies
│   └── vite.config.js       # Vite + Tailwind Config
│
├── database/
│   ├── schema.sql           # MySQL DDL (Users, Repositories, Pipelines, Deployments, Reports)
│   └── seed.sql             # Demo Data Seed Script
│
├── docs/                    # Project Documentation
└── README.md                # Platform Guide & Run Instructions
```

---

## 🛠️ Technology Stack

| Layer | Technology |
| :--- | :--- |
| **Frontend** | React 18 (Vite), Tailwind CSS v4, React Router DOM, Chart.js, Lucide Icons |
| **Backend** | Node.js, Express.js REST API |
| **Database** | MySQL (mysql2 pool with Promise API) |
| **Authentication** | JWT (JSON Web Tokens), bcrypt password hashing |
| **API Integration** | GitHub REST API v3 (Actions, Workflow Runs, Repositories) |

---

## 🗄️ Database Setup (MySQL)

1. Open your MySQL client (MySQL Workbench, phpMyAdmin, or MySQL CLI).
2. Execute `database/schema.sql` to create the database and tables:
   ```bash
   mysql -u root -p < database/schema.sql
   ```
3. Execute `database/seed.sql` to populate sample data:
   ```bash
   mysql -u root -p < database/seed.sql
   ```

---

## ⚙️ Environment Configuration

Edit `backend/.env` according to your local environment:

```env
PORT=5000
NODE_ENV=development

# MySQL Database Configuration
DB_HOST=localhost
DB_PORT=3306
DB_USER=root
DB_PASSWORD=root
DB_NAME=devops_analytics

# JWT Secret Key
JWT_SECRET=devops_pipeline_analytics_super_secret_jwt_key_2026
JWT_EXPIRES_IN=7d

# GitHub Personal Access Token (Optional)
GITHUB_TOKEN=
```

---

## 🚀 Running the Application

### 1. Start Backend Server

```bash
cd backend
npm start
```
*Backend API runs at:* `http://localhost:5000`  
*Health Check:* `http://localhost:5000/api/health`

### 2. Start Frontend Dev Server

```bash
cd frontend
npm run dev
```
*Frontend Application runs at:* `http://localhost:3000`

---

## 🧪 Module Verification (Module 1 Test Steps)

1. Verify backend starts without errors: `http://localhost:5000/api/health`. Response should return `status: "OK"` and `databaseConnected: true` (if MySQL service is running).
2. Verify frontend loads at `http://localhost:3000` displaying the dark-themed DevOps Analytics header, sidebar navigation, and platform initialization summary card.
