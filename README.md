﻿Notes App

A full-stack web application with secure user authentication and a feature-rich note management system. Built using **React**, **TypeScript**, **Node.js**, **Express**, and **MongoDB**, this project allows users to register, log in (via email/password or Google OAuth), and perform full CRUD operations on personal notes.

---

## 🌟 Features

### 🔐 Authentication
- Register/Login with email & password
- Google OAuth integration
- JWT-based token authentication

### 🗒️ Notes Management
- Create, read, update, and delete notes
- Notes are private and tied to individual users
- RESTful API for note operations

---

## 🛠️ Tech Stack

| Layer     | Technology                              |
|-----------|------------------------------------------|
| Frontend  | React, TypeScript, Vite                  |
| Backend   | Node.js, Express, TypeScript             |
| Database  | MongoDB Atlas                            |
| Auth      | JWT, Google OAuth 2.0                    |
| Email     | Gmail SMTP (Nodemailer)                  |

---

## 📁 Project Structure

highway-delite-assessment/
├── backend/ # Node.js + Express server
│ ├── controllers/ # Business logic
│ ├── models/ # Mongoose schemas
│ ├── routes/ # Auth & note routes
│ ├── config/ # DB and auth configs
│ ├── middleware/ # JWT & OAuth middleware
│ ├── server.ts # Entry point
│ └── .env # Environment variables
│
└── client/ # React frontend
├── src/ # App logic
├── public/ # Static assets
└── .env # Frontend environment variables
---

## 🧬 Environment Variables

### 📦 Backend (`/backend/.env`)
```env
PORT=5000
MONGODB_URI=your_mongo_uri
EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_email_app_password
JWT_SECRET=your_jwt_secret
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
FRONTEND_URL=http://localhost:3000
GOOGLE_CALLBACK_URL=http://localhost:5000/auth/google/callback
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
/////////////////////////////////////////////////////////////////////////////////////
💻 Frontend (/client/.env)

PORT=3000
JWT_SECRET=your_jwt_secret
REACT_APP_GOOGLE_CLIENT_ID=your_google_client_id
REACT_APP_BACKEND_API_BASE_URL=http://localhost:5000
///////////////////////////////////////////////////
Setup Backend
cd backend
npm install
# Create .env file and fill in variables
npx ts-node src/server.ts
Server runs at http://localhost:5000
/////////////////////////////////////////////////////
Setup Frontend
cd ../client
npm install
# Create .env file and fill in variables
npm start
App runs at http://localhost:3000

🔁 Application Workflow
User visits frontend

Registers/Login using email/password or Google

JWT is stored in local storage after successful login

Frontend sends token in headers for secure note operations

User can perform CRUD on notes (protected routes)

Notes stored in MongoDB, only visible to the authenticated user

📬 API Overview
🔐 Auth Routes
Method	Endpoint	Description
POST	/api/auth/register	Register a new user
POST	/api/auth/login	Login and get token
GET	/auth/google	Google OAuth Login
GET	/auth/google/callback	Google callback

📝 Notes Routes
All note routes require JWT token in Authorization header.

Method	Endpoint	Description
GET	/api/notes	Get all notes
POST	/api/notes	Create a note
PUT	/api/notes/:id	Update a specific note
DELETE	/api/notes/:id	Delete a specific note









