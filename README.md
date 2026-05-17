# Portfolio CMS

A full-stack portfolio website powered by a custom-built Content Management System.
All content — projects, skills, education, certificates, services, and messages — is
managed dynamically through a JWT-protected admin dashboard. No hardcoded data,
no redeployment needed to update anything on the live site.

🔗 **Live:** [afshan-qasim-portfolio.vercel.app](https://afshan-qasim-portfolio.vercel.app)

[![React](https://img.shields.io/badge/React-18-61DAFB?style=flat-square&logo=react)](https://react.dev/)
[![Node.js](https://img.shields.io/badge/Node.js-20.x-339933?style=flat-square&logo=nodedotjs)](https://nodejs.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-47A248?style=flat-square&logo=mongodb)](https://www.mongodb.com/)
[![Express](https://img.shields.io/badge/Express.js-4.x-000000?style=flat-square&logo=express)](https://expressjs.com/)
[![JWT](https://img.shields.io/badge/Auth-JWT-000000?style=flat-square&logo=jsonwebtokens)](https://jwt.io/)
[![Vercel](https://img.shields.io/badge/Deployed-Vercel-000000?style=flat-square&logo=vercel)](https://vercel.com/)



## What makes this different from a static portfolio

This is not a static site. Every section of the portfolio is driven by a REST API
and stored in MongoDB. The admin dashboard lets you create, edit, and delete any
content from a browser — without touching code or redeploying.

- **Projects** — add, edit, delete portfolio projects with title, description, image, live URL, GitHub URL
- **Skills** — manage tech stack entries per category
- **Education** — update academic history dynamically
- **Certificates** — add new certifications as they are earned
- **Site Content** — edit hero text, about section, and profile details
- **Services** — update offered services
- **Messages** — read contact form submissions from visitors



## Architecture


<img width="346" height="281" alt="image" src="https://github.com/user-attachments/assets/5e4f1789-63a3-49fc-95e4-4ab1dbae7259" />




## Admin Dashboard

After logging in at `/admin/login`, the admin has full control over every
section of the live portfolio:

| Section | Operations |
|---|---|
| Projects | Create, Edit, Delete — title, description, image, live URL, GitHub URL |
| Skills | Add, Edit, Delete — tech stack entries per category |
| Education | Update academic history and details |
| Certificates | Add new certifications with credential links |
| Site Content | Edit hero text, about section, profile description |
| Services | Update services offered section |
| Messages | Read contact form submissions from visitors |

All changes reflect on the live portfolio immediately — no redeployment required.



## Data Models

```js
// Project
{
  title:       String,
  description: String,
  imageUrl:    String,
  projectUrl:  String,
  githubUrl:   String,
  createdAt:   Date
}

// Skill
{
  name:     String,
  category: String,   // Frontend, Backend, DevOps
  icon:     String
}

// Certificate
{
  title:         String,
  issuer:        String,
  credentialUrl: String,
  issuedAt:      Date
}

// Message (contact form)
{
  name:      String,
  email:     String,
  message:   String,
  createdAt: Date,
  read:      Boolean
}

// Site Content
{
  heroTitle:    String,
  heroSubtitle: String,
  aboutText:    String,
  cvUrl:        String
}
```



## Quick Start

### Prerequisites

- Node.js 20+
- MongoDB Atlas account

### 1. Clone

```bash
git clone https://github.com/Afshan738/portfolio-cms
cd portfolio-cms
```

### 2. Configure environment

```bash
# backend/.env
MONGO_URI=mongodb+srv://<user>:<pass>@cluster.mongodb.net/portfolio
JWT_SECRET=your-secret-key
PORT=5000

# frontend/.env
VITE_API_URL=http://localhost:5000
```

### 3. Run locally

```bash
# Backend
cd backend
npm install
npm run dev

# Frontend
cd frontend
npm install
npm run dev
```



## Environment Variables

| Variable | Location | Description |
|---|---|---|
| `MONGO_URI` | backend | MongoDB Atlas connection string |
| `JWT_SECRET` | backend | Token signing secret |
| `PORT` | backend | API server port (default 5000) |
| `VITE_API_URL` | frontend | Backend API base URL |



## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React 18, Vite, CSS3 |
| Backend | Node.js 20, Express.js |
| Database | MongoDB Atlas, Mongoose ODM |
| Authentication | JWT (jsonwebtoken) |
| HTTP client | Axios |
| Deployment | Vercel |



## Live Demo

🔗 [afshan-qasim-portfolio.vercel.app](https://afshan-qasim-portfolio.vercel.app)

Admin login available on request for demo purposes.



## Author

**Afshan Qasim** · [GitHub](https://github.com/Afshan738) · [LinkedIn](https://www.linkedin.com/in/afshan-qasim-998917300)
