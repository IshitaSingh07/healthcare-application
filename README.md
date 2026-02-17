# 🏥 Health Care Application

A full-stack Health Care web application with secure authentication, protected routes, and a responsive user interface.  
Built using the MERN stack (MongoDB-ready architecture, Express, React, Node.js).

---

## 🚀 Features

### 🔐 Authentication System
- User Registration (Name, Email, Password)
- Secure Login with token-based authentication
- Persistent login using localStorage
- Logout with session cleanup
- Protected routes (unauthorized users redirected to login)
- Demo account for quick testing


## 🛠️ Tech Stack

### Frontend
- React.js
- HTML
- CSS3
- Javascript

### Backend
- Node.js
- Express.js

### (Production Ready Architecture)
- JWT Authentication (planned)
- MongoDB integration (datbase)
- Password hashing with bcrypt (planned)

---

## 📂 Project Structure

```
health-application
├── client        # Frontend (React)
├── server        # Backend (Node + Express)
├── README.md
```

---


## 🧪 Demo Account

Use the following credentials to test the application:

```
Email: demo@healthcare.com
Password: demo123
```

---
 
## ⚙️ Installation & Setup

### 1️⃣ Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
cd YOUR_REPO_NAME
```

### 2️⃣ Start Backend

```bash
cd server
npm install
npm run dev
```

### 3️⃣ Start Frontend

```bash
cd client
npm install
npm start
```

App runs at:  
👉 `http://localhost:3000`

---

## 🔒 Security Notes

This version is built for development/demo purposes.  
For production:

- Implement password hashing with `bcrypt`
- Use `jsonwebtoken` (JWT) with expiration
- Store users in a database (MongoDB/PostgreSQL)
- Use HTTPS
- Add rate limiting and CSRF protection

---

## 🌟 Future Improvements

- Password reset via email
- Appointment management system
- Admin dashboard
- Full production security hardening
- Improve UI/UX
- Deploy using Docker


⭐ If you like this project, give it a star!
