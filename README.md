# Employee Visitor Management System

## Quick start (one command each, no MongoDB needed)

```bash
npm run setup     # installs backend + frontend and builds the UI (run once)
npm start         # then open http://localhost:5000
```

With `MONGO_URI` empty in `backend/.env`, visitors are saved to `backend/data/visitors.json`.
Set `MONGO_URI` (local MongoDB or Atlas) to use MongoDB instead. If MongoDB is unreachable, the app falls back to the file.

Deploy on Render/Railway: Build Command `npm run setup`, Start Command `npm start`, and add `MONGO_URI` (Atlas). A file store is wiped on free hosts, so use MongoDB there.

Development with hot reload: run `npm run dev:backend` and `npm run dev:frontend` in two terminals (UI on http://localhost:5173).

---

A beginner-friendly MERN Stack project for digitally registering and managing organization visitors.

## Features
- Add visitor
- View visitor records
- Edit visitor
- Delete visitor
- Search by visitor name or mobile number
- Automatic date/time
- Checked In / Checked Out status
- Today's visitor dashboard
- CSV export
- Responsive React UI

## Requirements
- Node.js 18+ (Node.js 20+ recommended)
- MongoDB Community Server or MongoDB Atlas
- VS Code

## Project Structure
employee-visitor-management/
  backend/
    models/Visitor.js
    routes/visitorRoutes.js
    server.js
    package.json
    .env.example
  frontend/
    src/
      App.jsx
      main.jsx
      index.css
    index.html
    package.json
    vite.config.js

## Run Backend

Open terminal 1:

```bash
cd backend
npm install
```

Copy `.env.example` to `.env`.

For local MongoDB:
MONGO_URI=mongodb://127.0.0.1:27017/visitor_management
PORT=5000

Then:

```bash
npm run dev
```

Backend runs at http://localhost:5000

## Run Frontend

Open terminal 2:

```bash
cd frontend
npm install
npm run dev
```

Open the Vite URL, normally:
http://localhost:5173

IMPORTANT:
The root package.json only provides `setup`, `start` and the dev shortcuts; use `npm run dev:backend` / `npm run dev:frontend` from the root. The backend and frontend each have their own package.json.

## REST API
GET    /api/visitors
GET    /api/visitors?search=rahul
GET    /api/visitors/stats/today
POST   /api/visitors
PUT    /api/visitors/:id
DELETE /api/visitors/:id
